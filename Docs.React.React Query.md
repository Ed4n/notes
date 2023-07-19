---
id: v8h08jlewf5hcem5aiadzd4
title: React Query
desc: ""
updated: 1689726901121
created: 1689726898043
---

React Query
First install react query important to check documentation for lates [instalation documentation](https://tanstack.com/query/v4/docs/react/installation)

```json
npm i @tanstack/react-query
```

After installing create the following structure in the main or index document:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
import "./index.css";
// importacion de react query
import { QueryClientProvider, QueryClient } from "@tanstack/react-query";

// se guarda el query client en una constante (devuelve una instancia de query client)
const queryClient = new QueryClient();

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    {/* se envuelve el app en el query client provider */}
    <QueryClientProvider client={queryClient}>
      {" "}
      {/* se le pasa el query client como prop */}
      <App />
    </QueryClientProvider>
  </React.StrictMode>
);
```

To test all the things with react query will be necessary to use [Dev Tools](https://tanstack.com/query/v4/docs/react/devtools#options)

```bash
npm i @tanstack/react-query-devtools
```

Then import the package:

```javascript
import { ReactQueryDevtools } from "@tanstack/react-query-devtools";
```

Finally add the dev tools instance in the jsx code. The final code will look like this:

```javascript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
import "./index.css";
// importacion de react query
import { QueryClientProvider, QueryClient } from "@tanstack/react-query";
import { ReactQueryDevtools } from "@tanstack/react-query-devtools";

// se guarda el query client en una constante (devuelbvve una instancia de query client)
const queryClient = new QueryClient();

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    {/* se envuelve el app en el query client provider */}
    <QueryClientProvider client={queryClient}>
      <App />
      {/* Se intance react query dev tools */}
      <ReactQueryDevtools />
    </QueryClientProvider>
  </React.StrictMode>
);
```
