# generate — draft on-brand content from a request

One job: turn a content request into a draft that sounds like Ruff Cuts, using the voice guide.

## Inputs
- Working (this run): requests/&lt;request&gt;.md
- Reference (every run): ../voice-guide/01_identity/ (always)
- Reference (every run): ../voice-guide/02_language/ (always)
- Reference (as needed): the matching file in ../voice-guide/03_scenarios/ — pick the one that matches the request's content type

## Process
1. Read the request: what's being written, for whom, what happened (if it's a recovery situation).
2. Load identity + language layers. Load the one matching scenario file.
3. Draft. Check every line against phrases-to-avoid.md before finishing.
4. Write the draft to output/, named after the request.

## Outputs
- &lt;request-name&gt;-draft.md → output/

## Human check
Read the draft out loud. If any line would sound wrong said to someone in their driveway, or if it could appear in a children's book about a dog or an HOA newsletter, rewrite it. Edit in place — this is the file that ships.
