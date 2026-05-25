# PE04 – Cities React Application

A React application built for CS628 PE04 that demonstrates React Router, nested routes, `useParams`, and programmatic navigation (`useNavigate`).

---

# Input

The Cities application accepts two types of user input. First, the user interacts with the **Cities List** by clicking on any city name shown in the sidebar. Each city link is a React Router `<NavLink>` that changes the URL to `/cities/:id`, where `:id` is the unique identifier for the selected city. Second, the user can go to the **Add City** screen and fill out a form that collects a city's name, country, population, continent, primary language, timezone, flag emoji, and a short description. The required fields (name, country, population, continent) are checked before the form is accepted.

---

# Process

When a city link is clicked, React Router matches the `/cities/:id` route and renders the `CityDetail` component as a nested child of `CitiesList` using the `<Outlet />` component. Inside `CityDetail`, the `useParams` hook retrieves the `:id` parameter from the URL. It uses this ID to find the matching city object from the shared `cities` state array in `App`. When the Add City form is submitted, the `handleAddCity` function in `App` creates a new city object with a unique timestamp-based ID and adds it to the state array with `setCities`. The `AddCity` component then calls `useNavigate()` to redirect the browser to `/cities`, demonstrating React Router's navigation API.

---

# Output

The application displays three main screens. The **Cities List** screen shows a sidebar of all cities with a content area. When no city is selected, a prompt appears. When a city link is clicked, the `CityDetail` component shows up in the same layout without a full page reload, meeting the nested-route requirement. The **City Detail** screen presents a styled hero banner with the city's flag, name, and country, along with info cards for population, language, timezone, and continent. The **Add City** screen shows the input form. After a successful submission, the user is sent back to the Cities List, and a brief notification confirms the addition.