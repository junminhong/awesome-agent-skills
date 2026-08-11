---
name: routewarden-security-audit
description: Diff-aware security auditing for Express, NestJS, and Next.js routes. Use when creating, modifying, or reviewing web application routes to detect missing authentication (CWE-306) and sensitive information exposure (CWE-200).
---

# RouteWarden Security Audit

**Platforms:** Claude Code | Google Antigravity  
**Tags:** security, cwe-306, cwe-200, express, nestjs, nextjs  
**Use cases:** Use when creating, modifying, or reviewing API routes in Express, NestJS, or Next.js to detect missing authentication (CWE-306) or sensitive information exposure (CWE-200).

---

## Objective

Provide diff-aware security analysis for web application routes, identifying unprotected mutable endpoints (CWE-306) and sensitive data leakage in response payloads (CWE-200) without introducing false positives or altering existing code.

---

## Inputs

- **`git diff` output**: Modified or uncommitted lines in working tree (`git diff HEAD`, `git diff --cached`, or `git diff <branch>...HEAD`).
- **Target Files**: TypeScript/JavaScript source files (`.ts`, `.tsx`, `.js`, `.jsx`, `.mjs`, `.cjs`) containing route handlers or controllers.

---

## Outputs

- **Structured Security Findings**: A breakdown listing file, line number, vulnerability type (CWE-306 or CWE-200), severity, evidence code snippet, concise explanation, and concrete code remediation.

---

## Workflow

1. **Collect Diff**: Execute `git diff HEAD` (or staged/branch diff) to extract added lines (`+`).
2. **Filter Files**: Target TS/JS source files defining routes in Express, NestJS, or Next.js.
3. **Analyze HTTP Methods**:
   - For `POST`, `PUT`, `DELETE`, `PATCH`: Evaluate **CWE-306** (Missing Authentication).
   - For `GET`, `HEAD`, `OPTIONS`: Exempt from CWE-306 checks.
4. **Evaluate Auth Protection & Exemptions (CWE-306)**:
   - **Public Keywords Exemption**: Exempt if path contains `login`, `logout`, `signin`, `signout`, `register`, `signup`, `forgot-password`, `password-reset`, `reset-password`, or `refresh-token`.
   - **Recognized Guards**: Check for inline middleware, preceding `router.use(auth)` / `app.use(auth)`, NestJS `@UseGuards()`, or Next.js `getServerSession()` / `auth()`.
5. **Inspect Response Payloads (CWE-200)**:
   - Check all HTTP methods (`GET`, `POST`, etc.) for payloads directly returning sensitive keys (`password`, `token`, `secret`, `mock`, `bypass`, `private_key`).
6. **Generate Findings & Remediation**: Format output with precise line numbers and fix suggestions.

---

## Framework Guard Recognition & Rules

### Express.js
- **Inline**: `router.post("/path", authenticate, handler)`
- **Router-level**: `router.use(authenticate)` declared prior to route definitions in the file.
- **App-level**: `app.use("/api", authenticate)` declared before mounting routers.

### NestJS
- **Class Decorator**: `@UseGuards(JwtAuthGuard)` decorating `@Controller()` protects all class methods.
- **Method Decorator**: `@UseGuards(JwtAuthGuard)` decorating `@Post()`, `@Put()`, `@Delete()`, `@Patch()`.

### Next.js (App Router & Pages Router)
- **Body Calls**: `const session = await getServerSession()`, `const { userId } = await auth()`, `requireAuth()`.
- **Higher-Order Wrappers**: `export const POST = withAuth(...)`.

### Recognized Auth Catalog
- **Clerk**: `clerkMiddleware`, `requireAuth`, `ClerkExpressRequireAuth`, `ClerkExpressWithAuth`
- **Supabase**: `requireSupabaseAuth`, `supabaseAuthMiddleware`, `withSupabaseAuth`
- **Auth0**: `checkJwt`, `auth`, `requiresAuth`
- **NextAuth**: `withAuth`, `getServerSession`, `authMiddleware`
- **RealWorld Spec**: `auth.required`
- **Generic / Custom**: `authenticate`, `isAuthenticated`, `AuthGuard`, `JwtAuthGuard`, `requireLogin`, `protect`

---

## Constraints & Guardrails

- **Do Not Invent Guards**: Only match identifiers explicitly declared in the codebase or catalog.
- **Respect Read-Only Methods**: `GET` and `HEAD` requests MUST NOT be flagged for CWE-306.
- **Preserve Scope**: Mark routes as protected if preceding `router.use(auth)` or class-level `@UseGuards()` exists.
- **No False Alarm Spam**: Signal findings only when explicit evidence of missing auth or payload leak exists.

---

## Examples

### Example 1: Basic Usage (Express Unprotected POST - CWE-306)

**Input Command:**
```bash
git diff HEAD
```

**Input Diff:**
```diff
diff --git a/routes/users.js b/routes/users.js
new file mode 100644
index 0000000..1234567
--- /dev/null
+++ b/routes/users.js
@@ -0,0 +1,10 @@
+const express = require("express");
+const router = express.Router();
+
+// Unprotected mutable POST route
+router.post("/api/users", (req, res) => {
+  const { name, email } = req.body;
+  res.json({ id: 101, name, email });
+});
+
+module.exports = router;
```

**Expected Output:**
```markdown
### 🚨 RouteWarden Security Finding

- **File**: `routes/users.js` (Line 5)
- **Vulnerability**: `CWE-306: Missing Authentication for Critical Function`
- **Severity**: HIGH
- **Code Snippet**:
  ```js
  router.post("/api/users", (req, res) => {
    const { name, email } = req.body;
    res.json({ id: 101, name, email });
  });
  ```
- **Reason**: Mutable HTTP `POST` route lacks recognized authentication middleware and does not match a public entry-point keyword.
- **Remediation**:
  ```js
  const { authenticate } = require("../middleware/auth");

  router.post("/api/users", authenticate, (req, res) => {
    const { name, email } = req.body;
    res.json({ id: 101, name, email });
  });
  ```
```

---

## Evaluation Checklist

- [x] **Correctness**: Accurately identifies CWE-306 and CWE-200 vulnerabilities without false positives.
- [x] **Completeness**: Supports Express, NestJS, and Next.js guard patterns and router-level middleware.
- [x] **Safety**: Exclusively performs read-only analysis of git diffs without mutating repository code.
- [x] **Reproducibility**: Delivers consistent findings across identical diffs.
- [x] **Performance**: Runs rapidly using local git diff inspection.
- [x] **Documentation**: Self-contained with complete usage workflow and remediation steps.

---

## References

- [RouteWarden Repository](https://github.com/elicosilva/RouteWarden)
- [CWE-306: Missing Authentication for Critical Function](https://cwe.mitre.org/data/definitions/306.html)
- [CWE-200: Exposure of Sensitive Information to an Unauthorized Actor](https://cwe.mitre.org/data/definitions/200.html)

---

## Version History

- **v1.0.0** (2026-08-11): Initial release of RouteWarden Security Audit Skill for Claude Code and Antigravity.
