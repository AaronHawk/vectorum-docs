# Vectorum — user guide

**Shipment tracking and exception detection for stove-parts-unlimited.com**

ShipHero and BigCommerce can tell us a package *shipped*. Neither can tell us
where it *is*, or that it has stopped moving. Vectorum asks UPS, FedEx and
USPS about every parcel every day, spots the ones that have gone wrong, and
puts them in one short list with everything needed to act on them, before
the customer has to ask.

This guide is for the customer service team and for anyone the tool is
being shown to. Part 1 is the daily routine; Part 2 goes page by page; Part 3
covers the pages customers see; Part 4 is for presenting it.

> **Public documentation edition.** Production screenshots have been withheld because they may contain real order or tracking identifiers and staff details. The private application repository retains the original screenshots.

---

## Contents

- [The one-minute version](#the-one-minute-version)
- **Part 1 — Using it every day**
  - [Signing in](#signing-in)
  - [The daily routine](#the-daily-routine-about-10-minutes)
  - [The daily digest email](#the-daily-digest-email)
- **Part 2 — Every page**
  - [The board](#the-board) · [A parcel's page](#a-parcels-page) · [What each flag means](#what-each-flag-means)
  - [Search](#search) · [Holds](#holds) · [Resolved](#resolved) · [Returns](#returns)
  - [Email templates](#email-templates) · [Settings](#settings)
  - [Reference pages](#reference-pages): Carriers · Coverage · Shadow peak · What it saves · Staff use · People
- **Part 3 — What customers see**
  - [The tracking page](#the-tracking-page) · [Reporting a problem and asking for a return](#reporting-a-problem-and-asking-for-a-return)
- **Part 4 — Presenting Vectorum**
  - [What it does today, in numbers](#what-it-does-today-in-numbers) · [What it deliberately does not do yet](#what-it-deliberately-does-not-do-yet) · [Decisions it needs](#decisions-it-needs) · [Talking points](#talking-points)
- [Set-up: calling customers with GoTo](#set-up-calling-customers-with-goto)
- [Questions and troubleshooting](#questions-and-troubleshooting)

---

## The one-minute version

- **Every parcel, watched.** Each label printed in ShipHero, and each website
  order in BigCommerce, becomes a parcel Vectorum follows. It asks the carrier
  for scans daily, and again the moment anybody opens the parcel.
- **Only the problems reach you.** Of roughly 1,300 open parcels on a normal
  day, about 15–20 need a person. The board shows those and nothing else.
- **Everything to act on, in one place.** The parcel page has the carrier's
  words, the order value, the address, the customer's phone (one click to
  call with GoTo), what was in the box, and a ready-to-send email draft.
- **A record of what was done.** Each flag is resolved with a reason —
  reshipped, claim filed, false alarm and so on — which is how the tool learns
  which of its flags are worth a person's time.
- **Customers can serve themselves.** A branded tracking page answers "where
  is my order" with the contents of the box, and lets a customer report a
  problem or ask for a return.
- **Nothing is sent to customers automatically.** Every customer email today
  is a draft a person reviews and sends. Automatic emails are a decision that
  has not been made yet (see [Decisions it needs](#decisions-it-needs)).

---

# Part 1 — Using it every day

## Signing in

| | Where |
|---|---|
| **Staff board** | `https://tracking.stove-parts-unlimited.com/admin` |
| **Customer tracking page** | `https://tracking.stove-parts-unlimited.com/track` |
| **Sign in with** | your `@stove-parts-unlimited.com` Google account |

There is no separate password and no approval step: anyone with a company
Google account is in as soon as they sign in. Access is taken away on the
[People](#people) page.

The menu along the top of every staff page:

| Menu item | What it is for |
|---|---|
| **Vectorum** (logo) | The board — the day's work |
| **Resolved** | Everything somebody has already judged |
| **Carriers** | How fast each carrier and service actually is |
| **Returns** | Return requests from customers, and authorised returns that never came back |
| **Holds** | Every parcel the carrier is holding, and why |
| **Coverage** | What Vectorum can and cannot see, and why |
| **Shadow peak** | What automatic customer emails *would* have said |
| **What it saves** | How many "where is my order" questions the tracking page answered |
| **Staff use** | Who uses the tool and how |
| **People** | Who has access |
| **Settings** | Late thresholds, customer banner, feature switches, email wording |

## The daily routine (about 10 minutes)

1. **Read the digest** in your inbox (weekdays, 8:35 AM Mountain — 7:35 AM in
   winter). It lists every flagged parcel, worst first.
2. **Open the board** from the digest's button. It shows only the flagged
   parcels, in the same order.
3. **Work from the top.** Critical problems (red) first: a customer report,
   damage, a parcel coming back, a refusal, a lost parcel.
4. **For each row, either act or judge:**
   - Nothing to do (it is moving again, it was a blip)? Pick **False alarm**
     in the row's *Resolve as…* menu and press **Save**. Ten seconds.
   - Needs action? Click the tracking number, do what the parcel page
     suggests (call, email, reship, claim), then resolve it with what you did.
   - Can't finish today? **Claim** it so nobody else chases it too, or
     **Snooze** it until a date, and add a note saying what you are waiting on.
5. **Check [Holds](#holds) and [Returns](#returns)** if the board mentions
   customers waiting for a return authorisation.

> **Why resolving matters, even "False alarm":** the thresholds that decide
> what is "late" started as estimates. Every verdict is a measurement. Twenty
> or so are enough to see which flags are noise and tune them; until then the
> tool can only guess. Resolving is also what keeps a handled parcel off
> tomorrow's board.

## The daily digest email

*[Production screenshot omitted from public edition]*

Sent each weekday morning. It contains:

- **The counts strip** — critical problems, other exceptions, return requests
  waiting, and how many flagged parcels have never been judged.
- **Every flagged parcel**, grouped by problem, worst first. Each line has the
  order number (links straight to the parcel page), the tracking number and
  carrier, and how long it has been quiet.
- **"Open the board"** — the same list, ready to work.

Ages are **business days** (Monday–Friday, Mountain Time, holidays excluded).
"Quiet" means no carrier scan in that time. A zero shows the weekday of the
last scan instead ("Fri, last scan"), and "Today" only when it really was
today. Customer names and addresses are left out of the email on purpose;
open the parcel for them.

The digest currently goes to one address. Adding recipients is a one-line
change — say who.

---

# Part 2 — Every page

## The board

*[Production screenshot omitted from public edition]*

The board is the work queue. From top to bottom:

**1. The summary line** — open parcels, how many are lost or returning, stuck
or cancelled, or taking too long, and how many cannot be tracked at all
(see [Coverage](#coverage)).

**2. Search** — order number, tracking number, customer name or email. It
suggests matches as you type.

**3. Needs attention** — one card per kind of problem, with a count. Click a
card to show only those parcels; click it again to go back. Cards at zero
stay on the page, greyed out: a zero means the check ran and found nothing,
not that the check is missing.

**4. Trackable / Cannot track** — the board shows parcels we can follow. The
*Cannot track* tab lists older USPS parcels whose labels were printed on
another company's postage account, which USPS will not let us query (each
links to USPS's own website).

**5. The table** — only the flagged parcels. The line above it says how many
others are open, with a link to **show every open parcel** (and back).

| Column | What it shows |
|---|---|
| **Issue** | The problem, coloured by how serious, and the **Resolve as…** control |
| **Quiet for** | Business days since the carrier last scanned it ("bd" = business days) |
| **Tracking** | Click to open the parcel page. A name appears beside it when someone has **claimed** it |
| **Carrier** | Click to show only that carrier |
| **Order / Customer** | From BigCommerce or ShipHero |
| **Last scan** | Our plain-English reading of the newest scan, then where and when, then the carrier's own words (what to quote on the phone), then what ShipHero says |

Click a column heading with arrows to sort by it. Sorting, filtering and the
"every parcel" view all live in the address bar, so a view can be bookmarked
or pasted to a colleague.

### Resolving from the board

Each flagged row has a **Resolve as…** menu with five reasons, and **Save**:

| Reason | Use it when |
|---|---|
| **Reshipped** | You sent a replacement |
| **Claim filed** | You opened a claim or trace with the carrier |
| **Delivered late** | It turned up, just slowly |
| **False alarm** | Nothing was actually wrong — the most useful verdict for tuning |
| **Customer contacted** | You spoke to or emailed the customer and that settles it for now |

After saving, the board says what was recorded, with an **Undo**:

*[Production screenshot omitted from public edition]*

A resolved parcel leaves the board, but **comes back by itself if its problem
gets worse** than what was judged — for example a "Stalled" parcel resolved
as a false alarm that later becomes "Lost". Everything resolved is listed on
[Resolved](#resolved).

### Filtering

*[Production screenshot omitted from public edition]*

Clicking a card (here, *Held*) shows just those rows. The other cards keep
their counts so you can see what you are hiding; the *Filtered to* bar has
a **Clear** link.

## A parcel's page

*[Production screenshot omitted from public edition]*

Click any tracking number to get here. From the top:

**The banner** says what is wrong and what to do, in plain words — here,
the receiver refused the parcel and the carrier is disposing of it, so it is
*not* coming back and the customer needs a refund or a reshipment.

**The buttons:**

| Button | Does |
|---|---|
| **What the customer sees** | Opens this parcel's customer tracking page, exactly as they see it |
| **UPS / FedEx / USPS tracking, live** | The carrier's own page, which can be fresher than ours |
| **Everything on order …** | Every box on the same order |
| **Draft an email** | Opens a Gmail window to the customer, already filled in with the wording for this problem (from [Email templates](#email-templates)). **Nothing is sent until you press Send.** |

**Casework:**

- **Claim** — puts your name on the parcel (and on its board row) so two
  people don't chase the same thing. **Unclaim** to let go.
- **Snooze** — pick a date; the parcel stays off the board until then.
- **Resolve** — the same five reasons as on the board, plus an optional
  "why". Once resolved, the button becomes **Reopen**.
- **Note** — anything worth knowing later: "rang, no answer", "UPS trace
  #12345". Notes are kept on the parcel and never change a resolution.

**Shipment** — everything about the order in one box:

| Row | |
|---|---|
| **Order** | Number, date placed (with the year — replacements are sometimes sent against old orders), and **Open in BigCommerce ↗** for refunds and order history |
| **Customer / Contact** | Name, email and phone. **Click the phone number to call with GoTo** (see [set-up](#set-up-calling-customers-with-goto)) |
| **Ship to** | The full address this box went to. The recipient's name appears when it differs from the buyer's (gifts, job sites) |
| **Order total** | Total, shipping charged (or "free shipping"), payment method |
| **This box** | The value of the parts in *this* box — what a reshipment would cost |
| **Customer's note / Shop notes** | What the customer typed at checkout, and the shop's own notes from BigCommerce, when there are any |
| **Carrier, Threshold** | The service, and how many quiet business days it is allowed before it is flagged |
| **Shipped, Last scan, Tracking** | When it left, when it was last seen, and whether we are still asking the carrier |
| **Shipper says** | ShipHero's own status for the label — useful when the carrier has nothing |

On the right: the **carrier's promised delivery date** (when they gave one)
and **In this box** — each part with its photo, SKU, quantity and price,
linked to the part on the shop.

**Notifications** lists what an automatic email *would* have said at each
point, and to whom it would have gone (*auto* or *a person decides*). None
of these were sent; see [Shadow peak](#shadow-peak).

**Casework log** is every claim, note, snooze and resolution, with who and
when. **Scan history** is every carrier scan, newest first, with how long
each gap was.

A delivered parcel with several parts looks like this:

*[Production screenshot omitted from public edition]*

## What each flag means

**Critical** problems are red in the digest and on the board; everything
else is an **exception**. A parcel is listed once, under its most serious
problem.

| Flag | Tier | What happened | What to do |
|---|---|---|---|
| **Customer reported a problem** | Critical | The customer used *Tell us* on the tracking page (not arrived, damaged, wrong part, other). Their words are at the top of the parcel page. | Contact them; reship, refund or claim as needed. An alert email also goes out the moment a report comes in. |
| **Damage reported** | Critical | The carrier scanned it as damaged. | Contact the customer before they contact you; file a carrier claim. |
| **Returning to sender** | Critical | The carrier is sending it back. | Contact the customer now — refund or reship — before it lands back here. |
| **Refused by the receiver** | Critical | The receiver refused it (often import charges). The banner says whether it is coming back or being disposed of. | Contact the customer about a refund or reshipment. |
| **Lost** | Critical | No scan for well past its allowed quiet time (its threshold plus three business days). | Open a trace or claim with the carrier; usually reship. |
| **Shipper flagged a problem** | Exception | ShipHero marked the label as failed and the carrier has said nothing more. | Check the label in ShipHero. |
| **Label voided** | Exception | The label was cancelled and **nothing else on the order is moving**. (A voided label with a replacement on its way is not flagged.) | Check whether the order still needs to go out. |
| **Held** | Exception | The carrier is holding it: payment owed, address problem, no access, customs. Pickup notices and unpaid import duties only count after a wait; holds the customer asked for never count. See [Holds](#holds). | Usually: fix the address with the carrier, or ask the customer to pay/collect. |
| **Never collected** | Exception | A label was printed two or more business days ago and the carrier has never scanned it. If another label on the order moved, it says the label was probably replaced. | Check it isn't still on the shelf; void it in ShipHero if it was replaced. |
| **Overdue** | Exception | Past the date the carrier itself promised, and not moving. | Watch, or contact the customer if it keeps sliding. |
| **Stalled** | Exception | No scan for longer than its service allows (see the table below). | Check the carrier's live page; often it moves the next day. |
| **Delayed** | Exception | The carrier announced a delay (a bad address it is correcting, a remote area). | Usually wait; correct the address if asked. |

**How long a parcel may be quiet** before it counts as stalled (business
days; changeable on [Settings](#settings)):

| Service | Allowed |
|---|---|
| Overnight / Next Day Air | 1 |
| 2-Day | 2 |
| Ground / Home Delivery | 4 |
| USPS Ground Advantage / First Class | 5 |
| LTL / freight | never flagged automatically |

Business days are counted whole, in Mountain Time: a parcel last scanned on
Friday morning reads 0 on Monday and 1 on Tuesday.

## Search

*[Production screenshot omitted from public edition]*

Type an order number, tracking number, customer name or email into the box
on the board. Results get the same columns, sorting and filters as the
board, and each result is refreshed from the carrier before it is shown.

## Holds

*[Production screenshot omitted from public edition]*

Every open parcel the carrier is holding, **including the ones that are not
flagged**. A customer calling about a held parcel will often be on this page
even when it is not on the board. Click a reason at the top to filter.

The *On the board?* column says either which flag it carries or why it is
not flagged yet:

| Reason | When it becomes a flag |
|---|---|
| Refused by the receiver | Immediately, and as **critical** |
| Payment not collected, address problem, no access, held by customs, no reason given | Immediately |
| Import duties due | After 2 business days unpaid |
| Waiting to be picked up (PO box, locker, counter) | After 5 business days uncollected |
| Held at the customer's request | Never |

## Resolved

*[Production screenshot omitted from public edition]*

Everything somebody has judged: when, which parcel, what it was flagged as
at the time, the verdict, who, and whether it is still settled. A parcel
whose problem has since become worse returns to the board automatically and
shows that here.

## Returns

*[Production screenshot omitted from public edition]*

From the top:

- **Customers waiting for an answer** (only when there are any) — return
  requests customers made from the tracking page: which part, why, and
  photos. The board mentions them too. Each has a **draft approval email**
  with the return instructions; mark it **handled** once the RMA is issued in
  ShipHero.
- **Authorised, never arrived** — returns ShipHero authorised where the part
  never came back, oldest first. The top of the list is the part most likely
  to be settled rather than chased.
- **Why things come back**, **Which parts come back** and **Volume by
  month** — for spotting a part or a reason that keeps recurring.

The cards across the top count returns authorised, came back, still waiting,
and waiting over 30 days, for the last year.

## Email templates

*[Production screenshot omitted from public edition]*

*Settings → Edit the templates.* The wording of every email the tool drafts:
one per kind of problem, the return approval, and the automatic emails that
are not switched on yet. Click one to edit it with a live preview against a
real shipment. Placeholders like `{{order}}` fill in automatically.

**Your own macros** are text you write once and reuse — a sign-off, a line
of policy — written into any template as `{{name}}`.

Editing a template changes the next draft; it never sends anything and never
changes an email already sent. Every version is kept.

## Settings

*[Production screenshot omitted from public edition]*

| Section | What it does |
|---|---|
| **When a parcel counts as late** | The quiet-days threshold per service. Change one, say why, and it applies immediately. Every change is kept, with who and why. |
| **Notice shown to customers** | A banner at the top of every customer tracking page — "Shipping delays — severe weather". Optional start and end dates, with a preview. |
| **Let customers report a problem** | The *Tell us* link on the tracking page. On. |
| **Let customers request a return** | The *Start a return* link on delivered parcels, within 30 days. On. Requests land on [Returns](#returns); nothing is authorised automatically. |
| **Let a signed-in customer see everything at once** | The account page listing all of a customer's orders. Switched on for testing, but not linked from the shop yet. |

## Reference pages

These answer "how are we doing" rather than "what do I do now".

### Carriers

*[Production screenshot omitted from public edition]*

How each carrier and service actually performed over the last 90 days,
measured from our own scans: how many we delivered, the typical number of
business days, the slowest tenth, and how often the carrier met the date it
promised. Useful when choosing a service or answering "how long does it
usually take".

### Coverage

*[Production screenshot omitted from public edition]*

What Vectorum can see, with today's numbers. **100% of this week's labels
can be tracked**; the 1,248 older parcels it cannot track were printed on
other companies' USPS postage accounts before that was fixed, and they age
out of the open list over the coming weeks. The page also counts parcels
that shipped without going through ShipHero.

### Shadow peak

*[Production screenshot omitted from public edition]*

Every customer notification the system *would* have sent, if automatic
emails were on: how many, of what kind, which would go straight to the
customer (*auto*) and which to a person (*CSR*), and how many were held back
by the rule that skips a second email within 48 hours. **Nothing on this
page was sent.** It exists so the decision to switch automatic emails on is
made from numbers — about 4,300 customer emails a month at the current rate,
mostly delivery confirmations.

### What it saves

*[Production screenshot omitted from public edition]*

How many "where is my order" questions the tracking page answered without
anybody writing in. Counting started on 12 October, once staff visits were
separated from customers' — it will start to climb once the shop's shipping
emails link to the tracking page.

### Staff use

*[Production screenshot omitted from public edition]*

Who opened what and who did anything — casework, returns handled, settings
changed — by person, by week and by page. Reading is counted from
13 October; the casework columns go back to the start.

### People

*[Production screenshot omitted from public edition]*

Everyone who has signed in. **Switch off** removes someone's access at their
next click; it deletes nothing they did. You cannot switch off yourself, or
the last active account.

---

# Part 3 — What customers see

## The tracking page

Customers reach it from **Track an order** on the shop, or from a link in
their shipping email. They can type a tracking number, an order number or
their email address — whichever they have.

*[Production screenshot omitted from public edition]*

On the way, and delivered (shown at phone size, which is how most customers
see it):

| On the way | Delivered |
|---|---|
| *[Production screenshot omitted from public edition]* | *[Production screenshot omitted from public edition]* |

What the page shows:

- **The status in plain words** and the delivery date — the carrier's date
  and time window when they gave one, otherwise our own estimate, labelled as
  ours. Once delivered: when it was delivered.
- **The latest scan** with the full history one tap away, and a link to the
  carrier's own page.
- **Items in this shipment** — photo, name, price, each linked to the part on
  the shop. For an order in several boxes, only what is in *this* box.
- **Often needed with parts like this** — parts people commonly order
  together (a gasket and the cement to fit it). It adds nothing to the order.
- **Start a return** — on delivered parcels, with the days left in the
  30-day window.
- **Something wrong? Tell us** — the problem form.

It never shows the customer's name, street address, email or order total,
because order numbers can be guessed.

## Reporting a problem and asking for a return

- **Tell us** asks what went wrong — not arrived, damaged, wrong part,
  other — and lets them write a few words. The parcel goes to the **top of
  the board** as *Customer reported a problem*, and an alert email goes out
  straight away (to one address today, like the digest).
- **Start a return** asks which part and why, with photos. It lands on
  [Returns](#returns) as a customer waiting. It does **not** authorise
  anything: someone issues the RMA in ShipHero exactly as today.

Both can be switched off on [Settings](#settings) in seconds.

---

# Part 4 — Presenting Vectorum

## What it does today, in numbers

As of 14 October 2026:

| Measure | Today |
|---|---|
| Parcels followed | **9,154** (USPS, UPS, FedEx), about 1,300 open on a normal day |
| Carrier scans recorded | **98,076** |
| Parcels needing a person today | **16** of 1,307 trackable open parcels |
| Labels this week we can track | **100%** (86% over 30 days; older USPS labels were printed on other postage accounts) |
| On-time against the carrier's own date | UPS Ground **97%**, FedEx 2Day **98%**, USPS Ground Advantage **69%** (last 90 days) |
| Returns mirrored from ShipHero | 1,602 authorised in a year; 177 waiting over 30 days |
| Emails sent to customers automatically | **none** — every customer email is a reviewed draft |

What changed for the team:

- **Problems surface on their own**, ranked, the morning they happen —
  including ones nobody would otherwise notice: a label printed and never
  collected, a refused parcel being destroyed abroad, a voided label with
  nothing else on its way.
- **One page per parcel** replaces checking ShipHero, BigCommerce and the
  carrier's site separately: order value, address, phone, contents, carrier
  history and a ready email draft.
- **Customers can answer "where is my order" themselves**, with the contents
  of their box, and report problems or request returns without a phone call.

## What it deliberately does not do yet

- **No automatic customer emails.** Everything is logged in "shadow mode"
  ([Shadow peak](#shadow-peak)) so the volume and accuracy can be judged
  before anything is switched on.
- **No refunds or RMAs.** It links to BigCommerce and ShipHero, where those
  happen, rather than copying them.
- **It does not scrape carrier websites.** It uses the carriers' official
  tracking APIs only.

## Decisions it needs

| Decision | Why it matters |
|---|---|
| **Who gets the daily digest** | Today it goes to one person. The worklist only helps if the people who act on it see it. |
| **Work the board for a week** | Verdicts — even "false alarm" — are what turn the late thresholds from estimates into measurements. 16 flagged parcels are waiting. |
| **Link the shop's shipping email to the tracking page** | Until customers are sent there, *What it saves* cannot show what the page is worth. |
| **Whether to switch on automatic customer emails** | About 4,300 a month at today's rate, mostly "it arrived". A policy decision, not a technical one; it needs a separate sending address first. |

## Talking points

- *"Before, we found out a parcel was lost when the customer called. Now the
  board shows it the day it stops moving."*
- *"Of 1,300 parcels in transit, it shows the 15–20 that need us, with the
  reason and the next step."*
- *"Every resolution is recorded, so we can see what goes wrong, with which
  carrier, and how often — and tune what counts as late from evidence."*
- *"Nothing goes to customers without a person deciding. The automatic
  emails are built and measured, and switched off until we choose."*

A good live demo: open the board → click the *Refused by the receiver* row
→ show the banner, the order value and address, **Draft an email**, and
**What the customer sees** → back to the board, *Resolve as… Customer
contacted* → **Undo**.

---

## Set-up: calling customers with GoTo

The customer's phone number on a parcel page is a link that opens **GoTo**
with the number filled in. Once per computer:

1. Use the GoTo **desktop app** (the browser version cannot take these links).
2. Windows **Settings → Apps → Default apps**, search for **TEL**, choose
   **GoTo**.
3. The first time you click a number, the browser asks to open GoTo — tick
   **Always allow**.

If GoTo is missing from the list in step 2, reinstalling the desktop app
usually fixes it. Test on your own number first to see whether your GoTo
dials straight away or waits for you to press Call. International numbers
are shown as plain text to copy, so a click can never dial the wrong person.

## Questions and troubleshooting

**A parcel I resolved is back on the board.** Its problem got worse than
what was judged (for example, from stalled to lost). That is deliberate.

**The board says a parcel is quiet but the carrier's site shows a new scan.**
Our data refreshes daily and whenever a parcel is opened. Opening the parcel
page pulls the latest scans.

**A parcel isn't on the board at all.** Search for it. If it is on the
*Cannot track* tab, USPS will not share its scans with us; use the carrier
link on its page. If search finds nothing, it was probably shipped outside
ShipHero (see [Coverage](#coverage)).

**Clicking "Draft an email" opened Gmail — did it send?** No. It opens a
compose window; nothing is sent until you press Send.

**Clicking the phone number did nothing.** GoTo is not set as the default
calling app yet — see [the set-up](#set-up-calling-customers-with-goto).

**I picked the wrong reason.** Use **Undo** on the board straight away, or
**Reopen** on the parcel page, then resolve again.

**Who can see customer details?** Only signed-in staff. The digest email and
the customer pages leave out names, addresses and order totals.
