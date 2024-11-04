# Real-time Food Trend Mini-Dashboard

## Time Limit: 1 hour

### Overview

Create a simple dashboard that shows trending food ingredients and provides AI-powered insights. Focus on implementing core functionality rather than completeness.

### Requirements

### Backend (Node.js)

1. Create two main endpoints:
    - `GET /api/trends` - Returns a list of trending ingredients
    - `POST /api/trends/analyze` - Gets AI insight for a selected ingredient
2. Sample data structure (hardcode this array to save time):

```jsx
const trendData = [
  {
    ingredient: "matcha",
    popularity: 85,
    growthRate: 12.5,
    category: "beverages"
  },
  {
    ingredient: "kimchi",
    popularity: 92,
    growthRate: 15.8,
    category: "fermented"
  },
  // Add 3-4 more items
];

```

1. Basic WebSocket setup for real-time updates:

```jsx
// Simple WebSocket to push random popularity updates every 10 seconds
const WebSocket = require('ws');
const wss = new WebSocket.Server({ server });

wss.on('connection', (ws) => {
  const interval = setInterval(() => {
    const randomTrend = trendData[Math.floor(Math.random() * trendData.length)];
    randomTrend.popularity += Math.random() * 2 - 1; // Random fluctuation
    ws.send(JSON.stringify(randomTrend));
  }, 10000);

  ws.on('close', () => clearInterval(interval));
});

```

### Frontend (React)

Create a simple dashboard with:

1. A table/list showing trending ingredients
2. Real-time popularity updates
3. An "Analyze" button that fetches AI insight for the selected ingredient

Example component structure:
