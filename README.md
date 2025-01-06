# Liquidbook Indexer

Indexer for the LiquidBook decentralized orderbook, built using Ponder. This indexer processes and stores orderbook events for efficient querying and data access.

## 📋 Overview

This indexer tracks all events from the LiquidBook smart contracts, making the data easily accessible for applications and analysis. Built with Ponder, it provides reliable and efficient blockchain data indexing.

## 🏗️ Architecture

The indexer processes the following events:
- Order placements
- Order matches
- Order data updates
- Current tick updates
- Tick data updates

## 🛠️ Technical Stack

- **Framework**: Ponder
- **Database**: PostgreSQL
- **Language**: TypeScript

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL
- pnpm/yarn/npm

### Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd liquidbook-indexer
```

2. Install dependencies:
```bash
pnpm install
```

3. Configure environment:
```bash
cp .env.example .env
```
Edit `.env` with your specific configuration

### Running the Indexer

1. Start the development server:
```bash
pnpm dev
```

2. For production:
```bash
pnpm build
pnpm start
```


## 📊 Queries

The indexer provides a GraphQL API for querying indexed data. Here are some example queries:

### Get All Ticks
Retrieves all tick data including buy/sell status, timestamp, and volume:

```graphql
query GetAllTicks {
  ticks {
    items {
      id
      is_buy
      tick
      timestamp
      volume
    }
  }
}
```

Response fields:
- `id`: Unique identifier for the tick
- `is_buy`: Boolean indicating if it's a buy order
- `tick`: The price tick value
- `timestamp`: When the tick was created/updated
- `volume`: Trading volume at this tick

## 📍 Deployed Instances

Currently, the development instance is accessible at:
- Development GraphQL Endpoint: [https://liquidbook.renakaagusta.dev/](https://liquidbook.renakaagusta.dev/)

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.
