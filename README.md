
# React-Redux-Saga-Folder-Structured
A well-structured React boilerplate with Redux and Redux Saga for state management and side effects handling.


## Folder Structure

The folder structure is designed to separate concerns and promote reusability. Below is an overview of each folder and its purpose:


### `src/`

- **`components/`**: 
  - Contains **dumb components** (also known as presentational components) that focus solely on rendering UI elements.
  - These components receive data via props and render the UI accordingly without managing any application state or side effects.
  - Example: 
    - `Button.js`: A simple button component.
  
- **`containers/`**: 
  - Houses **smart components** that manage the state and business logic of the application.
  - They connect to the Redux store to retrieve and dispatch actions, effectively acting as a bridge between the Redux store and the presentational components.
  - Example:
    - `ProductContainer.js`: Fetches products and passes them down to the presentational component.

- **`pages/`**: 
  - Contains components that represent distinct pages in your application.
  - Each page component typically combines one or more container components to structure the content displayed.
  - Example:
    - `HomePage.js`: The homepage that displays featured products.

- **`layouts/`**: 
  - Defines the layout structure of pages, often wrapping page components.
  - This helps maintain consistent styling and structure across different pages.
  - Example:
    - `MainLayout.js`: Contains the header, footer, and main content area.

- **`commons/`**: 
  - Includes common components that are used across multiple pages, such as headers, footers, and navigation bars.
  - These components can be considered reusable UI elements.
  - Example:
    - `Header.js`: The site header with navigation links.

- **`routes/`**: 
  - Contains routing logic for the application.
  - Includes components for **public routes** (accessible to everyone) and **private routes** (restricted to authenticated users).
  - Example:
    - `PrivateRoute.js`: Ensures only authenticated users can access certain routes.

- **`store/`**: 
  - Manages Redux state, actions, and reducers.
  - This folder contains the Redux store configuration and root reducer that combines all the application reducers.
  - Example:
    - `store.js`: Configures the Redux store and applies middleware.

- **`shared/`**: 
  - Holds shared utilities and helper functions that can be used throughout the application.
  - This can include API functions and custom hooks.
  - Example:
    - `api.js`: Functions for making API requests.

- **`dependencies/`**: 
  - Contains third-party dependencies and configuration, such as Axios instances and interceptors.
  - Example:
    - `axiosInstance.js`: Custom Axios instance with interceptors for request and response handling.


## Redux and Redux Saga

This application uses **Redux** for state management and **Redux Saga** for handling side effects, such as asynchronous data fetching.

- **Redux**: 
  - A predictable state container for JavaScript apps.
  - Helps manage the application state globally and allows components to access the state as needed.

- **Redux Saga**: 
  - A middleware library that aims to make side effects (e.g., data fetching, API calls) easier to manage.
  - It uses generator functions to handle asynchronous flows more elegantly.
  - You can define sagas to watch for specific actions and execute corresponding side effects.

    
### Store Configuration

The store is set up with Redux and Redux Saga, including the following key files:

- **`store.js`**: Configures the Redux store and applies middleware.
- **`rootReducer.js`**: Combines all reducers into a single root reducer.
- **`rootSaga.js`**: Combines all sagas into a single root saga, using the `all` and `fork` effects to run sagas concurrently.
- **`rootActions.js`**: Contains action types and action creators that can be used across the application for dispatching actions related to fetching products and handling responses.


### Usage of Redux Saga

1. **Create Saga Watchers**: Define watcher sagas that listen for specific actions and trigger worker sagas.
2. **Worker Sagas**: These perform the actual side effects, like making API calls.
3. **Dispatch Actions**: Use action creators from `rootActions.js` to dispatch actions in your components or sagas.


### Example Usage

To fetch products, you would dispatch `fetchProductsRequest()` from a component, which would trigger the corresponding saga to handle the API request and update the Redux store with the results.


### Usage

1. **Dumb Components**: Use dumb components for UI rendering. They should not manage any state or side effects. They receive data and callbacks as props.
2. **Smart Containers**: Use smart containers to handle business logic and connect to the Redux store. They can dispatch actions and pass data to dumb components.
3. **Routing**: 
   - Use the `PublicRoute` component for routes that should be accessible to everyone.
   - Use the `PrivateRoute` component for routes that require authentication.


### Getting Started

1. **Clone the repository**:
   ```shell
   git clone https://github.com/aditya132p/React-Redux-Saga-Folder-Structured.git
   cd React-Redux-Saga-Folder-Structured

   ```

2. **Install dependencies**:
   ```shell
   npm install
   ```

2. **Install dependencies**:
   ```bash
   npm run dev
   ```


### Features
- Routing: Public and private routes for user authentication.
- Redux: State management for better application performance.
- Redux Saga: Handles side effects like API calls in a more manageable way.
- Axios: Axios instance with interceptors for centralized API request and response handling.
- Reusable Components: Easy-to-use components to maintain consistency across the app.

### Contributing
Feel free to create a pull request for any enhancements or bug fixes.


### Key Points Added:

- **Detailed Folder Structure**: Each folder’s purpose is described to help developers understand how to organize their components and logic.
- **Dumb vs. Smart Components**: Clear distinction between presentational (dumb) components and container (smart) components.
- **Redux and Redux Saga**: Explanation of how Redux manages state and how Redux Saga helps with side effects, making the flow of data fetching and state management clearer.

This `README.md` should provide a comprehensive understanding of the project structure and logic for anyone looking to use or contribute to your React application. If you need further adjustments, just let me know!
