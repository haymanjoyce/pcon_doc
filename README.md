# pcon_doc

Content repository for doc_app. Holds the markdown documents, evidence files, and vector index for the AI-assisted authoring platform.

---

## Structure

```
/pcon_doc
  /docs          ← markdown documents (tracked by git)
  /evidence      ← source PDFs and text files (gitignored)
  /index_store   ← LlamaIndex vector index cache (gitignored)
```

---

## What is tracked

| Path | Tracked | Notes |
|------|---------|-------|
| `docs/` | ✅ Yes | Markdown documents — versioned and pushed to GitHub |
| `evidence/` | ❌ No | Source PDFs and text files — local only |
| `index_store/` | ❌ No | Vector index cache — rebuilt automatically |

---

## Adding evidence

Drop PDF or `.txt` files into `evidence/`, then rebuild the index via the doc_app UI (sidebar → "Rebuild index") or API:

```bash
curl -X POST https://pcon.pro/api/index/rebuild
```

---

## Document commits

AI-generated document commits are prefixed `AI:` and pushed automatically by doc_app via the `commit_and_push` tool. Human commits should be prefixed `HUMAN:`.
