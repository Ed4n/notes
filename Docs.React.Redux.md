---
id: tiuhczvytuz9kzhy79og77d
title: Redux Toolkit
desc: ""
updated: 1689885190220
created: 1689883726920
---

#### Documentation:

https://redux-toolkit.js.org/tutorials/quick-start

### 1. First import redux:

```other
npm install @reduxjs/toolkit react-redux
```

### 2. Create a Slice file

create a slice file inside an app folder.

![Alt text](<CleanShot 2023-07-20 at 2.11.07.jpg>)

the file should look like this:

```javascript
import { configureStore } from "@reduxjs/toolkit";

export const store = configureStore({
  reducer: {
    // Reducers
  },
});
```

### 3. Create a Slice

Create a slice inside a feature folder.

- The structure doesn't matter but its recomended to divide the slices in folders.

![Alt text](<CleanShot 2023-07-20 at 2.14.07.jpg>)

- Then create this structure insiide the file:

```javascript
import { createSlice } from "@reduxjs/toolkit";

export const taskSlice = createSlice({
  name: "tasks",
  initialState: [],
  reducers: {
    // Reducers
  },
});

export default taskSlice.reducer;
```

Its important to export it with the .reducer at the end.

### 4. Import the created slice

Import the created slice in the main store file.

```javascript
import { configureStore } from "@reduxjs/toolkit";
import tasksReducer from "../features/tasks/taskSlice";

export const store = configureStore({
  reducer: {
    // Reducers
    tasks: tasksReducer,
  },
});
```

### 5. Wrap the App component in a Provider

Wrap the app component in the store provider, all the files that are wrapped with this provider will be able
to acces to the store:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";

// Redux
import { Provider } from "react-redux";
import { store } from "./app/store";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    {/* Redux Provider */}
    <Provider store={store}>
      <App />
    </Provider>
  </React.StrictMode>
);
```

6. ### Usage

```javascript
import React from "react";
// import useSelector
import { useSelector } from "react-redux";

export default function ReduxLearning() {
  const taskState = useSelector((state) => state.tasks);
  console.log(taskState);

  return (
    <div className="p-5">
      <h1>Redux Learning</h1>
    </div>
  );
}
```

## General Information

#### useDispatch

the **useDispatch** function is used to update the reducers form an specific slice.

#### useSelector

the **useSelector** is used to print & use the information from the main store.
