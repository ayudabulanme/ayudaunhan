<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AYUDA - Social Aid</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #003153;        /* deep blue */
            --primary-light: #1A4766;  /* lighter deep blue */
            --primary-dark: #001F3F;   /* darkest blue */
            --secondary: #FFB81C;      /* warm yellow */
            --success: #4caf50;
            --danger: #f44336;
            --warning: #ff9800;
            --light: #ffffff;
            --dark: #001F3F;
            --soft-blue: #FFF8E7;      /* warm off-white / light yellow */
            --soft-white: #ffffff;
            --text-light: #ffffff;
            --text-dark: #001F3F;
            --bg-light: #ffffff;
            --bg-blue: #FFF8E7;        /* soft yellow background */
            --card-white: #ffffff;
            --border-blue: #D4E6F1;    /* subtle blue border */
            --light-blue-bg: #E3F2FD;  /* very light blue for box highlights */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
        }

        body {
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
            flex-shrink: 0;
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--secondary), var(--primary), var(--secondary));
            background-size: 200% 200%;
            border-radius: 50%;
            position: relative;
            border: 3px solid white;
            color: white;
            font-size: 1.8rem;
            animation: shine 3s infinite;
            box-shadow: 0 0 15px rgba(255, 184, 28, 0.3);
        }

        @keyframes shine {
            0% {
                background-position: 0% 50%;
                box-shadow: 0 0 15px rgba(255, 184, 28, 0.3);
            }
            50% {
                background-position: 100% 50%;
                box-shadow: 0 0 25px rgba(255, 184, 28, 0.6);
            }
            100% {
                background-position: 0% 50%;
                box-shadow: 0 0 15px rgba(255, 184, 28, 0.3);
            }
        }

        .logo-icon::after {
            content: '';
            position: absolute;
            top: -3px;
            left: -3px;
            right: -3px;
            bottom: -3px;
            background: linear-gradient(135deg, var(--secondary), var(--primary), var(--secondary));
            background-size: 200% 200%;
            border-radius: 50%;
            z-index: -1;
            opacity: 0.5;
            animation: shine 3s infinite reverse;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: white;
        }

        nav {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            flex: 1;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            align-items: center;
            width: 100%;
            justify-content: space-between;
        }

        .nav-center {
            display: flex;
            gap: 25px;
            align-items: center;
            margin-left: auto;
            margin-right: auto;
        }

        .nav-right {
            display: flex;
            gap: 15px;
            align-items: center;
            margin-left: auto;
        }

        .nav-link {
            text-decoration: none;
            color: white;
            font-weight: 500;
            font-size: 15px;
            transition: all 0.3s ease;
            padding: 8px 0;
            position: relative;
        }

        .nav-center .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: white;
            transition: width 0.3s ease;
        }

        .nav-center .nav-link:hover::after {
            width: 100%;
        }

        .nav-right .nav-link {
            padding: 8px 20px !important;
            border-radius: 4px;
            font-weight: 600 !important;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            text-align: center;
            min-width: 80px;
        }

        .nav-right .nav-link[data-page="admin-login"] {
            background-color: transparent;
            color: white !important;
            border: 2px solid white;
        }

        .nav-right .nav-link[data-page="admin-login"]:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: translateY(-2px);
        }

        .nav-right .nav-link[data-page="admin-register"] {
            background-color: var(--secondary);
            color: var(--primary-dark) !important;
            border: 2px solid var(--secondary);
        }

        .nav-right .nav-link[data-page="admin-register"]:hover {
            background-color: rgba(255, 184, 28, 0.9);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(255, 184, 28, 0.3);
        }

        #logout-link {
            background-color: white;
            color: var(--primary-dark) !important;
            border: 2px solid white;
        }

        #logout-link:hover {
            background-color: rgba(255, 255, 255, 0.9);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(255, 255, 255, 0.2);
        }

        #logged-out-nav, #logged-in-nav {
            display: none;
            width: 100%;
        }

        #logged-out-nav.active, #logged-in-nav.active {
            display: flex;
        }

        .btn {
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            font-family: 'Inter', sans-serif;
            font-size: 14px;
        }

        .btn-primary {
            background-color: var(--secondary);
            color: var(--primary-dark);
            border: 2px solid var(--secondary);
        }

        .btn-outline {
            background-color: transparent;
            color: white;
            border: 1px solid white;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .page-section {
            min-height: 80vh;
            padding: 60px 0;
            background-color: var(--bg-light);
        }

        .page-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--primary-dark);
            font-size: 2.5rem;
            text-transform: uppercase;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        /* ========== HIGHLIGHT ONLY THE CONTENT BOXES ========== */
        #criteria .criteria-section,
        #about .about-section,
        #contact .contact-section {
            background-color: var(--light-blue-bg);
        }

        /* ========== HOME HERO – NEW IMAGE: Volunteers distributing relief goods ========== */
        .hero-section {
            background: linear-gradient(rgba(0, 49, 83, 0.3), rgba(0, 31, 63, 0.3)), 
                        url('https://images.unsplash.com/photo-1544027993-37dbfe43562a?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=80');
            background-size: cover;
            background-position: center 30%;
            color: white;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 80vh;
        }

        .hero-content {
            max-width: 800px;
            padding: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .hero-content h2 {
            font-size: 3rem;
            margin-bottom: 30px;
            text-transform: uppercase;
            font-weight: 700;
            letter-spacing: 1px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero-content .mission-statement {
            font-size: 1.3rem;
            margin-bottom: 40px;
            font-weight: 300;
            line-height: 1.8;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .platform-section {
            padding: 80px 0;
            background-color: white;
        }

        .platform-section h2 {
            text-align: center;
            margin-bottom: 50px;
            color: var(--primary-dark);
            font-size: 2.2rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .platform-content {
            display: flex;
            flex-direction: column;
            gap: 50px;
            align-items: center;
        }

        .platform-text {
            width: 100%;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .platform-text h3 {
            color: var(--primary-dark);
            margin-bottom: 25px;
            font-size: 1.8rem;
            font-weight: 600;
            line-height: 1.3;
        }

        .platform-text p {
            color: var(--text-dark);
            font-weight: 300;
            line-height: 1.8;
            font-size: 1.1rem;
            margin-bottom: 25px;
        }

        .platform-features-vertical {
            display: flex;
            flex-direction: column;
            gap: 25px;
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
        }

        .platform-feature-vertical {
            background: var(--soft-blue);
            padding: 30px;
            border-radius: 10px;
            border-left: 4px solid var(--secondary);
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            display: flex;
            align-items: flex-start;
            gap: 20px;
            transition: all 0.3s ease;
        }

        .platform-feature-vertical:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .platform-feature-vertical i {
            font-size: 1.8rem;
            color: var(--primary);
            background: white;
            padding: 15px;
            border-radius: 10px;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .platform-feature-content {
            flex: 1;
        }

        .platform-feature-content h4 {
            color: var(--primary-dark);
            margin-bottom: 15px;
            font-weight: 600;
            font-size: 1.3rem;
        }

        .platform-feature-content p {
            color: var(--text-dark);
            font-weight: 300;
            line-height: 1.7;
            font-size: 1.05rem;
        }

        /* ===== OUR SERVICES – UPDATED TEXT & ICONS ===== */
        .services-section {
            padding: 80px 0;
            background-color: var(--bg-blue);
        }

        .services-section h2 {
            text-align: center;
            margin-bottom: 50px;
            color: var(--primary-dark);
            font-size: 2.2rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .service-card {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
            text-align: center;
            transition: all 0.3s ease;
            border-top: 4px solid var(--secondary);
            position: relative;
            overflow: hidden;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--secondary), var(--primary-light));
        }

        .service-icon {
            font-size: 2.5rem;
            color: var(--primary);
            background: var(--soft-blue);
            width: 80px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            margin: 0 auto 25px;
            transition: all 0.3s ease;
        }

        .service-card:hover .service-icon {
            background: var(--secondary);
            color: var(--primary-dark);
            transform: scale(1.1);
        }

        .service-card h3 {
            color: var(--primary-dark);
            margin-bottom: 15px;
            font-weight: 600;
            font-size: 1.4rem;
        }

        .service-card p {
            color: var(--text-dark);
            font-weight: 300;
            line-height: 1.7;
            font-size: 1.05rem;
        }

        .mission-box {
            background-color: rgba(255, 255, 255, 0.15);
            border-radius: 10px;
            padding: 30px;
            margin: 40px auto;
            max-width: 800px;
            border-left: 4px solid var(--secondary);
        }

        .mission-box p {
            font-size: 1.2rem;
            font-weight: 300;
            line-height: 1.8;
            margin-bottom: 0;
        }

        /* ========== CRITERIA SECTION – BACKGROUND IMAGE REMOVED ========== */
        .criteria-section {
            position: relative;
            padding: 40px;
            border-radius: 15px;
            margin: 40px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            z-index: 1;
        }

        .criteria-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 30px;
            position: relative;
            z-index: 2;
        }

        .criteria-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            border-top: 4px solid var(--secondary);
        }

        .criteria-card h3 {
            color: var(--primary-dark);
            margin-bottom: 20px;
            font-weight: 600;
            font-size: 1.2rem;
        }

        .criteria-table {
            width: 100%;
            border-collapse: collapse;
            margin: 10px 0;
        }

        .criteria-table th {
            background-color: var(--soft-blue);
            color: var(--primary-dark);
            padding: 12px 15px;
            text-align: left;
            font-weight: 600;
            border-bottom: 2px solid var(--border-blue);
        }

        .criteria-table td {
            padding: 10px 15px;
            border-bottom: 1px solid var(--border-blue);
        }

        .criteria-table tr:hover {
            background-color: var(--soft-blue);
        }

        .points-badge {
            display: inline-block;
            padding: 5px 10px;
            background-color: var(--secondary);
            color: var(--primary-dark);
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .about-section {
            background-color: var(--card-white);
            padding: 40px;
            border-radius: 15px;
            margin: 40px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border: 1px solid var(--border-blue);
            position: relative;
            overflow: hidden;
        }

        .about-content {
            position: relative;
            z-index: 1;
        }

        .about-grid-vertical {
            display: flex;
            flex-direction: column;
            gap: 25px;
            margin: 40px 0;
        }

        .about-card-vertical {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            border-left: 4px solid var(--secondary);
            display: flex;
            align-items: flex-start;
            gap: 20px;
            position: relative;
            z-index: 1;
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(2px);
        }

        .about-card-vertical i {
            font-size: 1.5rem;
            color: var(--primary);
            background: var(--soft-blue);
            padding: 15px;
            border-radius: 10px;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .about-card-content {
            flex: 1;
        }

        .about-card-content h3 {
            color: var(--primary-dark);
            margin-bottom: 10px;
            font-weight: 600;
        }

        .about-card-content p {
            font-weight: 300;
            line-height: 1.7;
        }

        .faq-section {
            margin-top: 50px;
            position: relative;
            z-index: 1;
        }

        .faq-item {
            background: white;
            padding: 20px;
            margin-bottom: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            border-left: 3px solid var(--secondary);
            cursor: pointer;
            transition: all 0.3s ease;
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(2px);
        }

        .faq-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .faq-question {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            color: var(--primary-dark);
        }

        .faq-answer {
            margin-top: 15px;
            color: var(--text-dark);
            display: none;
            font-weight: 300;
            line-height: 1.7;
        }

        .faq-item.active .faq-answer {
            display: block;
        }

        .beneficiaries-section {
            background-color: var(--bg-blue);
            padding: 40px;
            border-radius: 15px;
            margin: 40px 0;
        }

        .add-beneficiary-form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        .ranking-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
        }

        .ranking-table th {
            background-color: var(--primary);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }

        .ranking-table td {
            padding: 12px 15px;
            border-bottom: 1px solid var(--border-blue);
        }

        .rank-badge {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            font-weight: bold;
        }

        .rank-1 { background-color: gold; color: #333; }
        .rank-2 { background-color: silver; color: #333; }
        .rank-3 { background-color: #cd7f32; color: white; }
        .rank-other { background-color: var(--primary-light); color: white; }

        .contact-section {
            background-color: var(--bg-blue);
            padding: 40px;
            border-radius: 15px;
            margin: 40px 0;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .contact-info {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 25px;
            gap: 15px;
        }

        .contact-item i {
            font-size: 1.2rem;
            color: var(--primary);
            background: var(--soft-blue);
            padding: 12px;
            border-radius: 50%;
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        footer {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            padding: 40px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            text-transform: uppercase;
            font-weight: 600;
        }

        .footer-section p, .footer-section a {
            color: #e3f2fd;
            margin-bottom: 10px;
            display: block;
            text-decoration: none;
            font-weight: 300;
        }

        .footer-section a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background-color: var(--secondary);
            color: var(--primary-dark);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bbdefb;
            font-size: 0.9rem;
            font-weight: 300;
        }

        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 15px;
            }
            .nav-menu {
                flex-direction: column;
                width: 100%;
            }
            .nav-center, .nav-right {
                flex-direction: column;
                width: 100%;
                gap: 10px;
            }
            .nav-right {
                margin-left: 0;
                margin-top: 15px;
            }
            .nav-right .nav-link {
                width: 100%;
                max-width: 200px;
            }
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            .page-title {
                font-size: 2rem;
            }
            .hero-content h2 {
                font-size: 2.2rem;
            }
            .hero-content .mission-statement {
                font-size: 1.1rem;
            }
            .criteria-section,
            .about-section,
            .beneficiaries-section,
            .contact-section {
                padding: 20px;
            }
            .mission-box {
                padding: 20px;
            }
            .about-card-vertical {
                flex-direction: column;
                gap: 15px;
            }
            .about-card-vertical i {
                align-self: center;
            }
            .services-grid {
                grid-template-columns: 1fr;
            }
            .platform-feature-vertical {
                flex-direction: column;
                gap: 15px;
            }
            .platform-feature-vertical i {
                align-self: center;
            }
            .platform-content {
                gap: 30px;
            }
        }

        @media (max-width: 480px) {
            .hero-content h2 {
                font-size: 1.8rem;
            }
            .hero-content .mission-statement {
                font-size: 1rem;
            }
            .criteria-grid {
                grid-template-columns: 1fr;
            }
            .services-section {
                padding: 50px 0;
            }
            .service-card {
                padding: 25px 20px;
            }
            .platform-section {
                padding: 50px 0;
            }
            .platform-feature-vertical {
                padding: 20px;
            }
            .platform-text h3 {
                font-size: 1.5rem;
            }
            .platform-feature-content h4 {
                font-size: 1.2rem;
            }
            .logo-icon {
                width: 40px;
                height: 40px;
                font-size: 1.5rem;
            }
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
            color: var(--primary-dark);
            font-size: 14px;
        }

        .form-control {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid var(--border-blue);
            border-radius: 4px;
            font-size: 14px;
            transition: border 0.3s ease;
            background-color: white;
            color: var(--text-dark);
            font-family: 'Inter', sans-serif;
        }

        .form-control:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 184, 28, 0.1);
        }

        .hidden {
            display: none !important;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in {
            animation: fadeIn 0.5s ease;
        }

        h1, h2, h3, h4, h5, h6 {
            font-weight: 600;
        }

        p {
            font-weight: 300;
        }

        strong {
            font-weight: 600;
        }

        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--success);
            color: white;
            padding: 12px 20px;
            border-radius: 8px;
            box-shadow: 0 3px 15px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 10px;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease;
            font-size: 14px;
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast.error {
            background-color: var(--danger);
        }

        .toast.warning {
            background-color: var(--warning);
            color: #333;
        }

        .admin-register-form {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 420px;
            margin: 0 auto;
            font-size: 14px;
        }

        .admin-register-form h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .password-strength {
            height: 4px;
            border-radius: 2px;
            margin-top: 5px;
            transition: all 0.3s ease;
        }

        .strength-weak { background-color: #f44336; width: 25%; }
        .strength-fair { background-color: #ff9800; width: 50%; }
        .strength-good { background-color: #4caf50; width: 75%; }
        .strength-strong { background-color: #2e7d32; width: 100%; }

        .strength-text {
            font-size: 12px;
            margin-top: 2px;
            color: #666;
        }

        .admin-login-form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: 0 auto;
        }

        .admin-login-form h3 {
            font-size: 1.8rem;
            margin-bottom: 25px;
            text-align: center;
            color: var(--primary-dark);
        }

        .form-actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 20px;
        }

        .form-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            font-size: 14px;
        }

        .form-link:hover {
            text-decoration: underline;
        }

        .admin-welcome {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .admin-welcome p {
            font-size: 3rem;
            margin-bottom: 10px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            text-align: center;
            border-top: 4px solid var(--secondary);
        }

        .stat-card i {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .stat-card h4 {
            color: var(--primary-dark);
            margin-bottom: 10px;
            font-weight: 600;
        }

        .stat-card p {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }

        .admin-actions {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
            overflow-y: auto;
        }

        .modal-content {
            background: white;
            padding: 25px;
            border-radius: 10px;
            width: 100%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 5px 25px rgba(0,0,0,0.2);
        }

        .modal-content h3 {
            color: var(--primary-dark);
            margin-bottom: 20px;
            text-align: center;
            font-weight: 600;
            font-size: 1.5rem;
        }

        .modal-content .form-group {
            margin-bottom: 15px;
        }

        .modal-content .form-group label {
            font-size: 14px;
        }

        .modal-content .form-control {
            font-size: 14px;
            padding: 10px 12px;
        }

        .modal-content small {
            font-size: 12px;
            color: #666;
            display: block;
            margin-top: 5px;
            line-height: 1.4;
        }

        .modal-buttons {
            display: flex;
            gap: 10px;
            margin-top: 25px;
        }

        .modal-buttons .btn {
            flex: 1;
            padding: 10px;
            font-size: 14px;
        }

        .announcement-form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .selection-options {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin: 20px 0;
        }

        .selection-option:nth-child(1) {
            grid-column: 1 / -1;
        }

        @media (max-width: 768px) {
            .selection-options {
                grid-template-columns: 1fr;
            }
            .selection-option:nth-child(1) {
                grid-column: 1;
            }
        }

        .selection-option {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            border: 2px solid transparent;
            position: relative;
            min-height: 120px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .selection-option:hover {
            background: var(--soft-blue);
            border-color: var(--secondary);
            transform: translateY(-3px);
        }

        .selection-option.selected {
            background: var(--primary);
            color: white;
            box-shadow: 0 5px 15px rgba(0, 49, 83, 0.3);
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .selection-option.selected::after {
            content: '✓';
            position: absolute;
            top: 10px;
            right: 10px;
            background: white;
            color: var(--primary);
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .selection-option h4 {
            margin-bottom: 10px;
            font-size: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .selection-option p {
            margin-bottom: 15px;
            color: #666;
            font-weight: 300;
        }

        .selection-input {
            margin-top: 10px;
            display: none;
        }

        .selection-input.active {
            display: block;
        }

        .preview-box {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            border: 2px dashed #ddd;
            min-height: 100px;
            margin: 20px 0;
        }

        .sms-preview {
            background: white;
            border: 2px solid var(--secondary);
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            font-family: monospace;
            white-space: pre-line;
        }

        .admin-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }

        .admin-tab-btn {
            padding: 12px 30px;
            background: #f8f9fa;
            border: none;
            border-radius: 8px 8px 0 0;
            cursor: pointer;
            font-weight: 600;
            color: #666;
            transition: all 0.3s;
        }

        .admin-tab-btn.active {
            background: var(--primary);
            color: white;
        }

        .admin-tab-content {
            display: none;
        }

        .admin-tab-content.active {
            display: block;
        }

        .history-table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            margin-top: 20px;
        }

        .history-table th {
            background-color: var(--primary-dark);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }

        .history-table td {
            padding: 12px 15px;
            border-bottom: 1px solid var(--border-blue);
        }

        .status-sending { color: #ff9800; font-weight: 600; }
        .status-partial { color: #ff9800; font-weight: 600; }
        .status-sent { color: #4caf50; font-weight: 600; }
        .status-pending { color: #ff9800; font-weight: 600; }
        .status-failed { color: #f44336; font-weight: 600; }

        .modal-buttons .btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
        }

        .btn .fa-spinner {
            margin-right: 5px;
        }

        .sms-config {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            border-left: 4px solid var(--secondary);
        }

        .sms-config h4 {
            color: var(--primary-dark);
            margin-bottom: 15px;
            font-weight: 600;
        }

        .carrier-select {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 10px;
            margin-top: 10px;
        }

        .carrier-option {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            text-align: center;
            transition: all 0.3s;
        }

        .carrier-option:hover {
            background: #f5f5f5;
        }

        .carrier-option.selected {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .points-breakdown-modal .modal-content {
            max-width: 600px;
        }

        .points-breakdown-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        .points-breakdown-table th {
            background-color: var(--soft-blue);
            color: var(--primary-dark);
            padding: 12px;
            text-align: left;
            font-weight: 600;
        }

        .points-breakdown-table td {
            padding: 10px;
            border-bottom: 1px solid var(--border-blue);
        }

        .points-breakdown-table tr:hover {
            background-color: var(--soft-blue);
        }

        .criterion-explanation {
            font-size: 12px;
            color: #666;
            margin-top: 5px;
        }

        .breakdown-total {
            background-color: var(--soft-blue);
            font-weight: bold;
            font-size: 1.1rem;
        }

        .loading {
            display: none;
            text-align: center;
            margin: 20px 0;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid var(--secondary);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto 10px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-hand-holding-heart"></i>
                    </div>
                    <h1>AYUDA</h1>
                </div>
                <nav>
                    <div id="logged-out-nav" class="active">
                        <div class="nav-menu">
                            <div class="nav-center">
                                <a href="#" class="nav-link active" data-page="home">Home</a>
                                <a href="#" class="nav-link" data-page="criteria">Criteria</a>
                                <a href="#" class="nav-link" data-page="about">About Us</a>
                                <a href="#" class="nav-link" data-page="contact">Contact Us</a>
                            </div>
                            <div class="nav-right">
                                <a href="#" class="nav-link" data-page="admin-login">Log In</a>
                                <a href="#" class="nav-link" data-page="admin-register">Sign up</a>
                            </div>
                        </div>
                    </div>
                    <div id="logged-in-nav">
                        <div class="nav-menu">
                            <div class="nav-center">
                                <a href="#" class="nav-link active" data-page="home">Home</a>
                                <a href="#" class="nav-link" data-page="beneficiaries">Beneficiaries</a>
                                <a href="#" class="nav-link" data-page="criteria">Criteria</a>
                                <a href="#" class="nav-link" data-page="about">About Us</a>
                                <a href="#" class="nav-link" data-page="contact">Contact Us</a>
                            </div>
                            <div class="nav-right">
                                <a href="#" class="nav-link" id="logout-link">Log Out</a>
                            </div>
                        </div>
                    </div>
                </nav>
            </div>
        </div>
    </header>

    <!-- Home Page -->
    <section id="home" class="page-section">
        <div class="hero-section">
            <div class="container">
                <div class="hero-content fade-in">
                    <h2>AYUDA</h2>
                    <p class="mission-statement">
                        At AYUDA, we fight bias to ensure help reaches those who need it most. Using fair, transparent, and data-driven methods, we identify the truly vulnerable and provide them with the resources to thrive. Our mission is justice in aid—empowering communities with equal opportunity and real change.
                    </p>
                    <div class="hero-buttons">
                        <button class="btn btn-primary" onclick="showPage('criteria')">View Criteria</button>
                        <button class="btn btn-outline" onclick="showPage('about')">Learn More</button>
                    </div>
                </div>
            </div>
        </div>

        <div class="platform-section">
            <div class="container">
                <div class="platform-content fade-in">
                    <div class="platform-text">
                        <h3>A Smarter Way to Help</h3>
                        <p>Our platform leverages technology to ensure aid reaches those who need it most, efficiently and transparently. We combine data-driven insights with community-based approaches to create meaningful impact.</p>
                    </div>
                    
                    <div class="platform-features-vertical">
                        <div class="platform-feature-vertical">
                            <i class="fas fa-robot"></i>
                            <div class="platform-feature-content">
                                <h4>Automated Ranking</h4>
                                <p>Our platform ranks beneficiaries based on custom criteria, ensuring aid distribution is fair, objective, and data-driven. The system automatically calculates points based on multiple factors to prioritize those with greatest need.</p>
                            </div>
                        </div>
                        <div class="platform-feature-vertical">
                            <i class="fas fa-chart-line"></i>
                            <div class="platform-feature-content">
                                <h4>Data-Driven Decisions</h4>
                                <p>We use advanced analytics to track impact, measure effectiveness, and continuously improve our aid distribution processes for maximum community benefit.</p>
                            </div>
                        </div>
                        <div class="platform-feature-vertical">
                            <i class="fas fa-shield-alt"></i>
                            <div class="platform-feature-content">
                                <h4>Transparent Process</h4>
                                <p>Every step of the aid distribution process is documented and verifiable, building trust within the community and ensuring accountability at all levels.</p>
                            </div>
                        </div>
                        <div class="platform-feature-vertical">
                            <i class="fas fa-bolt"></i>
                            <div class="platform-feature-content">
                                <h4>Real-Time Updates</h4>
                                <p>Beneficiary status and ranking updates in real-time as new information is added, ensuring the most current data drives decision-making.</p>
                            </div>
                        </div>
                        <div class="platform-feature-vertical">
                            <i class="fas fa-users-cog"></i>
                            <div class="platform-feature-content">
                                <h4>Community-Centric Design</h4>
                                <p>Built with input from community leaders and beneficiaries, our platform addresses real needs with practical, user-friendly solutions.</p>
                            </div>
                        </div>
                        <div class="platform-feature-vertical">
                            <i class="fas fa-mobile-alt"></i>
                            <div class="platform-feature-content">
                                <h4>Accessible Technology</h4>
                                <p>Designed to work on any device, our platform ensures that barangay officials and community members can access and use the system easily.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- OUR SERVICES -->
        <div class="services-section">
            <div class="container">
                <h2>Our Services</h2>
                <div class="services-grid">
                    <div class="service-card fade-in">
                        <div class="service-icon">
                            <i class="fas fa-balance-scale"></i>
                        </div>
                        <h3>Fair & Inclusive Assistance</h3>
                        <p>Our programs are committed to removing bias in the distribution of support. We use clear, objective criteria to identify individuals and families who need help the most, ensuring assistance is given fairly and transparently.</p>
                    </div>
                    <div class="service-card fade-in" style="animation-delay: 0.1s;">
                        <div class="service-icon">
                            <i class="fas fa-hand-holding-heart"></i>
                        </div>
                        <h3>Needs-Based Support</h3>
                        <p>We prioritize those facing the most urgent and serious challenges. By carefully assessing each situation, we help ensure that resources reach the people who truly deserve and require assistance.</p>
                    </div>
                    <div class="service-card fade-in" style="animation-delay: 0.2s;">
                        <div class="service-icon">
                            <i class="fas fa-handshake"></i>
                        </div>
                        <h3>Equal & Respectful Treatment</h3>
                        <p>We believe everyone deserves to be treated with dignity and respect. Our system promotes fairness, accountability, and equal opportunity, making sure no one is overlooked or discriminated against in receiving aid.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Criteria Page – Only the .criteria-section box is highlighted -->
    <section id="criteria" class="page-section hidden">
        <div class="container">
            <h2 class="page-title">Criteria</h2>
            
            <div class="criteria-section">
                <p class="description" style="margin-bottom: 30px; font-size: 1.1rem; color: var(--primary-dark); font-weight: 300; position: relative; z-index: 2;">
                    The following criteria are used to evaluate and rank beneficiaries based on their needs. Points are assigned to each criterion, and beneficiaries are ranked accordingly.
                </p>

                <div class="criteria-grid">
                    <!-- Income Level Card -->
                    <div class="criteria-card">
                        <h3>Income Level (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Income Range</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Below ₱5,000 monthly</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>₱5,001 - ₱10,000 monthly</td>
                                    <td><span class="points-badge">7 points</span></td>
                                </tr>
                                <tr>
                                    <td>₱10,001 - ₱15,000 monthly</td>
                                    <td><span class="points-badge">4 points</span></td>
                                </tr>
                                <tr>
                                    <td>Above ₱15,000 monthly</td>
                                    <td><span class="points-badge">0 points</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- Medical Conditions Card -->
                    <div class="criteria-card">
                        <h3>Medical Conditions (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Condition</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Person with Disability (PWD)</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>Chronic Illness (Maintenance)</td>
                                    <td><span class="points-badge">8 points</span></td>
                                </tr>
                                <tr>
                                    <td>Family Member with Disability</td>
                                    <td><span class="points-badge">5 points</span></td>
                                </tr>
                                <tr>
                                    <td>Family Member with Illness</td>
                                    <td><span class="points-badge">3 points</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- Family Size Card -->
                    <div class="criteria-card">
                        <h3>Family Size (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Family Size</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>5+ family members</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>3-4 family members</td>
                                    <td><span class="points-badge">5 points</span></td>
                                </tr>
                                <tr>
                                    <td>1-2 family members</td>
                                    <td><span class="points-badge">2 points</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- Employment Status Card -->
                    <div class="criteria-card">
                        <h3>Employment Status (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Status</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>No working household members</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>Only 1 working member</td>
                                    <td><span class="points-badge">7 points</span></td>
                                </tr>
                                <tr>
                                    <td>2 working members</td>
                                    <td><span class="points-badge">4 points</span></td>
                                </tr>
                                <tr>
                                    <td>3+ working members</td>
                                    <td><span class="points-badge">1 point</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- Special Circumstances Card -->
                    <div class="criteria-card">
                        <h3>Special Circumstances (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Circumstance</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>No stable income source</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>Natural disaster victim</td>
                                    <td><span class="points-badge">8 points</span></td>
                                </tr>
                                <tr>
                                    <td>Informal settler</td>
                                    <td><span class="points-badge">6 points</span></td>
                                </tr>
                                <tr>
                                    <td>Solo living senior citizen</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- Monthly Maintenance Card -->
                    <div class="criteria-card">
                        <h3>Monthly Maintenance (Max: 10 pts)</h3>
                        <table class="criteria-table">
                            <thead>
                                <tr>
                                    <th>Medical Expenses</th>
                                    <th>Points</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>₱5,000+ monthly medical expenses</td>
                                    <td><span class="points-badge">10 points</span></td>
                                </tr>
                                <tr>
                                    <td>₱3,000 - ₱4,999 medical expenses</td>
                                    <td><span class="points-badge">7 points</span></td>
                                </tr>
                                <tr>
                                    <td>₱1,000 - ₱2,999 medical expenses</td>
                                    <td><span class="points-badge">4 points</span></td>
                                </tr>
                                <tr>
                                    <td>Below ₱1,000 medical expenses</td>
                                    <td><span class="points-badge">2 points</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Us Page – Only the .about-section box is highlighted -->
    <section id="about" class="page-section hidden">
        <div class="container">
            <h2 class="page-title">About Us</h2>
            
            <div class="about-section">
                <div class="about-content">
                    <div class="about-grid-vertical">
                        <div class="about-card-vertical">
                            <i class="fas fa-eye"></i>
                            <div class="about-card-content">
                                <h3>Transparency</h3>
                                <p>We prioritize transparency in our processes to ensure all beneficiaries are fairly evaluated and ranked for aid distribution. Every point calculation and decision is documented and made available for review.</p>
                            </div>
                        </div>
                        <div class="about-card-vertical">
                            <i class="fas fa-bolt"></i>
                            <div class="about-card-content">
                                <h3>Efficiency</h3>
                                <p>Our goal is to streamline the aid distribution process, reducing delays and ensuring that help reaches those who need it most promptly through automated ranking and prioritization.</p>
                            </div>
                        </div>
                        <div class="about-card-vertical">
                            <i class="fas fa-balance-scale"></i>
                            <div class="about-card-content">
                                <h3>Fairness</h3>
                                <p>Every applicant is evaluated using the same criteria and point system, ensuring equal opportunity and eliminating bias in the selection process.</p>
                            </div>
                        </div>
                        <div class="about-card-vertical">
                            <i class="fas fa-handshake"></i>
                            <div class="about-card-content">
                                <h3>Community Focus</h3>
                                <p>We work closely with barangay officials and community leaders to identify and support those most in need within our community.</p>
                            </div>
                        </div>
                    </div>

                    <div class="faq-section">
                        <h3 style="color: var(--primary-dark); margin-bottom: 30px; text-align: center; font-weight: 600;">Your Questions Answered</h3>
                        <p style="text-align: center; margin-bottom: 30px; color: var(--text-dark); font-weight: 300;">
                            Find answers to common queries about our aid distribution process.
                        </p>
                        
                        <div class="faq-item">
                            <div class="faq-question">
                                <span><span style="margin-right: 10px;">🔎</span> What is the beneficiary ranking system?</span>
                                <i class="fas fa-chevron-down"></i>
                            </div>
                            <div class="faq-answer">
                                <p>The beneficiary ranking system is a point-based evaluation method used to determine the level of need of each applicant. It ensures that aid is distributed fairly and prioritized for individuals and families who are most vulnerable.</p>
                                <p style="margin-top: 10px;">Points are assigned based on six criteria: income level, medical conditions, family size, employment status, special circumstances, and monthly maintenance expenses. Higher total points indicate greater need.</p>
                            </div>
                        </div>
                        <div class="faq-item">
                            <div class="faq-question">
                                <span><span style="margin-right: 10px;">👥</span> Who is eligible for aid?</span>
                                <i class="fas fa-chevron-down"></i>
                            </div>
                            <div class="faq-answer">
                                <p>Eligibility for aid is determined based on socioeconomic status, health conditions, and individual or family circumstances. Those with lower income, medical needs, unemployment, or special vulnerabilities are given higher priority.</p>
                                <p style="margin-top: 10px;">Our goal is to support the most disadvantaged and at-risk members of the community.</p>
                            </div>
                        </div>
                        <div class="faq-item">
                            <div class="faq-question">
                                <span><span style="margin-right: 10px;">⚙️</span> How are beneficiaries ranked and filtered?</span>
                                <i class="fas fa-chevron-down"></i>
                            </div>
                            <div class="faq-answer">
                                <p>Beneficiaries are ranked using a standardized point system. Each applicant is evaluated using the same criteria to ensure fairness and transparency.</p>
                                <p style="margin-top: 10px;">On our website, authorized users can filter beneficiaries by their total points. This feature allows administrators to:</p>
                                <ul style="margin-left: 20px; margin-top: 10px;">
                                    <li>Sort from highest to lowest priority</li>
                                    <li>Quickly identify urgent cases</li>
                                    <li>Ensure efficient and organized aid distribution</li>
                                </ul>
                                <p style="margin-top: 10px;">This system promotes accountability and data-driven decision-making in the distribution process.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Admin Dashboard Page -->
    <section id="beneficiaries" class="page-section hidden">
        <div class="container">
            <div id="admin-dashboard">
                <!-- Admin Dashboard Content will be loaded here -->
            </div>
        </div>
    </section>

    <!-- Admin Registration Page – Updated username & password rules -->
    <section id="admin-register" class="page-section hidden">
        <div class="container">
            <h2 class="page-title">Admin Registration</h2>
            
            <div class="admin-register-form fade-in">
                <h3>Create Admin Account</h3>
                <form id="adminRegisterForm">
                    <div class="form-group">
                        <label for="adminUsername">Username (minimum 5 characters) *</label>
                        <input type="text" id="adminUsername" class="form-control" 
                               minlength="5" 
                               title="Minimum 5 characters – any letters, numbers, or symbols allowed" 
                               required>
                        <small>Minimum 5 characters – any letters, numbers, or symbols allowed</small>
                    </div>
                    <div class="form-group">
                        <label for="adminContact">Phone Number or Email *</label>
                        <input type="text" id="adminContact" class="form-control" 
                               pattern="(?:\+?\d{10,15}|[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,})" 
                               title="Enter a valid phone number (10-15 digits) or email address" 
                               required>
                        <small>Enter phone number (10-15 digits) or email address</small>
                    </div>
                    <div class="form-group">
                        <label for="adminPassword">Password *</label>
                        <input type="password" id="adminPassword" class="form-control" 
                               pattern="^(?=.*[A-Z]).{8,}$" 
                               title="Minimum 8 characters with at least 1 uppercase letter (any characters allowed)" 
                               required>
                        <small>Minimum 8 characters with at least 1 uppercase letter (any characters allowed)</small>
                        <div id="passwordStrength" class="password-strength"></div>
                        <div id="strengthText" class="strength-text"></div>
                    </div>
                    <div class="form-group">
                        <label for="adminConfirmPassword">Confirm Password *</label>
                        <input type="password" id="adminConfirmPassword" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="adminBarangay">Barangay Name *</label>
                        <input type="text" id="adminBarangay" class="form-control" placeholder="Enter your barangay name" required>
                        <small>Enter the full name of your barangay (e.g., Barangay San Isidro)</small>
                    </div>
                    <div class="form-actions">
                        <button type="submit" class="btn btn-primary">Register</button>
                        <a href="#" class="form-link" onclick="showPage('admin-login'); return false;">Already have an account? Login</a>
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- Admin Login Page -->
    <section id="admin-login" class="page-section hidden">
        <div class="container">
            <h2 class="page-title">Admin Login</h2>
            
            <div class="admin-login-form fade-in">
                <form id="adminLoginForm">
                    <div class="form-group">
                        <label for="loginUsername">Username</label>
                        <input type="text" id="loginUsername" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label for="loginPassword">Password</label>
                        <input type="password" id="loginPassword" class="form-control" required>
                    </div>
                    <div class="form-actions">
                        <button type="submit" class="btn btn-primary">Login</button>
                        <a href="#" class="form-link" onclick="showPage('admin-register'); return false;">Don't have an account? Register</a>
                    </div>
                </form>
            </div>
        </div>
    </section>

    <!-- Contact Us Page – Only the .contact-section box is highlighted -->
    <section id="contact" class="page-section hidden">
        <div class="container">
            <h2 class="page-title">Contact Us</h2>
            
            <div class="contact-section">
                <div class="contact-grid">
                    <div class="contact-info">
                        <h3 style="color: var(--primary-dark); margin-bottom: 25px; font-weight: 600;">Get In Touch</h3>
                        
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <div>
                                <h4 style="margin-bottom: 5px; color: var(--primary-dark); font-weight: 600;">Phone Number</h4>
                                <p style="font-size: 1.1rem;">09708262935</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <div>
                                <h4 style="margin-bottom: 5px; color: var(--primary-dark); font-weight: 600;">Email Address</h4>
                                <p style="font-size: 1.1rem;">ayudabulanph@gmail.com</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <h4 style="margin-bottom: 5px; color: var(--primary-dark); font-weight: 600;">Location</h4>
                                <p style="font-size: 1.1rem;">Bulan, Sorsogon, Philippines</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Toast Notification -->
    <div class="toast" id="toast"></div>

    <!-- Points Breakdown Modal -->
    <div class="modal hidden points-breakdown-modal" id="pointsBreakdownModal">
        <div class="modal-content">
            <h3>Points Breakdown</h3>
            <div id="points-breakdown-content">
                <!-- Points breakdown will be loaded here -->
            </div>
            <div class="modal-buttons">
                <button type="button" class="btn btn-primary" onclick="closePointsBreakdownModal()">Close</button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>About AYUDA</h3>
                    <p>AYUDA is a social aid platform that connects communities with resources, ensuring fair and transparent distribution of aid to those who need it most.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <a href="#" onclick="showPage('home'); return false;">Home</a>
                    <a href="#" onclick="showPage('criteria'); return false;">Criteria</a>
                    <a href="#" onclick="showPage('about'); return false;">About Us</a>
                    <a href="#" onclick="showPage('contact'); return false;">Contact Us</a>
                </div>
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p><i class="fas fa-phone"></i> 09708262935</p>
                    <p><i class="fas fa-envelope"></i> ayudabulanph@gmail.com</p>
                    <p><i class="fas fa-map-marker-alt"></i> Bulan, Sorsogon, Philippines</p>
                </div>
            </div>
            <div class="footer-bottom">
                &copy; 2026 AYUDA - Social Aid. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // ================================================
        // AYUDA CODE – MANUAL RANKING, NO SAMPLE DATA
        // ================================================
        
        let beneficiaries = [];
        let currentAdmin = null;
        let announcements = [];
        let rankingActive = false; // Whether ranking has been performed
        
        const pageSections = document.querySelectorAll('.page-section');
        const loggedOutNav = document.getElementById('logged-out-nav');
        const loggedInNav = document.getElementById('logged-in-nav');
        const logoutLink = document.getElementById('logout-link');
        const faqItems = document.querySelectorAll('.faq-item');
        const contactForm = document.getElementById('contactForm');
        const toast = document.getElementById('toast');
        const pointsBreakdownModal = document.getElementById('pointsBreakdownModal');

        function checkAdminStatus() {
            const adminData = localStorage.getItem('ayudaAdmin');
            if (adminData) {
                currentAdmin = JSON.parse(adminData);
                updateUIForLoggedInAdmin();
                return true;
            }
            updateUIForLoggedOut();
            return false;
        }

        function updateUIForLoggedInAdmin() {
            loggedOutNav.classList.remove('active');
            loggedInNav.classList.add('active');
            updateActiveNav();
        }

        function updateUIForLoggedOut() {
            loggedInNav.classList.remove('active');
            loggedOutNav.classList.add('active');
            updateActiveNav();
            const currentPage = window.location.hash.replace('#', '') || 'home';
            if (currentPage === 'beneficiaries') {
                showPage('home');
            }
        }

        function updateActiveNav() {
            const currentPage = window.location.hash.replace('#', '') || 'home';
            const navLinks = document.querySelectorAll('.nav-link');
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.dataset.page === currentPage) {
                    link.classList.add('active');
                }
            });
        }

        function logoutAdmin() {
            if (confirm('Are you sure you want to logout?')) {
                localStorage.removeItem('ayudaAdmin');
                currentAdmin = null;
                showToast('Logged out successfully!', 'success');
                updateUIForLoggedOut();
                showPage('home');
            }
        }

        function loadAdminDashboard() {
            if (!checkAdminStatus()) {
                showPage('admin-login');
                return;
            }
            beneficiaries = JSON.parse(localStorage.getItem('ayudaBeneficiaries') || '[]');
            announcements = JSON.parse(localStorage.getItem('ayudaAnnouncements') || '[]');
            const adminDashboard = document.getElementById('admin-dashboard');
            if (adminDashboard) {
                adminDashboard.innerHTML = `
                    <div class="admin-welcome">
                        <p>WELCOME BACK, ${currentAdmin.username}</p>
                    </div>
                    <div class="admin-tabs">
                        <button class="admin-tab-btn active" onclick="showAdminTab('beneficiaries')">Beneficiaries</button>
                    </div>
                    <div id="beneficiaries-tab" class="admin-tab-content active">
                        ${loadBeneficiariesTab()}
                    </div>
                `;
                updateBeneficiariesTable(false); // Show unranked initially
            }
        }

        function loadBeneficiariesTab() {
            return `
                <div class="admin-stats">
                    <div class="stat-card">
                        <i class="fas fa-users"></i>
                        <h4>Total Beneficiaries</h4>
                        <p>${beneficiaries.length}</p>
                    </div>
                    <div class="stat-card">
                        <i class="fas fa-chart-line"></i>
                        <h4>Highest Points</h4>
                        <p>${rankingActive ? (beneficiaries.length > 0 ? Math.max(...beneficiaries.map(b => b.totalPoints || 0)) : 0) : 'Not ranked'}</p>
                    </div>
                </div>
                
                <div id="add-beneficiary-container" class="add-beneficiary-form">
                    <h3 style="color: var(--primary-dark); margin-bottom: 25px; font-weight: 600;">Add New Beneficiary</h3>
                    <form id="beneficiaryForm">
                        <!-- Row 1: Full Name, Phone Number -->
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="beneficiaryName">Full Name *</label>
                                <input type="text" id="beneficiaryName" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="beneficiaryPhone">Phone Number *</label>
                                <input type="text" id="beneficiaryPhone" class="form-control" placeholder="+639123456789" required>
                            </div>
                        </div>
                        <!-- Row 2: Barangay, Monthly Income -->
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="beneficiaryBarangay">Barangay *</label>
                                <input type="text" id="beneficiaryBarangay" class="form-control" placeholder="Enter barangay name" required>
                            </div>
                            <div class="form-group">
                                <label for="monthlyIncome">Monthly Income (₱) *</label>
                                <input type="number" id="monthlyIncome" class="form-control" required>
                            </div>
                        </div>
                        <!-- Row 3: Medical Condition, Family Size, Working Household Members (three columns) -->
                        <div class="form-grid" style="grid-template-columns: repeat(3, 1fr);">
                            <div class="form-group">
                                <label for="medicalCondition">Medical Condition</label>
                                <select id="medicalCondition" class="form-control">
                                    <option value="">Select Condition</option>
                                    <option value="pwd">Person with Disability (PWD)</option>
                                    <option value="chronic">Chronic Illness</option>
                                    <option value="family_pwd">Family Member with Disability</option>
                                    <option value="family_illness">Family Member with Illness</option>
                                    <option value="none">None</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="familySize">Family Size *</label>
                                <input type="number" id="familySize" class="form-control" required>
                            </div>
                            <div class="form-group">
                                <label for="workingMembers">Working Household Members *</label>
                                <input type="number" id="workingMembers" class="form-control" required>
                            </div>
                        </div>
                        <!-- Row 4: Special Circumstance, Monthly Medical Expenses -->
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="specialCircumstance">Special Circumstance</label>
                                <select id="specialCircumstance" class="form-control">
                                    <option value="">Select Circumstance</option>
                                    <option value="no_income">No Stable Income Source</option>
                                    <option value="disaster">Natural Disaster Victim</option>
                                    <option value="informal">Informal Settler</option>
                                    <option value="solo_senior">Solo Living Senior Citizen</option>
                                    <option value="none">None</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="medicalExpenses">Monthly Medical Expenses (₱)</label>
                                <input type="number" id="medicalExpenses" class="form-control" value="0">
                            </div>
                        </div>
                        <div class="form-actions">
                            <button type="submit" class="btn btn-primary">Add Beneficiary</button>
                            <button type="button" class="btn" style="background: #f5f5f5; color: #333;" onclick="clearBeneficiaryForm()">Clear</button>
                        </div>
                    </form>
                </div>
                
                <h3 style="color: var(--primary-dark); margin: 40px 0 20px; font-weight: 600;">Beneficiaries List</h3>
                <div style="margin-bottom: 20px; display: flex; gap: 10px; align-items: center;">
                    <input type="text" id="searchBeneficiaries" class="form-control" placeholder="Search beneficiaries..." style="max-width: 300px;">
                    <button class="btn btn-outline" onclick="refreshList()" style="background: var(--primary); color: white;"><i class="fas fa-sync-alt"></i> Refresh List</button>
                    <button class="btn btn-primary" onclick="rankBeneficiaries()"><i class="fas fa-trophy"></i> Rank Beneficiaries</button>
                </div>
                <table class="ranking-table">
                    <thead>
                        <tr>
                            <th>Rank</th>
                            <th>Name</th>
                            <th>Phone</th>
                            <th>Barangay</th>
                            <th>Income (₱)</th>
                            <th>Family Size</th>
                            <th>Total Points</th>
                            <th>Actions</th>
                        </tr>
                    </thead>
                    <tbody id="beneficiariesTableBody">
                    </tbody>
                </table>
            `;
        }

        function showAdminTab(tabId) {
            document.querySelectorAll('.admin-tab-btn').forEach(btn => btn.classList.remove('active'));
            document.querySelectorAll('.admin-tab-content').forEach(content => content.classList.remove('active'));
            const tabBtn = Array.from(document.querySelectorAll('.admin-tab-btn')).find(btn => 
                btn.textContent.toLowerCase().includes(tabId)
            );
            if (tabBtn) tabBtn.classList.add('active');
            const tabContent = document.getElementById(`${tabId}-tab`);
            if (tabContent) tabContent.classList.add('active');
        }

        function calculatePointsWithBreakdown(data) {
            let breakdown = {
                income: { points: 0, explanation: '' },
                medicalCondition: { points: 0, explanation: '' },
                familySize: { points: 0, explanation: '' },
                workingMembers: { points: 0, explanation: '' },
                specialCircumstance: { points: 0, explanation: '' },
                medicalExpenses: { points: 0, explanation: '' }
            };
            
            if (data.income <= 5000) {
                breakdown.income.points = 10;
                breakdown.income.explanation = 'Income below ₱5,000 monthly';
            } else if (data.income <= 10000) {
                breakdown.income.points = 7;
                breakdown.income.explanation = 'Income ₱5,001 - ₱10,000 monthly';
            } else if (data.income <= 15000) {
                breakdown.income.points = 4;
                breakdown.income.explanation = 'Income ₱10,001 - ₱15,000 monthly';
            } else {
                breakdown.income.explanation = 'Income above ₱15,000 monthly';
            }
            
            switch(data.medicalCondition) {
                case 'pwd': 
                    breakdown.medicalCondition.points = 10;
                    breakdown.medicalCondition.explanation = 'Person with Disability (PWD)';
                    break;
                case 'chronic': 
                    breakdown.medicalCondition.points = 8;
                    breakdown.medicalCondition.explanation = 'Chronic Illness (Maintenance)';
                    break;
                case 'family_pwd': 
                    breakdown.medicalCondition.points = 5;
                    breakdown.medicalCondition.explanation = 'Family Member with Disability';
                    break;
                case 'family_illness': 
                    breakdown.medicalCondition.points = 3;
                    breakdown.medicalCondition.explanation = 'Family Member with Illness';
                    break;
                default:
                    breakdown.medicalCondition.explanation = 'No medical condition';
            }
            
            if (data.familySize >= 5) {
                breakdown.familySize.points = 10;
                breakdown.familySize.explanation = '5+ family members';
            } else if (data.familySize >= 3) {
                breakdown.familySize.points = 5;
                breakdown.familySize.explanation = '3-4 family members';
            } else if (data.familySize >= 1) {
                breakdown.familySize.points = 2;
                breakdown.familySize.explanation = '1-2 family members';
            }
            
            if (data.workingMembers === 0) {
                breakdown.workingMembers.points = 10;
                breakdown.workingMembers.explanation = 'No working household members';
            } else if (data.workingMembers === 1) {
                breakdown.workingMembers.points = 7;
                breakdown.workingMembers.explanation = 'Only 1 working member';
            } else if (data.workingMembers === 2) {
                breakdown.workingMembers.points = 4;
                breakdown.workingMembers.explanation = '2 working members';
            } else if (data.workingMembers >= 3) {
                breakdown.workingMembers.points = 1;
                breakdown.workingMembers.explanation = '3+ working members';
            }
            
            switch(data.specialCircumstance) {
                case 'no_income': 
                    breakdown.specialCircumstance.points = 10;
                    breakdown.specialCircumstance.explanation = 'No stable income source';
                    break;
                case 'disaster': 
                    breakdown.specialCircumstance.points = 8;
                    breakdown.specialCircumstance.explanation = 'Natural disaster victim';
                    break;
                case 'informal': 
                    breakdown.specialCircumstance.points = 6;
                    breakdown.specialCircumstance.explanation = 'Informal settler';
                    break;
                case 'solo_senior': 
                    breakdown.specialCircumstance.points = 10;
                    breakdown.specialCircumstance.explanation = 'Solo living senior citizen';
                    break;
                default:
                    breakdown.specialCircumstance.explanation = 'No special circumstance';
            }
            
            if (data.medicalExpenses >= 5000) {
                breakdown.medicalExpenses.points = 10;
                breakdown.medicalExpenses.explanation = '₱5,000+ monthly medical expenses';
            } else if (data.medicalExpenses >= 3000) {
                breakdown.medicalExpenses.points = 7;
                breakdown.medicalExpenses.explanation = '₱3,000 - ₱4,999 medical expenses';
            } else if (data.medicalExpenses >= 1000) {
                breakdown.medicalExpenses.points = 4;
                breakdown.medicalExpenses.explanation = '₱1,000 - ₱2,999 medical expenses';
            } else if (data.medicalExpenses > 0) {
                breakdown.medicalExpenses.points = 2;
                breakdown.medicalExpenses.explanation = 'Below ₱1,000 medical expenses';
            } else {
                breakdown.medicalExpenses.explanation = 'No medical expenses';
            }
            
            let totalPoints = 0;
            Object.values(breakdown).forEach(item => { totalPoints += item.points; });
            return { breakdown, totalPoints };
        }

        function calculatePoints(data) {
            return calculatePointsWithBreakdown(data).totalPoints;
        }

        function sortBeneficiaries() {
            return beneficiaries.sort((a, b) => (b.totalPoints || 0) - (a.totalPoints || 0));
        }

        function showPointsBreakdown(beneficiaryId) {
            const beneficiary = beneficiaries.find(b => b.id === beneficiaryId);
            if (!beneficiary) return;
            const result = calculatePointsWithBreakdown(beneficiary);
            const breakdownContent = document.getElementById('points-breakdown-content');
            breakdownContent.innerHTML = `
                <div style="background: var(--primary); color: var(--secondary); padding: 15px; border-radius: 8px; margin-bottom: 20px; text-align: center;">
                    <h4 style="margin: 0; font-size: 1.2rem;">TOTAL POINTS</h4>
                    <p style="font-size: 2.5rem; font-weight: 700; margin: 5px 0; color: var(--secondary);">${result.totalPoints}</p>
                    <p style="margin: 0; font-size: 0.9rem; opacity: 0.9;">Overall need assessment score</p>
                </div>
                <h4 style="color: var(--primary-dark); margin-bottom: 20px;">${beneficiary.name} - ${beneficiary.barangay}</h4>
                <table class="points-breakdown-table">
                    <thead>
                        <tr>
                            <th>Criterion</th>
                            <th>Points</th>
                            <th>Explanation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>Income Level</strong></td>
                            <td><span class="points-badge">${result.breakdown.income.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.income.explanation}</div></td>
                        </tr>
                        <tr>
                            <td><strong>Medical Condition</strong></td>
                            <td><span class="points-badge">${result.breakdown.medicalCondition.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.medicalCondition.explanation}</div></td>
                        </tr>
                        <tr>
                            <td><strong>Family Size</strong></td>
                            <td><span class="points-badge">${result.breakdown.familySize.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.familySize.explanation}</div></td>
                        </tr>
                        <tr>
                            <td><strong>Employment Status</strong></td>
                            <td><span class="points-badge">${result.breakdown.workingMembers.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.workingMembers.explanation}</div></td>
                        </tr>
                        <tr>
                            <td><strong>Special Circumstance</strong></td>
                            <td><span class="points-badge">${result.breakdown.specialCircumstance.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.specialCircumstance.explanation}</div></td>
                        </tr>
                        <tr>
                            <td><strong>Medical Expenses</strong></td>
                            <td><span class="points-badge">${result.breakdown.medicalExpenses.points} pts</span></td>
                            <td><div class="criterion-explanation">${result.breakdown.medicalExpenses.explanation}</div></td>
                        </tr>
                    </tbody>
                </table>
                <div style="margin-top: 20px; padding: 15px; background-color: var(--soft-blue); border-radius: 8px;">
                    <p style="margin: 0; color: var(--primary-dark); font-weight: 500;">
                        <i class="fas fa-info-circle"></i> Higher total points indicate greater need. Beneficiaries are ranked based on total points.
                    </p>
                </div>
            `;
            pointsBreakdownModal.classList.remove('hidden');
        }

        function closePointsBreakdownModal() {
            pointsBreakdownModal.classList.add('hidden');
        }

        function updateBeneficiariesTable(ranked) {
            const tableBody = document.getElementById('beneficiariesTableBody');
            if (!tableBody) return;
            
            tableBody.innerHTML = '';
            if (beneficiaries.length === 0) {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td colspan="8" style="text-align: center; padding: 40px; color: var(--text-dark); font-weight: 300;">
                        <i class="fas fa-users" style="font-size: 2rem; color: #ddd; margin-bottom: 10px; display: block;"></i>
                        No beneficiaries added yet. Add your first beneficiary using the form above.
                    </td>
                `;
                tableBody.appendChild(row);
                return;
            }

            let displayBeneficiaries;
            if (ranked) {
                // Sort by points descending
                displayBeneficiaries = [...beneficiaries].sort((a, b) => (b.totalPoints || 0) - (a.totalPoints || 0));
            } else {
                // Display as stored (by id or original order)
                displayBeneficiaries = [...beneficiaries].sort((a, b) => a.id - b.id);
            }

            displayBeneficiaries.forEach((beneficiary, index) => {
                const row = document.createElement('tr');
                const rank = ranked ? index + 1 : '-';
                let rankDisplay = '';
                if (ranked) {
                    if (rank === 1) {
                        rankDisplay = '<span class="rank-badge rank-1">1</span>';
                    } else if (rank === 2) {
                        rankDisplay = '<span class="rank-badge rank-2">2</span>';
                    } else if (rank === 3) {
                        rankDisplay = '<span class="rank-badge rank-3">3</span>';
                    } else {
                        rankDisplay = `<span class="rank-badge rank-other">${rank}</span>`;
                    }
                } else {
                    rankDisplay = '-';
                }
                
                const pointsDisplay = ranked ? (beneficiary.totalPoints || 0) : '-';
                
                row.innerHTML = `
                    <td>${rankDisplay}</td>
                    <td><strong>${beneficiary.name}</strong></td>
                    <td>${beneficiary.phone || 'N/A'}</td>
                    <td>${beneficiary.barangay || 'N/A'}</td>
                    <td>₱${(beneficiary.income || 0).toLocaleString()}</td>
                    <td>${beneficiary.familySize || beneficiary.householdSize || 0} members</td>
                    <td><strong>${pointsDisplay}</strong></td>
                    <td>
                        <button class="btn" onclick="showPointsBreakdown(${beneficiary.id})" style="padding: 5px 10px; background: var(--primary); color: white; border: none; font-weight: 500; margin-right: 5px;">
                            <i class="fas fa-chart-pie"></i> View Points
                        </button>
                        <button class="btn" onclick="editBeneficiary(${beneficiary.id})" style="padding: 5px 10px; background: var(--soft-blue); color: var(--primary); border: none; font-weight: 500; margin-right: 5px;">Edit</button>
                        <button class="btn" onclick="removeBeneficiary(${beneficiary.id})" style="padding: 5px 10px; background: #ffebee; color: #f44336; border: none; font-weight: 500;">Remove</button>
                    </td>
                `;
                tableBody.appendChild(row);
            });
        }

        function rankBeneficiaries() {
            // Calculate points for all beneficiaries
            beneficiaries.forEach(b => {
                const result = calculatePointsWithBreakdown(b);
                b.totalPoints = result.totalPoints;
            });
            // Save to localStorage
            localStorage.setItem('ayudaBeneficiaries', JSON.stringify(beneficiaries));
            rankingActive = true;
            updateBeneficiariesTable(true);
            showToast('Beneficiaries ranked successfully!', 'success');
        }

        function refreshList() {
            // Reload from storage and show unranked
            beneficiaries = JSON.parse(localStorage.getItem('ayudaBeneficiaries') || '[]');
            rankingActive = false;
            updateBeneficiariesTable(false);
            showToast('List refreshed (unranked view)', 'info');
        }

        function handleAddBeneficiary(e) {
            e.preventDefault();
            const newBeneficiary = {
                id: beneficiaries.length > 0 ? Math.max(...beneficiaries.map(b => b.id)) + 1 : 1,
                name: document.getElementById('beneficiaryName').value,
                phone: document.getElementById('beneficiaryPhone').value,
                barangay: document.getElementById('beneficiaryBarangay').value,
                income: parseInt(document.getElementById('monthlyIncome').value) || 0,
                familySize: parseInt(document.getElementById('familySize').value) || 1,
                workingMembers: parseInt(document.getElementById('workingMembers').value) || 0,
                medicalCondition: document.getElementById('medicalCondition').value,
                specialCircumstance: document.getElementById('specialCircumstance').value,
                medicalExpenses: parseInt(document.getElementById('medicalExpenses').value) || 0,
                status: 'active',
                dateAdded: new Date().toISOString(),
                addedBy: currentAdmin ? currentAdmin.username : 'System'
                // No totalPoints yet
            };
            beneficiaries.push(newBeneficiary);
            localStorage.setItem('ayudaBeneficiaries', JSON.stringify(beneficiaries));
            rankingActive = false; // New beneficiary added, ranking no longer valid
            showToast('Beneficiary added successfully!', 'success');
            updateBeneficiariesTable(false);
            clearBeneficiaryForm();
        }

        function clearBeneficiaryForm() {
            const form = document.getElementById('beneficiaryForm');
            if (form) form.reset();
        }

        function removeBeneficiary(id) {
            if (confirm('Are you sure you want to remove this beneficiary?')) {
                beneficiaries = beneficiaries.filter(b => b.id !== id);
                localStorage.setItem('ayudaBeneficiaries', JSON.stringify(beneficiaries));
                rankingActive = false;
                updateBeneficiariesTable(false);
                showToast('Beneficiary removed successfully!', 'success');
            }
        }

        function editBeneficiary(id) {
            const beneficiary = beneficiaries.find(b => b.id === id);
            if (beneficiary) {
                document.getElementById('beneficiaryName').value = beneficiary.name;
                document.getElementById('beneficiaryPhone').value = beneficiary.phone;
                document.getElementById('beneficiaryBarangay').value = beneficiary.barangay;
                document.getElementById('monthlyIncome').value = beneficiary.income;
                document.getElementById('familySize').value = beneficiary.familySize || beneficiary.householdSize || 1;
                document.getElementById('workingMembers').value = beneficiary.workingMembers;
                document.getElementById('medicalCondition').value = beneficiary.medicalCondition;
                document.getElementById('specialCircumstance').value = beneficiary.specialCircumstance;
                document.getElementById('medicalExpenses').value = beneficiary.medicalExpenses;
                showToast('Edit beneficiary details and save changes', 'info');
            }
        }

        function showPage(pageId) {
            pageSections.forEach(section => section.classList.add('hidden'));
            const pageElement = document.getElementById(pageId);
            if (pageElement) pageElement.classList.remove('hidden');
            updateActiveNav();
            if (pageId === 'beneficiaries') loadAdminDashboard();
            window.location.hash = pageId;
        }

        function showToast(message, type = 'success', duration = 3000) {
            toast.textContent = message;
            toast.className = 'toast';
            toast.classList.add(type, 'show');
            setTimeout(() => { toast.classList.remove('show'); }, duration);
        }

        function setupPasswordStrengthIndicator() {
            const passwordInput = document.getElementById('adminPassword');
            if (passwordInput) {
                passwordInput.addEventListener('input', function() {
                    const strengthIndicator = document.getElementById('passwordStrength');
                    const strengthText = document.getElementById('strengthText');
                    const password = this.value;
                    let strength = 0;
                    let text = 'Password Strength: ';
                    if (password.length >= 8) strength++;
                    if (/[A-Z]/.test(password)) strength++;
                    if (/\d/.test(password)) strength++;
                    if (/[!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]/.test(password)) strength++;
                    switch(strength) {
                        case 0: strengthIndicator.className = 'password-strength strength-weak'; text += 'Weak - Minimum 8 characters needed'; break;
                        case 1: strengthIndicator.className = 'password-strength strength-fair'; text += 'Fair - Add uppercase letter and number'; break;
                        case 2: strengthIndicator.className = 'password-strength strength-good'; text += 'Good - Almost there'; break;
                        case 3: strengthIndicator.className = 'password-strength strength-good'; text += 'Good - Consider adding special characters'; break;
                        case 4: strengthIndicator.className = 'password-strength strength-strong'; text += 'Strong - Meets all requirements'; break;
                    }
                    if (strengthText) strengthText.textContent = text;
                });
            }
        }

        function init() {
            checkAdminStatus();
            const pageFromHash = window.location.hash.replace('#', '');
            if (pageFromHash && document.getElementById(pageFromHash)) {
                showPage(pageFromHash);
            } else {
                showPage('home');
            }
            setupEventListeners();
            setupPasswordStrengthIndicator();
            // No sample data – start with empty array
            beneficiaries = JSON.parse(localStorage.getItem('ayudaBeneficiaries') || '[]');
            rankingActive = false; // Initially not ranked
        }

        function setupEventListeners() {
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const pageId = link.dataset.page;
                    if (pageId === 'beneficiaries' && !checkAdminStatus()) {
                        showPage('admin-login');
                        return;
                    }
                    showPage(pageId);
                });
            });
            if (logoutLink) {
                logoutLink.addEventListener('click', (e) => { e.preventDefault(); logoutAdmin(); });
            }
            faqItems.forEach(item => {
                item.addEventListener('click', () => { item.classList.toggle('active'); });
            });
            const adminRegisterForm = document.getElementById('adminRegisterForm');
            if (adminRegisterForm) {
                adminRegisterForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const username = document.getElementById('adminUsername').value;
                    const contact = document.getElementById('adminContact').value;
                    const password = document.getElementById('adminPassword').value;
                    const confirmPassword = document.getElementById('adminConfirmPassword').value;
                    const barangay = document.getElementById('adminBarangay').value;
                    
                    if (username.length < 5) {
                        showToast('Username must be at least 5 characters long', 'error');
                        return;
                    }
                    
                    const phoneRegex = /^\+?\d{10,15}$/;
                    const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
                    if (!phoneRegex.test(contact) && !emailRegex.test(contact)) {
                        showToast('Please enter a valid phone number (10-15 digits) or email address', 'error');
                        return;
                    }
                    
                    const passwordRegex = /^(?=.*[A-Z]).{8,}$/;
                    if (!passwordRegex.test(password)) {
                        showToast('Password must be at least 8 characters with at least 1 uppercase letter', 'error');
                        return;
                    }
                    
                    if (password !== confirmPassword) {
                        showToast('Passwords do not match', 'error');
                        return;
                    }
                    if (!barangay) {
                        showToast('Please enter your barangay name', 'error');
                        return;
                    }
                    const existingAdmins = JSON.parse(localStorage.getItem('ayudaAdmins') || '[]');
                    if (existingAdmins.some(admin => admin.username === username)) {
                        showToast('Username already exists. Please choose another.', 'error');
                        return;
                    }
                    const adminInfo = { username, contact, password, barangay, registeredAt: new Date().toISOString() };
                    existingAdmins.push(adminInfo);
                    localStorage.setItem('ayudaAdmins', JSON.stringify(existingAdmins));
                    currentAdmin = adminInfo;
                    localStorage.setItem('ayudaAdmin', JSON.stringify(adminInfo));
                    showToast('Admin registration successful! You are now logged in.', 'success');
                    updateUIForLoggedInAdmin();
                    showPage('home');
                    adminRegisterForm.reset();
                });
            }
            const adminLoginForm = document.getElementById('adminLoginForm');
            if (adminLoginForm) {
                adminLoginForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const username = document.getElementById('loginUsername').value;
                    const password = document.getElementById('loginPassword').value;
                    const existingAdmins = JSON.parse(localStorage.getItem('ayudaAdmins') || '[]');
                    const admin = existingAdmins.find(a => a.username === username && a.password === password);
                    if (admin) {
                        currentAdmin = admin;
                        localStorage.setItem('ayudaAdmin', JSON.stringify(admin));
                        showToast('Login successful! Welcome back.', 'success');
                        updateUIForLoggedInAdmin();
                        showPage('home');
                        adminLoginForm.reset();
                    } else {
                        showToast('Invalid username or password', 'error');
                    }
                });
            }
            document.addEventListener('submit', function(e) {
                if (e.target && e.target.id === 'beneficiaryForm') {
                    e.preventDefault();
                    handleAddBeneficiary(e);
                }
            });
            document.addEventListener('input', function(e) {
                if (e.target && e.target.id === 'searchBeneficiaries') {
                    const searchTerm = e.target.value.toLowerCase();
                    const tableBody = document.getElementById('beneficiariesTableBody');
                    if (tableBody) {
                        const rows = tableBody.querySelectorAll('tr');
                        rows.forEach(row => {
                            const nameCell = row.querySelector('td:nth-child(2)');
                            const phoneCell = row.querySelector('td:nth-child(3)');
                            const barangayCell = row.querySelector('td:nth-child(4)');
                            if (nameCell && phoneCell && barangayCell) {
                                const name = nameCell.textContent.toLowerCase();
                                const phone = phoneCell.textContent.toLowerCase();
                                const barangay = barangayCell.textContent.toLowerCase();
                                const matches = name.includes(searchTerm) || phone.includes(searchTerm) || barangay.includes(searchTerm);
                                row.style.display = matches ? '' : 'none';
                            }
                        });
                    }
                }
            });
            const modals = document.querySelectorAll('.modal');
            modals.forEach(modal => {
                modal.addEventListener('click', (e) => { if (e.target === modal) modal.classList.add('hidden'); });
            });
        }

        document.addEventListener('DOMContentLoaded', init);
        window.addEventListener('hashchange', function() {
            const pageFromHash = window.location.hash.replace('#', '');
            if (pageFromHash && document.getElementById(pageFromHash)) showPage(pageFromHash);
        });
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                document.querySelectorAll('.modal:not(.hidden)').forEach(modal => modal.classList.add('hidden'));
            }
        });

        window.showPage = showPage;
        window.showPointsBreakdown = showPointsBreakdown;
        window.closePointsBreakdownModal = closePointsBreakdownModal;
        window.showAdminTab = showAdminTab;
        window.clearBeneficiaryForm = clearBeneficiaryForm;
        window.editBeneficiary = editBeneficiary;
        window.removeBeneficiary = removeBeneficiary;
        window.logoutAdmin = logoutAdmin;
        window.rankBeneficiaries = rankBeneficiaries;
        window.refreshList = refreshList;
    </script>
</body>
</html>
