# BeneDoc

We build tools for regulatory compliance.

Our open-source libraries power document processing and machine learning inference in Go — released from work on the BeneDoc platform.

---

## Open Source

### [pdfer](https://github.com/benedoc-inc/pdfer)
Pure Go PDF library — zero CGO, no external dependencies. Covers the full document lifecycle:

- **XFA forms** — parse XFA into a typed form schema (fields, sections, rules, visibility logic); fill element-based and synthetic XFA datasets (including FDA eSTAR forms)
- **AcroForms** — create and fill text, checkbox, radio, listbox, combo, password, and multiline fields; generate appearance streams; flatten to static content
- **Digital signatures** — PKCS#7 (RSA + ECDSA), RFC 3161 TSA timestamps, LTV/DSS long-term validation, visible signature widgets
- **Redaction** — permanent content-stream redaction with opaque overlay; metadata scrubbing
- **PDF/A compliance** — validate and auto-repair PDF/A-1b/2b/3b (XMP metadata, ICC output intent, font embedding checks)
- **Manipulation** — encrypt/decrypt (AES-128), repair/linearize, text stamping, page numbering, merge, split, file attachments
- **Extraction** — tables (with merged cells and header detection), text, images, form field values

### [xfa-web](https://github.com/benedoc-inc/xfa-web)
Web renderer for XFA PDF forms — Go backend + React/TypeScript frontend. Drop in a PDF and get a fully interactive form:

- Renders all XFA field types: text, numeric, date/time, password, checkbox, radio, listbox, multi-select, file upload, signature, separator
- Section-based navigation with per-section completion tracking
- **Rules engine** — three-valued Kleene logic evaluates XFA script rules for field visibility, value, and validation; handles compound `&&`/`||`, `rawValue` patterns, and `.presence` checks
- XML round-trip: export current values back into the XFA datasets stream; import previously saved XML
- File attachments embedded into the output PDF via pdfer
- Hot-reload dev setup: Air (Go) + Vite HMR (React) with live pdfer volume mount

### [onnxer](https://github.com/benedoc-inc/onnxer)
Production-ready Go bindings for ONNX Runtime — no CGO required. Forked from [shota3506/onnxruntime-purego](https://github.com/shota3506/onnxruntime-purego) and significantly extended with session pooling, IO binding, LoRA adapter support, profiling, prepacked weights sharing, global thread pools, and comprehensive ORT v23/v24 API coverage.

---

[benedoc.com](https://benedoc.com)
