# SpendSmart: Personal Expense Tracker

A fully functional personal finance management web application built with React.js and JSON-Server. Track your income and expenses, categorize transactions, view monthly summaries, set budgets, and improve your financial habits.

## 🎥 Project Overview

SpendSmart is a personal expense tracking app that helps users record transactions, manage budgets, and analyze financial habits using charts and real-time data.

**Project Report**: https://drive.google.com/file/d/1krug-Lorgqm_shrVRuiqR6Dkb4iC_Y41/view?usp=drive_link  

**Project Demonstration**: https://drive.google.com/file/d/1oJrk14m-52bFq0xS_td7K4VMjc7rFLHD/view?usp=drive_link 

**Code Demonstration**: https://drive.google.com/file/d/12aCrpLtUA2EAEfJ_Zwy_hLopRse3n6N2/view?usp=drive_link

## 🚀 Features

- **Authentication**: Simple login/signup system
- **Dashboard**: Monthly overview with charts and analytics
- **Transactions**: Full CRUD operations (Create, Read, Update, Delete)
- **Budget Manager**: Set and track monthly budgets
- **Monthly Summary**: Detailed analytics with charts
- **Categories**: View category-wise spending breakdown
- **Responsive Design**: Mobile-first design with Tailwind CSS

## 📋 Prerequisites

- Node.js (v16 or higher)
- npm (v7 or higher)

## 🛠️ Installation

1. **Clone the repository** (or navigate to the project directory):
   ```bash
   cd spendsmart
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

## 🏃 Running the Application

### Start JSON-Server (Backend)

Open a terminal and run:
```bash
npm run server
```

This will start the JSON-Server on `http://localhost:3001`

### Start React Development Server

Open another terminal and run:
```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the port shown in the terminal)

## 📁 Project Structure

```
spendsmart/
├── src/
│   ├── components/          # Reusable UI components
│   │   ├── Layout.jsx
│   │   ├── Navigation.jsx
│   │   ├── ErrorBoundary.jsx
│   │   └── DataInitializer.jsx  # Initializes data from external APIs
│   ├── pages/              # Page components
│   │   ├── Login.jsx
│   │   ├── Signup.jsx
│   │   ├── Dashboard.jsx
│   │   ├── Transactions.jsx
│   │   ├── AddTransaction.jsx
│   │   ├── EditTransaction.jsx
│   │   ├── Budget.jsx
│   │   ├── MonthlySummary.jsx
│   │   └── Categories.jsx
│   ├── services/           # API service layer
│   │   ├── api.js          # JSON-Server API calls
│   │   └── dataFetcher.js  # External API data fetching
│   ├── utils/              # Utility functions
│   │   └── dataInitializer.js  # Syncs API data with JSON-Server
│   ├── App.jsx             # Main app component with routing
│   ├── main.jsx            # Entry point
│   └── index.css           # Global styles with Tailwind
├── db.json                 # JSON-Server database (stores API-fetched data)
├── package.json
└── README.md
```

## 🎯 Tech Stack

- **Frontend**: React.js (Vite)
- **Routing**: React Router DOM
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios
- **Backend**: JSON-Server
- **External APIs**: Currency Exchange API, JSONPlaceholder API
- **Charts**: Recharts
- **Icons**: React Icons
- **Notifications**: React Toastify

## 🔄 API Integration & Data Flow

This project meets the requirement of **fetching data from external APIs** and storing it in `db.json` for JSON-Server to manage:

1. **Data Fetching**: The application fetches sample data from external APIs:
   - Currency exchange rates from `exchangerate-api.com`
   - Sample transaction data from `jsonplaceholder.typicode.com`
   - Financial categories and structures

2. **Data Storage**: Fetched data is processed and stored in `db.json`

3. **JSON-Server Management**: JSON-Server manages all CRUD operations on the data stored in `db.json`

### Implementation Details

- **Data Fetcher Service** (`src/services/dataFetcher.js`): Handles fetching data from external APIs
- **Data Initializer** (`src/utils/dataInitializer.js`): Syncs API data with JSON-Server
- **DataInitializer Component**: Automatically initializes data when user logs in

The data flow: **External APIs → Process & Transform → db.json → JSON-Server → React App**

## 🔑 Demo Credentials

- **Email**: demo@spendsmart.com
- **Password**: demo123

## 📝 API Integration

### External APIs Used

1. **Currency Exchange API** (`exchangerate-api.com`)
   - Fetches real-time currency exchange rates
   - Used for multi-currency support

2. **JSONPlaceholder API** (`jsonplaceholder.typicode.com`)
   - Fetches sample data structure
   - Transformed into transaction format

### JSON-Server Endpoints

The JSON-Server provides the following endpoints for CRUD operations:

- `GET /users` - Get all users
- `POST /users` - Create a new user
- `GET /transactions?userId={id}` - Get user transactions
- `POST /transactions` - Create a transaction
- `PUT /transactions/:id` - Update a transaction
- `DELETE /transactions/:id` - Delete a transaction
- `GET /budgets?userId={id}` - Get user budgets
- `POST /budgets` - Create a budget
- `PUT /budgets/:id` - Update a budget
- `DELETE /budgets/:id` - Delete a budget
- `GET /categories` - Get all categories

## 🎨 Features in Detail

### Dashboard
- Monthly income and expense totals
- Budget progress tracking
- Category-wise expense chart
- Recent transactions list
- Quick action buttons

### Transactions
- Add new income/expense transactions
- Edit existing transactions
- Delete transactions
- Filter by type, category, and search
- View transaction summary

### Budget Manager
- Set monthly budgets
- Set category-specific budgets
- Track budget progress
- Visual progress indicators
- Budget exceeded warnings

### Monthly Summary
- Income vs expense comparison
- Category distribution charts
- 6-month trend analysis
- Savings calculation
- Detailed category breakdown

### Categories
- View all categories
- Category-wise spending statistics
- Period-based filtering (month/year/all time)
- Visual spending breakdown

## 🚀 Build for Production

```bash
npm run build
```

The production build will be in the `dist/` directory.

## 📄 License

This project is open source and available for educational purposes.

## 👨‍💻 Development

### Adding New Features

1. Create components in `src/components/`
2. Add pages in `src/pages/`
3. Update API services in `src/services/api.js`
4. Add routes in `src/App.jsx`

### Database Schema

The `db.json` file contains the following data models:

- **users**: User accounts
- **transactions**: Income and expense records
- **budgets**: Monthly budget settings
- **categories**: Available transaction categories

## 🤝 Contributing

- K Karthikeya Sharma & N Vivek 

## 📞 Support

For issues or questions, please open an issue on the repository.

---

Built with ❤️ using React.js and JSON-Server

