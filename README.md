# AI and Flying

A curated list of apps, tools, and projects — built by pilots, for pilots — that leverage AI or make aviation data more accessible for flight planning.

## Why This List?

Flight planning means synthesizing a lot of data: weather models, NOTAMs, airspace rules, customs forms, airport information across countries. AI — both as a coding assistant and as a runtime tool — can help process, prioritize, and present this information in ways that save pilots real time.

One big takeaway from early experiments: **data is everything**. The more structured aviation data available, the more useful AI tools become. This repo aims to collect and share what's out there so pilots can find what's useful and builders can learn from each other.

Contributions welcome — see [Contributing](#contributing) below.

## Contents

- [Weather](#weather)
- [Flight Planning](#flight-planning)
- [Airport & Airfield Data](#airport--airfield-data)
- [NOTAMs](#notams)
- [Forms & Customs](#forms--customs)
- [Aviation Data for AI/LLMs](#aviation-data-for-aillms)
- [European GA Community & Forums](#european-ga-community--forums)
- [Contributing](#contributing)

---

## Weather

### [FlyFun Weather](https://github.com/roznet/flyfun-weather) — Multi-Model Aviation Weather Analysis
`open-source` `free` `europe` `us` `released`

A medium-range weather assessment tool for cross-country GA flights. Full-featured for Europe with 6 NWP models (GFS, ECMWF, DWD ICON, UKMO, Meteo-France) and side-by-side comparisons with aviation-specific hazard assessments. Partial planning features also available for the US.

- ~40 derived metrics (CAPE, icing zones, turbulence, convective potential, wind shear)
- 13 route advisories with GREEN/AMBER/RED hazard ratings
- Interactive cross-section visualization and Skew-T soundings
- LLM-powered weather synopsis (Claude or ChatGPT)
- **Stack:** Python (FastAPI) + TypeScript frontend
- **Repo:** https://github.com/roznet/flyfun-weather
- **Live:** [flyfun.aero](https://flyfun.aero)

### [PlaneWx](https://www.planewx.ai) — AI Aviation Weather Intelligence
`commercial` `freemium` `us` `released`

An AI-powered weather platform for US general aviation pilots. Uses multiple weather models (HRRR, GFS, ECMWF) and NWS forecaster data to produce a personalized "WX Score" against your own minimums.

- WX Score (0–100%) personalized to your aircraft and personal minimums
- Multi-model analysis with Synoptic Intelligence
- 14-day advance forecasting with improving accuracy as flight date approaches
- PAVE risk assessment framework
- Convective Watch thunderstorm scoring
- **Free tier:** 2 active flights, 15 weekly briefings. **Pro:** $14.99/mo.

### [CloudPath](https://cloudpath.app) — GRAMET Weather Visualization
`freemium` `global` `released`

A web-based tool that generates GRAMET (graphical meteorological) cross-section forecasts along a planned route. Clean interface for visualizing weather conditions at altitude along your flight path.

- Interactive route planning with waypoints
- Visualization layers: clouds, wind, temperature, icing, turbulence, precipitation
- Customizable flight parameters (duration, airspeed, cruise altitude)
- PDF export and saved favorite routes
- **Free tier:** 48-hour forecasts. Premium ($4.99/mo) extends beyond 2 days.

---

## Flight Planning

### [Autorouter](https://autorouter.aero) — European IFR Flight Planning & Filing
`free` `europe` `released`

The gold standard of free flight planning for Europe. Widely used and trusted by GA pilots, Autorouter provides automated route planning through European airspace with full CFMU/IFPS validation and one-click flight plan filing.

- Automated IFR route generation with CFMU/IFPS compliance
- Flight plan filing directly to Eurocontrol
- Weather overlays and NOTAM integration
- GRAMET cross-section charts
- Route optimization for airspace restrictions

### [FlyFun Maps](https://maps.flyfun.aero) — Interactive European Airport Explorer
`open-source` `free` `europe` `released`

An interactive maps view of the European AIP data from [euro_aip](https://github.com/roznet/rzflight/tree/main/euro_aip). Browse, filter, and explore GA airports across Europe with detailed airport information, runway data, and route-based search.

- Interactive Leaflet map with advanced filtering
- Route-based airport search
- Detailed airport info from official AIP sources
- **Stack:** Python (FastAPI) + TypeScript frontend
- **Repo:** https://github.com/roznet/flyfun-apps

### [FlightOps Guru](https://flightops.guru) — AI Flight Planning Assistant
`free` `global` `beta`

An AI-powered flight planning assistant that analyzes weather and identifies risks along a planned route. Generates CAA CPL-standard briefings and recommends optimal weather windows up to 14 days ahead.

- Window recommendation for scheduling flights
- Evaluates cloud bases, freezing levels, wind patterns, crosswind components, density altitude, airspace constraints
- Integrates meteorological data, NOTAMs, aircraft performance data

---

## Airport & Airfield Data

### [Airfield Directory](https://github.com/airfield-directory) — Community Airport Database
`open-source` `free` `global` `released`

A community-driven aviation database with pilot comments, weather data (METAR/TAF), runway info, fuel prices, and landing fees for 13,500+ airfields worldwide.

- Pilot comments automatically translated into 6 languages
- Interactive map browsing
- Telegram bot integration and embeddable widgets
- Pilot comments licensed under Creative Commons BY-SA 4.0
- **Repo:** https://github.com/airfield-directory

### [OurAirports](https://ourairports.com) — Global Airport Database
`free` `open-source` `global` `released`

A community-driven, open-data database of 85,000+ airports worldwide. Widely used as a foundational data source by many aviation apps and projects. Data is freely downloadable as CSV files.

- Global coverage with community contributions
- Downloadable datasets (CSV)
- Airport search, map view, and nearby airport lookup
- **Live:** [ourairports.com](https://ourairports.com)
- **Data:** [ourairports.com/data](https://ourairports.com/data/)

### [euro_aip](https://github.com/roznet/rzflight/tree/main/euro_aip) — European AIP Data Library & Database
`open-source` `free` `europe` `released`

A Python library (`pip install euro-aip`) and SQLite database that ingests freely available European Aeronautical Information Publications. Covers airports, runways, procedures, and AIP entries across multiple countries.

- Fluent, chainable query API (LINQ-style)
- Parsers for multiple European AIP sources (France, UK, Norway, and more)
- Database downloadable from [flyfun.aero/data/airports.db](https://flyfun.aero/data/airports.db)
- **Stack:** Python (SQLAlchemy, FastAPI, Pandas)
- **Gap:** Several countries aren't automatically updated because their AIP data isn't easily parsable. Contributions welcome.
- **Repo:** https://github.com/roznet/rzflight/tree/main/euro_aip

### [OpenAIP](https://www.openaip.net) — Open Aviation Data
`free` `global` `released`

A crowd-sourced aviation database providing airspace, airport, and navaid data worldwide. Widely used as a data source by flight planning apps and EFBs. Offers downloadable datasets and an API for developers.

- Airspace boundaries, airports, navaids, hotspots
- Downloadable data in multiple formats
- API access for developers
- Used as a data backend by many aviation apps and devices
- **Live:** [openaip.net](https://www.openaip.net)

### [OpenNav](https://opennav.com) — Aeronautical Reference Database
`free` `global` `released`

A searchable aeronautical database for quick lookups of airports, navaids, and waypoints by ICAO, IATA, or FAA codes.

- Airport, navaid, and waypoint search
- Lookup by ICAO, IATA, FAA code, name, or city
- **Live:** [opennav.com](https://opennav.com)

---

## NOTAMs

### [FlyFun Brief](https://github.com/roznet/flyfun-apps) — Smart NOTAM Prioritization (iOS)
`open-source` `free` `global` `beta`

An iOS app that intelligently prioritizes NOTAMs for cross-country flights. Tools like ForeFlight can produce pages of NOTAMs for a long flight — this app helps pilots focus on the ones that actually matter.

- AI-assisted NOTAM relevance scoring and prioritization
- Designed for processing multi-page NOTAM briefings from long cross-country flights
- **Stack:** SwiftUI (iOS/macOS)
- **Key gap:** No official NOTAM API source — currently parses ForeFlight briefing packs.
- **Repo:** https://github.com/roznet/flyfun-apps

---

## Forms & Customs

### [FlyFun Forms](https://github.com/roznet/flyfun-forms) — Customs & Immigration Form Generator
`open-source` `free` `europe` `released`

An iOS app that pre-fills official customs, immigration, and FBO forms with flight data, crew, and passenger info. Built for pilots who frequently fly internationally in Europe (especially France/UK/Switzerland).

- Supports 50+ European airports (French customs, UK GAR, Swiss immigration, MyHandling FBO)
- Template-based — new forms added by dropping template files, no code changes needed
- Passenger list management and document collection for upload
- No PII stored on device
- **Stack:** SwiftUI (iOS) + Python (FastAPI) backend
- **Repo:** https://github.com/roznet/flyfun-forms
- **App Store:** [FlyFunForms](https://apps.apple.com/us/app/flyfunforms/id6760511907)

---

## Aviation Data for AI/LLMs

### [Airfield Directory MCP](https://airfield.directory/pages/faq#mcp-server) — Global Airfield Data for LLMs
`free` `global` `released`

A public, read-only remote MCP server at `https://airfield.directory/mcp` that exposes airfield data, PIREPs, weather, landing fees, and fuel prices to AI assistants. No authentication required.

- Works with Claude (web, Desktop, Code), ChatGPT, and Gemini CLI
- Queries airfield information, pilot reports, weather, fees
- Public endpoint — no sign-up needed

### [FlyFun MCP Server](https://github.com/roznet/flyfun-apps) — European Aviation Data for LLMs
`open-source` `free` `europe` `released`

An MCP (Model Context Protocol) server that exposes euro_aip airport, route, and airspace rules data to LLMs like Claude. Lets AI assistants answer questions about European airports, plan routes, and check rules — all backed by real AIP data.

- Airport lookups, nearest-airport search, route planning tools
- GA-friendliness scoring and persona-based rankings
- Also includes a LangGraph-based aviation chatbot agent
- **Repo:** https://github.com/roznet/flyfun-apps
- **Stack:** Python (FastMCP, LangGraph)

### [GA Trip Planner Skill](.claude/skills/ga-trip-planner/SKILL.md) — Claude Code Skill for Flight Planning
`open-source` `free` `europe` `released`

A Claude Code skill included in this repo that turns Claude into a GA trip planner. Uses the two MCP servers above (FlyFun MCP + Airfield Directory MCP) to search airports, compare fees, check facilities, and suggest destinations — then helps plan the full trip including ground transport, hotels, and activities.

- Asks for your aircraft type, home base, and preferences
- Discovers and evaluates candidate airports using real AIP data and community reviews
- Compares destinations on cost, convenience, and GA-friendliness
- Produces trip plans with airport comparison, accommodation, and activity suggestions
- **Requires:** Claude Code with the FlyFun MCP and Airfield Directory MCP servers connected

---

## European GA Community & Forums

### [EuroGA](https://euroga.org) — European General Aviation Forum
`free` `europe`

The main online forum for European GA pilots. Active discussions on cross-border flying, airport reviews, regulations, aircraft ownership, and trip reports. An invaluable resource for anyone flying GA in Europe — the collective knowledge on country-specific procedures, customs, and airport quirks is hard to find anywhere else.

### [PPLIR](https://pplir.org) — Instrument Pilots Community
`membership` `europe`

PPLIR (Private Pilot Licence Instrument Rating) is a community and advocacy group for instrument-rated GA pilots in Europe. Focused on promoting and supporting IFR flying for private pilots, with resources on training, regulation, and proficiency. Runs events, seminars, and provides guidance on obtaining and maintaining an instrument rating under EASA.

---

## Contributing

If you know of a tool that helps pilots with flight planning — free, open-source, or commercial — please open an issue or submit a PR to add it. Include:

- **Name and link** (website and/or repo)
- **What it does** (one paragraph)
- **Tags:** `open-source` / `free` / `freemium` / `commercial` and `global` / `europe` / `us` and `released` / `beta`
- **Key features** (bullet list)
