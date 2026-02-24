# Rexipeez - Recipe Website Specification

## 1. Project Overview

**Project Name:** Rexipeez
**Project Type:** Single Page Application (React)
**Core Functionality:** A recipe sharing platform where users can browse, add, like, and favorite recipes. Includes authentication with sign up/sign in.
**Target Users:** Home cooks, food enthusiasts, recipe creators

---

## 2. UI/UX Specification

### Theme & Visual Design

**Primary Colors:**
- Primary Yellow: `#FFD93D` (Bright yellow)
- Secondary Yellow: `#F4C430` (Saffron yellow)
- White: `#FFFFFF`
- Black: `#1A1A1A`
- Accent: `#FF6B35` (Orange for highlights)

**Pattern:** Yellow background with white diagonal stripes, black borders

**Typography:**
- Headings: 'Playfair Display', serif (elegant, food-magazine style)
- Body: 'Nunito', sans-serif (friendly, readable)
- Accent Text: 'Caveat', cursive (for recipe titles, personal touch)

**Spacing System:**
- Base unit: 8px
- Section padding: 48px (6 units)
- Card padding: 24px (3 units)
- Element gaps: 16px (2 units)

**Visual Effects:**
- Box shadows: `0 4px 20px rgba(0,0,0,0.15)`
- Border radius: 12px for cards, 8px for buttons
- Transitions: 0.3s ease for all interactive elements
- Hover effects: Scale 1.02, shadow increase

### Layout Structure

**Responsive Breakpoints:**
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

**Page Sections:**
- Header: Fixed navigation with logo, nav links, auth buttons
- Hero: Full-width banner with search
- Content: Grid-based recipe cards
- Footer: Links, social icons, copyright

### Routes/Pages

1. **Home** (`/`) - Featured recipes, search, categories
2. **Recipes** (`/recipes`) - All recipes grid
3. **Recipe Detail** (`/recipe/:id`) - Single recipe view
4. **Add Recipe** (`/add-recipe`) - Create new recipe form
5. **My Recipes** (`/my-recipes`) - User's added recipes
6. **Favorites** (`/favorites`) - Liked/favorited recipes
7. **Sign In** (`/signin`) - Login form
8. **Sign Up** (`/signup`) - Registration form

### Page-Specific Themes

Each page will have unique accent colors while maintaining the yellow/white stripe foundation:

- **Home**: Yellow primary (`#FFD93D`), Orange accents
- **Recipes**: Golden yellow (`#F4C430`), Red accents (`#E74C3C`)
- **Recipe Detail**: Warm yellow (`#FFE066`), Green accents (`#27AE60`)
- **Add Recipe**: Bright yellow (`#FFEB3B`), Blue accents (`#3498DB`)
- **My Recipes**: Amber (`#FFC107`), Purple accents (`#9B59B6`)
- **Favorites**: Soft yellow (`#FFF9C4`), Pink accents (`#E91E63`)
- **Sign In/Up**: Classic yellow (`#FDD835`), Teal accents (`#00BCD4`)

---

## 3. Functionality Specification

### Core Features

**1. Recipe Browsing**
- View all recipes in responsive grid
- Search recipes by name/ingredient
- Filter by category
- Sort by date, popularity, alphabetical

**2. Recipe Detail**
- Full recipe view with ingredients, instructions
- Like/unlike functionality
- Add to favorites
- View author info

**3. Recipe Management**
- Add new recipe with:
  - Title, description
  - Category (Breakfast, Lunch, Dinner, Dessert, Snack)
  - Ingredients list
  - Step-by-step instructions
  - Cooking time, servings
  - Image URL
- Edit own recipes
- Delete own recipes

**4. User Authentication**
- Sign Up with username, email, password
- Sign In with email/password
- Persistent session (localStorage)
- Sign Out functionality

**5. Social Features**
- Like recipes (toggle)
- Favorite recipes (toggle)
- View like/favorite counts

### Custom Fake API

**Endpoints:**
- `GET /recipes` - All recipes
- `GET /recipes/:id` - Single recipe
- `POST /recipes` - Add recipe
- `PUT /recipes/:id` - Update recipe
- `DELETE /recipes/:id` - Delete recipe
- `POST /auth/signup` - Register user
- `POST /auth/signin` - Login user
- `GET /users/:id/recipes` - User's recipes
- `POST /recipes/:id/like` - Toggle like
- `POST /recipes/:id/favorite` - Toggle favorite

**Data Storage:** localStorage with initial seed data

---

## 4. Technical Implementation

### Tech Stack
- React 18 with Vite
- React Router v6
- CSS3 with CSS Variables
- JavaScript ES6+
- LocalStorage for persistence

### Animations
- Page load: Fade in with stagger
- Card hover: Scale up, shadow
- Button hover: Color shift, slight lift
- Route transitions: Slide/fade
- Like heart: Pulse animation
- Loading: Skeleton shimmer

### Icons
Using emoji-based custom icons for:
- 🍳 Recipes
- ❤️ Likes
- ⭐ Favorites
- 👤 Profile
- 🔍 Search
- ➕ Add
- ✏️ Edit
- 🗑️ Delete
- ⏱️ Time
- 👥 Servings

---

## 5. Acceptance Criteria

- [ ] All 8 routes functional
- [ ] Theme consistently applied (yellow/white stripes, black borders)
- [ ] Each page has unique accent color
- [ ] Sign up creates new user
- [ ] Sign in validates credentials
- [ ] Can add new recipe
- [ ] Can like recipes (persists)
- [ ] Can favorite recipes (persists)
- [ ] My Recipes shows only user's recipes
- [ ] Favorites shows all favorited recipes
- [ ] Animations smooth and consistent
- [ ] Responsive on all breakpoints
- [ ] No console errors

---

## 6. File Structure

```
Rexipeez/
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── Header.jsx
│   │   ├── Footer.jsx
│   │   ├── RecipeCard.jsx
│   │   ├── SearchBar.jsx
│   │   ├── PrivateRoute.jsx
│   │   └── Loading.jsx
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Recipes.jsx
│   │   ├── RecipeDetail.jsx
│   │   ├── AddRecipe.jsx
│   │   ├── MyRecipes.jsx
│   │   ├── Favorites.jsx
│   │   ├── SignIn.jsx
│   │   └── SignUp.jsx
│   ├── context/
│   │   ├── AuthContext.jsx
│   │   └── RecipeContext.jsx
│   ├── api/
│   │   └── fakeApi.js
│   ├── styles/
│   │   ├── App.css
│   │   ├── index.css
│   │   └── variables.css
│   ├── App.jsx
│   └── main.jsx
├── package.json
├── vite.config.js
└── index.html
