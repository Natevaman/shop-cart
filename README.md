<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Include necessary meta tags, stylesheets, and scripts -->
</head>
<body>

  <!-- Cart contents -->
  <div id="cart">
    <!-- Cart items will be displayed here -->
  </div>

  <script>
    // Function to retrieve cart data from local storage and display it
    function displayCart() {
      const cartElement = document.getElementById('cart');
      cartElement.innerHTML = '';

      // Retrieve cart data from local storage
      let cart = JSON.parse(localStorage.getItem('cart')) || [];

      // Display cart items
      cart.forEach(item => {
        const itemElement = document.createElement('div');
        itemElement.textContent = `${item.name}: £${item.price}`;
        cartElement.appendChild(itemElement);
      });
    }

    // Initialize cart display
    displayCart();
  </script>
</body>
</html>
