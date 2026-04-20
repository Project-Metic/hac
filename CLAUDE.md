# CLAUDE.md — hac

HAC: Ada-based hierarchical clustering and analysis tooling. Used by Project-Metic for
binary analysis clustering — grouping binary artifacts by similarity, clustering vulnerability
patterns, and hierarchical classification of analysis results.

## What This Repo Is

An Ada/GNAT-based hierarchical clustering tool. The `.gpr` and `.hac` files indicate this
uses the HAC Ada compiler and GNAT project files.

## Key Invariants

- **Ada code must pass GNAT warnings without suppression.** Do not suppress GNAT warnings
  with pragmas to make code compile. Fix the underlying issue.
- **Cluster results must be reproducible.** HAC clustering is used in pipeline analysis —
  results must be deterministic given the same input.

## Dev Commands

```bash
# Build with GNAT
gprbuild -P hac.gpr

# Run fast mode
./fast.cmd

# Run tests
cd test && gprbuild -P test.gpr && ./run_tests
```

## Tech Stack

- Ada 2012, GNAT, HAC Ada compiler (`.hac` files), GPRbuild

## Integration with Project-Metic

- Clustering results used in the Metic portal vulnerability trend and anomaly correlation panels
- Binary similarity clustering for SBOM delta analysis

## What NOT to Do

- Do not suppress GNAT warnings with pragmas
- Do not produce non-deterministic clustering results
