<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Biodegradable Products | Eco-Friendly Living</title>
  <style>
    :root {
      --primary: #2e4d2c;
      --accent: #8fb339;
      --bg-light: #f4f3e8;
      --text: #333;
      --white: #ffffff;
    }

    #preloader {
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background-color: #fff;
      display: flex; flex-direction: column; justify-content: center; align-items: center;
      z-index: 9999; transition: opacity 0.5s ease;
    }
    #preloader img { width: 180px; height: auto; }
    #preloader p { margin-top: 20px; font-family: 'Segoe UI', sans-serif; color: var(--primary); font-weight: bold; letter-spacing: 2px; }

    * { margin:0; padding:0; box-sizing:border-box; font-family: 'Segoe UI', sans-serif; }
    
    body { 
      background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
                  url('https://hd.wallpaperswide.com/thumbs/sprout_plant-t2.jpg') no-repeat center center fixed; 
      background-size: cover;
      color: var(--text); 
      line-height: 1.6; 
      overflow-x: hidden;
      scroll-behavior: smooth;
    }

    /* TOP SEARCH BAR AREA */
    .top-bar {
      background: var(--white);
      padding: 10px 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 2000;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .search-wrapper { position: relative; width: 100%; max-width: 600px; }

    .search-container {
      display: flex; background: #eee; padding: 5px;
      border-radius: 50px; width: 100%;
    }
    .search-container input {
      border: none; padding: 10px 20px; flex-grow: 1; border-radius: 50px; outline: none; font-size: 0.9rem; background: transparent;
    }
    .recent-searches {
      position: absolute; top: 110%; left: 0; width: 100%;
      background: white; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      display: none; padding: 10px; z-index: 2001;
    }
    .recent-item { padding: 8px 15px; cursor: pointer; border-radius: 5px; font-size: 0.85rem; }
    .recent-item:hover { background: var(--bg-light); color: var(--primary); }
    .search-wrapper:hover .recent-searches { display: block; }

    #pot-counter {
      position: fixed; bottom: 20px; right: 20px;
      background: var(--primary); color: white;
      padding: 15px 25px; border-radius: 50px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      z-index: 1000; font-weight: bold; cursor: pointer;
      display: flex; align-items: center; gap: 10px;
    }

    .hero {
      height: 40vh;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center; color: white; padding: 0 20px;
    }

    .container {
      max-width: 1100px; margin: -40px auto 30px;
      background: rgba(244, 243, 232, 0.98); 
      border-radius: 15px; padding: 40px;
      box-shadow: 0 10px 40px rgba(0,0,0,0.4);
      position: relative;
    }

    header {
      display: flex; justify-content: space-between; align-items: center;
      margin-bottom: 40px; border-bottom: 2px solid #dcd8c5; padding-bottom: 20px;
    }
    .logo { color: var(--primary); font-weight: bold; font-size: 24px; }

    nav ul { display: flex; list-style: none; gap: 10px; align-items: center;}
    .nav-btn {
      background: var(--primary); color: white; padding: 8px 15px;
      border-radius: 5px; text-decoration: none; font-weight: 600;
      font-size: 13px; border: none; cursor: pointer;
    }

    /* LOGIN STYLES */
    #user-profile-btn {
      background: var(--white);
      color: var(--primary);
      border: 2px solid var(--primary);
      display: none; /* Hidden by default until login */
    }

    .login-form-container {
      display: flex;
      flex-direction: column;
      gap: 15px;
      margin-top: 20px;
    }
    .login-form-container input {
      padding: 12px;
      border: 1px solid #ddd;
      border-radius: 8px;
      outline: none;
    }
    .login-submit {
      background: var(--primary);
      color: white;
      border: none;
      padding: 12px;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
    }

    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 25px; }
    
    .card {
      background: white; border-radius: 12px; padding: 20px; border: 1px solid #eee;
      text-align: center; display: flex; flex-direction: column; justify-content: space-between;
    }
    .product-image {
      max-width: 100%;
      height: 150px;
      object-fit: contain;
      margin-bottom: 15px;
      border-radius: 8px;
    }
    .price-tag { color: var(--accent); font-weight: bold; font-size: 1.2rem; margin: 10px 0; }
    
    .btn-group { display: flex; gap: 5px; flex-direction: column; }
    .add-btn { background: var(--accent); color: white; border: none; padding: 10px; border-radius: 5px; cursor: pointer; font-weight: bold; }
    .info-btn { background: #555; color: white; border: none; padding: 8px; border-radius: 5px; cursor: pointer; font-size: 0.8rem; margin-top: 5px; }

    .hidden-product { display: none; }
    .view-more-container { text-align: center; margin-top: 40px; }
    #viewMoreBtn {
      background: transparent; border: 2px solid var(--primary); color: var(--primary);
      padding: 10px 30px; border-radius: 30px; cursor: pointer; font-weight: bold;
    }

    .modal-overlay {
      display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.7); z-index: 10000; justify-content: center; align-items: center;
      padding: 20px;
    }
    .modal-content {
      background: white; padding: 30px; border-radius: 15px; max-width: 500px; width: 100%;
      position: relative; max-height: 80vh; overflow-y: auto;
    }
    .close-modal { position: absolute; right: 20px; top: 15px; font-size: 30px; cursor: pointer; }

    footer { text-align: center; padding: 30px 0; font-size: 0.85rem; color: #555; }
    .footer-links span { cursor: pointer; color: var(--primary); font-weight: bold; margin: 0 10px; text-decoration: underline; }

    @keyframes fadeIn { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }
    
    /* Utility for checkout */
    .checkout-btn {
      display: block; width: 100%; background: #25D366; color: white; text-align: center; 
      padding: 15px; border-radius: 10px; text-decoration: none; font-weight: bold; margin-top: 20px;
    }
    .pot-item { display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #eee; padding: 10px 0; }
    .qty-btn { background: #ddd; border: none; padding: 5px 10px; cursor: pointer; border-radius: 4px; }

    /* LOCATION BUTTON STYLE */
    .location-link {
      display: inline-block;
      margin-top: 10px;
      color: var(--primary);
      font-weight: bold;
      text-decoration: none;
      border: 1px solid var(--primary);
      padding: 5px 15px;
      border-radius: 20px;
      transition: 0.3s;
    }
    .location-link:hover {
      background: var(--primary);
      color: white;
    }
  </style>
</head>
<body>

  <div id="preloader">
    <img src="https://classroomclipart.com/image/content2/30370/thumb.gif" alt="Eco Loading">
    <p>GROWING SUSTAINABILITY...</p>
  </div>

  <div class="top-bar">
    <div class="search-wrapper">
        <div class="search-container">
            <input type="text" placeholder="Search for products or locations...">
            <button class="search-btn" style="background:none; border:none; padding-right:15px; cursor:pointer;">🔍</button>
        </div>
        <div class="recent-searches">
            <div style="font-size: 0.7rem; color: #999; margin-bottom: 5px; padding-left: 10px;">RECENT SEARCHES</div>
            <div class="recent-item" onclick="alert('Viewing Adoni Inventory')">📍 Adoni</div>
            <div class="recent-item" onclick="alert('Viewing Yemmiganur Inventory')">📍 Yemmiganur</div>
        </div>
    </div>
  </div>

  <div id="pot-counter" onclick="openModal('potModal')">
    🏺 My Pot: <span id="pot-count">0</span> Items
  </div>

  <section class="hero">
    <h1>Sustainable Living</h1>
    <p>Replace plastic with nature. 100% Biodegradable solutions.</p>
  </section>

  <div class="container">
    <header>
      <div class="logo">Eco-Products</div>
      <nav>
        <ul>
          <li><button class="nav-btn" onclick="location.reload()">Home</button></li>
          <li><a href="#products" class="nav-btn">Products</a></li>
          <li><a href="#contact" class="nav-btn">Contact</a></li>
          <li><button id="login-nav-btn" class="nav-btn" onclick="openModal('loginModal')" style="background-color: var(--accent);">Login</button></li>
          <li><button id="user-profile-btn" class="nav-btn" onclick="alert('Profile Details Coming Soon!')">👤 <span id="display-name">User</span></button></li>
        </ul>
      </nav>
    </header>

    <section id="products">
      <h2>Featured Products</h2>
      <div class="grid">
        <div class="card">
          <img src="https://kamereo.vn/blog/wp-content/uploads/2024/05/biodegradable-bags-1.jpg" alt="Bags" class="product-image">
          <h3>Bags</h3>
          <p class="price-tag">₹10 /Pc</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Bags', 10)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Bags', 'Eco-friendly carry bags made from biodegradable materials; reduce plastic pollution.')">View Details</button>
          </div>
        </div>
        <div class="card">
          <img src="https://m.media-amazon.com/images/I/71Ljx0Qz6hL._AC_UF894,1000_QL80_.jpg" alt="Plates" class="product-image">
          <h3>Plates</h3>
          <p class="price-tag">₹3 /Pc</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Plates', 3)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Plates', 'Disposable plates made from natural materials like leaves or paper.')">View Details</button>
          </div>
        </div>
        <div class="card">
          <img src="https://5.imimg.com/data5/SH/WQ/ZF/SELLER-10830238/8cp-biodegradable-500x500.jpg" alt="Trays" class="product-image">
          <h3>Trays</h3>
          <p class="price-tag">₹30</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Trays', 50)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Trays', 'Used for serving or packaging, made from eco-safe materials.')">View Details</button>
          </div>
        </div>

        <div class="card hidden-product">
          <img src="https://cdni.haymarketmedia.in/utils/ImageResizer.ashx?n=https://img.haymarketmedia.in/printweek/b88222f4-7e4e-456d-8100-76f1dcf3117a.jpg&w=735&h=490&q=80" alt="Bottles" class="product-image">
          <h3>Bottles</h3>
          <p class="price-tag">₹30 /Pc</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Bottles', 30)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Bottles', 'Biodegradable or recyclable bottles for liquids.')">View Details</button>
          </div>
        </div>
        <div class="card hidden-product">
          <img src="https://www.greenhandle.in/blog/wp-content/uploads/2017/08/spoon1.jpg" alt="Spoons" class="product-image">
          <h3>Spoons</h3>
          <p class="price-tag">₹5 /Pc</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Spoons', 5)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Spoons', 'Made from wood, bamboo, or other natural materials.')">View Details</button>
          </div>
        </div>
        <div class="card hidden-product">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQQp-tYt_7yz5rWMMAL4V9JB0p7HwrRYY0uLw&s" alt="Bamboo Pens" class="product-image">
          <h3>Bamboo Pens</h3>
          <p class="price-tag">₹5 /Pc</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Bamboo Pens', 5)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Bamboo Pens', 'Sustainable writing tools made from bamboo.')">View Details</button>
          </div>
        </div>
        <div class="card hidden-product">
          <img src="https://organicbazar.net/cdn/shop/products/Cow-Dung-Manure.jpg?v=1763882767&width=1445" alt="Cow Dung Manure" class="product-image">
          <h3>Cow Dung Manure</h3>
          <p class="price-tag">₹249 /Bag</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Cow Dung Manure', 249)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Cow Dung Manure', 'Traditional manure that enriches soil with nutrients.')">View Details</button>
          </div>
        </div>
        <div class="card hidden-product">
          <img src="https://images.squarespace-cdn.com/content/v1/660b1679b9474e2fa179dbb4/42c8cf8d-a1b5-4350-99ce-2fe36672dca6/360_F_1464751144_U1YRRgxGqMMygaAFwBoHeW9Ciddxe1Og.jpg" alt="Vermicompost" class="product-image">
          <h3>Vermicompost</h3>
          <p class="price-tag">₹249 /Bag</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Vermicompost', 249)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Vermicompost', 'Compost produced using earthworms; highly nutritious for plants.')">View Details</button>
          </div>
        </div>
        <div class="card hidden-product">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTnBKV3eutd__wS9qnP7hMrqDapPwJYDlDkIQ&s" alt="Organic Fertilizer" class="product-image">
          <h3>Organic Fertilizer</h3>
          <p class="price-tag">₹249 /Bag</p>
          <div class="btn-group">
            <button class="add-btn" onclick="addToPot('Organic Fertilizer', 249)">Add to Pot</button>
            <button class="info-btn" onclick="showInfo('Organic Fertilizer', 'Chemical-free plant nutrients for healthy crop growth.')">View Details</button>
          </div>
        </div>
      </div>

      <div class="view-more-container">
        <button id="viewMoreBtn" onclick="toggleProducts()">More Products</button>
      </div>
    </section>

    <section id="contact" style="margin-top: 60px;">
      <h2>Contact Us</h2>
      <div style="background: white; padding: 25px; border-radius: 12px; border: 1px solid #ddd;">
        <p><strong>Manager:</strong> Karthik</p>
        <p><strong>Phone:</strong> +91 9701099846</p>
        <p><strong>Service Area:</strong> Adoni & Yemmiganur</p>
        <p><strong>Store Location:</strong> <a href="https://maps.app.goo.gl/MnUsXMXvM4oUWizP8" target="_blank" class="location-link">📍 View on Google Maps</a></p>
      </div>
    </section>

    <footer>
      <div class="footer-links">
        <span onclick="openModal('aboutModal')">About Us</span> | 
        <span onclick="openModal('securityModal')">Security Policy</span>
      </div>
      <p style="margin-top: 15px;">© 2026 Biodegradable Products</p>
    </footer>
  </div>

  <div id="loginModal" class="modal-overlay">
    <div class="modal-content">
      <span class="close-modal" onclick="closeModal('loginModal')">×</span>
      <h2 style="color: var(--primary);">Login to Your Account</h2>
      <p style="color: #666; font-size: 0.9rem;">Access eco-friendly living today.</p>
      
      <form onsubmit="handleLogin(event)" class="login-form-container">
        <input type="text" id="login-name" placeholder="Full Name" required>
        <input type="email" id="login-email" placeholder="Email Address" required>
        <input type="password" placeholder="Password" required>
        <button type="submit" class="login-submit">Login</button>
      </form>
    </div>
  </div>

  <div id="potModal" class="modal-overlay">
    <div class="modal-content">
      <span class="close-modal" onclick="closeModal('potModal')">×</span>
      <h2>Your Eco-Pot</h2>
      <div id="pot-list-items"></div>
      <div style="margin-top: 20px; font-size: 1.5rem; font-weight: bold; text-align: right; color: var(--primary);">
        Total: ₹<span id="grand-total">0</span>
      </div>
      <button class="checkout-btn" onclick="checkout()">Checkout on WhatsApp</button>
    </div>
  </div>

  <div id="infoModal" class="modal-overlay">
    <div class="modal-content">
      <span class="close-modal" onclick="closeModal('infoModal')">×</span>
      <h2 id="infoTitle">Product Detail</h2>
      <p id="infoBody" style="margin-top:20px; line-height:1.8; color:#555;"></p>
    </div>
  </div>

  <div id="aboutModal" class="modal-overlay">
    <div class="modal-content">
      <span class="close-modal" onclick="closeModal('aboutModal')">×</span>
      <h2>About Our Store</h2>
      <div style="margin-top:20px; line-height:1.8; color:#555;">
        <p>Welcome to <strong>Eco-Products</strong>. We are a locally operated business serving <strong>Adoni</strong> and <strong>Yemmiganur</strong> with a mission to eliminate single-use plastics.</p>
        <br>
        <p>Our catalog features carefully selected biodegradable items designed for daily use, catering to eco-conscious individuals and businesses. Managed by Karthik, we prioritize customer satisfaction and environmental health in every transaction.</p>
      </div>
    </div>
  </div>

  <div id="securityModal" class="modal-overlay">
    <div class="modal-content">
      <span class="close-modal" onclick="closeModal('securityModal')">×</span>
      <h2>Security & Privacy Policy</h2>
      <div style="margin-top:20px; line-height:1.6; color:#555;">
        <p><strong>1. Data Collection:</strong> We do not store your personal browsing data. The "Pot" functionality is handled locally on your device for your convenience.</p>
        <br>
        <p><strong>2. Transaction Security:</strong> All orders are completed via WhatsApp messaging. We do not process payments directly on this website, ensuring your financial information remains private.</p>
        <br>
        <p><strong>3. Contact Policy:</strong> Your contact information is only used by our manager to fulfill your specific order inquiry and is never shared with third-party advertisers.</p>
      </div>
    </div>
  </div>

  <script>
    let pot = {};

    window.addEventListener('load', () => {
      setTimeout(() => {
        document.getElementById('preloader').style.opacity = '0';
        setTimeout(() => document.getElementById('preloader').style.display = 'none', 500);
      }, 800);
    });

    // LOGIN LOGIC
    function handleLogin(event) {
      event.preventDefault();
      const userName = document.getElementById('login-name').value;
      
      // Update UI
      document.getElementById('login-nav-btn').style.display = 'none';
      document.getElementById('user-profile-btn').style.display = 'block';
      document.getElementById('display-name').innerText = userName;
      
      closeModal('loginModal');
      alert('Welcome back, ' + userName + '!');
    }

    function showInfo(title, desc) {
      document.getElementById('infoTitle').innerText = title;
      document.getElementById('infoBody').innerText = desc;
      openModal('infoModal');
    }

    function toggleProducts() {
      const hidden = document.querySelectorAll('.hidden-product');
      const btn = document.getElementById('viewMoreBtn');
      if (btn.innerText.includes('More')) {
        hidden.forEach(i => i.style.display = 'flex');
        btn.innerText = 'Show Less';
      } else {
        hidden.forEach(i => i.style.display = 'none');
        btn.innerText = 'More Products';
        window.location.href = "#products";
      }
    }

    function addToPot(name, price) {
      if(pot[name]) pot[name].qty += 1;
      else pot[name] = { qty: 1, price: price };
      updatePotUI();
      const count = document.getElementById('pot-count');
      count.style.transform = 'scale(1.2)';
      setTimeout(() => count.style.transform = 'scale(1)', 200);
    }

    function updateQty(name, delta) {
      pot[name].qty += delta;
      if(pot[name].qty <= 0) delete pot[name];
      updatePotUI();
    }

    function updatePotUI() {
      const list = document.getElementById('pot-list-items');
      const countLabel = document.getElementById('pot-count');
      const totalLabel = document.getElementById('grand-total');
      list.innerHTML = "";
      let total = 0; let totalQty = 0;

      for (let item in pot) {
        let itemTotal = pot[item].qty * pot[item].price;
        total += itemTotal; totalQty += pot[item].qty;
        list.innerHTML += `<div class="pot-item">
            <div><strong>${item}</strong><br><small>₹${pot[item].price}</small></div>
            <div>
              <button class="qty-btn" onclick="updateQty('${item}', -1)">-</button>
              <span style="margin:0 10px">${pot[item].qty}</span>
              <button class="qty-btn" onclick="updateQty('${item}', 1)">+</button>
            </div>
          </div>`;
      }
      if(totalQty === 0) list.innerHTML = '<p style="text-align:center; padding:20px;">Your pot is empty!</p>';
      countLabel.innerText = totalQty;
      totalLabel.innerText = total.toLocaleString('en-IN');
    }

    function checkout() {
      if (Object.keys(pot).length === 0) return alert("Pot is empty!");
      let msg = "Eco Order Inquiry:%0A";
      for (let item in pot) msg += `- ${item}: ${pot[item].qty}%0A`;
      window.open(`https://wa.me/919701099846?text=${msg}`, '_blank');
    }

    function openModal(id) { document.getElementById(id).style.display = 'flex'; }
    function closeModal(id) { document.getElementById(id).style.display = 'none'; }
    window.onclick = (e) => { if(e.target.className === 'modal-overlay') e.target.style.display = 'none'; }
  </script>
</body>
</html>
