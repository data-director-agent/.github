# AI usage statement

This statement records how generative AI is used to develop the Data Director reference
implementation, so that readers of the software, its documentation and its citations can judge the
work. It covers every repository in the organisation. The rules for contributors are in
[Use of generative AI](CONTRIBUTING.md#use-of-generative-ai); this page says what the project
itself has done. It follows the University of Sheffield's
[principles for using GenAI in research and innovation](https://sheffield.ac.uk/research-services/policies/generative-ai):
appropriateness, attribution, accuracy, adherence to data protection and accountability.

## What AI is used for

Maintainers and contributors use AI coding agents, chiefly Claude Code (Anthropic), to help write
code, tests, documentation, specifications, issue and pull request text, and
configuration. A substantial part of the software and its prose has been drafted this way. People
decide what to build, make and record the design decisions, review every change and are
responsible for what is merged.

AI is not used to produce research findings, evaluation results or data. The project holds no
research data ([Projects](https://github.com/data-director-agent/data-director/blob/main/docs/specs/projects.md)
in the `data-director` specifications).

Two things are not AI output:

- The Blueprint in `docs/blueprint/` of the `data-director` repository is the text published by the
  RDA, reproduced verbatim. A script converts it and a second script checks it against the PDF.
- Text quoted from other sources is marked as quotation and cited.

## Appropriateness

AI is used where it saves effort on well-specified work that a person can check, and not as a
substitute for design judgement, for reading the Blueprint or for reviewing. Use is optional for
contributors. Models and sessions are chosen for the task, because running them has an energy cost.

## Attribution

- Every merged commit that an AI agent helped to write carries a `Co-Authored-By` trailer naming
  the model, from the end of the pull request description, which is the squash-merged commit's
  message. The person who takes responsibility for it certifies it under the [DCO](DCO.md), never
  the agent: implicitly, by opening the pull request from their own account, or explicitly, with
  a `Signed-off-by` line at the end of the description. An agent may author the commits on a pull
  request branch. CI enforces the sign-off: it rejects any sign-off by a coding agent, and a pull
  request that no human opened or signed off.
- Pull request descriptions written by an agent say so.
- The record of tools and models is the commit history. To list the models used in a repository
  and the period:

  ```sh
  git log --format=%B | grep -i '^co-authored-by: claude' | sort | uniq -c
  git log --format=%ad --date=short --reverse | head -1
  ```

- The agent's own version, and the exact date of each use, are not recorded beyond the commit
  date. A contributor who needs them for a publication should say so in the pull request.
- The `CITATION.cff` file credits people. Bots and AI assistants are not authors, and are
  disclosed here instead.

## Accuracy

Agent output is a draft. A change merges only through a pull request that a maintainer reviews,
and it must pass the repository's automated checks, which for `data-director` include unit and
browser tests, linting, type checks, a link check and a citation check. Citations, identifiers and
claims about the Blueprint, standards and sources are checked by a person against the original
source, because generated references are unreliable. Requirements are traced to the Blueprint by
ID, so a statement about what the Blueprint requires can be looked up.

## Data protection

No personal, confidential or unpublished research data is given to an AI tool during development.
Contributors must follow their institution's rules on which tools they may use. This statement is
about development only. Where the running software calls a hosted model, which two agents can do
when an operator turns them on, the repository's operations guide
(`docs/guide/operations/ai-models.md`) says what the provider receives and who supplies the key.

## Prompts

Prompt texts are not retained in full. The specifications in the `data-director` repository
state the current design and its reasons; the commit history, pull requests and issues, RFCs
among them, record how it got there. Together these are the project's record of intent. Whether
to keep prompts or session transcripts as well, and where, is open:
[data-director-agent/data-director#380](https://github.com/data-director-agent/data-director/issues/380).

## Accountability

The maintainers are accountable for the project's outputs, whoever or whatever drafted them. A
contributor is accountable for what they submit. Maintainers may ask for changes to, or decline, a
contribution that shows no sign of human review. The project follows the policies of its funders
and publishers, and keeps this statement up to date as the tools and its practice change.
