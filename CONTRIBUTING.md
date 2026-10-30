# Contribution guide

Thank you for your interest in contributing to Data Director, a reference implementation of the
Research Data Alliance's Data Director Agentic AI Blueprint. This project is community-driven and
welcomes issues, discussion, and pull requests.

This guide applies to every repository in the `data-director-agent` organisation. A repository may
add its own `CONTRIBUTING.md` covering its structure, tooling and tests; where it does, read both.

## Before you start

- **Bugs and small changes**: open an issue or go straight to a pull request.
- **Changes affecting spec conformance** (interfaces, data models, or behaviour defined by the
  Blueprint): open an `RFC` issue first. See [GOVERNANCE.md](GOVERNANCE.md#rfc-process-for-spec-conformance-changes)
  for the process.
- **Planning**: how issues are triaged, made ready and scheduled into two-week sprints is
  described in [PLANNING.md](PLANNING.md).
- **Using AI tools**: read [Use of generative AI](#use-of-generative-ai) below.

## Developer Certificate of Origin (DCO)

Every commit must be signed off to certify that you wrote it or otherwise have the right to submit
it under the project's licence, per the [Developer Certificate of Origin](DCO.md).

Sign off each commit by adding the `-s` flag:

```sh
git commit -s -m "Your commit message"
```

This appends a `Signed-off-by` trailer with your name and email to the commit message, e.g.:

```
Signed-off-by: Jane Doe <jane@example.com>
```

Use your real name and a working email address — anonymous or pseudonymous sign-offs cannot be
accepted. Pull requests containing unsigned commits will be asked to amend before merge.

Your affiliation (declared via your sign-off name/email or stated in the PR description) also
helps the maintainers track the [Technical Steering Committee trigger](GOVERNANCE.md#technical-steering-committee-tsc).

## Pull request workflow

1. Fork the repository and create a branch for your change.
2. Make your change, with tests where applicable.
3. Ensure all commits are signed off (see above).
4. Open a pull request against `main` describing the change and its motivation. Link to the
   relevant issue or RFC if there is one.
5. A maintainer reviews and approves. Per [GOVERNANCE.md](GOVERNANCE.md#decision-making-lazy-consensus),
   the pull request merges under lazy consensus once approved and no objection is raised within
   the review window.

## Use of generative AI

We encourage the use of AI agents and assistants, such as Claude Code or OpenAI Codex, to work
faster and learn. Use is optional, and it must be responsible. These principles draw on the
University of Sheffield's principles for the use of generative AI for productivity.

- **Accountability**: AI supports your judgement and does not replace it. You are responsible for
  everything you submit, whoever or whatever drafted it, and you must be able to explain it.
  Sign-off under the [DCO](DCO.md) is yours alone.
- **Verification**: never accept output uncritically. Read, test and fact-check it, in particular
  code, citations, data and claims about the Blueprint. Apply your own knowledge of the context.
- **Bias and misinformation**: watch for biased or false output, and do not pass it on.
- **Data protection**: do not give personal, sensitive or confidential data, credentials or
  unpublished material to AI tools that are not approved for it. Comply with GDPR and your
  institution's policies, and use only tools your institution permits.
- **Intellectual property**: respect copyright and licences. Generated content may reproduce
  existing work, so check that you have the right to submit it under the project's licence.
- **Transparency**: say in the pull request when AI produced a substantial part of a change, and
  keep agent-authored commits identifiable (for example with a `Co-Authored-By` trailer). The
  project's own use of AI is set out in the [AI usage statement](AI_USAGE.md).
- **Sustainability**: use AI where it adds clear value.

Maintainers may ask for changes to, or decline, contributions that show no sign of human review.

## Conduct

Everyone taking part is expected to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## Getting help

Open an issue with your question, or start a discussion thread if the repository has discussions
enabled.
