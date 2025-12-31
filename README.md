# rust-contract-foundry
# Institutional Contract Foundry (Rust)

An open-source Rust project generator that scaffolds **security-first, audit-friendly smart contract repositories**.

This project is intentionally conservative and structured for environments where:
- permissions must be explicit
- behavior must be deterministic
- every state change must be auditable
- tests and invariants are mandatory
- operational controls (pause/limits) are expected

> ⚠️ **Security Notice:** This repository is NOT audited.  
> Do not use generated contracts in production without independent security review.

---

## What this project is (simple explanation)

Think of this project like a **cookie-cutter** for smart contracts:

- You choose what you want to build (example: `vault`).
- The tool generates a project folder with:
  - contract code
  - tests
  - documentation
  - safety controls (permissions, pause switch, limits)
  - CI checks (formatting + linting + tests)

Instead of starting from scratch every time, the generator creates a consistent “professional starting point”.

---

## Why “institutional-grade”?

In regulated financial systems, the most important things are:
- **Correctness:** the code always does what it says
- **Auditability:** every important action can be traced
- **Controls:** permissions, emergency stops, limits
- **Repeatability:** the same rules every time, not random styles

This project encodes those expectations into templates and rules.

---

## Level 1 scope (what we are building first)

**Level 1 = MVP**

We will build:
1. A Rust CLI tool that can generate one contract template (`vault`)
2. A “rules checker” that refuses unsafe patterns in generated code
3. A generated project that includes:
   - RBAC (Role Based Access Control)
   - Pause switch
   - Checked arithmetic (no silent overflow)
   - Events for audit logs
   - Tests (happy + failure paths)

---

## What gets generated (output structure)

When you run the tool, it produces something like:

