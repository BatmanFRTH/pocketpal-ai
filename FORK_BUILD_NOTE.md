# Fork build note

This file exists for one reason: the upstream CI job `detect-changes` computes
`git diff --name-only HEAD~1` and treats an empty change list as
`translation_only=true`, which skips `build-android` and `build-ios`. An empty
commit therefore cannot trigger an Android build.

Any file outside `src/locales/` satisfies the detector. A root markdown file is
used because it is never bundled by Metro and is not read by any build script,
so the built APK still corresponds to the upstream source tree
(`a-ghorbani/pocketpal-ai@33aca61`).

This file can be deleted once the artifacts are retrieved.
