# Data Model

```mermaid
erDiagram
    USER ||--o{ MEMBERSHIP : has
    ORGANISATION ||--o{ MEMBERSHIP : contains
    USER ||--o{ ATTEMPT : starts
    ASSESSMENT ||--o{ ATTEMPT : receives
    ATTEMPT ||--o{ ANSWER : contains
    QUESTION_VERSION ||--o{ ANSWER : references
    ATTEMPT ||--o| RESULT : produces
    RESULT ||--o{ REVIEW : may_have

    USER { string id string role }
    ORGANISATION { string id string name }
    MEMBERSHIP { string role string scope }
    ASSESSMENT { string id string blueprint_version }
    ATTEMPT { string id string state datetime started_at datetime submitted_at }
    ANSWER { string id string response_hash }
    QUESTION_VERSION { string id string rubric_version }
    RESULT { string id string scoring_version }
    REVIEW { string id string reviewer_type string decision }
```

Important constraints:

- Attempt ownership and organisation scope are checked together.
- Answers are immutable after submission.
- Results point to the scoring/rubric versions used.
- Reviews preserve reviewer/model provenance and cannot overwrite raw evidence.
- Unique keys make submission and report generation idempotent.
