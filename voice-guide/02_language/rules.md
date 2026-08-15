# Checkable rules

The single source of truth for anything the checker in `brand-app/` can test mechanically: a literal phrase or a phrase family (regex pattern). This is separate from [mechanics.md](mechanics.md), which covers *computed* checks (sentence length, exclamation counts, emoji counts by content type) — those depend on counting and context, not a static match, so they stay as procedural logic in the build stage rather than table rows here.

When this table changes, `brand-app/02_build/output/index.html`'s checker must be rebuilt from it — don't hand-edit the JS rule list independently, or the two drift apart. See `brand-app/02_build/CONTEXT.md`.

## Columns

- **type** — `phrase` (exact wording) or `pattern` (a regex family covering variants)
- **severity** — `hard` (breaks a rule outright) or `soft` (worth a look, not always wrong)
- **context** — `any`, `email`, or `caption` — restricts the rule to one content type
- **why** — the reason, in one line
- **try instead** — what to write instead

## Cutesy / pun wordplay

Researched against how dog owners and pet brands actually talk online — [50 dog puns (Today)](https://www.today.com/pets/dog-puns-rcna131831), [the ultimutt list of dog puns](https://thecaninecopywriter.co.uk/the-ultimutt-list-of-dog-puns/), [Dogster's dog slang dictionary](https://www.dogster.com/lifestyle/dog-slang/), and [Barketing on pet-business language](https://barketing.co/watch-your-language-key-phrases-for-pet-business-marketing/), which makes the same call we do: "pet parent" reads softer and more sophisticated than "fur baby," but a premium brand still uses it sparingly, not as a default.

| pattern | type | severity | context | why | try instead |
|---|---|---|---|---|---|
| `fur[\s-]?bab\w*` | pattern | hard | any | Reads cutesy, not warm | The dog's name, or "your dog" |
| `\bpupper\b`, `\bdoggo\b`, `\bpawrent\w*` | pattern | hard | any | Baby-talk for the dog | The dog's name, or "your dog" |
| `fur family` | phrase | hard | any | Same problem as "fur baby," dressed up | "Your dog," or the dog's name |
| `pawsitiv\w*`, `furrific\w*`, `fur-?fect\w*`, `fur-?ever` | pattern | hard | any | Banned dog-pun wordplay | Say it straight, skip the pun |
| `paw-?some`, `paw-?fect`, `a-paw-log\w*` | pattern | hard | any | Same pun-wordplay problem, different word | Say it straight |
| `pupdate` | phrase | hard | any | Pun wordplay, same family as "pawsitively" | "Update" |
| `mutts about (you\|it)`, `raise the woof`, `pup-?arazzi`, `paw-?lease`, `paw-?don\w*`, `woof-?derful`, `(un-?)?fur-?gettable`, `fur-?tastic` | pattern | hard | any | More pun wordplay in the same family | Say it straight |
| `ruff day` | phrase | hard | any | Pun on "rough day" | "A hard day," "a long day" |
| `toe beans`, `sploot\w*`, `\bblep\w*`, `\bmlem\w*`, `\bderp\w*` | pattern | hard | any | Internet pet-slang ("DoggoLingo") — too online for our register | Describe plainly |
| `\bdog mom\b`, `\bdog dad\b` | pattern | soft | any | Common shorthand, but leans cutesy-pet-parent | Describe by name or relationship instead |
| `\bzoomies\b` | phrase | soft | any | Cute and common, but casual — worth a second look in brand copy | "Burst of energy," or describe what happened |
| `pet parent\w*` | phrase | soft | any | Softer than "fur baby," but still a pet-brand default — we said "smart adults," not "parents" | "You," their name, or "your dog's person" |

## Corporate deflection and filler

| pattern | type | severity | context | why | try instead |
|---|---|---|---|---|---|
| `per our policy`, `as per our previous` | phrase | hard | any | Corporate deflection | Say what happened, plainly |
| `valued customer` | phrase | hard | any | Nobody says this and means it | Use their name |
| `please be advised` | phrase | hard | any | Corporate throat-clearing | Just say the thing |
| `we are writing to inform you`, `this email is to inform you` | pattern | hard | email | Stiff, buries the point | Lead with the point |
| `due to unforeseen circumstances`, `circumstances beyond our control` | pattern | hard | any | Blame-shifting, no accountability | Say plainly what happened — see [apology-email.md](../03_scenarios/apology-email.md) |
| `we sincerely apologize for any inconvenience this may have caused` | phrase | hard | any | The textbook non-apology | Say what happened and what we're doing — see [apology-email.md](../03_scenarios/apology-email.md) |
| `we (take\|appreciate) your (concerns?\|patience)[^.?!]*(very seriously\|during this time)` | pattern | soft | any | Stock corporate opener | Say the specific thing instead |
| `at this time`, `at the present time` | pattern | soft | any | Filler — cut it | "Now," or delete it |
| `moving forward` | phrase | soft | any | Corporate filler | Usually deletable entirely |
| `rest assured` | phrase | soft | any | Corporate reassurance filler | State the fact plainly |
| `please do not hesitate to contact us` | phrase | soft | any | Stiff, generic | "Text us if anything changes" |

## Hedging and passive blame-dodging

| pattern | type | severity | context | why | try instead |
|---|---|---|---|---|---|
| `mistakes were made` | phrase | hard | any | Passive blame-dodge | Say who/what plainly, own it |
| `it has come to our attention` | phrase | soft | any | Stiff, impersonal opener | Just say what happened |
| `we regret to inform you` | phrase | soft | any | Stiff | Say it plainly and warmly |

## Superlatives and hard-sell pressure

| pattern | type | severity | context | why | try instead |
|---|---|---|---|---|---|
| `best in austin`, `#1\b` | pattern | soft | any | Unverifiable superlative | Name the specific thing you're proud of |
| `don't miss out`, `limited time only`, `act now` | pattern | soft | any | Hard-sell pressure — not our register | State the fact, let them decide |

## Sign-offs

| pattern | type | severity | context | why | try instead |
|---|---|---|---|---|---|
| `best regards`, `kind regards`, `sincerely,?` | phrase | soft | email | Formal sign-off | "— Dana" or "— The Ruff Cuts team" |
