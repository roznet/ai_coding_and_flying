---
name: ga-trip-planner
description: >
  Plan flying trips for GA pilots based in Europe. Use this skill whenever the user mentions
  trip planning, destination discovery, airport scouting, weekend flying, vacation planning by plane,
  finding GA-friendly airports, or exploring new places to fly to. Also trigger when the user asks about
  landing fees, handling, fuel stops, or wants to combine flying with leisure (hotels, restaurants, activities).
  Even casual mentions like "where should I fly this weekend" or "nice airports in Italy" should trigger this skill.
---

# GA Trip Planner

Plan leisure flying trips across Europe for general aviation pilots. The goal is to find great destinations
where general aviation is welcome, affordable, and convenient — and where there are genuinely enjoyable
things to do once on the ground.

## Getting Started

Before planning, confirm the following with the user if not already known from context:

1. **Aircraft type** — what are you flying? (needed to determine runway requirements, range, fuel type, and speed)
2. **Home base(s)** — where are you departing from?
3. **Where to save trip plans** — ask the user where they'd like files saved (e.g., a local folder, Dropbox, etc.)

Once known, apply the aircraft's constraints throughout the planning process:
- **Runway requirements** — minimum length and surface type for the aircraft
- **Fuel type** — Avgas (100LL), Jet-A, mogas, etc. — must be available at or near the destination
- **Range** — plan comfortable legs with margin; suggest fuel stops for longer trips
- **Approach capability** — IFR-capable airports preferred for flexibility, but VFR-only is fine for fair-weather trips

## MCP Servers Available

This skill works best when the following MCP servers are connected. Check whether they're available before starting.

### 1. Euro AIP Airport Database (`euro_aip` / mcp.flyfun.aero)
An MCP server with European airport data from official AIPs. Tools:
- `search_airports` — free-text search with filters (runway length, country, etc.) and priority strategies (`cost_optimized`, etc.)
- `find_airports_near_route` — find airports along a route between two points
- `find_airports_near_location` — find airports near a city or landmark
- `get_airport_details` — full details for an ICAO code (frequencies, runways, fees, hours, etc.)
- `get_notification_for_airport` — NOTAMs and notifications, optionally filtered by day of week

### 2. Airfield Directory (`airfield.directory/mcp`)
Community-sourced airfield reviews. Important: **only use human-generated reviews**, not AI-generated ones. The MCP response should indicate the source — if it doesn't, mention this caveat to the pilot.

### If MCP servers are not connected
Fall back to web search for airport information, but note that the data may be less accurate or current than the AIP database. Suggest the pilot connect the MCPs for better results.

## Planning Workflow

### Step 1: Understand the Trip

Clarify these if not already clear from the conversation:
- **Departure base**
- **Dates or time of year** (affects weather, daylight, airport hours, seasonal closures)
- **Trip duration** (weekend vs. multi-day)
- **Region or direction of interest** (or "surprise me")
- **Number of passengers** (affects range with fuel)
- **Any specific interests** (wine, hiking, beaches, culture, skiing, etc.)

### Step 2: Discover Candidate Airports

Use the MCP tools (or web search as fallback) to find airports that meet the aircraft constraints. Consider:

- **Direct range**: For longer trips, plan fuel stops based on the aircraft's comfortable range.
- **Multiple airports per destination**: A city might have several nearby airfields. Compare them on cost, convenience, and GA-friendliness.
- **Seasonal factors**: Some small airfields have limited winter hours or close seasonally. Mountain airports may have weather restrictions.

When using `search_airports` or `find_airports_near_location`, apply the `cost_optimized` priority strategy by default unless the pilot asks for something different.

### Step 3: Evaluate Each Airport

For each candidate, build a profile covering:

**Aviation side:**
- Landing and handling fees (flag if expensive, e.g., >€50 landing + >€30/night parking)
- Fuel availability and approximate price
- Opening hours (especially important for weekend trips — some close Sunday afternoon)
- Customs/immigration if crossing borders (check requirements for the aircraft's registration)
- GA friendliness — is this an airport that welcomes small planes, or a commercial airport that tolerates them?
- Community reviews from airfield.directory (human-generated only)

**Destination side:**
- Distance from airport to town/activities (under 15 min taxi/drive is ideal)
- Transport options (rental car, taxi, walking distance?)
- Hotels — a couple of options at different price points
- Restaurants — local favorites, not just tourist traps
- Activities matching the pilot's interests
- General vibe — is this a place worth the flight?

### Step 4: Present Recommendations

Structure the output as a clear comparison. For each destination:

1. **The pitch** — one sentence on why this place is worth flying to
2. **Airport(s)** — ICAO code, name, key facts (runway, fees, fuel, hours)
3. **Getting there** — distance from base, approximate flight time, any route considerations
4. **On the ground** — transport, hotels, restaurants, activities
5. **Community reviews** — what other pilots say (human reviews only)
6. **Watch out for** — any gotchas (seasonal closures, PPR requirements, expensive handling, noise restrictions, etc.)

Rank destinations by overall appeal, factoring in the pilot's stated priorities.

### Step 5: Offer Next Steps

After presenting options, offer to:
- Deep-dive on a specific destination
- Check NOTAMs/notifications for a specific date
- Plan the route (fuel stops, alternates)
- Save the trip plan to a file (in the user's chosen location)
- Compare two destinations side by side

## Output Format

For trip plans saved to files, use spreadsheets (xlsx) saved to the location the user specified. Include sheets for:
- Trip overview (dates, route, distances)
- Airport comparison (fees, facilities, ratings)
- Accommodation options
- Activity suggestions

For conversational responses, keep it concise and scannable — the pilot is busy and wants to make a decision, not read an essay.

## Important Notes

- **Aircraft registration**: Some countries or airports have specific requirements based on aircraft registration (insurance, permits, radio license). Flag these when relevant.
- **GAR forms**: For UK flights, a GAR (General Aviation Report) is required.
- **Currency**: Use euros (€) for continental Europe, pounds (£) for UK, Swiss francs (CHF) for Switzerland. Don't convert unless asked.
- **Language**: Airport and destination names in the local language are fine, but describe things in English.
