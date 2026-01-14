# Hotel Booking 2 Landing Page - React, Vite, TailwindCSS Fundamental Frontend Project

A modern, responsive hotel booking frontend website built with React, Vite, TailwindCSS. This project demonstrates core React concepts (components, context API, hooks), advanced UI/UX with custom components, a mobile-friendly layout, and integration with third-party React libraries. It is designed both as a learning resource and a practical template for static hotel or accommodation websites.

- **Live Demo:** [https://hotel-booking-arnob.netlify.app](https://hotel-booking-arnob.netlify.app)

<img width="1200" alt="Screenshot 2024-09-13 at 00 01 03" src="https://github.com/user-attachments/assets/51070abc-f3ae-47ef-8bc1-e17151f075da"> ![Screenshot 2024-09-13 at 00 08 31](https://github.com/user-attachments/assets/5b984db0-c8c0-4a9a-bc25-543d30586225) <img width="1200" alt="Screenshot 2024-09-13 at 00 03 29" src="https://github.com/user-attachments/assets/4e1a4f30-ab6a-492a-8607-68963542f151"> ![Screenshot 2024-09-13 at 00 08 53](https://github.com/user-attachments/assets/edbabe77-1879-477d-8711-30bf245ff5b7)

## Table of Contents

- [Project Summary](#project-summary)
- [Features](#features)
- [Tech Stack & Keywords](#tech-stack--keywords)
- [Project Structure](#project-structure)
- [Components Overview](#components-overview)
- [Pages & Routing](#pages--routing)
- [Functionality Walkthrough](#functionality-walkthrough)
- [How to Run / Usage Instructions](#how-to-run--usage-instructions)
- [Learning & Teaching Notes](#learning--teaching-notes)
- [Code Examples](#code-examples)
- [Conclusion](#conclusion)

---

## Features

- 🏨 **Responsive hotel booking frontend** — fully mobile-ready
- ⚡ **Vite-powered** for fast development and hot-reloading
- 🎨 **TailwindCSS styling** for utility-first, customizable design
- 🔄 **React Context API** for state management (room filtering, selection, etc.)
- 🧩 **Reusable React components** like Room Cards, Booking Form, Dropdowns
- 📅 **React Date Picker** for check-in/check-out selection
- 🚀 **Swiper Slider** for hero images
- 🔗 **React Router** for SPA navigation and room details
- 🌀 **Spinner** loading indicator for data fetch simulation
- ⬆️ **Scroll to Top** on route changes
- 🛠️ **Example hotel data**, facilities, and images
- ☑️ **Hotel rules** and details on each room page

---

## Tech Stack & Keywords

- **React**, **Vite**, **React Router DOM**, **TailwindCSS**, **PostCSS**, **Autoprefixer**
- **Context API**, **Hooks**, **Reusable Components**
- **React Date Picker**, **Swiper**, **Spinners**
- **Responsive Design**, **SVG/Images**, **Single Page Application (SPA)**
- **Frontend Only** (No backend integration)

---

## Project Structure

```
HotelBooking--TailwindCSS-Fundamental-Project-3/
├── public/
│   └── favicon, static assets...
├── src/
│   ├── assets/           # Images & SVGs
│   ├── components/       # UI Components (Header, Footer, Rooms, etc.)
│   ├── constants/        # Static data (e.g., hotel rules)
│   ├── context/          # React Context (RoomContext.js)
│   ├── pages/            # Page-level components (Home, RoomDetails)
│   ├── utils/            # Utility functions (ScrollToTop)
│   ├── App.jsx           # Main app component, routing
│   ├── main.jsx          # App entry point
│   └── index.css         # TailwindCSS directives
├── index.html
├── package.json
├── tailwind.config.js
├── postcss.config.js
└── README.md
```

---

## Components Overview

- **Header:** Navigation bar with logo and links
- **Footer:** Footer with copyright
- **HeroSlider:** Swiper slider with hotel images (homepage)
- **BookForm:** Main booking form for guests (date pickers, dropdowns)
- **Rooms:** List/grid of available rooms (with spinner effect)
- **Room:** Card for an individual room
- **RoomDetails:** Page for detailed info about a single room (facilities, price, rules)
- **AdultsDropdown, KidsDropdown:** Select number of guests
- **CheckIn, CheckOut:** Date pickers for reservation
- **PageNotFound:** 404 fallback
- **ScrollToTop:** Utility component to scroll on navigation

---

## Pages & Routing

- `/` **Home:** Hero slider, booking form, room listing
- `/room/:id` **Room Details:** Details for a selected room (from Rooms grid)
- `*` **PageNotFound:** Handles all unmatched routes

Routing is implemented via `react-router-dom` in `src/App.jsx`.

---

## Functionality Walkthrough

### Homepage (`/`)
- **HeroSlider:** Engaging slider with hotel images.
- **BookForm:** Users select check-in, check-out dates, number of adults/kids. (State managed by context)
- **Rooms Grid:** Dynamically lists all rooms pulled from static data. Clicking a room navigates to its details.

### Room Details (`/room/:id`)
- Fetches room info by ID.
- Shows:
  - **Room images, name, description**
  - **Facilities grid** (icons, features)
  - **Reservation block** (right column) — allows user to select dates/guests and see price.
  - **Hotel Rules** (list with icons)
- All state (selected room, guest counts, dates) handled using React context/hooks.

### Spinner Loading
- When room data is "loading", a full-screen spinner overlay is shown using `spinners-react`.

### Responsive/Mobile
- Layout adapts for different screen sizes using Tailwind's utility classes.
- Mobile navigation, grid stacking, and component sizes adjust accordingly.

---

## How to Run / Usage Instructions

### 1. **Clone the Repository**
```bash
git clone https://github.com/arnobt78/HotelBooking--TailwindCSS-Fundamental-Project-3.git
cd HotelBooking--TailwindCSS-Fundamental-Project-3
```

---

### 2. **Install NodeJS**
- Download and install from [nodejs.org](https://nodejs.org/en/)

---

### 3. **Install Project Dependencies**
```bash
npm install
```

---

### 4. **(Optional) Create your own Vite + TailwindCSS React Project**

```bash
npm create vite@latest my-project -- --template react
cd my-project
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
Edit `tailwind.config.js`:
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: { extend: {} },
  plugins: [],
}
```
Add the following to `src/index.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
---

### 5. **Run the Project Locally**
```bash
npm run dev
```
- Open your browser at: [http://localhost:5173/](http://localhost:5173/)

---

### 6. **Project Dependencies Used**
```bash
npm create vite
npm add -D react-icons
npm add -D react-router-dom
npm add -D react-datepicker
npm add -D @headlessui/react
npm add -D spinners-react
npm add -D swiper
npm add -D vite-plugin-svgr
npm add -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
---

## Learning & Teaching Notes

- **React Context API** is used to manage state globally (room filters, room selection, etc.).
- **Hooks** (`useState`, `useContext`, `useParams`) are leveraged throughout to drive interactivity.
- **TailwindCSS** enables quick UI development with utility classes; no traditional CSS files are needed.
- **Component Reusability:** All UI blocks (dropdowns, forms, cards) are reusable and composable.
- **Router Design:** Routing is declarative and supports dynamic parameters (`/room/:id`).
- **Third-Party Libraries:** Enhance user experience (date picker, spinner, slider, icons).
- **Deployment:** Easily deployable to Netlify or Vercel as a static site.

---

## Code Examples

### App Routing (`src/App.jsx`)
```jsx
import { BrowserRouter, Route, Routes } from 'react-router-dom';
import { Footer, Header, PageNotFound } from './components';
import { Home, RoomDetails } from './pages';

const App = () => (
  <main>
    <BrowserRouter>
      <Header />
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/room/:id' element={<RoomDetails />} />
        <Route path='*' element={<PageNotFound />} />
      </Routes>
      <Footer />
    </BrowserRouter>
  </main>
);
export default App;
```
---

### Room Listing (`src/components/Rooms.jsx`)
```jsx
import { useRoomContext } from '../context/RoomContext';
import { SpinnerDotted } from 'spinners-react';
import { Room } from '.';

const Rooms = () => {
  const { rooms, loading } = useRoomContext();
  return (
    <section className='py-24'>
      {loading && (
        <div className='h-screen w-full fixed bottom-0 top-0 bg-black/80 z-50 grid place-items-center'>
          <SpinnerDotted />
        </div>
      )}
      <div className='container mx-auto lg:px-0'>
        <div className='text-center'>
          <p className='font-tertiary uppercase text-[15px] tracking-[6px]'>Hotel & Spa Adina</p>
          <h2 className='font-primary text-[45px] mb-6'>Room & Suites</h2>
        </div>
        <div className='grid grid-cols-1 max-w-sm mx-auto gap-[30px] lg:grid-cols-3 lg:max-w-none lg:mx-0'>
          {rooms.map(room => <Room key={room.id} room={room} />)}
        </div>
      </div>
    </section>
  );
};
export default Rooms;
```
---

### Booking Form Snippet (`src/components/BookForm.jsx`)
```jsx
import { CheckIn, CheckOut, AdultsDropdown, KidsDropdown } from '.';

const BookForm = () => (
  <form>
    <CheckIn />
    <CheckOut />
    <AdultsDropdown />
    <KidsDropdown />
    <button type="submit">Book Now</button>
  </form>
);
export default BookForm;
```
---

## Conclusion

This project is a comprehensive example of modern frontend development, combining the power of React, TailwindCSS, and Vite for rapid, scalable, and beautiful web applications. It is ideal for learning, teaching, or as a starter template for your own hotel or resort web apps.

---

## Happy Coding! 🚀

Thank you for using and exploring this project!

---
