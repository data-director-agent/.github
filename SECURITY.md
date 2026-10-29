# Security policy

This policy applies to every repository in the `data-director-agent` organisation unless a
repository adds its own `SECURITY.md`.

## Reporting a vulnerability

Please report suspected vulnerabilities privately. Do not open a public issue, pull request or
discussion for them.

Use GitHub's private vulnerability reporting: open the **Security** tab of the affected
repository and choose **Report a vulnerability**. If the repository does not offer that option,
open an issue that asks for a private contact without describing the problem, and a maintainer
will arrange one.

Include, as far as you can:

- the repository and version or commit affected;
- what the problem is and what an attacker could do with it;
- steps or a minimal example to reproduce it;
- any suggested fix.

## What to expect

- We aim to acknowledge a report within 5 working days.
- We will tell you whether we consider it a vulnerability, and keep you informed as we work on it.
- We will agree a disclosure date with you. Once a fix is released we publish a security advisory
  and credit you, unless you prefer not to be named.

Data Director is maintained by volunteers, so these are aims rather than guarantees.

## Supported versions

Data Director is at an early stage. Security fixes are made on the latest release of each
repository and on `main`; older releases are not patched.

## Scope

In scope: code, configuration and workflows in this organisation's repositories, including the
way an agent or the harness handles credentials, user-supplied files and model output.

Out of scope: vulnerabilities in third-party dependencies (report them to the upstream project,
though we welcome a heads-up), and weaknesses in a model provider's service.

Never include real credentials, personal data or unpublished research data in a report. If you
find that a secret has been committed to a repository, report it as above so that we can revoke it.
