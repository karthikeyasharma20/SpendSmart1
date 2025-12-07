# API Integration Documentation

## Overview

This project meets the requirement of **fetching data from external APIs** and storing it in `db.json` for JSON-Server to manage and operate on.

## Data Flow Architecture

```
External APIs → Data Fetcher → Transform Data → db.json → JSON-Server → React App
```

## External APIs Used

### 1. Currency Exchange API
- **URL**: `https://api.exchangerate-api.com/v4/latest/USD`
- **Purpose**: Fetches real-time currency exchange rates
- **Implementation**: `src/services/dataFetcher.js` → `fetchCurrencyRates()`
- **Fallback**: Returns default rates if API fails

### 2. JSONPlaceholder API
- **URL**: `https://jsonplaceholder.typicode.com/posts`
- **Purpose**: Fetches sample data structure
- **Implementation**: `src/services/dataFetcher.js` → `fetchSampleTransactions()`
- **Transformation**: Converts API response into transaction format
- **Fallback**: Generates sample transactions if API fails

## Implementation Files

### 1. `src/services/dataFetcher.js`
Contains functions to fetch data from external APIs:
- `fetchCurrencyRates()` - Fetches currency exchange rates
- `fetchSampleCategories()` - Fetches/returns category data
- `fetchSampleTransactions()` - Fetches and transforms transaction data
- `initializeDataFromAPI()` - Main function to fetch all data

### 2. `src/utils/dataInitializer.js`
Handles syncing API data with JSON-Server:
- `initializeDatabase()` - Prepares data for db.json
- `syncDataWithJSONServer()` - Syncs fetched data with JSON-Server

### 3. `src/components/DataInitializer.jsx`
React component that automatically initializes data when user logs in:
- Runs silently in the background
- Fetches data from external APIs
- Ensures data is available in db.json for JSON-Server

## How It Works

1. **User Login**: When a user logs in, `DataInitializer` component mounts
2. **API Fetching**: Component calls `syncDataWithJSONServer()` which:
   - Fetches data from external APIs using `dataFetcher.js`
   - Transforms the data into the required format
   - Prepares it for storage in `db.json`
3. **Data Storage**: Data is stored in `db.json` file
4. **JSON-Server Management**: JSON-Server automatically manages the data in `db.json`
5. **CRUD Operations**: All CRUD operations are performed via JSON-Server endpoints

## Verification

To verify API integration is working:

1. Open browser console (F12)
2. Log in to the application
3. Look for console messages:
   - "Fetching data from external APIs..."
   - "Data fetched successfully"
   - "Data initialized from external APIs"

## Error Handling

- All API calls have fallback mechanisms
- If external APIs fail, the application generates sample data
- Application continues to function even if APIs are unavailable
- Errors are logged to console for debugging

## Requirements Compliance

✅ **Fetches data from external APIs** - Implemented via `dataFetcher.js`
✅ **Stores data in db.json** - Data is stored in `db.json` file
✅ **JSON-Server manages data** - All CRUD operations go through JSON-Server
✅ **Full CRUD operations** - Create, Read, Update, Delete all functional

## Technical Details

- **API Client**: Axios (already in dependencies)
- **Data Transformation**: Custom functions transform API responses
- **Automatic Initialization**: Data is fetched automatically on user login
- **Non-blocking**: API fetching doesn't block UI rendering
- **Error Resilient**: Application works even if APIs fail

