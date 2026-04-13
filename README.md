<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ইউনিকবিডি - ছাতা, ফ্যান ও টর্চ লাইট</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        /* CSS Variables */
        :root {
            --primary: #FF6B00;
            --primary-dark: #E05E00;
            --secondary: #1A1A2E;
            --accent: #00D4AA;
            --bg-light: #F8F9FC;
            --text-dark: #1A1A2E;
            --text-light: #6B7280;
            --white: #FFFFFF;
            --shadow: 0 4px 24px rgba(0,0,0,0.08);
            --shadow-lg: 0 12px 40px rgba(0,0,0,0.12);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Noto Sans Bengali', sans-serif;
            color: var(--text-dark);
            background: var(--bg-light);
            line-height: 1.6;
        }

        /* Navbar */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(0,0,0,0.05);
            transition: 0.3s;
        }

        .navbar.scrolled {
            box-shadow: var(--shadow);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }

        .logo {
            font-size: 24px;
            font-weight: 800;
            color: var(--secondary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logo span { color: var(--primary); }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-light);
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-links a:hover { color: var(--primary); }

        .nav-btn {
            background: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
        }

        .nav-btn:hover { background: var(--primary-dark); }

        /* Hero Section */
        .hero {
            padding: 140px 20px 80px;
            background: linear-gradient(135deg, #FFF5EB 0%, #F0F7FF 100%);
            text-align: center;
        }

        .hero-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 48px;
            font-weight: 900;
            margin-bottom: 20px;
            color: var(--secondary);
        }

        .hero h1 span { color: var(--primary); }

        .hero p {
            font-size: 18px;
            color: var(--text-light);
            margin-bottom: 30px;
        }

        /* Products Grid */
        .section-padding { padding: 80px 20px; }
        .container { max-width: 1200px; margin: 0 auto; }
        .section-title { text-align: center; margin-bottom: 50px; }
        .section-title h2 { font-size: 32px; font-weight: 800; }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: 0.3s;
            text-align: center;
            padding-bottom: 25px;
        }

        .product-card:hover { transform: translateY(-10px); box-shadow: var(--shadow-lg); }

        .product-img {
            height: 200px;
            background: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
        }

        .product-info { padding: 20px; }
        .product-info h3 { margin-bottom: 10px; font-size: 20px; }
        .price { color: var(--primary); font-size: 24px; font-weight: 800; margin-bottom: 15px; }

        .order-btn {
            background: var(--secondary);
            color: white;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
            transition: 0.3s;
        }

        .order-btn:hover { background: var(--primary); }

        /* Footer */
        footer {
            background: var(--secondary);
            color: white;
            padding: 50px 20px;
            text-align: center;
        }

        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #25D366;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            text-decoration: none;
            z-index: 1000;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 32px; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#" class="logo">ইউনিক<span>বিডি</span></a>
            <ul class="nav-links">
                <li><a href="#home">হোম</a></li>
                <li><a href="#products">পণ্যসমূহ</a></li>
                <li><a href="#contact">যোগাযোগ</a></li>
            </ul>
            <a href="https://wa.me/8801700000000" class="nav-btn">অর্ডার করুন</a>
        </div>
    </nav>

    <section class="hero" id="home">
        <div class="hero-container">
            <h1>আপনার দৈনন্দিন জীবনের <span>সেরা সঙ্গী</span></h1>
            <p>সেরা মানের ছাতা, রিচার্জেবল ফ্যান এবং টর্চ লাইট কিনুন সাশ্রয়ী মূল্যে। সারা বাংলাদেশে ক্যাশ অন ডেলিভারি!</p>
            <a href="#products" class="order-btn" style="background: var(--primary); padding: 15px 40px; font-size: 18px;">🛍️ কেনাকাটা শুরু করুন</a>
        </div>
    </section>

    <section class="section-padding container" id="products">
        <div class="section-title">
            <h2>আমাদের পণ্যসমূহ</h2>
            <p>সেরা মানের পণ্য বেছে নিন</p>
        </div>
        <div class="products-grid">
            <!-- Product 1 -->
            <div class="product-card">
                <div class="product-img">☂️</div>
                <div class="product-info">
                    <h3>অটোমেটিক ফোল্ডিং ছাতা</h3>
                    <div class="price">৳৩৯০</div>
                    <a href="https://wa.me/8801700000000?text=আমি ছাতাটি কিনতে চাই" class="order-btn">অর্ডার করুন</a>
                </div>
            </div>
            <!-- Product 2 -->
            <div class="product-card">
                <div class="product-img">🌀</div>
                <div class="product-info">
                    <h3>রিচার্জেবল মিনি ফ্যান</h3>
                    <div class="price">৳৫৫০</div>
                    <a href="https://wa.me/8801700000000?text=আমি ফ্যানটি কিনতে চাই" class="order-btn">অর্ডার করুন</a>
                </div>
            </div>
            <!-- Product 3 -->
            <div class="product-card">
                <div class="product-img">🔦</div>
                <div class="product-info">
                    <h3>হাই-পাওয়ার টর্চ লাইট</h3>
                    <div class="price">৳২৯০</div>
                    <a href="https://wa.me/8801700000000?text=আমি টর্চ লাইটটি কিনতে চাই" class="order-btn">অর্ডার করুন</a>
                </div>
            </div>
        </div>
    </section>

    <footer id="contact">
        <p>© ২০২৫ ইউনিকবিডি - সর্বস্বত্ব সংরক্ষিত</p>
        <p style="margin-top: 10px; font-size: 14px; opacity: 0.7;">যোগাযোগ: +৮৮০ ১৭XX-XXXXXX</p>
    </footer>

    <a href="https://wa.me/8801700000000" class="whatsapp-float" target="_blank">
        <svg width="35" height="35" fill="currentColor" viewBox="0 0 16 16">
            <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
        </svg>
    </a>

    <script>
        window.onscroll = function() {
            var nav = document.getElementById('navbar');
            if (window.pageYOffset > 50) {
                nav.classList.add('scrolled');
            } else {
                nav.classList.remove('scrolled');
            }
        };
    </script>
</body>
</html>
