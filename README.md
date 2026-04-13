<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=.5">
    <title>ইউনিকবিডি - ছাতা, ফ্যান ও টর্চ লাইট</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@300;400;500;600;700;800;900&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

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

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Noto Sans Bengali', sans-serif;
            color: var(--text-dark);
            background: var(--bg-light);
            overflow-x: hidden;
        }

        /* === NAVBAR === */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            box-shadow: var(--shadow);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 70px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
        }

        .logo-icon {
            width: 42px;
            height: 42px;
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            color: white;
            font-weight: 800;
            box-shadow: 0 4px 12px rgba(255,107,0,0.3);
        }

        .logo-text {
            font-size: 22px;
            font-weight: 800;
            color: var(--secondary);
        }

        .logo-text span {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-light);
            font-weight: 500;
            font-size: 15px;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-btn {
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            color: white;
            border: none;
            padding: 10px 24px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 12px rgba(255,107,0,0.3);
            font-family: inherit;
        }

        .nav-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255,107,0,0.4);
        }

        .mobile-toggle {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            background: none;
            border: none;
            padding: 8px;
        }

        .mobile-toggle span {
            width: 24px;
            height: 2.5px;
            background: var(--secondary);
            border-radius: 2px;
            transition: all 0.3s;
        }

        /* === HERO === */
        .hero {
            padding: 140px 24px 80px;
            background: linear-gradient(160deg, #FFF5EB 0%, #F0F7FF 50%, #F0FFF8 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(255,107,0,0.08), transparent 70%);
            border-radius: 50%;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -10%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0,212,170,0.06), transparent 70%);
            border-radius: 50%;
        }

        .hero-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(255,107,0,0.1);
            color: var(--primary);
            padding: 8px 16px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 20px;
            animation: fadeInUp 0.6s ease;
        }

        .hero-badge .pulse {
            width: 8px;
            height: 8px;
            background: var(--accent);
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.5); }
        }

        .hero h1 {
            font-size: 48px;
            font-weight: 900;
            line-height: 1.2;
            margin-bottom: 20px;
            color: var(--secondary);
            animation: fadeInUp 0.6s ease 0.1s both;
        }

        .hero h1 .highlight {
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 17px;
            color: var(--text-light);
            line-height: 1.8;
            margin-bottom: 32px;
            max-width: 480px;
            animation: fadeInUp 0.6s ease 0.2s both;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            animation: fadeInUp 0.6s ease 0.3s both;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            color: white;
            border: none;
            padding: 14px 32px;
            border-radius: 50px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 16px rgba(255,107,0,0.3);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-family: inherit;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 24px rgba(255,107,0,0.4);
        }

        .btn-secondary {
            background: var(--white);
            color: var(--secondary);
            border: 2px solid #E5E7EB;
            padding: 14px 32px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-family: inherit;
        }

        .btn-secondary:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: translateY(-3px);
        }

        .hero-stats {
            display: flex;
            gap: 40px;
            margin-top: 40px;
            animation: fadeInUp 0.6s ease 0.4s both;
        }

        .stat h3 {
            font-size: 28px;
            font-weight: 800;
            color: var(--primary);
        }

        .stat p {
            font-size: 13px;
            color: var(--text-light);
            margin: 0;
        }

        .hero-visual {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: fadeInRight 0.8s ease 0.3s both;
        }

        .hero-cards {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
            transform: rotate(-3deg);
        }

        .hero-card {
            background: var(--white);
            border-radius: 20px;
            padding: 24px;
            box-shadow: var(--shadow);
            text-align: center;
            transition: all 0.4s ease;
        }

        .hero-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
        }

        .hero-card:nth-child(2) {
            transform: translateY(20px);
        }

        .hero-card:nth-child(3) {
            transform: translateY(-20px);
        }

        .hero-card .emoji {
            font-size: 48px;
            margin-bottom: 12px;
            display: block;
        }

        .hero-card h4 {
            font-size: 15px;
            font-weight: 700;
            margin-bottom: 4px;
        }

        .hero-card p {
            font-size: 13px;
            color: var(--text-light);
            margin: 0;
        }

        /* === FEATURES === */
        .features {
            padding: 100px 24px;
            background: var(--white);
        }

        .section-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-tag {
            display: inline-block;
            background: rgba(255,107,0,0.1);
            color: var(--primary);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 16px;
        }

        .section-header h2 {
            font-size: 36px;
            font-weight: 800;
            margin-bottom: 12px;
        }

        .section-header p {
            font-size: 16px;
            color: var(--text-light);
            max-width: 500px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 24px;
        }

        .feature-card {
            background: var(--bg-light);
            border-radius: 20px;
            padding: 36px 28px;
            transition: all 0.4s ease;
            border: 1px solid transparent;
            cursor: default;
        }

        .feature-card:hover {
            background: var(--white);
            border-color: rgba(255,107,0,0.15);
            transform: translateY(-6px);
            box-shadow: var(--shadow-lg);
        }

        .feature-icon {
            width: 56px;
            height: 56px;
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 26px;
            margin-bottom: 20px;
        }

        .feature-card:nth-child(1) .feature-icon { background: rgba(255,107,0,0.12); }
        .feature-card:nth-child(2) .feature-icon { background: rgba(0,212,170,0.12); }
        .feature-card:nth-child(3) .feature-icon { background: rgba(99,102,241,0.12); }
        .feature-card:nth-child(4) .feature-icon { background: rgba(236,72,153,0.12); }
        .feature-card:nth-child(5) .feature-icon { background: rgba(245,158,11,0.12); }
        .feature-card:nth-child(6) .feature-icon { background: rgba(16,185,129,0.12); }

        .feature-card h3 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .feature-card p {
            font-size: 14px;
            color: var(--text-light);
            line-height: 1.7;
        }

        /* === PRODUCTS === */
        .products {
            padding: 100px 24px;
            background: var(--bg-light);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 28px;
        }

        .product-card {
            background: var(--white);
            border-radius: 24px;
            overflow: hidden;
            transition: all 0.4s ease;
            box-shadow: var(--shadow);
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
        }

        .product-badge {
            position: absolute;
            top: 16px;
            left: 16px;
            background: var(--primary);
            color: white;
            padding: 4px 12px;
            border-radius: 50px;
            font-size: 12px;
            font-weight: 600;
            z-index: 2;
        }

        .product-image {
            height: 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            position: relative;
            overflow: hidden;
        }

        .product-card:nth-child(1) .product-image { background: linear-gradient(135deg, #FFF5EB, #FFE8D6); }
        .product-card:nth-child(2) .product-image { background: linear-gradient(135deg, #EBF5FF, #D6E8FF); }
        .product-card:nth-child(3) .product-image { background: linear-gradient(135deg, #F0FFF4, #D6FFE8); }
        .product-card:nth-child(4) .product-image { background: linear-gradient(135deg, #FFF0F5, #FFD6E8); }
        .product-card:nth-child(5) .product-image { background: linear-gradient(135deg, #FFFBEB, #FFF3C4); }
        .product-card:nth-child(6) .product-image { background: linear-gradient(135deg, #F5F0FF, #E8D6FF); }

        .product-info {
            padding: 24px;
        }

        .product-category {
            font-size: 12px;
            color: var(--primary);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 6px;
        }

        .product-info h3 {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .product-info .desc {
            font-size: 13px;
            color: var(--text-light);
            line-height: 1.6;
            margin-bottom: 16px;
        }

        .product-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .price {
            font-size: 22px;
            font-weight: 800;
            color: var(--primary);
        }

        .price small {
            font-size: 13px;
            color: var(--text-light);
            text-decoration: line-through;
            margin-left: 6px;
            font-weight: 400;
        }

        .add-cart {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            border: none;
            color: white;
            font-size: 20px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 12px rgba(255,107,0,0.3);
        }

        .add-cart:hover {
            transform: scale(1.1);
        }

        /* === OFFERS === */
        .offers {
            padding: 100px 24px;
            background: var(--white);
        }

        .offer-banner {
            max-width: 1200px;
            margin: 0 auto;
            background: linear-gradient(135deg, var(--secondary) 0%, #16213E 100%);
            border-radius: 32px;
            padding: 60px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .offer-banner::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255,107,0,0.15), transparent 70%);
            border-radius: 50%;
        }

        .offer-content {
            position: relative;
            z-index: 1;
        }

        .offer-content .tag {
            display: inline-block;
            background: rgba(255,107,0,0.2);
            color: var(--primary);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .offer-content h2 {
            font-size: 36px;
            font-weight: 900;
            color: var(--white);
            margin-bottom: 16px;
            line-height: 1.3;
        }

        .offer-content p {
            color: rgba(255,255,255,0.7);
            font-size: 15px;
            line-height: 1.7;
            margin-bottom: 28px;
        }

        .countdown {
            display: flex;
            gap: 16px;
            margin-bottom: 28px;
        }

        .countdown-item {
            background: rgba(255,255,255,0.1);
            border-radius: 16px;
            padding: 16px 20px;
            text-align: center;
            min-width: 72px;
            backdrop-filter: blur(10px);
        }

        .countdown-item .num {
            font-size: 28px;
            font-weight: 800;
            color: var(--primary);
            display: block;
        }

        .countdown-item .label {
            font-size: 11px;
            color: rgba(255,255,255,0.6);
            margin-top: 4px;
            display: block;
        }

        .offer-visual {
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 120px;
            position: relative;
            z-index: 1;
        }

        .offer-visual .floating {
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* === REVIEWS === */
        .reviews {
            padding: 100px 24px;
            background: var(--bg-light);
        }

        .reviews-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 24px;
        }

        .review-card {
            background: var(--white);
            border-radius: 20px;
            padding: 32px;
            box-shadow: var(--shadow);
            transition: all 0.3s;
        }

        .review-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
        }

        .stars {
            color: #FBBF24;
            font-size: 18px;
            margin-bottom: 16px;
        }

        .review-card .text {
            font-size: 14px;
            color: var(--text-light);
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .reviewer {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .reviewer-avatar {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            font-weight: 700;
            color: white;
        }

        .review-card:nth-child(1) .reviewer-avatar { background: linear-gradient(135deg, #FF6B00, #FF8C38); }
        .review-card:nth-child(2) .reviewer-avatar { background: linear-gradient(135deg, #6366F1, #818CF8); }
        .review-card:nth-child(3) .reviewer-avatar { background: linear-gradient(135deg, #10B981, #34D399); }

        .reviewer-info h4 {
            font-size: 15px;
            font-weight: 700;
        }

        .reviewer-info p {
            font-size: 12px;
            color: var(--text-light);
        }

        /* === CONTACT === */
        .contact {
            padding: 100px 24px;
            background: var(--white);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 48px;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 24px;
            font-weight: 800;
            margin-bottom: 16px;
        }

        .contact-info > p {
            color: var(--text-light);
            line-height: 1.7;
            margin-bottom: 32px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 20px;
        }

        .contact-icon {
            width: 48px;
            height: 48px;
            border-radius: 14px;
            background: rgba(255,107,0,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 22px;
            flex-shrink: 0;
        }

        .contact-item h4 {
            font-size: 14px;
            font-weight: 700;
            margin-bottom: 2px;
        }

        .contact-item p {
            font-size: 13px;
            color: var(--text-light);
        }

        .contact-form {
            background: var(--bg-light);
            border-radius: 24px;
            padding: 36px;
        }

        .form-group {
            margin-bottom: 16px;
        }

        .form-group label {
            display: block;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 6px;
            color: var(--text-dark);
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #E5E7EB;
            border-radius: 12px;
            font-size: 14px;
            font-family: inherit;
            transition: all 0.3s;
            background: var(--white);
            color: var(--text-dark);
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(255,107,0,0.1);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 100px;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        .submit-btn {
            width: 100%;
            background: linear-gradient(135deg, var(--primary), #FF8C38);
            color: white;
            border: none;
            padding: 14px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s;
            font-family: inherit;
            box-shadow: 0 4px 16px rgba(255,107,0,0.3);
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(255,107,0,0.4);
        }

        /* === FOOTER === */
        .footer {
            background: var(--secondary);
            color: rgba(255,255,255,0.7);
            padding: 60px 24px 24px;
        }

        .footer-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-brand .logo-text {
            color: white;
            font-size: 22px;
            margin-bottom: 12px;
        }

        .footer-brand p {
            font-size: 14px;
            line-height: 1.7;
        }

        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 20px;
        }

        .social-link {
            width: 40px;
            height: 40px;
            border-radius: 12px;
            background: rgba(255,255,255,0.08);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: rgba(255,255,255,0.7);
            font-size: 18px;
            transition: all 0.3s;
        }

        .social-link:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }

        .footer-col h4 {
            color: white;
            font-size: 16px;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col li {
            margin-bottom: 10px;
        }

        .footer-col a {
            color: rgba(255,255,255,0.6);
            text-decoration: none;
            font-size: 14px;
            transition: color 0.3s;
        }

        .footer-col a:hover {
            color: var(--primary);
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 0 auto;
            padding-top: 24px;
            border-top: 1px solid rgba(255,255,255,0.08);
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }

        .payment-methods {
            display: flex;
            gap: 12px;
            align-items: center;
        }

        .payment-badge {
            background: rgba(255,255,255,0.1);
            padding: 4px 12px;
            border-radius: 6px;
            font-size: 12px;
            font-weight: 600;
        }

        /* === FLOATING WHATSAPP === */
        .whatsapp-float {
            position: fixed;
            bottom: 24px;
            right: 24px;
            z-index: 999;
            width: 56px;
            height: 56px;
            background: #25D366;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 28px;
            text-decoration: none;
            box-shadow: 0 4px 16px rgba(37,211,102,0.4);
            transition: all 0.3s;
            animation: float 3s ease-in-out infinite;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
        }

        /* === SCROLL TOP === */
        .scroll-top {
            position: fixed;
            bottom: 24px;
            left: 24px;
            z-index: 999;
            width: 44px;
            height: 44px;
            background: var(--secondary);
            border-radius: 50%;
            display: none;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 18px;
            cursor: pointer;
            border: none;
            transition: all 0.3s;
            box-shadow: var(--shadow);
        }

        .scroll-top.show {
            display: flex;
        }

        .scroll-top:hover {
            background: var(--primary);
        }

        /* === TOAST === */
        .toast {
            position: fixed;
            bottom: 90px;
            right: 24px;
            background: var(--secondary);
            color: white;
            padding: 14px 24px;
            border-radius: 12px;
            font-size: 14px;
            font-weight: 600;
            z-index: 9999;
            transform: translateX(120%);
            transition: transform 0.4s ease;
            box-shadow: var(--shadow-lg);
            font-family: inherit;
        }

        .toast.show {
            transform: translateX(0);
        }

        /* === ANIMATIONS === */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInRight {
            from { opacity: 0; transform: translateX(40px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* === RESPONSIVE === */
        @media (max-width: 968px) {
            .hero-container { grid-template-columns: 1fr; text-align: center; }
            .hero p { margin: 0 auto 32px; }
            .hero-buttons { justify-content: center; }
            .hero-stats { justify-content: center; }
            .hero-visual { margin-top: 40px; }
            .hero-cards { transform: rotate(0); }
            .products-grid { grid-template-columns: repeat(2, 1fr); }
            .features-grid { grid-template-columns: repeat(2, 1fr); }
            .reviews-grid { grid-template-columns: 1fr; }
            .contact-grid { grid-template-columns: 1fr; }
            .offer-banner { grid-template-columns: 1fr; text-align: center; padding: 40px 24px; }
            .countdown { justify-content: center; }
            .footer-grid { grid-template-columns: 1fr 1fr; }
        }

        @media (max-width: 640px) {
            .nav-links { display: none; }
            .nav-btn { display: none; }
            .mobile-toggle { display: flex; }
            .nav-links.open {
                display: flex;
                flex-direction: column;
                position: absolute;
                top: 70px;
                left: 0;
                right: 0;
                background: white;
                padding: 24px;
                box-shadow: var(--shadow);
                gap: 16px;
            }
            .hero h1 { font-size: 32px; }
            .hero-buttons { flex-direction: column; align-items: center; }
            .hero-stats { flex-direction: column; gap: 16px; }
            .hero-cards { grid-template-columns: 1fr; }
            .hero-card:nth-child(2), .hero-card:nth-child(3) { transform: none; }
            .products-grid { grid-template-columns: 1fr; }
            .features-grid { grid-template-columns: 1fr; }
            .form-row { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
            .footer-bottom { flex-direction: column; gap: 12px; text-align: center; }
            .section-header h2 { font-size: 28px; }
            .offer-content h2 { font-size: 28px; }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#" class="logo">
                <div class="logo-icon">U</div>
                <div class="logo-text">ইউনিক<span>বিডি</span></div>
            </a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">হোম</a></li>
                <li><a href="#products">পণ্যসমূহ</a></li>
                <li><a href="#offers">অফার</a></li>
                <li><a href="#reviews">রিভিউ</a></li>
                <li><a href="#contact">যোগাযোগ</a></li>
            </ul>
            <button class="nav-btn" onclick="scrollTo('#products')">🛒 অর্ডার করুন</button>
            <button class="mobile-toggle" id="mobileToggle" onclick="toggleMenu()">
                <span></span><span></span><span></span>
            </button>
        </div>
    </nav>

    <!-- HERO -->
    <section class="hero" id="home">
        <div class="hero-container">
            <div class="hero-content">
                <div class="hero-badge">
                    <span class="pulse"></span> সারা বাংলাদেশে ডেলিভারি
                </div>
                <h1>
                    আপনার দৈনন্দিন জীবনের <span class="highlight">সেরা সঙ্গী</span>
                </h1>
                <p>
                    ইউনিকবিডি-তে পাচ্ছেন সেরা মানের ছাতা, রিচার্জেবল ফ্যান এবং টর্চ লাইট। সাশ্রয়ী মূল্যে, দ্রুত ডেলিভারি ও ১০০% গুণগত মান নিশ্চিত।
                </p>
                <div class="hero-buttons">
                    <a href="#products" class="btn-primary">🛍️ পণ্য দেখুন</a>
                    <a href="#contact" class="btn-secondary">📞 যোগাযোগ</a>
                </div>
                <div class="hero-stats">
                    <div class="stat">
                        <h3>৫০০০+</h3>
                        <p>সন্তুষ্ট গ্রাহক</p>
                    </div>
                    <div class="stat">
                        <h3>৩০০+</h3>
                        <p>পণ্য ভ্যারাইটি</p>
                    </div>
                    <div class="stat">
                        <h3>৬৪</h3>
                        <p>জেলায় ডেলিভারি</p>
                    </div>
                </div>
            </div>
            <div class="hero-visual">
                <div class="hero-cards">
                    <div class="hero-card">
                        <span class="emoji">☂️</span>
                        <h4>প্রিমিয়াম ছাতা</h4>
                        <p>৳২৫০ থেকে</p>
                    </div>
                    <div class="hero-card">
                        <span class="emoji">🌀</span>
                        <h4>রিচার্জেবল ফ্যান</h4>
                        <p>৳৪৫০ থেকে</p>
                    </div>
                    <div class="hero-card">
                        <span class="emoji">🔦</span>
                        <h4>টর্চ লাইট</h4>
                        <p>৳১৫০ থেকে</p>
                    </div>
                    <div class="hero-card">
                        <span class="emoji">🎁</span>
                        <h4>স্পেশাল অফার</h4>
                        <p>৩০% পর্যন্ত ছাড়</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FEATURES -->
    <section class="features" id="features">
        <div class="section-container">
            <div class="section-header animate-on-scroll">
                <span class="section-tag">✨ কেন ইউনিকবিডি?</span>
                <h2>আমাদের বিশেষত্ব</h2>
                <p>গুণগত মান ও গ্রাহক সন্তুষ্টি আমাদের প্রধান লক্ষ্য</p>
            </div>
            <div class="features-grid">
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">🏆</div>
                    <h3>প্রিমিয়াম মান</h3>
                    <p>প্রতিটি পণ্য কঠোর মান নিয়ন্ত্রণের মধ্য দিয়ে যায়। সেরা কোয়ালিটি নিশ্চিত।</p>
                </div>
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">🚚</div>
                    <h3>দ্রুত ডেলিভারি</h3>
                    <p>ঢাকায় ২৪ ঘণ্টা ও ঢাকার বাইরে ৪৮-৭২ ঘণ্টায় ডেলিভারি পাবেন।</p>
                </div>
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">💰</div>
                    <h3>সাশ্রয়ী মূল্য</h3>
                    <p>বাজারের সবচেয়ে কম দামে সেরা পণ্য। পাইকারি দামে খুচরা বিক্রি।</p>
                </div>
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">🔄</div>
                    <h3>রিপ্লেসমেন্ট গ্যারান্টি</h3>
                    <p>পণ্যে সমস্যা হলে ৭ দিনের মধ্যে ফ্রি রিপ্লেসমেন্ট পাবেন।</p>
                </div>
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">📞</div>
                    <h3>২৪/৭ সাপোর্ট</h3>
                    <p>যেকোনো সমস্যায় আমাদের কাস্টমার সাপোর্ট সবসময় আপনার পাশে।</p>
                </div>
                <div class="feature-card animate-on-scroll">
                    <div class="feature-icon">💵</div>
                    <h3>ক্যাশ অন ডেলিভারি</h3>
                    <p>পণ্য হাতে পেয়ে মূল্য পরিশোধ করুন। আগাম পেমেন্টের ঝামেলা নেই।</p>
                </div>
            </div>
        </div>
    </section>

    <!-- PRODUCTS -->
    <section class="products" id="products">
        <div class="section-container">
            <div class="section-header animate-on-scroll">
                <span class="section-tag">🛍️ আমাদের পণ্যসমূহ</span>
                <h2>জনপ্রিয় পণ্য</h2>
                <p>সেরা মানের পণ্য বেছে নিন আপনার পছন্দমতো</p>
            </div>
            <div class="products-grid">
                <div class="product-card animate-on-scroll">
                    <span class="product-badge">বেস্ট সেলার</span>
                    <div class="product-image">☂️</div>
                    <div class="product-info">
                        <div class="product-category">ছাতা</div>
                        <h3>অটোমেটিক ফোল্ডিং ছাতা</h3>
                        <p class="desc">UV প্রটেকশন, উইন্ডপ্রুফ, ওয়ান-ক্লিক ওপেন। টেকসই ও মজবুত।</p>
                        <div class="product-footer">
                            <span class="price">৳৩৫০ <small>৳৫০০</small></span>
                            <button class="add-cart" onclick="addToCart('অটোমেটিক ফোল্ডিং ছাতা')">🛒</button>
                        </div>
                    </div>
                </div>
                <div class="product-card animate-on-scroll">
                    <span class="product-badge">নতুন</span>
                    <div class="product-image">🌀</div>
                    <div class="product-info">
                        <div class="product-category">ফ্যান</div>
                        <h3>রিচার্জেবল টেবিল ফ্যান</h3>
                        <p class="desc">৩ স্পিড, ৮ ঘণ্টা ব্যাটারি ব্যাকআপ, LED লাইট সহ।</p>
                        <div class="product-footer">
                            <span class="price">৳৫৫০ <small>৳৮০০</small></span>
                            <button class="add-cart" onclick="addToCart('রিচার্জেবল টেবিল ফ্যান')">🛒</button>
                        </div>
                    </div>
                </div>
                <div class="product-card animate-on-scroll">
                    <span class="product-badge">জনপ্রিয়</span>
                    <div class="product-image">🔦</div>
                    <div class="product-info">
                        <div class="product-category">টর্চ লাইট</div>
                        <h3>হাই-পাওয়ার LED টর্চ</h3>
                        <p class="desc">জুম ফোকাস, ওয়াটারপ্রুফ, রিচার্জেবল ব্যাটারি সহ।</p>
                        <div class="product-footer">
                            <span class="price">৳২৮০ <small>৳৪৫০</small></span>
                            <button class="add-cart" onclick="addToCart('হাই-পাওয়ার LED টর্চ')">🛒</button>
                        </div>
                    </div>
                </div>
                <div class="product-card animate-on-scroll">
                    <div class="product-image">☂️</div>
                    <div class="product-info">
                        <div class="product-category">ছাতা</div>
                        <h3>বড় ফ্যামিলি ছাতা</h3>
                        <p class="desc">ডবল লেয়ার, অতিরিক্ত বড় সাইজ। ২-৩ জন একসাথে ব্যবহার।</p>
                        <div class="product-footer">
                            <span class="price">৳৪৫০ <small>৳৬৫০</small></span>
                            <button class="add-cart" onclick="addToCart('বড় ফ্যামিলি ছাতা')">🛒</button>
                        </div>
                    </div>
                </div>
                <div class="product-card animate-on-scroll">
                    <span class="product-badge">হট ডিল</span>
                    <div class="product-image">🌀</div>
                    <div class="product-info">
                        <div class="product-category">ফ্যান</div>
                        <h3>মিনি USB ফ্যান</h3>
                        <p class="desc">পকেট সাইজ, ক্লিপ অন, পাওয়ারব্যাংক দিয়ে চলে।</p>
                        <div class="product-footer">
                            <span class="price">৳২৫০ <small>৳৪০০</small></span>
                            <button class="add-cart" onclick="addToCart('মিনি USB ফ্যান')">🛒</button>
                        </div>
                    </div>
                </div>
                <div class="product-card animate-on-scroll">
                    <div class="product-image">🔦</div>
                    <div class="product-info">
                        <div class="product-category">টর্চ লাইট</div>
                        <h3>মিনি কিচেইন টর্চ</h3>
                        <p class="desc">কমপ্যাক্ট, সুপার ব্রাইট, চাবির রিংয়ে লাগানো যায়।</p>
                        <div class="product-footer">
                            <span class="price">৳১৫০ <small>৳২৫০</small></span>
                            <button class="add-cart" onclick="addToCart('মিনি কিচেইন টর্চ')">🛒</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- OFFERS -->
    <section class="offers" id="offers">
        <div class="offer-banner animate-on-scroll">
            <div class="offer-content">
                <span class="tag">🔥 সীমিত সময়ের অফার</span>
                <h2>গ্রীষ্মকালীন মেগা সেল!</h2>
                <p>যেকোনো ৩টি পণ্য একসাথে কিনলে পাচ্ছেন ৩০% ডিসকাউন্ট + ফ্রি ডেলিভারি। অফার শেষ হওয়ার আগেই অর্ডার করুন!</p>
                <div class="countdown" id="countdown">
                    <div class="countdown-item">
                        <span class="num" id="days">০৭</span>
                        <span class="label">দিন</span>
                    </div>
                    <div class="countdown-item">
                        <span class="num" id="hours">১২</span>
                        <span class="label">ঘণ্টা</span>
                    </div>
                    <div class="countdown-item">
                        <span class="num" id="minutes">৪৫</span>
                        <span class="label">মিনিট</span>
                    </div>
                    <div class="countdown-item">
                        <span class="num" id="seconds">৩০</span>
                        <span class="label">সেকেন্ড</span>
                    </div>
                </div>
                <a href="#products" class="btn-primary">🎯 এখনই অর্ডার করুন</a>
            </div>
            <div class="offer-visual">
                <span class="floating" style="font-size:140px;">🎉</span>
            </div>
        </div>
    </section>

    <!-- REVIEWS -->
    <section class="reviews" id="reviews">
        <div class="section-container">
            <div class="section-header animate-on-scroll">
                <span class="section-tag">💬 গ্রাহকদের মতামত</span>
                <h2>তারা কী বলছেন?</h2>
                <p>আমাদের সন্তুষ্ট গ্রাহকদের অভিজ্ঞতা</p>
            </div>
            <div class="reviews-grid">
                <div class="review-card animate-on-scroll">
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="text">"ছাতার কোয়ালিটি অসাধারণ! ভারী বৃষ্টিতেও একটুও পানি ঢোকেনি। দামের তুলনায় মান অনেক ভালো। ইউনিকবিডিকে ধন্যবাদ!"</p>
                    <div class="reviewer">
                        <div class="reviewer-avatar">র</div>
                        <div class="reviewer-info">
                            <h4>রাকিব হাসান</h4>
                            <p>ঢাকা, বাংলাদেশ</p>
                        </div>
                    </div>
                </div>
                <div class="review-card animate-on-scroll">
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="text">"রিচার্জেবল ফ্যানটা দারুণ! লোডশেডিংয়ের সময় খুবই কাজে আসে। ব্যাটারি ব্যাকআপও ভালো। পরিবারের সবাই খুশি।"</p>
                    <div class="reviewer">
                        <div class="reviewer-avatar">ন</div>
                        <div class="reviewer-info">
                            <h4>নাফিসা আক্তার</h4>
                            <p>চট্টগ্রাম, বাংলাদেশ</p>
                        </div>
                    </div>
                </div>
                <div class="review-card animate-on-scroll">
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="text">"টর্চ লাইটটা জুম করা যায়, খুব ব্রাইট। রাতে হাঁটার সময় অনেক কাজে আসে। দ্রুত ডেলিভারি পেয়েছি। সবকিছু পারফেক্ট!"</p>
                    <div class="reviewer">
                        <div class="reviewer-avatar">ক</div>
                        <div class="reviewer-info">
                            <h4>কামরুল ইসলাম</h4>
                            <p>রাজশাহী, বাংলাদেশ</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CONTACT -->
    <section class="contact" id="contact">
        <div class="section-container">
            <div class="section-header animate-on-scroll">
                <span class="section-tag">📞 যোগাযোগ</span>
                <h2>আমাদের সাথে কথা বলুন</h2>
                <p>অর্ডার বা যেকোনো প্রশ্নে যোগাযোগ করুন</p>
            </div>
            <div class="contact-grid">
                <div class="contact-info animate-on-scroll">
                    <h3>সরাসরি যোগাযোগ</h3>
                    <p>আমরা সবসময় আপনার সেবায় প্রস্তুত। নিচের যেকোনো মাধ্যমে যোগাযোগ করতে পারেন।</p>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div>
                            <h4>ফোন/হোয়াটসঅ্যাপ</h4>
                            <p>+৮৮০ ১৭XX-XXXXXX</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div>
                            <h4>ইমেইল</h4>
                            <p>info@uniquebd.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h4>ঠিকানা</h4>
                            <p>ঢাকা, বাংলাদেশ</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">⏰</div>
                        <div>
                            <h4>সেবা সময়</h4>
                            <p>সকাল ৯টা - রাত ১০টা (প্রতিদিন)</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form animate-on-scroll">
                    <form onsubmit="handleSubmit(event)">
                        <div class="form-row">
                            <div class="form-group">
                                <label>আপনার নাম *</label>
                                <input type="text" placeholder="নাম লিখুন" required>
                            </div>
                            <div class="form-group">
                                <label>ফোন নম্বর *</label>
                                <input type="tel" placeholder="০১XXXXXXXXX" required>
                            </div>
                        </div>
                        <div class="form-group">
                            <label>পণ্য নির্বাচন</label>
                            <select>
                                <option value="">পণ্য বেছে নিন</option>
                                <option>ছাতা</option>
                                <option>রিচার্জেবল ফ্যান</option>
                                <option>টর্চ লাইট</option>
                                <option>কম্বো প্যাকেজ</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>ডেলিভারি ঠিকানা</label>
                            <input type="text" placeholder="সম্পূর্ণ ঠিকানা লিখুন">
                        </div>
                        <div class="form-group">
                            <label>বিস্তারিত বার্তা</label>
                            <textarea placeholder="আপনার অর্ডার বা প্রশ্ন সম্পর্কে লিখুন..."></textarea>
                        </div>
                        <button type="submit" class="submit-btn">📩 অর্ডার / মেসেজ পাঠান</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="footer">
        <div class="footer-grid">
            <div class="footer-brand">
                <div class="logo-text" style="font-size:24px; font-weight:800; margin-bottom:12px;">ইউনিক<span style="color:var(--primary);">বিডি</span></div>
                <p>আপনার দৈনন্দিন জীবনের বিশ্বস্ত সঙ্গী। সেরা মানের পণ্য, সাশ্রয়ী মূল্যে।</p>
                <div class="social-links">
                    <a href="#" class="social-link">📘</a>
                    <a href="#" class="social-link">📸</a>
                    <a href="#" class="social-link">▶️</a>
                    <a href="#" class="social-link">💬</a>
                </div>
            </div>
            <div class="footer-col">
                <h4>দ্রুত লিংক</h4>
                <ul>
                    <li><a href="#home">হোম</a></li>
                    <li><a href="#products">পণ্যসমূহ</a></li>
                    <li><a href="#offers">অফার</a></li>
                    <li><a href="#reviews">রিভিউ</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>পণ্য ক্যাটাগরি</h4>
                <ul>
                    <li><a href="#">ছাতা</a></li>
                    <li><a href="#">রিচার্জেবল ফ্যান</a></li>
                    <li><a href="#">টর্চ লাইট</a></li>
                    <li><a href="#">কম্বো অফার</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>সাহায্য</h4>
                <ul>
                    <li><a href="#">ডেলিভারি তথ্য</a></li>
                    <li><a href="#">রিটার্ন পলিসি</a></li>
                    <li><a href="#">প্রাইভেসি পলিসি</a></li>
                    <li><a href="#contact">যোগাযোগ</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© ২০২৫ ইউনিকবিডি। সর্বস্বত্ব সংরক্ষিত।</p>
            <div class="payment-methods">
                <span class="payment-badge">💳 বিকাশ</span>
                <span class="payment-badge">💳 নগদ</span>
                <span class="payment-badge">💳 রকেট</span>
                <span class="payment-badge">💵 ক্যাশ</span>
            </div>
        </div>
    </footer>

    <!-- WHATSAPP FLOAT -->
    <a href="https://wa.me/8801700000000" class="whatsapp-float" target="_blank" title="WhatsApp-এ মেসেজ করুন">💬</a>

    <!-- SCROLL TOP -->
    <button class="scroll-top" id="scrollTop" onclick="window.scrollTo({top:0,behavior:'smooth'})">⬆</button>

    <!-- TOAST -->
    <div class="toast" id="toast"></div>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            const scrollTop = document.getElementById('scrollTop');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
            if (window.scrollY > 400) {
                scrollTop.classList.add('show');
            } else {
                scrollTop.classList.remove('show');
            }
        });

        // Mobile menu toggle
        function toggleMenu() {
            document.getElementById('navLinks').classList.toggle('open');
        }

        // Close mobile menu on link click
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.getElementById('navLinks').classList.remove('open');
            });
        });

        // Smooth scroll
        function scrollTo(selector) {
            document.querySelector(selector)?.scrollIntoView({ behavior: 'smooth' });
        }

        // Toast notification
        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3000);
        }

        // Add to cart
        function addToCart(product) {
            showToast(`✅ "${product}" কার্টে যোগ হয়েছে!`);
        }

        // Form submit
        function handleSubmit(e) {
            e.preventDefault();
            showToast('✅ আপনার মেসেজ সফলভাবে পাঠানো হয়েছে!');
            e.target.reset();
        }

        // Countdown timer
        function toBanglaNum(num) {
            const banglaDigits = ['০','১','২','৩','৪','৫','৬','৭','৮','৯'];
            return String(num).padStart(2, '0').split('').map(d => banglaDigits[parseInt(d)]).join('');
        }

        function updateCountdown() {
            const now = new Date();
            const end = new Date(now.getTime() + 7 * 24 * 60 * 60 * 1000);
            if (!window.countdownEnd) {
                const saved = localStorage.getItem('uniquebd_countdown');
                if (saved && new Date(saved) > now) {
                    window.countdownEnd = new Date(saved);
                } else {
                    window.countdownEnd = end;
                    localStorage.setItem('uniquebd_countdown', end.toISOString());
                }
            }

            const diff = window.countdownEnd - now;
            if (diff <= 0) {
                window.countdownEnd = new Date(now.getTime() + 7 * 24 * 60 * 60 * 1000);
                localStorage.setItem('uniquebd_countdown', window.countdownEnd.toISOString());
            }

            const d = Math.floor(diff / (1000 * 60 * 60 * 24));
            const h = Math.floor((diff / (1000 * 60 * 60)) % 24);
            const m = Math.floor((diff / (1000 * 60)) % 60);
            const s = Math.floor((diff / 1000) % 60);

            document.getElementById('days').textContent = toBanglaNum(d);
            document.getElementById('hours').textContent = toBanglaNum(h);
            document.getElementById('minutes').textContent = toBanglaNum(m);
            document.getElementById('seconds').textContent = toBanglaNum(s);
        }

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // Scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry, i) => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.classList.add('visible');
                    }, i * 80);
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
