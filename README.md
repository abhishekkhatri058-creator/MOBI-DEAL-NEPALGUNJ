mobile-shop/
│── index.html        (Homepage + product listing)
│── about.html        (About Us page)
│── contact.html      (Contact form page)
│── style.css         (Styling)
│── script.js         (Cart functionality)

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mobile Shop</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Mobile Shop</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About Us</a>
      <a href="contact.html">Contact</a>
      <a href="#" id="cart-link">Cart (<span id="cart-count">0</span>)</a>
    </nav>
  </header>

  <section class="banner">
    <h2>Welcome to the Best Mobile Deals!</h2>
  </section>

  <section class="products">
    <h2>Our Mobiles</h2>
    <div class="product-list">
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Phone 1">
        <h3>Phone Model A</h3>
        <p>$499</p>
        <button onclick="addToCart('Phone Model A', 499)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Phone 2">
        <h3>Phone Model B</h3>
        <p>$699</p>
        <button onclick="addToCart('Phone Model B', 699)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Phone 3">
        <h3>Phone Model C</h3>
        <p>$899</p>
        <button onclick="addToCart('Phone Model C', 899)">Add to Cart</button>
      </div>
    </div>
  </section>

  <section id="cart" class="cart">
    <h2>Your Cart</h2>
    <ul id="cart-items"></ul>
    <p>Total: $<span id="cart-total">0</span></p>
  </section>

  <script src="script.js"></script>
  <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>About Us - Mobile Shop</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>About Us</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About Us</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>

  <section>
    <h2>Who We Are</h2>
    <p>We are a trusted mobile retailer offering the latest smartphones at unbeatable prices.</p>
  </section>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Contact Us - Mobile Shop</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Contact Us</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About Us</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>

  <section>
    <h2>Get in Touch</h2>
    <form>
      <label>Name:</label>
      <input type="text" required>
      <label>Email:</label>
      <input type="email" required>
      <label>Message:</label>
      <textarea required></textarea>
      <button type="submit">Send</button>
    </form>
  </section>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header {
  background: #333;
  color: #fff;
  padding: 15px;
  text-align: center;
}

nav a {
  color: #fff;
  margin: 0 10px;
  text-decoration: none;
}

.banner {
  background: #007BFF;
  color: #fff;
  padding: 50px;
  text-align: center;
}

.products {
  padding: 20px;
}

.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.product {
  border: 1px solid #ddd;
  padding: 15px;
  width: 200px;
  text-align: center;
}

.cart {
  background: #f4f4f4;
  padding: 20px;
}

@media (max-width: 600px) {
  .product-list {
    flex-direction: column;
    align-items: center;
  }
}

let cart = [];
let total = 0;

function addToCart(product, price) {
  cart.push({ product, price });
  total += price;
  updateCart();
}

function updateCart() {
  const cartItems = document.getElementById("cart-items");
  cartItems.innerHTML = "";
  cart.forEach(item => {
    const li = document.createElement("li");
    li.textContent = `${item.product} - $${item.price}`;
    cartItems.appendChild(li);
  });
  document.getElementById("cart-total").textContent = total;
  document.getElementById("cart-count").textContent = cart.length;
}


</body>
</html>
