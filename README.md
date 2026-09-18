# Met Museum API Demo — Egyptian Art, "cat" Search

This is a worked example of pulling open collection data from the Metropolitan Museum of Art's public API, scoped to a single department.

## What was searched

- **Department:** Egyptian Art
- **Department ID:** `10` (exactly as returned by the museum's own department listing — `/departments`)
- **Search term:** `cat`
- **Result:** **Total objects found: 1**
- **Object IDs returned (first five or so — the API listed only one):** `552008`

The lone match is object `552008` — *Unfinished pseudo block statue* (diorite), where the term "cat" appears in its catalog data. Note the department-scoped full-text match for "cat" is genuinely narrow; searching `cats` in the same department returns the identical single object, and `feline` returns none.

## How to rerun the search

Call the Met's public collection API: `GET https://collectionapi.metmuseum.org/public/v1/search?departmentId=10&q=cat` — first fetch `/departments` to confirm the department ID, then read `total` and the `objectIDs` array from the response.

## Notes for the demo

- The department ID must come from the museum's department listing, not guessed — the numeric IDs skip values (e.g. Ancient West Asian Art is `3`, and there is no `2`).
- `total` and `objectIDs` are returned verbatim by the API; the sample above is unedited.
