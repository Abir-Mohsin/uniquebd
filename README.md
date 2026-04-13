<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>UniqueBD</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f5f5f5;
    }

    header {
      background: linear-gradient(45deg,#0d6efd,#00c6ff);
      color: white;
      padding: 20px;
      text-align: center;
      font-size: 26px;
      font-weight: bold;
    }

    .buttons {
      text-align: center;
      margin: 20px;
    }

    .buttons a {
      text-decoration: none;
      background: #198754;
      color: white;
      padding: 12px 20px;
      margin: 5px;
      border-radius: 25px;
      display: inline-block;
      font-weight: bold;
    }

    .section {
      padding: 30px 15px;
      text-align: center;
    }

    .products {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
    }

    .card {
      background: white;
      padding: 15px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      width: 260px;
      transition: 0.3s;
    }

    .card:hover {
      transform: scale(1.05);
    }

    .card img {
      width: 100%;
      border-radius: 10px;
    }

    .price {
      color: #e63946;
      font-weight: bold;
      font-size: 18px;
    }

    form {
      max-width: 400px;
      margin: auto;
      text-align: left;
    }

    input, textarea {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
    }

    button {
      width: 100%;
      padding: 12px;
      background: #0d6efd;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
    }

    .payment {
      margin-top: 15px;
      background: #fff3cd;
      padding: 10px;
      border-radius: 8px;
    }

    footer {
      background: #222;
      color: white;
      padding: 15px;
      text-align: center;
      margin-top: 20px;
    }
  </style>
</head>
<body>

<header>
  UniqueBD Store
</header>

<div class="buttons">
  <a href="#products">পণ্য দেখুন</a>
  <a href="#order">অর্ডার করুন</a>
  <a href="#contact">যোগাযোগ</a>
</div>

<section id="products" class="section">
  <h2>আমাদের পণ্য</h2>
  <div class="products">

    <div class="card">
      <img src="umbrella.jpg" alt="umbrella">
      <h3>ফাইবার ছাতা</h3>
      <p class="price">৳ 850</p>
      <p>মজবুত ও স্টাইলিশ</p>
    </div>

    <div class="card">
      <img src="fan.jpg" alt="fan">
      <h3>Rechargeable Fan</h3>
      <p class="price">৳ 1500</p>
      <p>লোডশেডিংয়ে সেরা সমাধান</p>
    </div>

  </div>
</section>

<section id="order" class="section">
  <h2>অর্ডার ফর্ম</h2>

  <form>
    <label>আপনার নাম</label>
    <input type="text" placeholder="নাম লিখুন" required>

    <label>মোবাইল নাম্বার</label>
    <input type="tel" placeholder="01XXXXXXXXX" required>

    <label>ঠিকানা</label>
    <textarea placeholder="আপনার ঠিকানা লিখুন" required></textarea>

    <button type="submit">অর্ডার সাবমিট</button>
  </form>

  <div class="payment">
    <p><strong>Payment Method:</strong></p>
    <p>📱 বিকাশ / নগদ: 0567828001</p>
  </div>

  <br>
  <a href="https://wa.me/880567828001" style="background:#25D366; color:white; padding:10px 20px; border-radius:5px; text-decoration:none;">WhatsApp Order</a>
</section>

<section id="contact" class="section">
  <h2>যোগাযোগ</h2>
  <p>📞 0567828001</p>
  <p>📧 jahidulislam202530@gmail.com</p>
</section>

<footer>
  © 2026 UniqueBD | Developed by You 🚀
</footer>

</body>
</html>
