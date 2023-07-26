---
id: tiuhczvytuz9kzhy79og77d
title: Redux Toolkit
desc: ""
updated: 1690414719296
created: 1689883726920
---

#### Documentation:

https://redux-toolkit.js.org/tutorials/quick-start

## Initialization

### 1. First import redux:

```other
npm install @reduxjs/toolkit react-redux
```

### 2. Create a Store file

create a store file inside an app folder.

![Alt text](<CleanShot 2023-07-20 at 2.11.07.jpg>)

the file should look like this:

```javascript
import { configureStore } from "@reduxjs/toolkit";

export const store = configureStore({
  reducer: {},
});
```

### 3. Create a Slice

Create a slice inside a feature folder.

- The structure doesn't matter but its recomended to divide the slices in folders.

![Alt text](<CleanShot 2023-07-20 at 2.14.07.jpg>)

- Then create this structure insiide the file:

```javascript
import { createSlice } from "@reduxjs/toolkit";

export const DemoSlice = createSlice({
  name: "DemoSlice",
  initialState: [],
  reducers: {
    // Reducers
  },
});

export default DemoSlice.reducer;
```

Its important to export it with the .reducer at the end.

### 4. Import the created slice

Import the created slice in the main store file.

```javascript
import { configureStore } from "@reduxjs/toolkit";
import demoReducer from "../features/tasks/DemoSlice";

export const store = configureStore({
  reducer: {
    // name | import name
    DemoSlice: demoReducer,
  },
});
```

### 5. Wrap the App component in a Provider

First import the dependencies then wrap the app component in the store provider, all the files that are wrapped with this provider will be able
to acces to the store:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";

// Redux imports
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

---

## Usage

### Use Selector

the use selector hook is used to consume the state stored in the slice created before.

- useSelector has acces to the whole state.

```javascript
import React from "react";

// import useSelector
import { useSelector } from "react-redux";

export default function ReduxLearning() {
  // Initializing useSelector
  const demoState = useSelector((state) => state.DemoSlice);
  console.log(demoState);

  return (
    <div className="p-5">
      <h1>Redux Learning</h1>
    </div>
  );
}
```

Usually you'll be working with objects, so if you store an object in the **DemoSlice** you'll be able to map the results.

### useDispatch

the **useDispatch** function is used to update the reducers form an specific slice.

To use **useDispatch** previeosly you need to create a function inside the slice reducers and export it.

```javascript
export const DemoSlice = createSlice({
  name: "DemoSlice",
  initialState: [],
  reducers: {
    demoFunction: (state, action) => {
      console.log(action.payload);
    },
  },
});
export const { demoFunction } = DemoSlice.actions;
export default DemoSlice.reducer;
```

Now you can use the **useDispatch** hook and here is how:

```javascript
// import useDispatch
import { useDispatch } from "react-redux";

// import the function to use
import { demoFunction } from "../features/demoFunction";

// Initializing useDispatch
const dispatch = useDispatch();

// Usage
dispatch(demoFunction("Hello"));
```

## General Information
