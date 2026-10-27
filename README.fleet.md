# mikenavi Crucible fleet source

This branch is upstream `main` with a merge of each feature branch. Each feature
lives on its own branch from upstream `main`, ready for an upstream pull request:

| Branch | Change |
|---|---|
| `fix/retire-dead-branch-tails` | a tail that a later client prompt contradicts stops being a protected resume point, so a growing conversation no longer re-prefills its whole prompt on every turn once the conversation cache is full |

Update: merge upstream `main` into each feature branch and fix it there, then merge
upstream `main` and the feature branches into this branch. A change that upstream
accepts drops out of the list. Newer upstream commits are not silently selected.

The gfx1151 engine is built with plain hipcc (`make engine SPLIT=0`) inside the
deployment's ROCm SDK image; the CPU tests run with `make test-cpu`. No weights or
private host state are included.
