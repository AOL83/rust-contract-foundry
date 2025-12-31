# Institutional Contract Foundry (Rust)

An open-source Rust project generator that scaffolds security-first, audit-friendly smart contract repositories.

This project is intentionally conservative and structured for environments where:
- permissions must be explicit
- behavior must be deterministic
- every state change must be auditable
- tests and invariants are mandatory
- operational controls (pause, limits) are expected

SECURITY NOTICE  
This repository is NOT audited.  
Do not use generated contracts in production without independent security review.

What this project is (plain English)

This project is a tool that helps you build smart contracts in a structured, professional way.

Instead of starting from an empty folder, the tool creates a complete project for you, including:
- contract code structure
- safety controls
- tests
- documentation
- continuous integration checks

The goal is to make smart contracts easier to build correctly, especially for environments where mistakes are expensive.

Why institutional-grade?

In regulated or high-risk systems, smart contracts are judged on:
- correctness – the code must always behave as expected
- auditability – every important action must be traceable
- controls – permissions, emergency stops, and limits
- repeatability – consistent patterns instead of one-off designs

This project encodes those expectations directly into its templates and rules.

Level 1 scope (current milestone)

Level 1 focuses on delivering a minimal but serious foundation.

At this level, the project will:
- provide a Rust command-line tool (CLI)
- generate one contract template (Vault)
- enforce basic safety rules
- include tests and continuous integration
- produce audit-friendly repository structures

What gets generated:

```
my-vault/
Cargo.toml
contracts/
vault/
src/
lib.rs
access.rs
controls.rs
state.rs
events.rs
error.rs
tests/
unit.rs
invariants.rs
docs/
ARCHITECTURE.md
THREAT_MODEL.md
OPERATIONS.md
.github/workflows/ci.yml
README.md
LICENSE
```

This structure is audit-friendly:
- policies are separated
- errors are explicit
- invariants are testable
- documentation exists from day one

Definitions (explained in plain English)

RBAC (Role-Based Access Control)

A way to clearly define who is allowed to do what:
- Admins can do everything
- Operators can do some privileged actions
- Users can only do basic actions

This ensures no unauthorized or random user can perform sensitive operations.

Pause switch (circuit breaker)

A global “stop everything” control.

If a problem is detected, an administrator can pause the contract so that:
- state-changing actions are blocked
- further damage is prevented
- investigation and recovery can happen safely

Invariants

Rules that must always remain true, no matter what actions are taken.

Examples:
- balances can never be negative
- totals must always match expected accounting values
- when the contract is paused, withdrawals are blocked

Invariants are enforced through tests and defensive checks.

Roadmap

Level 1 (first milestone)
- CLI generates one contract template
- rules and validations are enforced
- CI pipeline is active and running

Level 2
- additional templates (escrow, registry)
- expanded rules and documentation
- optional policy-as-code configuration

Level 3
- multi-chain targets (Soroban first, then others)
- stronger invariant and property-based testing
- upgrade and migration templates

Contributing

This project is beginner-friendly.

Contributions are welcome, including:
- documentation improvements
- new validation rules
- improved templates
- additional tests

Please open an issue or pull request with a clear explanation of your change.

License

MIT License.
