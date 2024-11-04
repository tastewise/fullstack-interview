# Real-time Food Trend Mini-Dashboard

## Time Limit: 1 hour

### Overview

Create a simple dashboard that shows trending food ingredients and provides AI-powered insights. Focus on implementing core functionality rather than completeness.

### Requirements

This task is divided into three parts, each with its own requirements:
1. Create a simple Trend Dashboard with a list of trending ingredients.
    a. Each ingredient should have a popularity, growth rate and a category.
    b. Backend - Build the `GET /api/trends` - Returns a list of trending ingredients endpoint in your favorite backend framework.
    c. Frontend - Display the list of trending ingredients in a table or list.
2. Implement real-time updates for the trending ingredients.
    b. Backend - Create a WebSocket server that pushes random popularity updates every 10 seconds.
    c. Frontend - Display real-time updates for the trending ingredients in the respective table or list from step 1.
3. Implement an "Analyze" button that fetches AI insight for the selected ingredient.
    a. Backend - Build the `POST /api/trends/analyze` - Gets AI insight for a selected ingredient endpoint in your favorite backend framework.
    b. Frontend - Add an "Analyze" button to each ingredient row that fetches AI insight for the selected ingredient and displays it.

### Backend (Node.js)

Sample data structure (hardcode this array to save time):

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
