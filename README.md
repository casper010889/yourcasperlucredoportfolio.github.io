<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Professional portfolio of Casper - Web Developer and Graphic Designer">
    <title>Casper | Web Developer & Graphic Designer</title>

    <style>
        /* =========================================================
           PROFESSIONAL PORTFOLIO WEBSITE
           Everything is contained in this single index.html file.
           No external libraries are required.
           ========================================================= */

        :root {
            --bg: #070b16;
            --bg-secondary: #0c1222;
            --card: rgba(17, 25, 45, 0.78);
            --card-solid: #11192d;
            --text: #f4f7ff;
            --muted: #9ba8c7;
            --primary: #4f7cff;
            --primary-light: #7c9cff;
            --accent: #6c4cff;
            --border: rgba(124, 156, 255, 0.16);
            --shadow: 0 20px 50px rgba(0, 0, 0, 0.28);
            --radius: 18px;
            --max-width: 1180px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        html {
            scroll-padding-top: 85px;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background:
                radial-gradient(circle at 10% 10%, rgba(79, 124, 255, 0.13), transparent 30%),
                radial-gradient(circle at 90% 20%, rgba(108, 76, 255, 0.12), transparent 28%),
                var(--bg);
            color: var(--text);
            line-height: 1.7;
            overflow-x: hidden;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        img {
            max-width: 100%;
            display: block;
        }

        section {
            padding: 100px 20px;
        }

        .container {
            width: min(var(--max-width), 100%);
            margin: auto;
        }

        /* =========================================================
           NAVIGATION
           ========================================================= */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(7, 11, 22, 0.82);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
        }

        .navbar {
            width: min(var(--max-width), calc(100% - 40px));
            height: 72px;
            margin: auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-size: 1.4rem;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .logo span {
            color: var(--primary-light);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 28px;
            align-items: center;
        }

        .nav-links a {
            color: var(--muted);
            font-size: 0.92rem;
            font-weight: 600;
            transition: 0.3s ease;
        }

        .nav-links a:hover,
        .nav-links a.active {
            color: var(--text);
        }

        .menu-toggle {
            display: none;
            border: none;
            background: transparent;
            color: white;
            font-size: 1.7rem;
            cursor: pointer;
        }

        /* =========================================================
           GENERAL COMPONENTS
           ========================================================= */

        .section-label {
            display: inline-block;
            color: var(--primary-light);
            background: rgba(79, 124, 255, 0.1);
            border: 1px solid rgba(79, 124, 255, 0.18);
            padding: 7px 13px;
            border-radius: 999px;
            font-size: 0.78rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }

        .section-title {
            font-size: clamp(2rem, 5vw, 3rem);
            line-height: 1.1;
            margin-bottom: 18px;
            letter-spacing: -1.5px;
        }

        .section-description {
            color: var(--muted);
            max-width: 650px;
        }

        .section-heading {
            margin-bottom: 50px;
        }

        .gradient-text {
            background: linear-gradient(90deg, #7c9cff, #8b7cff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 13px 21px;
            border-radius: 10px;
            font-weight: 700;
            font-size: 0.92rem;
            transition: 0.3s ease;
            cursor: pointer;
            border: 1px solid transparent;
        }

        .btn-primary {
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            box-shadow: 0 10px 30px rgba(79, 124, 255, 0.2);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(79, 124, 255, 0.32);
        }

        .btn-outline {
            border-color: var(--border);
            color: var(--text);
            background: rgba(255, 255, 255, 0.02);
        }

        .btn-outline:hover {
            border-color: var(--primary);
            background: rgba(79, 124, 255, 0.08);
            transform: translateY(-3px);
        }

        .card {
            background: var(--card);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            backdrop-filter: blur(12px);
        }

        /* =========================================================
           HOME
           ========================================================= */

        #home {
            min-height: 100vh;
            padding-top: 150px;
            display: flex;
            align-items: center;
            position: relative;
        }

        .hero {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 70px;
            align-items: center;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 7px 12px;
            background: rgba(79, 124, 255, 0.09);
            border: 1px solid rgba(79, 124, 255, 0.18);
            border-radius: 999px;
            color: var(--primary-light);
            font-size: 0.8rem;
            margin-bottom: 20px;
        }

        .status-dot {
            width: 8px;
            height: 8px;
            background: #55e69b;
            border-radius: 50%;
            box-shadow: 0 0 12px rgba(85, 230, 155, 0.8);
        }

        .hero h1 {
            font-size: clamp(3rem, 7vw, 5.5rem);
            line-height: 0.98;
            letter-spacing: -4px;
            margin-bottom: 22px;
        }

        .hero-subtitle {
            color: var(--muted);
            font-size: 1.12rem;
            max-width: 640px;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .hero-card {
            min-height: 420px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            padding: 35px;
        }

        .hero-card::before {
            content: "";
            position: absolute;
            width: 240px;
            height: 240px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            filter: blur(55px);
            opacity: 0.32;
        }

        .profile-circle {
            width: 230px;
            height: 230px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            z-index: 1;
            background:
                linear-gradient(var(--bg-secondary), var(--bg-secondary)) padding-box,
                linear-gradient(135deg, var(--primary), var(--accent)) border-box;
            border: 2px solid transparent;
        }

        .profile-circle span {
            font-size: 4.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fff, #7c9cff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .floating-card {
            position: absolute;
            z-index: 2;
            background: rgba(14, 21, 39, 0.9);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 13px 16px;
            box-shadow: var(--shadow);
            font-size: 0.82rem;
        }

        .floating-card.one {
            top: 50px;
            right: 25px;
        }

        .floating-card.two {
            bottom: 55px;
            left: 20px;
        }

        /* =========================================================
           ABOUT
           ========================================================= */

        .about-grid {
            display: grid;
            grid-template-columns: 0.85fr 1.15fr;
            gap: 50px;
            align-items: stretch;
        }

        .about-card {
            padding: 35px;
        }

        .about-icon {
            width: 58px;
            height: 58px;
            border-radius: 14px;
            display: grid;
            place-items: center;
            background: rgba(79, 124, 255, 0.1);
            color: var(--primary-light);
            font-size: 1.5rem;
            margin-bottom: 22px;
        }

        .about-card h3 {
            margin-bottom: 15px;
            font-size: 1.35rem;
        }

        .about-card p {
            color: var(--muted);
            margin-bottom: 18px;
        }

        .quick-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-top: 25px;
        }

        .info-item {
            padding: 15px;
            background: rgba(255, 255, 255, 0.025);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 12px;
        }

        .info-item small {
            display: block;
            color: var(--muted);
            margin-bottom: 3px;
        }

        .info-item strong {
            font-size: 0.9rem;
        }

        /* =========================================================
           SKILLS
           ========================================================= */

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 18px;
        }

        .skill-card {
            padding: 25px;
            transition: 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-7px);
            border-color: rgba(124, 156, 255, 0.35);
        }

        .skill-top {
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;
        }

        .skill-top span:last-child {
            color: var(--primary-light);
            font-size: 0.82rem;
        }

        .progress {
            height: 7px;
            background: rgba(255, 255, 255, 0.07);
            border-radius: 99px;
            overflow: hidden;
        }

        .progress span {
            display: block;
            height: 100%;
            border-radius: inherit;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }

        /* =========================================================
           EXPERIENCE / EDUCATION
           ========================================================= */

        .timeline {
            position: relative;
            max-width: 850px;
            margin: auto;
        }

        .timeline::before {
            content: "";
            position: absolute;
            left: 13px;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(var(--primary), rgba(79, 124, 255, 0.05));
        }

        .timeline-item {
            position: relative;
            padding-left: 50px;
            margin-bottom: 35px;
        }

        .timeline-dot {
            position: absolute;
            left: 5px;
            top: 6px;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            background: var(--bg);
            border: 4px solid var(--primary);
            box-shadow: 0 0 15px rgba(79, 124, 255, 0.5);
        }

        .timeline-content {
            padding: 27px;
        }

        .timeline-date {
            display: inline-block;
            color: var(--primary-light);
            font-size: 0.78rem;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .timeline-content h3 {
            margin-bottom: 5px;
        }

        .timeline-content h4 {
            color: var(--muted);
            font-size: 0.9rem;
            font-weight: 500;
            margin-bottom: 13px;
        }

        .timeline-content p {
            color: var(--muted);
        }

        /* =========================================================
           PROJECTS
           ========================================================= */

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 22px;
        }

        .project-card {
            overflow: hidden;
            transition: 0.35s ease;
        }

        .project-card:hover {
            transform: translateY(-8px);
            border-color: rgba(124, 156, 255, 0.35);
        }

        .project-image {
            height: 190px;
            position: relative;
            overflow: hidden;
            display: grid;
            place-items: center;
            background:
                linear-gradient(135deg, rgba(79, 124, 255, 0.3), rgba(108, 76, 255, 0.2)),
                #10182b;
        }

        .project-image::before {
            content: "";
            width: 100px;
            height: 100px;
            border-radius: 25px;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            transform: rotate(25deg);
            filter: blur(2px);
            opacity: 0.8;
        }

        .project-number {
            position: absolute;
            font-size: 3rem;
            font-weight: 900;
            opacity: 0.85;
        }

        .project-body {
            padding: 25px;
        }

        .project-body h3 {
            margin-bottom: 10px;
        }

        .project-body p {
            color: var(--muted);
            font-size: 0.9rem;
            margin-bottom: 18px;
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 7px;
        }

        .tag {
            padding: 5px 9px;
            border-radius: 7px;
            background: rgba(79, 124, 255, 0.09);
            color: var(--primary-light);
            font-size: 0.72rem;
            border: 1px solid rgba(79, 124, 255, 0.12);
        }

        /* =========================================================
           SERVICES
           ========================================================= */

        .services-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .service-card {
            padding: 30px;
            transition: 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-7px);
            border-color: rgba(124, 156, 255, 0.35);
        }

        .service-icon {
            width: 54px;
            height: 54px;
            display: grid;
            place-items: center;
            border-radius: 13px;
            background: rgba(79, 124, 255, 0.1);
            color: var(--primary-light);
            font-size: 1.4rem;
            margin-bottom: 20px;
        }

        .service-card h3 {
            margin-bottom: 10px;
        }

        .service-card p {
            color: var(--muted);
            font-size: 0.9rem;
        }

        /* =========================================================
           CERTIFICATIONS
           ========================================================= */

        .certification-card {
            padding: 32px;
            display: flex;
            align-items: center;
            gap: 25px;
            max-width: 850px;
            margin: auto;
        }

        .certificate-icon {
            min-width: 70px;
            height: 70px;
            border-radius: 16px;
            display: grid;
            place-items: center;
            background: linear-gradient(135deg, rgba(79, 124, 255, 0.2), rgba(108, 76, 255, 0.2));
            border: 1px solid var(--border);
            font-size: 1.8rem;
        }

        .certification-card p {
            color: var(--muted);
        }

        /* =========================================================
           CONTACT
           ========================================================= */

        .contact-grid {
            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 25px;
        }

        .contact-info {
            padding: 30px;
        }

        .contact-info h3 {
            margin-bottom: 12px;
        }

        .contact-info > p {
            color: var(--muted);
            margin-bottom: 25px;
        }

        .contact-item {
            display: flex;
            gap: 15px;
            align-items: flex-start;
            margin-bottom: 22px;
        }

        .contact-icon {
            width: 42px;
            height: 42px;
            min-width: 42px;
            display: grid;
            place-items: center;
            border-radius: 10px;
            background: rgba(79, 124, 255, 0.1);
            color: var(--primary-light);
        }

        .contact-item small {
            display: block;
            color: var(--muted);
            margin-bottom: 2px;
        }

        .contact-item a:hover {
            color: var(--primary-light);
        }

        .contact-form {
            padding: 30px;
        }

        .form-group {
            margin-bottom: 18px;
        }

        .form-group label {
            display: block;
            margin-bottom: 7px;
            font-size: 0.82rem;
            font-weight: 700;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            border: 1px solid rgba(255, 255, 255, 0.08);
            background: rgba(255, 255, 255, 0.035);
            color: white;
            border-radius: 10px;
            padding: 13px 14px;
            outline: none;
            font-family: inherit;
            transition: 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 124, 255, 0.08);
        }

        .form-group textarea {
            min-height: 130px;
            resize: vertical;
        }

        /* =========================================================
           FOOTER
           ========================================================= */

        footer {
            padding: 35px 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.06);
            background: rgba(0, 0, 0, 0.15);
        }

        .footer-content {
            width: min(var(--max-width), 100%);
            margin: auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
        }

        .footer-content p {
            color: var(--muted);
            font-size: 0.85rem;
        }

        .social-links {
            display: flex;
            gap: 10px;
        }

        .social-links a {
            width: 38px;
            height: 38px;
            display: grid;
            place-items: center;
            border: 1px solid var(--border);
            border-radius: 9px;
            color: var(--muted);
            transition: 0.3s ease;
        }

        .social-links a:hover {
            color: white;
            border-color: var(--primary);
            background: rgba(79, 124, 255, 0.1);
            transform: translateY(-3px);
        }

        /* =========================================================
           SCROLL REVEAL
           ========================================================= */

        .reveal {
            opacity: 0;
            transform: translateY(25px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }

        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* =========================================================
           RESPONSIVE DESIGN
           ========================================================= */

        @media (max-width: 900px) {
            .hero,
            .about-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .hero {
                gap: 45px;
            }

            .hero-card {
                min-height: 320px;
            }

            .skills-grid,
            .projects-grid,
            .services-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 700px) {
            section {
                padding: 75px 18px;
            }

            .navbar {
                width: calc(100% - 30px);
            }

            .menu-toggle {
                display: block;
            }

            .nav-links {
                position: absolute;
                top: 72px;
                left: 0;
                width: 100%;
                flex-direction: column;
                gap: 0;
                padding: 10px 20px 20px;
                background: rgba(7, 11, 22, 0.97);
                border-bottom: 1px solid var(--border);
                transform: translateY(-150%);
                transition: 0.3s ease;
                pointer-events: none;
            }

            .nav-links.open {
                transform: translateY(0);
                pointer-events: auto;
            }

            .nav-links li {
                width: 100%;
            }

            .nav-links a {
                display: block;
                padding: 13px 5px;
            }

            .hero h1 {
                letter-spacing: -2px;
            }

            .skills-grid,
            .projects-grid,
            .services-grid {
                grid-template-columns: 1fr;
            }

            .quick-info {
                grid-template-columns: 1fr;
            }

            .certification-card {
                align-items: flex-start;
                flex-direction: column;
            }

            .footer-content {
                flex-direction: column;
                text-align: center;
            }
        }

        @media (max-width: 430px) {
            .hero-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }

            .hero-card {
                min-height: 290px;
            }

            .profile-circle {
                width: 185px;
                height: 185px;
            }

            .profile-circle span {
                font-size: 3.5rem;
            }

            .floating-card.one {
                right: 10px;
                top: 30px;
            }

            .floating-card.two {
                left: 10px;
                bottom: 30px;
            }
        }
    </style>
</head>

<body>

    <!-- =========================================================
         NAVIGATION
         ========================================================= -->

    <header>
        <nav class="navbar">
            <!-- EDIT: Change your logo/name here -->
            <a href="#home" class="logo">Casper<span>.</span></a>

            <button class="menu-toggle" id="menuToggle" aria-label="Open navigation">
                ☰
            </button>

            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#certifications">Certifications</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>


    <!-- =========================================================
         HOME
         ========================================================= -->

    <main>

        <section id="home">
            <div class="container hero">

                <div class="hero-content reveal">

                    <div class="hero-badge">
                        <span class="status-dot"></span>
                        Available for opportunities
                    </div>

                    <!-- EDIT: Change your name and professional title here -->
                    <h1>
                        Hi, I'm <span class="gradient-text">Casper</span>.
                        <br>
                        <span style="font-size: 0.72em;">Web Developer & Graphic Designer</span>
                    </h1>

                    <!-- EDIT: Replace this with your own short introduction -->
                    <p class="hero-subtitle">
                        I create modern websites and engaging visual designs that help
                        individuals, businesses, and organizations build a strong digital presence.
                    </p>

                    <div class="hero-buttons">
                        <a href="#projects" class="btn btn-primary">
                            View My Projects →
                        </a>

                        <a href="#contact" class="btn btn-outline">
                            Let's Work Together
                        </a>
                    </div>

                </div>

                <div class="hero-card card reveal">

                    <div class="profile-circle">
                        <!-- EDIT: You can replace "C" with your initials -->
                        <span>C</span>
                    </div>

                    <div class="floating-card one">
                        💻 Web Development
                    </div>

                    <div class="floating-card two">
                        🎨 Graphic Design
                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             ABOUT
             ===================================================== -->

        <section id="about">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">About Me</span>
                    <h2 class="section-title">Building digital experiences with <span class="gradient-text">purpose.</span></h2>

                    <!-- EDIT: Replace this description with your own -->
                    <p class="section-description">
                        I'm a passionate web developer and graphic designer interested in
                        creating clean, useful, and visually appealing digital experiences.
                    </p>
                </div>

                <div class="about-grid">

                    <div class="about-card card reveal">
                        <div class="about-icon">✦</div>

                        <h3>Who I Am</h3>

                        <!-- EDIT: Write more about yourself here -->
                        <p>
                            I enjoy combining technology and creativity to develop websites,
                            digital interfaces, and visual materials. My goal is to create
                            work that is professional, easy to use, and visually engaging.
                        </p>

                        <p>
                            I'm continuously learning new technologies and improving my
                            design and development skills.
                        </p>
                    </div>

                    <div class="about-card card reveal">

                        <h3>Quick Information</h3>

                        <div class="quick-info">

                            <div class="info-item">
                                <small>Name</small>
                                <strong>Casper</strong>
                            </div>

                            <div class="info-item">
                                <small>Profession</small>
                                <strong>Web Developer & Graphic Designer</strong>
                            </div>

                            <div class="info-item">
                                <small>Education</small>
                                <strong>STI Surigao</strong>
                            </div>

                            <div class="info-item">
                                <small>Certification</small>
                                <strong>NC II</strong>
                            </div>

                            <div class="info-item">
                                <small>Email</small>
                                <strong>Casper010889@gmail.com</strong>
                            </div>

                            <div class="info-item">
                                <small>Location</small>
                                <strong>Surigao City, Philippines</strong>
                            </div>

                        </div>

                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             SKILLS
             ===================================================== -->

        <section id="skills">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Skills</span>
                    <h2 class="section-title">My <span class="gradient-text">Skills</span></h2>

                    <!-- EDIT: Replace or add your skills -->
                    <p class="section-description">
                        A combination of technical, creative, and problem-solving skills
                        used to build professional digital projects.
                    </p>
                </div>

                <div class="skills-grid">

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>HTML5</strong>
                            <span>90%</span>
                        </div>
                        <div class="progress">
                            <span style="width:90%"></span>
                        </div>
                    </div>

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>CSS3</strong>
                            <span>85%</span>
                        </div>
                        <div class="progress">
                            <span style="width:85%"></span>
                        </div>
                    </div>

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>JavaScript</strong>
                            <span>75%</span>
                        </div>
                        <div class="progress">
                            <span style="width:75%"></span>
                        </div>
                    </div>

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>Web Design</strong>
                            <span>85%</span>
                        </div>
                        <div class="progress">
                            <span style="width:85%"></span>
                        </div>
                    </div>

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>Graphic Design</strong>
                            <span>85%</span>
                        </div>
                        <div class="progress">
                            <span style="width:85%"></span>
                        </div>
                    </div>

                    <div class="skill-card card reveal">
                        <div class="skill-top">
                            <strong>UI / UX Design</strong>
                            <span>75%</span>
                        </div>
                        <div class="progress">
                            <span style="width:75%"></span>
                        </div>
                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             EXPERIENCE
             ===================================================== -->

        <section id="experience">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Experience</span>
                    <h2 class="section-title">My <span class="gradient-text">Experience</span></h2>

                    <!-- EDIT: Replace the example experience below with your real work -->
                    <p class="section-description">
                        My professional and practical experience in web development,
                        graphic design, and digital projects.
                    </p>
                </div>

                <div class="timeline">

                    <div class="timeline-item reveal">
                        <span class="timeline-dot"></span>

                        <div class="timeline-content card">
                            <span class="timeline-date">CURRENT</span>
                            <h3>Web Developer & Graphic Designer</h3>
                            <h4>Freelance / Independent Projects</h4>

                            <p>
                                Designing responsive websites, creating digital graphics,
                                and developing user-friendly web experiences for personal
                                and client projects.
                            </p>
                        </div>

                    </div>

                    <div class="timeline-item reveal">
                        <span class="timeline-dot"></span>

                        <div class="timeline-content card">
                            <span class="timeline-date">PROJECT EXPERIENCE</span>
                            <h3>Web & Design Projects</h3>
                            <h4>Academic / Personal Work</h4>

                            <p>
                                Worked on website concepts, digital layouts, visual designs,
                                and technology-related projects while developing practical
                                skills and professional experience.
                            </p>
                        </div>
                    </div>

                    <!-- EDIT: Add additional experience by copying a timeline-item -->

                </div>

            </div>
        </section>


        <!-- =====================================================
             PROJECTS
             ===================================================== -->

        <section id="projects">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Portfolio</span>
                    <h2 class="section-title">Featured <span class="gradient-text">Projects</span></h2>

                    <!-- EDIT: Replace these projects with your real projects -->
                    <p class="section-description">
                        A selection of projects demonstrating my development and creative skills.
                    </p>
                </div>

                <div class="projects-grid">

                    <article class="project-card card reveal">
                        <div class="project-image">
                            <span class="project-number">01</span>
                        </div>

                        <div class="project-body">
                            <h3>Business Website</h3>

                            <p>
                                A modern responsive website concept designed for a small
                                business or organization.
                            </p>

                            <div class="tags">
                                <span class="tag">HTML</span>
                                <span class="tag">CSS</span>
                                <span class="tag">JavaScript</span>
                            </div>
                        </div>
                    </article>


                    <article class="project-card card reveal">
                        <div class="project-image">
                            <span class="project-number">02</span>
                        </div>

                        <div class="project-body">
                            <h3>Personal Portfolio</h3>

                            <p>
                                A responsive personal portfolio website showcasing
                                professional skills, projects, and services.
                            </p>

                            <div class="tags">
                                <span class="tag">Web Design</span>
                                <span class="tag">UI/UX</span>
                                <span class="tag">Responsive</span>
                            </div>
                        </div>
                    </article>


                    <article class="project-card card reveal">
                        <div class="project-image">
                            <span class="project-number">03</span>
                        </div>

                        <div class="project-body">
                            <h3>Graphic Design Project</h3>

                            <p>
                                A collection of digital visual materials created with
                                an emphasis on clean and professional presentation.
                            </p>

                            <div class="tags">
                                <span class="tag">Graphic Design</span>
                                <span class="tag">Branding</span>
                                <span class="tag">Creative</span>
                            </div>
                        </div>
                    </article>

                    <!-- EDIT: Add more project cards here -->

                </div>

            </div>
        </section>


        <!-- =====================================================
             EDUCATION
             ===================================================== -->

        <section id="education">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Education</span>
                    <h2 class="section-title">My <span class="gradient-text">Education</span></h2>
                </div>

                <div class="timeline">

                    <div class="timeline-item reveal">
                        <span class="timeline-dot"></span>

                        <div class="timeline-content card">
                            <span class="timeline-date">EDUCATION</span>

                            <!-- EDIT: Add your exact course/program and dates -->
                            <h3>STI Surigao</h3>
                            <h4>Surigao City, Surigao del Norte</h4>

                            <p>
                                Education and technical training focused on developing
                                practical knowledge and skills in information technology
                                and related digital fields.
                            </p>
                        </div>
                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             CERTIFICATIONS
             ===================================================== -->

        <section id="certifications">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Certifications</span>
                    <h2 class="section-title">Professional <span class="gradient-text">Certification</span></h2>
                </div>

                <div class="certification-card card reveal">

                    <div class="certificate-icon">
                        🏆
                    </div>

                    <div>
                        <!-- EDIT: Add the complete NC II qualification name -->
                        <h3>NC II Certification</h3>

                        <p>
                            National Certificate II — demonstrating competency in
                            a nationally recognized technical-vocational qualification.
                        </p>
                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             SERVICES
             ===================================================== -->

        <section id="services">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Services</span>
                    <h2 class="section-title">What I Can <span class="gradient-text">Do</span></h2>

                    <!-- EDIT: Customize the services you actually offer -->
                    <p class="section-description">
                        Professional digital services for individuals, businesses,
                        organizations, and personal projects.
                    </p>
                </div>

                <div class="services-grid">

                    <div class="service-card card reveal">
                        <div class="service-icon">💻</div>
                        <h3>Web Development</h3>
                        <p>
                            Responsive and modern websites built with clean,
                            efficient, and maintainable code.
                        </p>
                    </div>

                    <div class="service-card card reveal">
                        <div class="service-icon">🎨</div>
                        <h3>Graphic Design</h3>
                        <p>
                            Professional visual designs for digital content,
                            branding, promotional materials, and more.
                        </p>
                    </div>

                    <div class="service-card card reveal">
                        <div class="service-icon">✨</div>
                        <h3>UI / UX Design</h3>
                        <p>
                            Clean and user-friendly interfaces designed to create
                            a better experience for website visitors.
                        </p>
                    </div>

                    <div class="service-card card reveal">
                        <div class="service-icon">📱</div>
                        <h3>Responsive Design</h3>
                        <p>
                            Websites that adapt smoothly to desktop computers,
                            tablets, and mobile devices.
                        </p>
                    </div>

                    <div class="service-card card reveal">
                        <div class="service-icon">🖼️</div>
                        <h3>Digital Content</h3>
                        <p>
                            Creative digital materials designed for websites,
                            social media, and online presentation.
                        </p>
                    </div>

                    <div class="service-card card reveal">
                        <div class="service-icon">🔧</div>
                        <h3>Website Maintenance</h3>
                        <p>
                            Updates, improvements, content changes, and basic
                            website troubleshooting.
                        </p>
                    </div>

                </div>

            </div>
        </section>


        <!-- =====================================================
             CONTACT
             ===================================================== -->

        <section id="contact">
            <div class="container">

                <div class="section-heading reveal">
                    <span class="section-label">Contact</span>
                    <h2 class="section-title">Let's <span class="gradient-text">Work Together</span></h2>

                    <p class="section-description">
                        Have a project, job opportunity, or collaboration in mind?
                        Feel free to get in touch.
                    </p>
                </div>

                <div class="contact-grid">

                    <div class="contact-info card reveal">

                        <h3>Get In Touch</h3>

                        <p>
                            I'm open to freelance opportunities, employment,
                            collaborations, and interesting digital projects.
                        </p>

                        <div class="contact-item">
                            <div class="contact-icon">✉</div>
                            <div>
                                <small>Email</small>
                                <a href="mailto:Casper010889@gmail.com">
                                    Casper010889@gmail.com
                                </a>
                            </div>
                        </div>

                        <div class="contact-item">
                            <div class="contact-icon">📍</div>
                            <div>
                                <small>Location</small>
                                <span>
                                    Purok 6, Barangay Canlanipa,<br>
                                    Surigao City, Surigao del Norte
                                </span>
                            </div>
                        </div>

                    </div>


                    <form class="contact-form card reveal" id="contactForm">

                        <!--
                            IMPORTANT:
                            This form works without a server by opening the visitor's
                            default email application.

                            EDIT the JavaScript email address near the bottom if needed.
                        -->

                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input
                                type="text"
                                id="name"
                                name="name"
                                placeholder="Enter your name"
                                required
                            >
                        </div>

                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input
                                type="email"
                                id="email"
                                name="email"
                                placeholder="you@example.com"
                                required
                            >
                        </div>

                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea
                                id="message"
                                name="message"
                                placeholder="Tell me about your project..."
                                required
                            ></textarea>
                        </div>

                        <button type="submit" class="btn btn-primary">
                            Send Message →
                        </button>

                    </form>

                </div>

            </div>
        </section>

    </main>


    <!-- =========================================================
         FOOTER
         ========================================================= -->

    <footer>
        <div class="footer-content">

            <p>
                © <span id="year"></span> Casper. All rights reserved.
            </p>

            <div class="social-links">

                <!-- EDIT: Replace # with your actual social media links -->

                <a href="#" aria-label="Facebook" title="Facebook">f</a>

                <a href="#" aria-label="LinkedIn" title="LinkedIn">in</a>

                <a href="#" aria-label="GitHub" title="GitHub">⌘</a>

            </div>

        </div>
    </footer>


    <!-- =========================================================
         JAVASCRIPT
         ========================================================= -->

    <script>

        /* =========================================================
           MOBILE NAVIGATION
           ========================================================= */

        const menuToggle = document.getElementById("menuToggle");
        const navLinks = document.getElementById("navLinks");

        menuToggle.addEventListener("click", function () {
            navLinks.classList.toggle("open");

            if (navLinks.classList.contains("open")) {
                menuToggle.textContent = "✕";
            } else {
                menuToggle.textContent = "☰";
            }
        });


        /* Close mobile menu after clicking a navigation link */

        document.querySelectorAll(".nav-links a").forEach(function (link) {

            link.addEventListener("click", function () {

                navLinks.classList.remove("open");
                menuToggle.textContent = "☰";

            });

        });


        /* =========================================================
           ACTIVE NAVIGATION LINK
           ========================================================= */

        const sections = document.querySelectorAll("section");
        const navigationLinks = document.querySelectorAll(".nav-links a");

        window.addEventListener("scroll", function () {

            let currentSection = "";

            sections.forEach(function (section) {

                const sectionTop = section.offsetTop - 130;

                if (window.scrollY >= sectionTop) {
                    currentSection = section.getAttribute("id");
                }

            });

            navigationLinks.forEach(function (link) {

                link.classList.remove("active");

                if (link.getAttribute("href") === "#" + currentSection) {
                    link.classList.add("active");
                }

            });

        });


        /* =========================================================
           SCROLL REVEAL ANIMATION
           ========================================================= */

        const revealElements = document.querySelectorAll(".reveal");

        const observer = new IntersectionObserver(
            function (entries, observer) {

                entries.forEach(function (entry) {

                    if (entry.isIntersecting) {

                        entry.target.classList.add("visible");

                        observer.unobserve(entry.target);

                    }

                });

            },
            {
                threshold: 0.12
            }
        );

        revealElements.forEach(function (element) {
            observer.observe(element);
        });


        /* =========================================================
           CONTACT FORM
           =========================================================

           EDIT THIS EMAIL ADDRESS if you want messages sent
           somewhere else.
        */

        const contactForm = document.getElementById("contactForm");

        contactForm.addEventListener("submit", function (event) {

            event.preventDefault();

            const name = document.getElementById("name").value;
            const email = document.getElementById("email").value;
            const message = document.getElementById("message").value;

            const destinationEmail = "Casper010889@gmail.com";

            const subject = encodeURIComponent(
                "Portfolio Contact from " + name
            );

            const body = encodeURIComponent(
                "Name: " + name +
                "\nEmail: " + email +
                "\n\nMessage:\n" + message
            );

            window.location.href =
                "mailto:" + destinationEmail +
                "?subject=" + subject +
                "&body=" + body;

        });


        /* =========================================================
           CURRENT YEAR
           ========================================================= */

        document.getElementById("year").textContent =
            new Date().getFullYear();


        /* =========================================================
           SMALL HEADER EFFECT
           ========================================================= */

        window.addEventListener("scroll", function () {

            const header = document.querySelector("header");

            if (window.scrollY > 30) {
                header.style.background = "rgba(7, 11, 22, 0.94)";
            } else {
                header.style.background = "rgba(7, 11, 22, 0.82)";
            }

        });

    </script>

</body>
</html>
