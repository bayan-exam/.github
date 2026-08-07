# Security policy

This is the security policy for every repository in the [hikma-exam](https://github.com/hikma-exam) organisation. The single most important point: report anything sensitive **privately**, never as a public issue. The most likely incident in this project is an exposed API key, and a public issue would show it to everyone before it can be revoked. Below: what is in scope today, how to report, what to expect in return, and which concerns belong in another channel.

## Current scope

Hikma is early. As of August 2026 the public repositories hold specification documents and no code that runs, so there is very little to attack. That changes when the JLPT pipeline lands, and this policy is written for both stages.

The realistic risks worth reporting:

- **An exposed credential.** The pipeline runs against an Anthropic API key. A key, token, or other secret committed to a Hikma repository, left in a run manifest, or visible in build output is the most serious thing you can find here. Report it at once, and do not test it.
- **A vulnerability in pipeline or review-interface code**, once that code exists. The pipeline is an offline batch job, not a live service that answers requests, so the risk is anything that lets an untrusted caller make model calls at all, and with them spend without limit against the project's API key.
- **A dependency vulnerability with a demonstrated path** into a Hikma repository. A scanner advisory with no reachable path does not help. A working path does.

## How to report

**Preferred:** use GitHub private vulnerability reporting on the affected repository, under the **Security** tab, then **Report a vulnerability**. This opens a private thread that only the maintainer can see, and it keeps the whole exchange attached to the repository.

**Alternative:** email <hikma@cypherpunkzero.com>. Use email if the repository is private, if private reporting is not available to you, or if you simply prefer it.

Please say what you found, where it is, and how to reproduce it. If you have a proof of concept, describe it instead of running it against anything live.

## What to expect

One person maintains Hikma, outside of full-time work, so replies are not fast. You will get an acknowledgement. A report that finds a real problem will get a fix, and public credit if you want it. There is no bug bounty and no payment, and you should assume that before you spend much time here.

Please give the maintainer a fair chance to fix a problem before you disclose it publicly. No fixed embargo applies. This is a request made in good faith, not a legal condition.

## Not a security issue

Three things get reported here that belong elsewhere:

- **Copyright and provenance concerns**, meaning material you believe copies a copyrighted exam or word list, go through the [Provenance concern](https://github.com/hikma-exam/hikma-jlpt/issues/new?template=provenance-concern.yml) issue template, or privately to the email address above. The organisation profile explains how those reports are handled.
- **Wrong or badly levelled questions** are a data quality problem, not a security one. Open a normal issue on the repository that published the dataset.
- **Scanner output with no reachable exploit path** will be closed with no action. Please establish the path first.
