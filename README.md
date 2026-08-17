# Catalog-bound authority

**Lifecycle control over records you do not store.**

An experiment report on governing AI-agent memory that lives in a store you
neither own nor can delete from.

- [Read the note (English)](NOTE-EN.md)
- [Читать заметку (по-русски)](NOTE-RU.md)

---

## The pattern in one paragraph

Split ownership by *what*, not by *where*. The external provider keeps content,
embeddings and similarity search. A local catalog keeps identity, exact version,
provenance, lifecycle status and a keyed fingerprint of what was catalogued.
Search returns references, never bytes. Policy runs on the catalog. Only after
an allow decision does the boundary fetch that exact version itself and verify
the fingerprint.

Two properties follow that are not obvious:

- **A denied record is never fetched.** The decision happens on references, so
  the content never leaves the provider.
- **Revocation works without deletion.** Strike the catalog entry and the record
  cannot be disclosed, while it sits untouched in the provider's store.

The generalisation:

> To hold lifecycle authority over a record, you do not need to hold the record.
> You need to be the only path to disclosure, and to hold a keyed fingerprint of
> what you catalogued.

## What this is not

This is an experiment report, not a product, a specification, or a security
guarantee. The arrangement was verified as an executable matrix of ten checks
against an in-process fixture. The note states, in full, what the fixture does
not demonstrate — including the unsolved question of who may write to the
catalog in the first place.

The harness itself is not published here. The ten checks are described in the
note as a specification, which is enough to rebuild the same matrix against a
different stack.

## Status

Published as a dated technical note to make the idea findable and citable.
Feedback is welcome, particularly from anyone running agent memory on a store
they do not control. The reconciliation and post-filter-refill questions in the
note are open, and hearing how they break in practice is more useful than
guessing.

## Licence

The text is licensed under [CC BY 4.0](LICENSE). Attribution appreciated;
reuse, adaptation and commercial use are permitted.

## Citing

See [`CITATION.cff`](CITATION.cff). A DOI will be assigned via Zenodo on the
first tagged release.
