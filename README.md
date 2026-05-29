
# ShelfScout

> Crowdsourced store navigation for warehouse stores, such as Costco

Live demo: [shelf-scout-nu.vercel.app](https://shelf-scout-nu.vercel.app)

---

## What is ShelfScout?

ShelfScout is a full-stack web application that helps users locate items in warehouse stores like Costco, build grocery lists, and navigate an optimized route through the store. Item locations are crowdsourced — users confirm and update locations in real time, keeping the data accurate even as stores rearrange.

---

## Current Status

**In active development.** Core infrastructure is complete. Map and routing features are in progress.

### Done
- Next.js + TypeScript project deployed on Vercel
- Relational PostgreSQL database schema (Supabase) with normalized tables for categories, zones, shelves, and items
- 25 store zones modeled from real store data
- Foreign key relationships connecting items to physical shelf locations

### In Progress
- Interactive SVG store map with clickable zones
- Item search with zone highlighting
- Grocery list input
- Nearest-neighbor routing algorithm for optimized in-store navigation

### Planned
- Crowdsourced item submission and confirmation system
- User authentication
- Real-time updates when items move
- PWA support for mobile installation
- React Native mobile app

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 16, React, TypeScript |
| Styling | Tailwind CSS |
| Database | PostgreSQL via Supabase |
| Deployment | Vercel |
| Version Control | Git / GitHub |

---

## Data Model

ShelfScout uses a hierarchical tree structure to model the store:
Category (merchandise type)
└── Zone (physical area of the store)
└── Shelf (specific unit or display)
└── Item (individual product)

---

## Routing Algorithm

Grocery list routing uses a nearest-neighbor approximation of the Travelling Salesman Problem:

1. Start at the store entrance
2. Find the closest unvisited item on the list
3. Move to that item, repeat
4. End at checkout

For a typical grocery list of 10-20 items this produces a near-optimal route in constant time.

---
