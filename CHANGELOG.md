# Changelog

## [0.2.0] - 2026-08-09

### Changed

- Rebranded from `hypothesi` to `yurvon-screamo` (npm scope, git URLs, Android
  package, crate authors, LICENSE dual copyright)
- Android OCR: ML Kit script recognizers (Japanese, Chinese, Korean, Devanagari)
  are now `compileOnly` — host apps opt in per script. Latin remains always
  bundled. Previously Japanese was hardcoded as a required dependency.
- Replaced 8 `unwrap()` calls in macOS speech recognition callbacks with
  poison-recovery pattern to prevent host-application crashes

### Added

- `OcrScript` enum (Rust, TypeScript) for Android script model selection
- `OcrOptions.script` field + `with_script()` builder method
- README section documenting Android OCR opt-in with Gradle examples
- Unit tests for `OcrScript` serialization and `OcrOptions` script field

### Removed

- Build artifacts from git tracking: `.gradle/`, generated Tauri schemas
- Foreign tooling configs: `.beads/` issue tracker, `ai.json`, `CLAUDE.md`
- Beads integration section from `AGENTS.md`

## [0.1.1] - 2026-08-05

### Fixed

- Android: use Japanese text recognizer instead of Latin (ML Kit ships separate
  models per script)
- Android/iOS: mobile bridge compile fixes (JSObject return types, Swift
  PluginError encoding, VNRecognizeTextRequest recognition level)
- iOS: flush previous utterance before speak (matching Android QUEUE_FLUSH)

## [0.1.0] - 2026-08-03

### Added

- Initial implementation: speech recognition, TTS, OCR, barcode detection, face
  detection, image classification, language identification, on-device LLM
