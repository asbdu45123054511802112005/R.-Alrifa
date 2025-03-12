<!DOCTYPE html>
<html>
<head>
	<title>Supermarket</title>
</head>
<body>
	<!-- Header Section -->
	<header>
		<h1>Supermarket</h1>
		<nav>
			<ul>
				<li><a href="#home">Home</a></li>
				<li><a href="#products">Products</a></li>
				<li><a href="#services">Services</a></li>
				<li><a href="#contact">Contact</a></li>
			</ul>
		</nav>
	</header>
	
	<!-- Hero Section -->
	<section id="home">
		<h2>Welcome to Our Supermarket</h2>
		<p>We offer a wide range of products at affordable prices.</p>
		<button>Shop Now</button>
	</section>
	
	<!-- Products Section -->
	<section id="products">
		<h2>Our Products</h2>
		<ul>
			<li>
				<h3>Fresh Produce</h3>
				<p>Fresh fruits and vegetables.</p>
				<img src="fresh-produce.jpg" alt="Fresh Produce">
			</li>
			<li>
				<h3>Meat and Poultry</h3>
				<p>Fresh meat and poultry products.</p>
				<img src="meat-poultry.jpg" alt="Meat and Poultry">
			</li>
			<li>
				<h3>Dairy and Eggs</h3>
				<p>Fresh dairy products and eggs.</p>
				<img src="dairy-eggs.jpg" alt="Dairy and Eggs">
			</li>
		</ul>
	</section>
	
	<!-- Services Section -->
	<section id="services">
		<h2>Our Services</h2>
		<ul>
			<li>
				<h3>Home Delivery</h3>
				<p>We offer home delivery services for our customers.</p>
			</li>
			<li>
				<h3>Online Ordering</h3>
				<p>Order online and pick up at our store.</p>
			</li>
			<li>
				<h3>Loyalty Program</h3>
				<p>Join our loyalty program and earn rewards.</p>
			</li>
		</ul>
	</section>
	
	<!-- Contact Section -->
	<section id="contact">
		<h2>Contact Us</h2>
		<p>Phone: 555-555-5555</p>
		<p>Email: <a href="mailto:info@supermarket.com">info@supermarket.com</a></p>
		<p>Address: 123 Main St, Anytown, USA</p>
	</section>
	
	<!-- Footer Section -->
	<footer>
		<p>&copy; 2023 Supermarket</p>
	</footer>
</body>
</html>
body {
	font-family: Arial, sans-serif;
	margin: 0;
	padding: 0;
	background-color: #f5f5f5;
}

header {
	background-color: #333;
	color: #fff;
	padding: 20px;
	text-align: center;
}

header nav ul {
	list-style: none;
	margin: 0;
	padding: 0;
	display: flex;
	justify-content: space-between;
}

header nav ul li {
	margin-right: 20px;
}

header nav a {
	color: #fff;
	text-decoration: none;
}

#home {
	background-image: url('hero-image.jpg');
	background-size: cover;
	background-position: center;
	height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
	color: #fff;
}

#home button {
	background-color: #333;
	color: #fff;
	padding: 10px 20px;
	border: none;
	border-radius: 5px;
	cursor: pointer;
}

#products {
	padding: 20px;
}

#products ul {
	list-style: none;
	margin: 0;
	padding: 0;
}

#products li {
	margin-bottom: 20px;
}

#products h3 {
	font-size: 24px;
	margin-bottom: 10px;
}

#products img {
	width: 100%;
	height: 150px;
	object-fit: cover;
	margin-bottom: 10px;
}

#services {
	padding: 20px;
}

#services ul {
	list-style: none;
	margin: 0;
	padding: 0;
}

#services li {
	margin-bottom: 20px;
}

#services h3 {
	font-size: 24px;
	margin-bottom: 10px;
}

#contact {
	padding: 20px;
}

footer {
	background-color: #333;
	color: #fff;
	padding: 10px;
	text-align: center;
	clear: both;
}
```Here is an example of JavaScript code for a supermarket website:

```
// Product array
const products = [
  {
    id: 1,
    name: "Apple",
    price: 1.99,
    quantity: 10
  },
  {
    id: 2,
    name: "Banana",
    price: 0.99,
    quantity: 20
  },
  {
    id: 3,
    name: "Orange",
    price: 2.99,
    quantity: 15
  }
];

// Shopping cart array
const cart = [];

// Function to add product to cart
function addProductToCart(productId) {
  const product = products.find((product) => product.id === productId);
  if (product) {
    cart.push(product);
    updateCart();
  }
}

// Function to update cart
function updateCart() {
  const cartElement = document.getElementById("cart");
  cartElement.innerHTML = "";
  cart.forEach((product) => {
    const productHTML = `
      <p>${product.name} x ${product.quantity} = $${product.price * product.quantity}</p>
    `;
    cartElement.insertAdjacentHTML("beforeend", productHTML);
  });
}

// Function to handle product button click
function handleProductButtonClick(event) {
  const productId = event.target.dataset.productId;
  addProductToCart(productId);
}

// Event listener for product button click
document.addEventListener("click", (event) => {
  if (event.target.classList.contains("add-to-cart")) {
    handleProductButtonClick(event);
  }
});

// Display products on page load
window.onload = () => {
  const productsElement = document.getElementById("products");
  productsElement.innerHTML = "";
  products.forEach((product) => {
    const productHTML = `
      <div>
        <h2>${product.name}</h2>
        <p>Price: $${product.price}</p>
        <p>Quantity: ${product.quantity}</p>
        <button class="add-to-cart" data-product-id="${product.id}">Add to Cart</button>
      </div>
    `;
    productsElement.insertAdjacentHTML("beforeend", productHTML);
  });
};

