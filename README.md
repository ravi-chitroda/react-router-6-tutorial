# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

<!-- Project related readme file -->

# React Router 6

#### React Course

[My React Course](https://www.udemy.com/course/react-tutorial-and-projects-course/?referralCode=FEE6A921AF07E2563CEF)

#### Support

Find the App Useful? [You can always buy me a coffee](https://www.buymeacoffee.com/johnsmilga)

#### Run Complete Project

- index.js

```js
// import App from './App';
import App from "./final/App";
```

#### Docs

[React Router Docs](https://reactrouter.com/docs/en/v6/getting-started/overview)

#### Install

```sh
npm install react-router-dom@6
```

#### First Pages

- App.js

```js
import { BrowserRouter, Routes, Route } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<div>home page</div>} />
        <Route
          path="testing"
          element={
            <div>
              <h2>testing </h2>
            </div>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

#### Components

- App.js

```js
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Home from "./pages/Home";
import About from "./pages/About";
import Products from "./pages/Products";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="about" element={<About />} />
        <Route path="products" element={<Products />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

#### Links

- Home.js, About.js

```js
import { Link } from 'react-router-dom';

const Home = () => {
  return (
    <div>
      <h2>Home Page</h2>
      <Link to='/about' className='btn'>
        About
      </Link>
      <a href="">
    </div>
  );
};
export default Home;
```

#### Error Page

- App.js

```js
function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="about" element={<About />} />
        <Route path="products" element={<Products />} />
        <Route path="*" element={<Error />} />
      </Routes>
    </BrowserRouter>
  );
}
```

- Error.js

```js
import { Link } from "react-router-dom";

const Error = () => {
  return (
    <section className="section">
      <h2>404</h2>
      <p>page not found</p>
      <Link to="/">back home</Link>
    </section>
  );
};
export default Error;
```

#### Nested Pages

- will refactor few times

- App.js

```js
function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />}>
          <Route path="about" element={<About />} />
          <Route path="products" element={<Products />} />
          <Route path="*" element={<Error />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}
```

#### Shared Layout

- Home.js

```js
import { Link, Outlet } from "react-router-dom";

const Home = () => {
  return (
    <section className="section">
      <h2>Home Page</h2>
      <Outlet />
    </section>
  );
};
export default Home;
```

#### Navbar

- Navbar.js

```js
import { Link } from "react-router-dom";

const Navbar = () => {
  return (
    <nav className="navbar">
      <Link to="/">Home</Link>
      <Link to="/about">About</Link>
      <Link to="/products">Products</Link>
    </nav>
  );
};
export default Navbar;
```

- Home.js

```js
import { Link, Outlet } from "react-router-dom";
import Navbar from "../components/Navbar";
const Home = () => {
  return (
    <>
      <Navbar />
      <section className="section">
        <Outlet />
      </section>
    </>
  );
};
export default Home;
```

#### Index Routes

- Index routes render in the parent routes outlet at the parent route's path.
- Index routes match when a parent route matches but none of the other children match.
- Index routes are the default child route for a parent route.
- Index routes render when the user hasn't clicked one of the items in a navigation list yet.

- copy Home.js content
- SharedLayout.js

```js
import { Link, Outlet } from "react-router-dom";
import Navbar from "../components/Navbar";
const SharedLayout = () => {
  return (
    <>
      <Navbar />
      <section className="section">
        <Outlet />
      </section>
    </>
  );
};
export default SharedLayout;
```

- Home.js

```js
const Home = () => {
  return (
    <section className="section">
      <h2>Home Page</h2>
    </section>
  );
};
export default Home;
```

- App.js

```js
function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<SharedLayout />}>
          <Route index element={<Home />} />
          <Route path="about" element={<About />} />
          <Route path="products" element={<Products />} />
          <Route path="*" element={<Error />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}
```

#### NavLink (style)

- StyledNavbar.js

```js
import { NavLink } from "react-router-dom";

<nav className="navbar">
  <NavLink
    to="/about"
    style={({ isActive }) => {
      return { color: isActive ? "red" : "grey" };
    }}
  >
    Home
  </NavLink>
</nav>;
```

#### NavLink (className)

- StyledNavbar.js

```js
<nav className="navbar">
  <NavLink
    to="/"
    className={({ isActive }) => (isActive ? "link active" : "link")}
  >
    Home
  </NavLink>
</nav>
```

#### Reading URL Params

- App.js

```js
function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<SharedLayout />}>
          <Route index element={<Home />} />
          <Route path="about" element={<About />} />
          <Route path="products" element={<Products />} />
          <Route path="products/:productId" element={<SingleProduct />} />
          <Route path="*" element={<Error />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}
```

#### Single Product

- SingleProduct.js

```js
import { Link, useParams } from "react-router-dom";
import products from "../data";
const SingleProduct = () => {
  const { productId } = useParams();

  return (
    <section className="section product">
      <h2>{productId}</h2>
      <Link to="/products">back to products</Link>
    </section>
  );
};

export default SingleProduct;
```

#### Products Page

- Products.js

```js
import { Link } from "react-router-dom";
import products from "../data";
const Products = () => {
  return (
    <section className="section">
      <h2>products</h2>
      <div className="products">
        {products.map((product) => {
          return (
            <article key={product.id}>
              <h5>{product.name}</h5>
              <Link to={`/products/${product.id}`}>more info</Link>
            </article>
          );
        })}
      </div>
    </section>
  );
};

export default Products;
```

#### Single Product

- SingleProduct.js

```js
import { Link, useParams } from "react-router-dom";
import products from "../data";
const SingleProduct = () => {
  const { productId } = useParams();
  const product = products.find((product) => product.id === productId);
  const { image, name } = product;

  return (
    <section className="section product">
      <img src={image} alt={name} />
      <h5>{name}</h5>
      <Link to="/products">back to products</Link>
    </section>
  );
};

export default SingleProduct;
```

#### useNavigate()

[ (?.) or Optional Chaining Explained](https://youtu.be/PuEGrylM1x8)

- App.js

```js
function App() {
  const [user, setUser] = useState(null);

  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<SharedLayout />}>
          <Route index element={<Home />} />
          <Route path="about" element={<About />} />
          <Route path="products" element={<Products />} />
          <Route path="products/:productId" element={<SingleProduct />} />
          <Route path="login" element={<Login setUser={setUser} />} />
          <Route path="dashboard" element={<Dashboard user={user} />} />
          <Route path="*" element={<Error />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}
```

- Login.js

```js
 import { useState } from 'react';
import { useNavigate } from 'react-router-dom';
const Login = ({ setUser }) => {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  const navigate = useNavigate();

  const handleSubmit = async (e) => {
    e.preventDefault();
    if (!name || !email) return;
    setUser({ name: name, email: email });
    navigate('/dashboard');
  };

```

[ (?.) or Optional Chaining Explained](https://youtu.be/PuEGrylM1x8)

- Dashboard.js

```js
const Dashboard = ({ user }) => {
  return (
    <section className="section">
      <h4>Hello, {user?.name}</h4>
    </section>
  );
};
export default Dashboard;
```

#### Protected Route

- App.js

```js
<Route
  path="dashboard"
  element={
    <ProtectedRoute user={user}>
      <Dashboard user={user} />
    </ProtectedRoute>
  }
/>
```

- ProtectedRoute.js

```js
import { Navigate } from "react-router-dom";

const ProtectedRoute = ({ children, user }) => {
  if (!user) {
    return <Navigate to="/" />;
  }
  return children;
};

export default ProtectedRoute;
```
