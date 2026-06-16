# AquaSafe

AquaSafe is a map-based web app that helps people find safer water options during disasters.
Instead of only showing nearby taps or fountains, it also looks at disaster activity and infrastructure risk around the selected location.

## Why this project exists

During emergencies, "closest water point" is not always the safest choice. Flooding, power outages, and facility incidents can affect local supply quickly.

AquaSafe gives users a clearer picture by combining map data with risk context in one place.

## What it does

- Click anywhere on the map to get a water safety risk score.
- View disaster declarations affecting the selected area.
- See nearby water sources and community-reported safe water points.
- Report a safe water location from the map.
- Get route links to selected water points.

## Data sources

- [OpenFEMA](https://www.fema.gov/openfema-data-page/disaster-declarations-summaries-v2): disaster declarations
- [OpenStreetMap / Overpass](https://www.openstreetmap.org/): nearby water points
- Demo reservoir and facility datasets included in this project

## Tech stack

- Frontend: React, TypeScript, Vite, Leaflet, Tailwind CSS
- Backend: Express, TypeScript
- Storage: SQLite (for reports)
- Optional AI: summary/risk explanation if `OPENAI_API_KEY` is set

## Run locally

### Requirements

- Node.js 18+ (Node 20 recommended)

### Setup

```bash
npm install
cp .env.example .env
```

`OPENAI_API_KEY` is optional. The app works without it.

### Start development servers

```bash
npm run dev
```

- Client: `http://localhost:5173`
- API: `http://localhost:5001/api/health`

## Deploying

This project is configured to deploy on Vercel with:

- Static client build from `client/dist`
- Serverless API route via `api/[...all].ts`

If you fork this repo, make sure your Vercel project points at the repository root and uses the included `vercel.json`.

## Project status / next steps

Current version is a functional hackathon prototype. Planned improvements include:

- More accurate source-water mapping by region
- Production-grade infrastructure/facility datasets
- Improved risk model calibration and explanations

## Team

- Gensen Pawlicki
- Nigel Purvis
- Lucas Fujii
- Miki Ashaye
