# Hikma

Hikma builds practice questions for standardized exams and publishes them under an open license. Good practice material is hard to find for most exams, and almost all of it is proprietary.

Hikma is meant to help two groups. People preparing for an exam get practice questions that cost nothing and that carry evidence of the level they are aimed at. People building a study app get a dataset to start from, so they do not have to generate, calibrate, and review a question bank of their own before anyone can use the app. Datasets are intended for release under CC BY 4.0. A code license never implies a dataset license, so read the license that ships with a given release.

## Repositories

| Repository | What it is | Status | License |
| --- | --- | --- | --- |
| [`core`](https://github.com/hikma-exam/core) | The architecture: the schema, the pipeline stages, and the provenance and difficulty rules, plus how to set them up for one exam. | Public, early | MIT |
| `hikma-jlpt` | A reference implementation for the Japanese-Language Proficiency Test. | Private, in development | MIT for code and docs, CC BY 4.0 for generated data |

Start with [`core`](https://github.com/hikma-exam/core). The architecture suits any exam that publishes ability levels and uses a stable question format. Implementation repositories are named `hikma-<exam>`, one per exam.

## Two rules every implementation follows

- **Inputs are derived independently.** We use no official exam papers, no published sample questions, and no commercial question bank content as source material. Every generation call is logged with its model, prompt template version, prompt hash, and pipeline commit SHA. So the claim that no copyrighted material entered the pipeline can be checked against a record instead of believed on trust. That record is an audit trail, not a legal guarantee, and we do not present it as one.
- **Difficulty is measured.** A panel of model personas, one per ability level of the exam, answers each new question. We keep the question only if the pattern of who answers it correctly matches the level it claims. A question that misses is generated once more with that evidence attached, and dropped if it misses again.

## Trademarks and non-affiliation

Exam names in this organisation are trademarks of their owners. They appear only to describe which exams the practice material is for. That is descriptive use, not a claim of any relationship. Hikma makes study material for people preparing for an exam. It is not exam content, and no exam content is used to make it.

Hikma is not affiliated with, endorsed by, sponsored by, or approved by any examining body, test publisher, or their agents. The JLPT is administered by the Japan Foundation and Japan Educational Exchanges and Services. No logo, wordmark, brand styling, or visual identity belonging to any examining body is used anywhere in this organisation.

## If you believe something here infringes

Open a provenance concern on the repository that holds the material, or email <hikma@cypherpunkzero.com> to report it privately. Both routes are handled the same way, and the form says what happens next.

Maintained by [Chairul Akmal](https://chairulakmal.com).
