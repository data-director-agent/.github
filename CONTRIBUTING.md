# Contribution guide

Thank you for your interest in contributing to Data Director, a reference implementation of the
Research Data Alliance's Data Director Agentic AI Blueprint. This project is community-driven and
welcomes issues, discussion, and pull requests.

This guide applies to every repository in the `data-director-agent` organisation. A repository may
add its own `CONTRIBUTING.md` covering its structure, tooling and tests; where it does, read both.

## Your first contribution

New to the project? You do not need to read the governance documents first. For the code
repository, [`data-director`](https://github.com/data-director-agent/data-director):

1. Fork it, clone your fork and create a branch.
2. From the root of the clone, run `uv run scripts/dev.py setup`, then `uv run scripts/dev.py doctor`
   to check the result.
3. Make your change and run the tests (`uv run pytest`).
4. Commit your change.
5. Open a pull request against `main`, describing what you changed and how you tested it, and end
   the description with your sign-off (see [below](#developer-certificate-of-origin-dco)).

[Your first contribution](https://data-director-agent.github.io/data-director/developer-guide/first-contribution/)
on the documentation site has each step in full, and the repository's own
[CONTRIBUTING.md](https://github.com/data-director-agent/data-director/blob/main/CONTRIBUTING.md)
covers its structure, tooling and checks.

| I want to… | Do this |
|---|---|
| Fix a typo or improve a document | Edit the file on GitHub and open a pull request. |
| Report a bug | Open an issue with the steps that reproduce it. |
| Review the Blueprint mapping, or the advice an agent gave | Open an issue with the matching form in the code repository: no code needed. |
| Fix a bug or add a small feature | Follow the steps above. |
| Add an agent | Read [Writing an agent](https://data-director-agent.github.io/data-director/developer-guide/writing-an-agent/), then follow the steps above. |
| Change an interface, data model or behaviour the Blueprint defines | Open an `RFC` issue first ([RFC process](GOVERNANCE.md#rfc-process-for-spec-conformance-changes)). |

## Before you start

- **Bugs and small changes**: open an issue or go straight to a pull request.
- **Changes affecting spec conformance** (interfaces, data models, or behaviour defined by the
  Blueprint): open an `RFC` issue first. See [GOVERNANCE.md](GOVERNANCE.md#rfc-process-for-spec-conformance-changes)
  for the process.
- **Planning**: how issues are triaged, made ready and scheduled into two-week sprints is
  described in [PLANNING.md](PLANNING.md).
- **Using AI tools**: read [Use of generative AI](#use-of-generative-ai) below.

## Developer Certificate of Origin (DCO)

Every pull request must be signed off to certify that you wrote it or otherwise have the right to
submit it under the project's licence, per the [Developer Certificate of Origin](DCO.md).

Pull requests are squash-merged, and the merged commit's message is the pull request's title and
description. So sign off at the end of the description, as its last line, where it becomes a
trailer of the merged commit:

```
Signed-off-by: Jane Doe <jane@example.com>
```

Use your real name and a working email address — anonymous or pseudonymous sign-offs cannot be
accepted. You can add or edit the line in the browser at any time before merge, and the check runs
again. Signing off your commits as well (`git commit -s`) is welcome but not required. Edits made
in GitHub's web editor are signed off automatically.

Only a human can sign off. An AI agent may co-author the work (a `Co-authored-by` line at the end
of the description, above the sign-off) but must never add a `Signed-off-by` line, to a commit or
to a description, whatever name its git identity carries. An agent may author commits. CI rejects
any sign-off by a coding agent, and a pull request whose description has no human sign-off.
Dependabot's and the release tool's pull requests are exempt.

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
