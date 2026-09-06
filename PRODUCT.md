# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Four friends from Oslo in their thirties, planning a three-to-four-week trip through China in 2027. They open the deck together in a planning conversation, most often on a laptop, and individually afterwards to re-read a detail, sometimes on a phone. Partners and family may be sent the link. It is read a handful of times over the planning period, not daily.

## Product Purpose

A single shareable slide deck that gets the group to agree on one route, a season and a rough budget, and that holds the practical facts (visa, payments, internet, trains, hotels) in one place they trust. It is also made for fun: the page itself is part of the pleasure of planning the trip.

Success is that the four of them decide and start booking without anyone having to re-research the basics.

## Positioning

Not a travel product. A personal planning artifact built from one piece of research (September 2026) and shaped through the group's own decisions: the chosen route, the alternatives they weighed and rejected, and the reasons. The map and stop cards are generated from the group's data, so the deck can change as fast as the plan does.

## Operating Context

- Presented as slides: arrow keys, space or click advance; the map slide is interactive and steps between stops with the same keys while zoomed in.
- Hosted publicly on GitHub Pages (https://bragear.github.io/china-2027/) from github.com/Bragear/china-2027. The repo is the source of truth; an older copy on Cheffelo's internal host is a snapshot.
- Edited by Brage with Claude. Route changes are made in the `window.ROUTE` data in `index.html`; the China outline is rebuilt only if the projection changes (`tools/build-map.py`, Natural Earth 1:50m, public domain).
- Printable: one slide per page, animations and dimming off.

## Capabilities and Constraints

- Single `index.html`. No build step, no framework, no external dependencies, no API keys.
- Fifteen slides: title, summary, key findings, the chosen route (overview and interactive map), alternatives on one slide, logistics, visa, practicalities, timing, budget, group-of-four notes, staged plan, week by week, thresholds that would change the plan.
- Map: pins, labels, legs and framing generated from stop data with a fixed equirectangular projection; focus mode zooms to a stop and swaps the list for a stop card; pin and list stay linked; keyboard operable; respects reduced motion.
- Facts are dated and provisional: visa-free entry for Norwegians is confirmed only to 31 Dec 2026; prices are 2026 observations; travel times and night counts for the chosen route are estimates, and the deck says so where that is the case.
- Language: English, with Chinese place names as a secondary label on the map and cards.
- Undecided: whether the alternative routes ever appear as toggles on the map; whether Oslo appears as an origin on the map; whether the group adds their own photos to the stop cards (an optional `image` field exists per stop).

## Brand Commitments

Personal, not a company deck. Deliberately not Cheffelo-branded. No stock photography: images appear only if they are the group's own.

## Evidence on Hand

- The research document the deck was built from: "China 2027: Three Itineraries for Four Friends from Oslo", September 2026 (kept by Brage; not in the repo).
- Natural Earth 1:50m country outlines, public domain, processed by `tools/build-map.py`.
- Flight and train times for the chosen route were spot-checked against public schedule sites in September 2026 and recorded as approximate.
- No photos, testimonials or bookings exist yet. Nothing about hotels, exact dates or fares is confirmed.

## Product Principles

- One route leads; the alternatives exist to show what was weighed, not to compete.
- Every number is dated and hedged where it is an estimate. The deck never presents a guess as a fact.
- Change the data, not the drawing. Anything that follows from the route is generated from it.
- Works as a presentation first: readable from across a room, driven from the keyboard, one idea per slide.
- Made for fun. Interaction and detail are welcome where they serve the trip, and dropped when they get in the way of deciding.
