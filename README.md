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
      max-width: 420px;
      margin: auto;
      text-align: left;
      background: white;
      padding: 20px;
      border-radius: 10px;
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
      cursor: pointer;
    }

    .payment {
      margin-top: 15px;
      background: #fff3cd;
      padding: 10px;
      border-radius: 8px;
    }

    .wa-btn {
      display: inline-block;
      margin-top: 10px;
      background: #25D366;
      color: white;
      padding: 12px 20px;
      border-radius: 8px;
      text-decoration: none;
      font-weight: bold;
    }

    iframe {
      width: 100%;
      height: 600px;
      border: none;
      margin-top: 10px;
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
      <img src="umbrella.jpg" alt="Umbrella">
      <h3>ফাইবার ছাতা</h3>
      <p class="price">৳ 850</p>
    </div>

    <div class="card">
      <img src="fan.jpg" alt="Fan">
      <h3>Rechargeable Fan</h3>
      <p class="price">৳ 1500</p>
    </div>

  </div>
</section>

<section id="order" class="section">
  <h2>অর্ডার করুন</h2>

  <form>
    <label>আপনার নাম</label>
    <input type="text" id="name" placeholder="নাম লিখুন">

    <label>মোবাইল নাম্বার</label>
    <input type="tel" id="phone" placeholder="01788876206">

    <label>ঠিকানা</label>
    <textarea id="address" placeholder="আপনার ঠিকানা"></textarea>

    <button type="button" onclick="sendWhatsApp()">WhatsApp এ অর্ডার পাঠান</button>
  </form>

  <a class="wa-btn" href="https://wa.me/8801788876206" target="_blank">Direct WhatsApp</a>

  <div class="payment">
    <p><strong>Google Form (Backup Order System):</strong></p>
    <p>নিচের ফর্মে অর্ডার দিন 👇</p>

    <!-- এখানে তোমার Google Form link বসাবে -->
    <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSeE7z37kBYqvSbVbDDu420uZPFA-tu4r3iqmSeTiuepZJUUfA/viewform?embedded=true" width="640" height="724" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
  </div>
</section>

<section id="contact" class="section">
  <h2>যোগাযোগ</h2>
  <p>📞 8801788876206</p>
  <p>📧 abirmohsin02@gmail.com</p>
</section>

<footer>
  © 2026 UniqueBD | All rights reserved
</footer>

<script>
function sendWhatsApp() {
  let name = document.getElementById('name').value;
  let phone = document.getElementById('phone').value;
  let address = document.getElementById('address').value;

  let message = `নতুন অর্ডার:%0Aনাম: ${name}%0Aমোবাইল: ${phone}%0Aঠিকানা: ${address}`;

  let url = `https://wa.me/8801788876206?text=${message}`;
  window.open(url, '_blank');
}
</script>

</body>
</html>
