<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My E-Commerce Store</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>My E-Commerce Store</h1>
    </header>

    <main>
        <section class="product">
            <img src="product1.jpg" alt="Product 1">
            <h2>Product 1</h2>
            <p>Price: $19.99</p>
            <button class="add-to-cart">Add to Cart</button>
        </section>

        <section class="product">
            <img src="product2.jpg" alt="Product 2">
            <h2>Product 2</h2>
            <p>Price: $29.99</p>
            <button class="add-to-cart">Add to Cart</button>
        </section>
    </main>

    <aside id="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items">
            <!-- Cart items will be added here dynamically using JavaScript -->
        </ul>
        <p>Total: $<span id="cart-total">0.00</span></p>
        <button id="checkout">Checkout</button>
    </aside>

    <footer>
        <p>&copy; 2023 My E-Commerce Store</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>


   /* Reset default styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
}

header {
    background-color: #333;
    color: white;
    padding: 20px;
    text-align: center;
}

h1 {
    margin: 0;
}

nav ul {
    list-style: none;
}

nav li {
    display: inline;
    margin: 0 10px;
}

main {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    padding: 20px;
}

.product {
    width: 250px;
    margin: 20px;
    padding: 20px;
    background-color: white;
    border: 1px solid #ccc;
    text-align: center;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

.product img {
    max-width: 100%;
    height: auto;
}

.product h2 {
    font-size: 1.2em;
    margin: 10px 0;
}

.product p {
    font-size: 1.1em;
    margin: 10px 0;
}

button.add-to-cart {
    background-color: #0074cc;
    color: white;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
    font-size: 1.1em;
    border-radius: 4px;
}

button.add-to-cart:hover {
    background-color: #0058a8;
}

aside {
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

#cart-items li {
    list-style: none;
    margin: 10px 0;
}

footer {
    text-align: center;
    background-color: #333;
    color: white;
    padding: 10px;
}

document.addEventListener("DOMContentLoaded", function () {
    const products = [
        { name: "Product 1", price: 19.99 },
        { name: "Product 2", price: 29.99 },
        // Add more products here
    ];

    const cart = [];
    const addToCartButtons = document.querySelectorAll(".add-to-cart");
    const cartItems = document.getElementById("cart-items");
    const cartTotal = document.getElementById("cart-total");

    addToCartButtons.forEach((button, index) => {
        button.addEventListener("click", function () {
            cart.push(products[index]);
            updateCartDisplay();
        });
    });

    function updateCartDisplay() {
        cartItems.innerHTML = "";
        let total = 0;

        cart.forEach(item => {
            const li = document.createElement("li");
            li.textContent = item.name;
            cartItems.appendChild(li);
            total += item.price;
        });

        cartTotal.textContent = total.toFixed(2);
    }

    document.getElementById("checkout").addEventListener("click", function () {
        // Implement checkout logic here
        alert("Checkout functionality will be implemented in a real e-commerce site.");
    });
});
