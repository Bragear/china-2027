# China 2027

A single-file slide deck for a 23-night trip through China, four friends from Oslo. Lives at https://bragear.github.io/china-2027/

Everything is in `index.html`. No build step, no dependencies.

## Editing the route

The map on slide 5 is drawn from data. Open `index.html`, find `window.ROUTE`, and edit the `stops` and `legs` arrays. Pins, labels, lines and the map framing are generated from it when the page loads.

- `anchor` sets where a stop's label sits: `right`, `left`, `above`, `below`, `belowright`, `aboveright`. Use it to resolve overlaps.
- `legs` run in stop order. `mode` is `rail` or `fly`. A flight can name a `via` transit point and a `bow` (arc curvature; flip the sign to bow the other way).
- `why` is the one-sentence case for the stop, `alt` its altitude in metres, `hi` twelve typical daytime highs (°C, Jan–Dec, approximate) shown on the card for the month you land there. `mainland: false` marks a stop outside mainland immigration (Hong Kong), which splits the visa count.
- `image` (optional) is a path or URL to a photo shown on the stop card, with `imageAlt` for its description. Leave it out and the card is type-only.
- The list beside the map is plain HTML in the same slide. Keep its rows in the same order as `stops`; the stop card is built from each row's travel line, activities and caveat.

## Using the map

**Play the route** walks the trip stop by stop: the map zooms to each stop, the leg into it redraws, and the card fills. Space pauses, Escape stops.

**Pick a landing date** on the route overview slide ("We land in Beijing on") and the deck fills in the days: dates on each stop card and week, the visa slide's mainland-stay count, and a check against Chinese holidays and the July–August heat. The date is remembered in the browser only.

Click a pin or a row to zoom in on that stop. The card on the right shows how you arrive, what to do, and previous/next buttons to walk the route. Arrow keys step between stops while zoomed in, and Escape (or clicking the sea, or "Back to the route") zooms out. Hovering a row highlights its pin and the leg that arrives there.

## Rebuilding the China outline

Only needed if the projection constants change. Download Natural Earth 1:50m countries as GeoJSON (public domain), then:

```bash
python3 tools/build-map.py path/to/ne_50m_admin_0_countries.geojson
```

It rewrites the outline paths between the `outline:start` / `outline:end` markers in `index.html`.
