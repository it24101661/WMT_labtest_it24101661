# WMT_labtest_it24101661
lab test for wmt
# WMT Lab Test – Item Manager App
### Student ID: it24101661

A full-stack MERN Item Manager application built for the WMT Lab Test. It allows users to add, view, edit, and delete items with details including Name, Category, Price, Description, Model Number, and Image URL.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, React Router v6, Axios, Vite |
| Backend | Node.js, Express.js |
| Database | MongoDB Atlas |
| Frontend Hosting | Vercel |
| Backend Hosting | Render |

---

## Features

- View all items on the Home page
- Add new items via the Add Item form
- Edit existing items
- Delete items
- Model Number field added as part of Task 02 functional enhancement

---

## Project Structure

```
WMT_LabTest_Project/
├── backend/
│   ├── controllers/
│   │   └── itemController.js
│   ├── models/
│   │   └── Item.js
│   ├── routes/
│   │   └── itemRoutes.js
│   ├── server.js
│   ├── .env
│   └── package.json
└── frontend/
    ├── src/
    │   ├── api/
    │   │   └── itemApi.js
    │   ├── components/
    │   │   ├── ItemCard.jsx
    │   │   ├── ItemForm.jsx
    │   │   └── Navbar.jsx
    │   ├── pages/
    │   │   ├── HomePage.jsx
    │   │   ├── AddItemPage.jsx
    │   │   └── EditItemPage.jsx
    │   └── App.jsx
    └── package.json
```

---

## Local Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/it24101661/WMT_labtest_it24101661.git
cd WMT_labtest_it24101661
```

### 2. Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file in the `backend` folder:

```
MONGO_URI=your_mongodb_atlas_connection_string
PORT=5000
```

Start the backend:

```bash
npm run dev
```

### 3. Setup Frontend

```bash
cd frontend
npm install
```

Create a `.env` file in the `frontend` folder:

```
VITE_API_URL=http://localhost:5000/api
```

Start the frontend:

```bash
npm run dev
```

The app will be running at `http://localhost:5173`

---

## Deployment

### Frontend – Vercel
- Platform: [Vercel](https://vercel.com)
- Root Directory: `frontend`
- Build Command: `npm run build`
- Output Directory: `dist`
- Environment Variable: `VITE_API_URL` = your Render backend URL

### Backend – Render
- Platform: [Render](https://render.com)
- Root Directory: `backend`
- Start Command: `node server.js`
- Environment Variables: `MONGO_URI`, `PORT`

### Database – MongoDB Atlas
- Platform: [MongoDB Atlas](https://cloud.mongodb.com)
- Cloud-hosted MongoDB cluster
- Connection string added to backend `.env` as `MONGO_URI`

---

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/items` | Get all items |
| GET | `/api/items/:id` | Get single item |
| POST | `/api/items` | Create new item |
| PUT | `/api/items/:id` | Update item |
| DELETE | `/api/items/:id` | Delete item |

---

## Task 02 – Functional Enhancement

Added a new **Model Number** field to the application:

- `backend/models/Item.js` — added `modelNumber` field to Mongoose schema
- `frontend/src/components/ItemForm.jsx` — added Model Number input to the form
- `frontend/src/components/ItemCard.jsx` — displays Model Number on the Home page card
