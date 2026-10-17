# Context and Time Metadata

## Purpose

Organize information by meaning, relationships, provenance, and time so that the reasoning engine can retrieve it in a relevant order and avoid treating old or uncertain information as universally true.

## Suggested record schema

- `id`: stable record identifier;
- `kind`: observation, fact claim, inference, hypothesis, preference, event, formula result, or task state;
- `content` / `value`: structured payload, not necessarily natural language;
- `entities` and `relations`: linked concepts and records;
- `category` and `topics`: retrieval indexes;
- `source`: origin or provenance;
- `observed_at`: when the event/observation occurred, if known;
- `recorded_at`: when the system stored it;
- `valid_from` / `valid_until`: interval during which the record is intended to apply, if relevant;
- `confidence`: calibrated estimate where meaningful;
- `status`: verified, unverified, disputed, stale, superseded, or expired;
- `supersedes` / `contradicts` / `supports`: explicit relationships;
- `privacy` and `permissions`: access and use constraints.

## Time-aware principles

- Store timestamps with an explicit timezone or normalized UTC representation.
- Keep event time separate from storage/ingestion time.
- A timestamp does not prove a claim is true.
- Validity depends on the type of information; do not force an expiry date where it makes no sense.
- Track changes as events rather than silently overwriting history.
- Resolve conflicts using source quality, scope, and time; preserve disputes when evidence is insufficient.

## Relational organization

Put each record near its strongest conceptual links by using indexed categories and a relationship graph. Physical folder placement may aid organization, but retrieval should follow explicit links and metadata rather than depend on folder names alone.

## Open questions

- Which concepts should be primitives and which should be learned?
- How should context-dependent meaning be represented without forcing one permanent interpretation?
- How should confidence be calibrated across unrelated domains?
- Which records should be cached, archived, refreshed, or forgotten?
