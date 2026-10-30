## v1.28 (30 Oct 2026): IIIF viewer fix (on top of v1.28-dev1)

Fixed
- **IIIF viewer showed the wrong pages for manifests with repeated canvas labels** (found with Trinity College R.16.38A/B, where labels such as "1", "2" repeat). Canvases are now looked up by their position in the manifest, not by label. "Go to canvas", prev/next and unit locks use the same position.
- **IIIF viewer skipped canvases with an empty label**, shifting every later canvas number. An unlabelled canvas now keeps its place and is labelled `[n]`.

Unchanged
- Manifests with unique labels behave exactly as before.
- `NEWT_VERSION` (backup/config stamp) is still `newt_v1_27`.

Known open issues: see `IIIF_failure_modes_Newt_viewer_v1_0.md` (O1-O10).
