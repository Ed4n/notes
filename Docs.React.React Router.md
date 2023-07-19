---
id: dbcpkrg1m7kejpzf3e3x2fs
title: React Router
desc: ""
updated: 1689725923625
created: 1689725573758
---

here I will store all the notes that I find

- ## **React Router**

### 1. Install React router:

```other
   npm install react-router-dom@6
```

### 2. Setup React Router

Inside the index.js add the following code:

```javascript

   //First copy the imports
   import { BrowserRouter } from 'react-router-dom';

   const root = ReactDOM.createRoot(document.getElementById('root'));
   root.render(
    <React.StrictMode>
     //Capsule the "App" component inside <BrowserRouter>
       <BrowserRouter>
          <App />
       </BrowserRouter>
    </React.StrictMode>
   );

```

### 3. Add a Nav component

Inside the Nav component add the following code:

```JS
    //Just import Link library
    import { Link } from 'react-router-dom';

    const NavBar = () => {
     return (
     <nav>
       <Link to="/">Home</Link>
       <Link to="/about">About</Link>
       <Link to="/products">Products</Link>
     </nav>
     );
    };

    export default NavBar;

```

### 4. Set up the App component

    Inside the app component add the following code:

```javascript
//Import react router in the necessary page/component
import { Routes, Route } from "react-router-dom";

//Import all the pages
import Home from "./Pages/Home";
import About from "./Pages/About";
import Products from "./Pages/Products";

const App = () => {
  return (
    <>
      <NavBar />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/products" element={<Products />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </>
  );
};
```

### Reference

[React Router](https://hygraph.com/blog/routing-in-react)

```

```
