<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Shop</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>Simple Shop</h1>
    <div class="cart">
      🛒 Cart (<span id="cart-count">0</span>)
    </div>
  </header>

  <main>
    <div class="product-grid">
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Product 1" />
        <h2>Product 1</h2>
        <p>$10.00</p>
        <button onclick="addToCart('Product 1', 10)">Add to Cart</button>
      </div>

      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Product 2" />
        <h2>Product 2</h2>
        <p>$15.00</p>
        <button onclick="addToCart('Product 2', 15)">Add to Cart</button>
      </div>

      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Product 3" />
        <h2>Product 3</h2>
        <p>$20.00</p>
        <button onclick="addToCart('Product 3', 20)">Add to Cart</button>
      </div>
    </div>
  </main>

  <script src="script.js"></script>
</body>
</html>
