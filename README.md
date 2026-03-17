 Visit Oman – Smart Travel Planner

A frontend-only tourism discovery and itinerary generation platform
built using Next.js.

The platform allows users to discover destinations across Oman
and generate a realistic multi-day travel itinerary entirely in the browser.



 Features

Discover Oman destinations
Filter by region, category and season
Save favorite destinations
Generate intelligent itineraries
Map-based route visualization
Budget estimation
Arabic and English support



Architecture

The application uses a hybrid rendering model:

SSR (Server Side Rendering)
Used for marketing pages and destination discovery.

CSR (Client Side Rendering)
Used for itinerary planning and interactive map rendering.



State Management

User preferences, saved destinations and generated itineraries
are stored in LocalStorage and synchronized through a global state store.

Itinerary Planning Algorithm

The itinerary generator uses a deterministic multi-objective scoring model.

score(i) =
w_interest × interest_match
+ w_season × season_fit
- w_crowd × normalized_crowd
- w_cost × normalized_cost
- w_detour × route_detour
+ w_diversity × category_diversity

Weights:

interest 0.30
season 0.20
crowd 0.15
cost 0.15
detour 0.10
diversity 0.10

Route Optimization

A deterministic 2-opt local search optimization is applied
to reduce total route distance for each day.



Distance Calculation

Distances between destinations are computed locally
using the Haversine formula.



Cost Estimation

Fuel = total_km / 12 × fuel_price
Food = 6 OMR × days
Hotel depends on budget tier.


Running the Project

npm install

npm run dev


