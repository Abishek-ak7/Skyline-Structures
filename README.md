# Skyline Structures - Frontend Documentation (HTML Only)

## Project Overview
This is a pure frontend construction services management system built with HTML, CSS, and JavaScript. The application provides a complete interface for managing construction services, customer contacts, and orders without any backend dependencies (except localStorage for data persistence).

## Complete HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Skyline Structures</title>
  <style>
    /* All CSS styles from the project */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      display: flex;
    }
    nav {
      width: 250px;
      background-color: #1a1a2e;
      color: #fff;
      height: 100vh;
      padding: 20px;
      box-sizing: border-box;
      position: fixed;
    }
    /* ... (all other CSS rules) ... */
  </style>
</head>
<body>
  <!-- Navigation Sidebar -->
  <nav>
    <h2>Skyline Structures</h2>
    <input type="text" placeholder="Search...">
    <ul>
      <li onclick="showTab('home')">Home</li>
      <li onclick="showTab('products')">Products</li>
      <li onclick="showTab('mobileNumbers')">Profile</li>
      <li onclick="showTab('cart')">Cart</li>
      <li onclick="showTab('company')">Company</li>
    </ul>
  </nav>

  <!-- Main Content Area -->
  <div class="content">
    <!-- Home Tab -->
    <div id="home" class="tab home">
      <!-- Hero Banner -->
      <div class="hero-banner">
        <!-- ... hero content ... -->
      </div>
      
      <!-- Services Grid -->
      <div class="product-grid" id="homeProducts"></div>
    </div>

    <!-- Products Tab -->
    <div id="products" class="tab products hidden">
      <h1>Products</h1>
      <div class="product-grid" id="productList"></div>
    </div>

    <!-- Customer Contacts Tab -->
    <div id="mobileNumbers" class="tab hidden">
      <!-- Contacts management interface -->
    </div>

    <!-- Shopping Cart Tab -->
    <div id="cart" class="tab hidden">
      <!-- Cart contents and checkout -->
    </div>

    <!-- Company Info Tab -->
    <div id="company" class="tab hidden">
      <!-- About us and contact form -->
    </div>
  </div>

  <!-- Popup Modals -->
  <div id="actionPopup" class="popup">...</div>
  <div id="successPopup" class="popup">...</div>

  <!-- JavaScript Implementation -->
  <script>
    // Product Data
    const serviceProducts = [
      {
        id: 1,
        name: "Brickwork and Plastering",
        price: 1250,
        image: "images/brickwork.jpg",
        pricingInfo: "Mason: ₹1250/day"
      },
      // ... other products
    ];

    // Core Functions
    function showTab(tabId) {
      // Tab switching logic
    }

    function loadProducts(containerId) {
      // Product loading logic
    }

    function addToCart(productId, quantity) {
      // Cart management
    }

    // Customer Contact Functions
    function addCustomerContact(event) {
      event.preventDefault();
      // Form handling
    }

    // Initialization
    document.addEventListener("DOMContentLoaded", function() {
      // Setup event listeners
      // Load initial data
    });
  </script>
</body>
</html>
```

## Key Components

### 1. Navigation System
- Fixed sidebar with 5 main tabs
- Programmatic tab switching via `showTab()` function
- Search functionality (frontend only)

### 2. Product Management
- Two product grids (home featured and full products)
- Service cards with:
  - Image
  - Pricing information
  - Quantity selectors
  - Add to cart functionality

### 3. Customer Contact System
- Form for adding new contacts
- Contact list with filtering
- LocalStorage persistence
- CRUD operations:
  ```javascript
  // Example contact structure
  {
    name: "John Doe",
    mobile: "9876543210",
    work: "Brickwork",
    location: "Chennai"
  }
  ```

### 4. Shopping Cart
- Cart item listing with quantities
- Price calculations (subtotal, tax, shipping)
- Quantity adjustment controls
- Checkout button (simulated)

### 5. Company Information
- About section
- Service highlights
- Contact form with validation

## Data Management

### Product Data Structure
```javascript
{
  id: Number,
  name: String,
  price: Number,
  image: String,
  pricingInfo: String
}
```

### Cart Data Structure
```javascript
{
  productId: Number,
  quantity: Number,
  name: String,
  price: Number,
  image: String
}
```

## JavaScript API

### Core Functions
| Function | Parameters | Description |
|----------|------------|-------------|
| `showTab()` | tabId | Switches between application views |
| `loadProducts()` | containerId | Renders products into specified container |
| `addToCart()` | productId, quantity | Manages cart items |
| `updateCartUI()` | none | Refreshes cart display |

### Customer Contact API
| Function | Description |
|----------|-------------|
| `addCustomerContact()` | Handles form submission |
| `updateCustomerContactsList()` | Refreshes contact list |
| `filterContacts()` | Filters by work type |
| `deleteCustomerContact()` | Removes contacts |

## Usage Examples

### Adding a Product
```javascript
// In your product card HTML
<button onclick="addToCart(1, 1)">Add to Cart</button>
```

### Creating a New Contact
```javascript
// Form submission handler
document.getElementById('addMobileForm').addEventListener('submit', addCustomerContact);
```

## Responsive Design

### Breakpoints
- **Desktop**: >1024px (3-column grid)
- **Tablet**: 768px-1024px (2-column grid)
- **Mobile**: <768px (1-column stack)

### Adaptive Elements
- Flexible grids
- Responsive typography
- Mobile-friendly navigation

## Browser Support
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

Note: This is a frontend-only implementation using localStorage for data persistence. For a production environment, you would need to integrate with a backend service.
