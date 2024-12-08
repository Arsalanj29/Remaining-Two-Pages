# Remaining-Two-Pages
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Enhanced Product Details Page</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="product-page">
    <!-- Header -->
    <header class="header">
      <h1 class="logo">ShopEasy</h1>
    </header>

    <!-- Product Section -->
    <section class="product-section">
      <!-- Product Image Carousel -->
      <div class="image-carousel">
        <div class="image-container">
          <img id="main-image" src="images/product1.jpg" alt="Product Image">
        </div>
        <div class="thumbnail-container">
          <img class="thumbnail" src="images/product1.jpg" alt="Thumbnail 1" onclick="changeImage('images/product1.jpg')">
          <img class="thumbnail" src="images/product2.jpg" alt="Thumbnail 2" onclick="changeImage('images/product2.jpg')">
          <img class="thumbnail" src="images/product3.jpg" alt="Thumbnail 3" onclick="changeImage('images/product3.jpg')">
        </div>
      </div>

      <!-- Product Details -->
      <div class="product-details">
        <h2>Stylish Sneakers</h2>
        <p class="description">These sneakers are perfect for both casual and athletic use. Lightweight, durable, and available in various colors.</p>
        <p class="price">$89.99</p>
        <button id="add-to-cart-button" onclick="showPaymentOptions()">Add to Cart</button>
      </div>
    </section>

    <!-- Payment and Delivery Modal -->
    <div id="payment-modal" class="modal hidden">
      <div class="modal-content">
        <span class="close-button" onclick="closeModal()">&times;</span>
        <h2>Select Payment and Delivery Options</h2>
        <form id="payment-form">
          <label for="payment-method">Payment Method:</label>
          <select id="payment-method" required>
            <option value="bank">Bank Payment</option>
            <option value="cash">Cash on Delivery</option>
          </select>
          <label for="delivery-speed">Delivery Speed:</label>
          <select id="delivery-speed" required>
            <option value="fast">Fast Delivery</option>
            <option value="slow">Slow Delivery</option>
          </select>
          <button type="submit">Confirm</button>
        </form>
      </div>
    </div>

    <!-- Related Products Section -->
    <section class="related-products">
        <h2>Related Products</h2>
        <div class="product-grid">
          <div class="related-product" onclick="viewProduct('Product 1')">Casual Shoes</div>
          <div class="related-product" onclick="viewProduct('Product 2')">Running Shoes</div>
          <div class="related-product" onclick="viewProduct('Product 3')">Training Sneakers</div>
          <div class="related-product" onclick="viewProduct('Product 4')">Sports Shoes</div>
        </div>
      </section>
    <!-- Footer -->
    <footer class="footer">
      <p>&copy; 2024 ShopEasy. All rights reserved.</p>
    </footer>
  </div>
  <script src="script.js"></script>
</body>
</html>

/* General Styles */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f5f5f5;
  color: #333;
}

h1, h2 {
  font-weight: bold;
}

a {
  text-decoration: none;
  color: inherit;
}

/* Header */
.header {
  background-color: #4CAF50;
  color: #fff;
  padding: 10px 20px;
  text-align: center;
}

.logo {
  margin: 0;
}

/* Product Section */
.product-section {
  display: flex;
  justify-content: space-around;
  align-items: flex-start;
  padding: 20px;
  background-color: #fff;
  border-radius: 8px;
  margin: 20px auto;
  max-width: 1200px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.image-carousel {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.image-container {
  width: 400px;
  height: 400px;
  overflow: hidden;
  border: 2px solid #ddd;
  border-radius: 8px;
}

#main-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

#main-image:hover {
  transform: scale(1.2);
}

.thumbnail-container {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

.thumbnail {
  width: 80px;
  height: 80px;
  object-fit: cover;
  cursor: pointer;
  border: 2px solid transparent;
  border-radius: 4px;
  transition: border-color 0.2s;
}

.thumbnail:hover {
  border-color: #4CAF50;
}

.product-details {
  flex: 1;
  margin-left: 20px;
}

.product-details h2 {
  font-size: 2rem;
  margin-bottom: 10px;
}

.description {
  color: #666;
  margin-bottom: 10px;
}

.price {
  color: #4CAF50;
  font-size: 1.8rem;
  margin-bottom: 20px;
}

button {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #45a049;
}

/* Related Products */
.related-products {
  padding: 20px;
  margin-top: 20px;
  background-color: #fff;
  border-radius: 8px;
  max-width: 1200px;
  margin: 20px auto;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 20px;
}

.related-product {
  padding: 20px;
  text-align: center;
  background-color: #f5f5f5;
  border: 2px solid #ddd;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
}

.related-product:hover {
  background-color: #e8f5e9;
  transform: translateY(-5px);
}

/* Footer */
.footer {
  text-align: center;
  padding: 10px 20px;
  background-color: #4CAF50;
  color: white;
  margin-top: 20px;
}
/* Modal Styles */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
}

.modal.hidden {
  display: none;
}

.modal-content {
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  max-width: 400px;
  width: 90%;
}

.close-button {
  float: right;
  font-size: 1.5rem;
  cursor: pointer;
  color: #555;
}

.modal-content h2 {
  margin-top: 0;
}

label {
  display: block;
  margin-top: 15px;
  font-weight: bold;
}

select {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  display: block;
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  border-radius: 4px;
  cursor: pointer;
  margin-top: 20px;
}

button:hover {
  background-color: #45a049;
}

function changeImage(imageSrc) {
    const mainImage = document.getElementById('main-image');
    mainImage.src = imageSrc;
  }
  
  function showPaymentOptions() {
    const modal = document.getElementById('payment-modal');
    modal.classList.remove('hidden');
  }
  
  function closeModal() {
    const modal = document.getElementById('payment-modal');
    modal.classList.add('hidden');
  }
  
  document.getElementById('payment-form').addEventListener('submit', function (event) {
    event.preventDefault();
  
    const paymentMethod = document.getElementById('payment-method').value;
    const deliverySpeed = document.getElementById('delivery-speed').value;
  
    alert(Payment Method: ${paymentMethod}\nDelivery Speed: ${deliverySpeed});
    closeModal();
  });

  #END
