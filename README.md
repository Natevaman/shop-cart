<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Head content -->
</head>
<body>

  <div class="cart-container">
    <h2>Cart</h2>
    <div id="cart">
      <!-- Cart content will be displayed here -->
    </div>
  </div>

  <script>
    // Function to update cart display
    function updateCartDisplay() {
      const cartElement = document.getElementById('cart');
      cartElement.innerHTML = '';

      // Ensure that localStorage is available before accessing it
      if (localStorage.getItem('cart')) {
        let cart = JSON.parse(localStorage.getItem('cart'));

        cart.forEach(item => {
          const itemElement = document.createElement('div');
          itemElement.classList.add('cart-item');
          itemElement.textContent = `${item.name}: £${item.price}`;
          cartElement.appendChild(itemElement);
        });
      }
    }

    // Initialize cart display
    updateCartDisplay();
  </script>
</body>
</html>
