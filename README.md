# 🎬 Movix - Movie & TV Show Discovery Platform

[![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-4.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-1.9-764ABC?style=for-the-badge&logo=redux&logoColor=white)](https://redux-toolkit.js.org/)
[![Sass](https://img.shields.io/badge/Sass-1.57-CC6699?style=for-the-badge&logo=sass&logoColor=white)](https://sass-lang.com/)
[![TMDB API](https://img.shields.io/badge/TMDB_API-v3-01D277?style=for-the-badge&logo=themoviedatabase&logoColor=white)](https://www.themoviedb.org/)

**Movix** is a modern, responsive entertainment discovery web application built with **React 18**, **Vite**, and **Redux Toolkit**, powered by **The Movie Database (TMDB) API**. It provides a cinematic browsing experience allowing users to explore trending movies and TV shows, watch trailers, filter by genres and ratings, and search across thousands of titles with infinite scrolling.

---

## ✨ Features

- **🎯 Dynamic Hero Banner**: Highlights upcoming movies with randomized dynamic backdrop wallpapers and an instant search bar.
- **🔥 Trending, Popular & Top Rated Feeds**: Interactive horizontal carousels with smooth tab switching (*Day/Week* and *Movies/TV Shows*).
- **🔎 Multi-Search with Infinite Scroll**: Fast, multi-entity search querying movies and TV series simultaneously with automatic infinite scroll pagination.
- **🧭 Advanced Explore Page**: Browse catalogs by media type with multi-select genre filtering and custom sorting (*Popularity, Rating, Release Date, Title*).
- **🎥 Rich Media Details**:
  - High-resolution dynamic backdrops, posters, taglines, and plot overviews.
  - Interactive circular rating indicators with dynamic color codes (green, orange, red).
  - **YouTube Trailer Modal Player** powered by `react-player`.
  - Cast & crew roster with profile images and character credits.
  - Official video clips and teaser previews.
  - Contextual **Similar** and **Recommended** carousels.
- **⚡ Performance & UX Optimizations**:
  - Image lazy loading with progressive blur-up placeholders (`react-lazy-load-image-component`).
  - Custom CSS shimmer skeleton loaders during data fetch states.
  - Global state caching of TMDB image configurations and unified genre dictionaries via Redux.
- **📱 Smart Responsive Design**:
  - Scroll-direction-aware navigation bar (auto-hides on scroll-down, reveals on scroll-up).
  - Mobile drawer navigation and collapsible quick-search drawer.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend Framework** | [React 18](https://reactjs.org/) |
| **Build Tool & Bundler** | [Vite](https://vitejs.dev/) |
| **State Management** | [Redux Toolkit](https://redux-toolkit.js.org/) & [React-Redux](https://react-redux.js.org/) |
| **Routing** | [React Router DOM v6](https://reactrouter.com/) |
| **Styling** | [Sass (SCSS)](https://sass-lang.com/) with custom responsive mixins & CSS variables |
| **API Client** | [Axios](https://axios-http.com/) |
| **Data Provider** | [The Movie Database (TMDB) API](https://developers.themoviedb.org/3) |
| **UI Components & Utilities** | `react-circular-progressbar`, `react-lazy-load-image-component`, `react-player`, `react-select`, `react-infinite-scroll-component`, `react-icons`, `dayjs` |

---

## 📁 Project Structure

```
movix/
├── public/                 # Static assets
├── src/
│   ├── assets/             # Images, fallback posters, logo, placeholders
│   ├── components/         # Reusable UI components
│   │   ├── carousel/       # Horizontal scrolling item carousel with skeleton
│   │   ├── circleRating/   # Circular progress score gauge
│   │   ├── contentWrapper/ # Centered responsive container
│   │   ├── footer/         # Footer with links and social icons
│   │   ├── genres/         # Genre badge pills
│   │   ├── header/         # Smart scroll-aware navigation bar
│   │   ├── lazyLoadImage/  # Lazy image wrapper with blur effect
│   │   ├── movieCard/      # Grid/list media card component
│   │   ├── spinner/        # Loading spinner
│   │   ├── switchTabs/     # Animated tab switcher
│   │   └── videoPopup/     # YouTube video modal player
│   ├── hooks/
│   │   └── useFetch.jsx    # Custom hook for API data fetching & lifecycle
│   ├── pages/
│   │   ├── 404/            # Page Not Found
│   │   ├── details/        # Media details page (banner, cast, videos, carousels)
│   │   ├── explore/        # Filterable catalog page
│   │   ├── home/           # Landing page (hero banner & feed carousels)
│   │   └── searchResult/   # Multi-search results page
│   ├── store/
│   │   ├── homeSlice.js    # Redux slice for TMDB configurations and genres
│   │   └── store.js        # Redux store setup
│   ├── utils/
│   │   └── api.js          # Configured Axios instance for TMDB API
│   ├── App.jsx             # Main router & initial configuration dispatcher
│   ├── index.scss          # Design tokens, global theme, and skeleton shimmer
│   ├── mixins.scss         # Responsive breakpoint mixins
│   └── main.jsx            # React root mount
├── .env                    # Environment variables (TMDB API token)
├── package.json            # Dependencies and scripts
└── vite.config.js          # Vite configuration
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v16.0.0 or higher recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/movix.git
cd movix
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Setup TMDB API Credentials

1. Create a free account at [The Movie Database (TMDB)](https://www.themoviedb.org/).
2. Navigate to **Settings > API** to generate an **API Read Access Token (v4 auth)**.
3. Create a `.env` file in the root directory and add your token:

```env
VITE_APP_TMDB_TOKEN=your_tmdb_read_access_token_here
```

### 4. Run the Development Server

```bash
npm run dev
```

Open your browser and navigate to `http://localhost:5173`.

### 5. Build for Production

```bash
npm run build
```

To preview the production build locally:

```bash
npm run preview
```

---

## 🔑 Environment Variables

| Variable | Description |
| :--- | :--- |
| `VITE_APP_TMDB_TOKEN` | TMDB API Read Access Token (Bearer Token) for authentication |

---

## 📜 Available Scripts

- `npm run dev` – Starts the local development server with Hot Module Replacement (HMR).
- `npm run build` – Compiles and bundles production-ready assets into the `dist/` folder.
- `npm run preview` – Serves the local production build for testing.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- Data, posters, and backdrop images provided by [The Movie Database (TMDB)](https://www.themoviedb.org/).
- Icons by [React Icons](https://react-icons.github.io/react-icons/).
