This repository holds the shared GitHub configuration for the Hikma organisation. It carries no project content: no pipeline code, no specification, no dataset. Every other repository in the organisation inherits what is here, so one change here takes effect across all of them at once.

## What is here

| Path | What it does |
|------|--------------|
| [`profile/README.md`](profile/README.md) | GitHub renders this as the public organisation profile at [github.com/hikma-exam](https://github.com/hikma-exam). It says what Hikma is, lists the repositories, states the trademark and non-affiliation position, and tells a rights holder how to report a concern. Edit it to change what a visitor sees there. |
| [`SECURITY.md`](SECURITY.md) | The security policy for the whole organisation. Any repository without its own `SECURITY.md` shows this one under its Security tab and links to it from the "Report a vulnerability" prompt. |
| [`ISSUE_TEMPLATE/provenance-concern.yml`](ISSUE_TEMPLATE/provenance-concern.yml) | The form a rights holder fills in to report material they believe copies a copyrighted work. The organisation profile and the JLPT README both send people here, so the form has to stay reachable. It applies the `provenance` label, and a label only sticks if the repository already has it. |
| [`ISSUE_TEMPLATE/config.yml`](ISSUE_TEMPLATE/config.yml) | Controls the issue chooser. It keeps blank issues available for ordinary reports, and it adds two links that are not issues: the private email route and the security policy. |

GitHub treats this repository in two special ways. `profile/README.md` becomes the organisation profile page. Any issue or pull request template placed here is inherited by every repository in the organisation that does not define its own. Because of that inheritance, an unrelated file added here can change behaviour across the organisation without anyone noticing.

Two results of that inheritance are worth stating plainly. A repository that defines its own file at the same path **overrides** this one instead of merging with it, so a repo-local `SECURITY.md` or issue template quietly wins. And a broken `ISSUE_TEMPLATE/config.yml` breaks the issue chooser for **every** repository in the organisation, not just one, so open the "New issue" page of a public repo and check it after any change.
