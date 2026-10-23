# ZERO ONE 8.5.0 verification

Verified 23 October 2026. This update adds automatic free AI and four named provider choices to the existing native encrypted Vault. Existing dirty development and Store checkouts were preserved; implementation started from the clean public 8.4 main branch.

## Verified checks

- `npm run dist:win` completed successfully, including `npm run check`: 69 Vitest UI/contract tests and 251 Node backend tests, TypeScript, production Vite build and static website validation.
- The 29 Vault/backend tests cover paid-ID rejection, official endpoint binding, zero prompt/completion/request ceilings, disabled fallback, single-request quota failures, actual routed-model metadata, encrypted profile persistence, cancellation and redacted transport errors.
- Pinned ZSEC payload verification passed: 89 files, including 60 Windows PE files. Pinned CPU runtime verification passed: 34 files.
- Production Windows package smoke passed launch/DOM, fresh CPU setup state, isolated Browser Pilot and ZSEC clean/incomplete scan behavior. The smoke now saves/selects/loads/deletes a free-router profile through actual packaged IPC with OS encryption, checks all new provider definitions and verifies no saved key appears in snapshots. It uses a disposable synthetic profile and sends no provider inference request.
- Archived `electron/main.cjs` and `electron/zerothink-providers.cjs` match source bytes. Packaged application metadata identifies 8.5.0. Electron Builder transforms package metadata during packaging, so complete package.json byte equality is not asserted.
- Tracked-path review found no database, private-key or genomic-data files. A targeted high-confidence credential-pattern scan found only an existing explicit synthetic API-key export-rejection fixture. New changes contain public source, tests, provider references and build evidence. This is a bounded audit, not a guarantee that every possible secret format can be detected.

## Local Windows installer

Filename: `ZERO-ONE-8.5.0-win-x64.exe`

Size: 145,863,124 bytes.

SHA-256: `02f17a2365a7224d728e68aae5f2640e8f5becc8c15f6afc962e4188abc5dc8c`.

Authenticode state: `NotSigned`.

The local package is built and its unpacked production app passed smoke testing. The installer was not run against the user's existing installation. No live hosted inference, account eligibility, quota or billing result was tested. No new CPU generation benchmark was needed for the provider-only production changes.

## Delivery boundary

This receipt establishes local source validation and Windows packaging. It does not establish a public 8.5 installer release, Microsoft Store upload/submission, certification or installed update. Existing website snapshot validation reports published 7.9.2; that snapshot is historical and is not the current-release authority. Current public download links are documented separately in README.
