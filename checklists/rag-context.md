# RAG & Context Design Checklist

Checklist for reviewing retrieval, context construction, and knowledge usage in an AI system.

## 1. Context Sources

- [ ] The system documents which data sources can be used as context.
- [ ] Each data source has an owner.
- [ ] Source freshness is understood.
- [ ] Sensitive or restricted sources are clearly identified.
- [ ] The system distinguishes between user-provided context, retrieved context, and system-level instructions.

## 2. Retrieval Design

- [ ] Retrieval is used only where it improves the task.
- [ ] Retrieval queries are generated or transformed intentionally.
- [ ] Retrieved documents are ranked.
- [ ] Irrelevant or low-quality results are filtered.
- [ ] Retrieval behavior is tested on real examples.

## 3. Chunking and Indexing

- [ ] Chunking strategy matches the data type.
- [ ] Chunks preserve enough context to be useful.
- [ ] Metadata is stored with chunks.
- [ ] Index updates are handled reliably.
- [ ] Deleted or outdated content can be removed from the index.

## 4. Context Construction

- [ ] The system controls how much context is inserted.
- [ ] Context is ordered intentionally.
- [ ] Context includes source references where useful.
- [ ] Conflicting context is handled explicitly.
- [ ] The system avoids uncontrolled context growth.

## 5. Grounding and Citations

- [ ] The system can explain which sources influenced the answer.
- [ ] Citations or source links are included where needed.
- [ ] The model is instructed to separate retrieved facts from assumptions.
- [ ] The system handles missing evidence safely.
- [ ] Users can inspect or verify important sources where appropriate.

## 6. Memory and Personalization

- [ ] User-specific memory is separated from global knowledge.
- [ ] Memory has clear write rules.
- [ ] Memory has deletion or correction rules.
- [ ] Old memory does not silently override newer evidence.
- [ ] Personalization is tested for harmful or incorrect behavior.

## 7. Red Flags

- [ ] “We use RAG” only means vector search plus prompt injection.
- [ ] Retrieval quality is not measured.
- [ ] Outdated documents remain in the index.
- [ ] The system cannot explain where answers came from.
- [ ] User memory and global knowledge are mixed together.
- [ ] Context windows are filled without ranking or filtering.