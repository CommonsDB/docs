# CommonsDB Schema & Context

Versioned JSON Schema and JSON-LD context definitions for CommonsDB metadata declarations.

## Contents

- **`schema/`** — JSON Schema files for validating declaration metadata
- **`context/`** — JSON-LD context files for semantic interoperability

## Usage

Reference these files via w3id.org persistent URLs:

```
https://w3id.org/commonsdb/schema/0.3.0.json
https://w3id.org/commonsdb/context/0.3.0.json
```

Published versions are never edited; corrections are released as a new version.

## Changes in 0.3.0

**Context**

- The `lic` prefix is the Liccium ontology namespace (`https://w3id.org/liccium/ont/`), not a `.ttl` file URL.
- The ISCC prefix is `iscc_ont`. In 0.2.0 it shared the name `iscc` with the term, which made the definition cyclic and stopped JSON-LD processors.
- The credentials namespace is `https://www.w3.org/2018/credentials#`.

**Schema**

- Unknown keys are rejected in `declarationMetadata`, `publicMetadata`, `supplierMetadata` and `commonsDbRegistry`. A misspelt key such as `supplierData` no longer passes unchecked.
- `original`, `redirect`, `entryUUID` and `supersedes` are listed in `publicMetadata`, and `declarationId` in `commonsDbRegistry`. The declaration API accepts them and suppliers send them, but 0.2.0 did not describe them. The context maps them as well.
- `pdRationale` must be one of the nine Wikidata copyright determination methods.

