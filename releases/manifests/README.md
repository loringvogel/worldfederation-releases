# Update manifest log

Every signed update manifest is committed here as `<version>/<id>.json` before the release
carries it. Clients refuse to install a manifest that is not here byte-for-byte
(design/self-update.md, section 3.7).

Rules:
- Only the release owner adds files here, from `federation release sign`. CI never does.
- Files are never edited or deleted. A withdrawn release gets a hold, not a removal.
- A manifest here that the owner did not sign means a signing key is compromised.
