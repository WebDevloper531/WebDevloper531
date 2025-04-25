<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Innovative portfolio of the Developer Team">
    <title>DevTeam X | Next-Gen Developers</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0066ff;
            --secondary: #00f7ff;
            --dark: #0a192f;
            --light: #e6f1ff;
            --accent: #64ffda;
            --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--dark);
            color: var(--light);
            overflow-x: hidden;
            line-height: 1.7;
        }

        h1, h2, h3 {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 10% 20%, rgba(0, 102, 255, 0.1) 0%, rgba(0, 247, 255, 0.05) 90%);
            overflow: hidden;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            top: -50%;
            left: -50%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><circle cx="50" cy="50" r="40" stroke="%230066ff" stroke-width="0.5" fill="none" /></svg>');
            opacity: 0.1;
            animation: rotate 120s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Header with Parallax Effect */
        header {
            background: rgba(10, 25, 47, 0.9);
            backdrop-filter: blur(10px);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
            border-bottom: 1px solid rgba(100, 255, 218, 0.1);
            transition: all 0.3s ease;
        }

        header.scrolled {
            padding: 0.5rem 0;
            background: rgba(10, 25, 47, 0.98);
        }

        .header-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent);
            text-decoration: none;
        }

        .logo span {
            color: var(--light);
        }

        .logo i {
            margin-right: 10px;
            font-size: 2rem;
        }

        nav ul {
            list-style-type: none;
            display: flex;
            gap: 2rem;
        }

        nav ul li a {
            color: var(--light);
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 0;
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background: var(--accent);
            transition: width 0.3s ease;
        }

        nav ul li a:hover::after {
            width: 100%;
        }

        nav ul li a:hover {
            color: var(--accent);
        }

        .menu-toggle {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 2rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to right, rgba(10, 25, 47, 0.9), rgba(10, 25, 47, 0.7));
            z-index: -1;
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .hero h1 {
            font-size: 4rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            line-height: 1.2;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.2s forwards;
            opacity: 0;
        }

        .hero-btns {
            display: flex;
            gap: 1rem;
            animation: fadeInUp 1s ease 0.4s forwards;
            opacity: 0;
        }

        .btn {
            padding: 0.8rem 1.8rem;
            border-radius: 5px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .btn-primary {
            background: var(--gradient);
            color: white;
            box-shadow: 0 4px 15px rgba(0, 102, 255, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 102, 255, 0.6);
        }

        .btn-outline {
            border: 2px solid var(--accent);
            color: var(--accent);
        }

        .btn-outline:hover {
            background: rgba(100, 255, 218, 0.1);
            transform: translateY(-3px);
        }

        /* Floating Particles */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            background: rgba(100, 255, 218, 0.6);
            border-radius: 50%;
            animation: float linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-100vh) rotate(360deg); }
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--gradient);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: flex;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--accent);
        }

        .about-text p {
            margin-bottom: 1rem;
            opacity: 0.9;
        }

        .about-skills {
            flex: 1;
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .skill-card {
            background: rgba(100, 255, 218, 0.1);
            border: 1px solid rgba(100, 255, 218, 0.2);
            padding: 1rem 1.5rem;
            border-radius: 5px;
            transition: all 0.3s ease;
            cursor: default;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            background: rgba(100, 255, 218, 0.2);
            box-shadow: 0 5px 15px rgba(0, 102, 255, 0.2);
        }

        .skill-card i {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--accent);
        }

        .skill-card h4 {
            margin-bottom: 0.5rem;
        }

        /* Video Container */
        .video-container {
            width: 100%;
            margin: 2rem 0;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 102, 255, 0.3);
            border: 1px solid rgba(100, 255, 218, 0.3);
        }

        .video-container iframe {
            width: 100%;
            height: 400px;
            border: none;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 255, 218, 0.1);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 102, 255, 0.3);
            border-color: rgba(100, 255, 218, 0.3);
        }

        .project-img {
            height: 200px;
            overflow: hidden;
        }

        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .project-card:hover .project-img img {
            transform: scale(1.1);
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-info h3 {
            margin-bottom: 0.5rem;
            color: var(--accent);
        }

        .project-info p {
            margin-bottom: 1rem;
            opacity: 0.8;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .project-tag {
            background: rgba(100, 255, 218, 0.1);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .project-links a:hover {
            color: var(--accent);
        }

        /* Team Section */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }

        .team-member {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
            text-align: center;
            border: 1px solid rgba(100, 255, 218, 0.1);
            position: relative;
            cursor: pointer;
        }

        .team-member:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 102, 255, 0.2);
            border-color: rgba(100, 255, 218, 0.3);
        }

        .member-img {
            height: 200px;
            width: 200px;
            margin: 2rem auto 1rem;
            border-radius: 50%;
            overflow: hidden;
            border: 3px solid rgba(100, 255, 218, 0.3);
            position: relative;
        }

        .member-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: all 0.5s ease;
        }

        .team-member:hover .member-img img {
            transform: scale(1.1);
        }

        .member-info {
            padding: 1.5rem;
        }

        .member-info h3 {
            margin-bottom: 0.5rem;
            color: var(--accent);
        }

        .member-info p {
            opacity: 0.8;
            margin-bottom: 1rem;
        }

        .member-social {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .member-social a {
            color: var(--light);
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .member-social a:hover {
            background: var(--gradient);
            color: white;
            transform: translateY(-3px);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(10, 25, 47, 0.9);
            z-index: 2000;
            overflow-y: auto;
            backdrop-filter: blur(5px);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal.show {
            opacity: 1;
        }

        .modal-content {
            background: rgba(20, 40, 70, 0.95);
            max-width: 800px;
            margin: 5% auto;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(100, 255, 218, 0.3);
            position: relative;
            transform: translateY(-50px);
            transition: transform 0.3s ease;
        }

        .modal.show .modal-content {
            transform: translateY(0);
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 1.5rem;
            color: var(--light);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .close-modal:hover {
            color: var(--accent);
            transform: rotate(90deg);
        }

        .modal-header {
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid rgba(100, 255, 218, 0.2);
        }

        .modal-header h2 {
            color: var(--accent);
            font-size: 2rem;
        }

        .modal-body {
            margin-bottom: 2rem;
        }

        .modal-footer {
            display: flex;
            justify-content: flex-end;
            gap: 1rem;
        }

        /* Contact Section */
        .contact-container {
            display: flex;
            gap: 3rem;
        }

        .contact-info {
            flex: 1;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(100, 255, 218, 0.1);
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            transform: translateY(-5px);
            border-color: rgba(100, 255, 218, 0.3);
            box-shadow: 0 10px 20px rgba(0, 102, 255, 0.2);
        }

        .contact-card i {
            font-size: 1.5rem;
            color: var(--accent);
            margin-bottom: 1rem;
        }

        .contact-card h3 {
            margin-bottom: 0.5rem;
        }

        .contact-form {
            flex: 1;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 2rem;
            border: 1px solid rgba(100, 255, 218, 0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-control {
            width: 100%;
            padding: 0.8rem 1rem;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            color: var(--light);
            font-family: 'Poppins', sans-serif;
            transition: all 0.3s ease;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--accent);
            background: rgba(100, 255, 218, 0.05);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        .submit-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 102, 255, 0.4);
        }

        /* Footer */
        footer {
            background: rgba(10, 25, 47, 0.9);
            padding: 2rem 0;
            text-align: center;
            border-top: 1px solid rgba(100, 255, 218, 0.1);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 1rem;
            display: inline-block;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1.5rem;
        }

        .footer-links a {
            color: var(--light);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        .footer-social {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .footer-social a {
            color: var(--light);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .footer-social a:hover {
            background: var(--gradient);
            color: white;
            transform: translateY(-3px);
        }

        .copyright {
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }

        .animate.show {
            opacity: 1;
            transform: translateY(0);
        }

        .delay-1 {
            transition-delay: 0.2s;
        }

        .delay-2 {
            transition-delay: 0.4s;
        }

        .delay-3 {
            transition-delay: 0.6s;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .about-content {
                flex-direction: column;
            }
            
            .contact-container {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            nav ul {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: rgba(10, 25, 47, 0.98);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                gap: 2rem;
                transition: all 0.5s ease;
            }
            
            nav ul.active {
                left: 0;
            }
            
            .menu-toggle {
                display: block;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }

            .video-container iframe {
                height: 300px;
            }
        }

        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero-btns {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
                text-align: center;
            }

            .video-container iframe {
                height: 200px;
            }
        }
    </style>

</head>

<body>
    <!-- Animated Background -->
    <div class="bg-animation"></div>
    
    <!-- Floating Particles -->
    <div class="particles" id="particles"></div>
    
    <!-- Header -->
    <header id="header">
        <div class="header-container">
            <a href="#" class="logo">
                <i class="fas fa-code"></i>
                Dev<span>Team</span>X
            </a>
            
            <nav>
                <ul id="nav-menu">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#team">Team</a></li>
                    <li><a href="#contact">Contact</a></li>
		    <li><a href="https://sydneymet.edu.au/">SydneyMet</a></li>
                </ul>
                
                <div class="menu-toggle" id="menu-toggle">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Building The Future With Innovative Solutions</h1>
            <p>We are a passionate team of developers creating cutting-edge digital experiences that push boundaries and deliver exceptional results.</p>
            <div class="hero-btns">
                <a href="#projects" class="btn btn-primary">View Our Work</a>
                <a href="#contact" class="btn btn-outline">Get In Touch</a>
            </div>
        </div>
    </section>
    
    <!-- About Section -->
    <section id="about" class="section">
        <div class="section-title">
            <h2>About Us</h2>
            <p>Get to know our team and what drives us</p>
        </div>
        
        <div class="about-content animate">
            <div class="about-text">
                <h3>Who We Are</h3>
                <p>We are a team of dedicated developers with a passion for technology and innovation. Aspiring students of Mr. Md Mahmudul Hasan, we combine academic knowledge with practical skills to deliver high-quality solutions.</p>
                <p>Our diverse skill sets allow us to tackle complex problems from multiple angles, ensuring we deliver comprehensive solutions that meet and exceed client expectations.</p>
                <p>We believe in continuous learning and staying at the forefront of technological advancements to provide the best possible service to our clients.</p>
                
                <!-- Added YouTube Video Here -->
                <div class="video-container animate delay-1">
                    <iframe src="https://www.youtube.com/embed/-4PCwWMBHcg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>
            </div>
            
            <div class="about-skills">
                <div class="skill-card animate delay-1">
                    <i class="fas fa-laptop-code"></i>
                    <h4>Web Development</h4>
                    <p>Modern, responsive websites with cutting-edge technologies</p>
                </div>
                
                <div class="skill-card animate delay-2">
                    <i class="fas fa-mobile-alt"></i>
                    <h4>Mobile Solutions</h4>
                    <p>Cross-platform applications for all devices</p>
                </div>
                
                <div class="skill-card animate delay-1">
                    <i class="fas fa-brain"></i>
                    <h4>AI Integration</h4>
                    <p>Smart solutions powered by machine learning</p>
                </div>
                
                <div class="skill-card animate delay-2">
                    <i class="fas fa-paint-brush"></i>
                    <h4> Design</h4>
                    <p>Beautiful, intuitive user interfaces</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="section-title">
            <h2>Our Projects</h2>
            <p>Some of our recent work</p>
        </div>
        
        <div class="projects-grid">
            <div class="project-card animate">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Organisational Website">
                </div>
                <div class="project-info">
                    <h3>Organisational Website</h3>
                    <p>A responsive portfolio website showcasing an organization's work and team members with modern design elements.</p>
                    <div class="project-tags">
                        <span class="project-tag">HTML5</span>
                        <span class="project-tag">CSS3</span>
                        <span class="project-tag">JavaScript</span>
                    </div>
                    <div class="project-links">
                        <a href="#" onclick="openModal('orgSiteModal')">
                            <i class="fas fa-eye"></i> View Details
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="project-card animate delay-1">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1620712943543-bcc4688e7485?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=765&q=80" alt="MADRS Trace">
                </div>
                <div class="project-info">
                    <h3>MADRS Trace</h3>
                    <p>An AI-powered tool for image scanning and privacy protection on social media platforms.</p>
                    <div class="project-tags">
                        <span class="project-tag">Python</span>
                        <span class="project-tag">AI/ML</span>
                        <span class="project-tag">OpenCV</span>
                    </div>
                    <div class="project-links">
                        <a href="#" onclick="openModal('madrsModal')">
                            <i class="fas fa-eye"></i> View Details
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="project-card animate delay-2">
                <div class="project-img">
                    <img src="https://images.unsplash.com/photo-1555774698-0b77e0d5fac6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="E-commerce Platform">
                </div>
                <div class="project-info">
                    <h3>E-commerce Platform</h3>
                    <p>A full-featured online shopping platform with payment integration and inventory management.</p>
                    <div class="project-tags">
                        <span class="project-tag">React</span>
                        <span class="project-tag">Node.js</span>
                        <span class="project-tag">MongoDB</span>
                    </div>
                    <div class="project-links">
                        <a href="#">
                            <i class="fas fa-eye"></i> Coming Soon
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Team Section -->
    <section id="team" class="section">
        <div class="section-title">
            <h2>Meet Our Team</h2>
            <p>The talented individuals behind our success</p>
        </div>
        
        <div class="team-grid">
            <div class="team-member animate" onclick="openModal('rohitModal')">
                <div class="member-img">
                    <img src="rohit1.jpeg" alt="Rohit Kandel">
                </div>
                <div class="member-info">
                    <h3>Rohit Kandel</h3>
                    <p>Front-end Developer</p>
                    <div class="member-social">
                        <a href="https://www.linkedin.com/in/rohit-kandel-473b25266/" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            
            <div class="team-member animate delay-1" onclick="openModal('madanModal')">
                <div class="member-img">
                    <img src="Madan.jpeg" alt="Madan Bishowkarma">
                </div>
                <div class="member-info">
                    <h3>Madan Bishowkarma</h3>
                    <p>Back-end Developer</p>
                    <div class="member-social">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            
            <div class="team-member animate delay-2" onclick="openModal('srijalModal')">
                <div class="member-img">
                    <img src="Srijal.jpeg" alt="Srijal Gautam">
                </div>
                <div class="member-info">
                    <h3>Srijal Gautam</h3>
                    <p>Creative Director</p>
                    <div class="member-social">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            
            <div class="team-member animate" onclick="openModal('sandeshModal')">
                <div class="member-img">
                    <img src="Sandesh.jpeg" alt="Sandesh">
                </div>
                <div class="member-info">
                    <h3>Sandesh</h3>
                    <p>Technical Assistant</p>
                    <div class="member-social">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
            
            <div class="team-member animate delay-1" onclick="openModal('asthaModal')">
                <div class="member-img">
                    <img src="Astha.jpeg" alt="Astha Sah">
                </div>
                <div class="member-info">
                    <h3>Astha Sah</h3>
                    <p> Technical Assistant</p>
                    <div class="member-social">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Section -->
    <section id="contact" class="section">
        <div class="section-title">
            <h2>Get In Touch</h2>
            <p>We'd love to hear from you</p>
        </div>
        
        <div class="contact-container">
            <div class="contact-info">
                <div class="contact-card animate">
                    <i class="fas fa-envelope"></i>
                    <h3>Email Us</h3>
                    <p>devteam@sydneymet.edu.au</p>
                </div>
                
                <div class="contact-card animate delay-1">
                    <i class="fas fa-map-marker-alt"></i>
                    <h3>Visit Us</h3>
                    <p>Sydney Met College<br>432 Kent St, Sydney NSW 2000</p>
                </div>
                
                <div class="contact-card animate delay-2">
                    <i class="fas fa-clock"></i>
                    <h3>Working Hours</h3>
                    <p>Monday - Friday: 9am - 5pm<br>Saturday: 10am - 2pm<br>Sunday: Closed</p>
                </div>
            </div>
            
            <div class="contact-form animate delay-1">
                <form id="contactForm">
                    <div class="form-group">
                        <label for="name">Your Name</label>
                        <input type="text" id="name" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">Your Email</label>
                        <input type="email" id="email" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="message">Your Message</label>
                        <textarea id="message" class="form-control" required></textarea>
                    </div>
                    
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <a href="#" class="footer-logo">DevTeam<span>X</span></a>
            
            <div class="footer-links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#team">Team</a>
                <a href="#contact">Contact</a>
            </div>
            
            <div class="footer-social">
                <a href="#"><i class="fab fa-facebook-f"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
            
            <p class="copyright">© 2025 Developer Team | Sydney Met College. All rights reserved.</p>
        </div>
    </footer>
    
    <!-- Project Modals -->
    <div class="modal" id="orgSiteModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('orgSiteModal')">&times;</span>
            <div class="modal-header">
                <h2>Organisational Website / Portfolio</h2>
            </div>

            <div class="modal-body">
                <p>This project involves the development of a clean and responsive website using HTML, CSS, and optionally JavaScript or Python to showcase either an organisation or an individual's portfolio.</p>
                <p>It is designed to provide an online platform for institutions like <strong>Sydney Met College</strong>, or for individuals such as students and developers to highlight their skills, experiences, and work.</p>
                <p>The website includes sections such as Home, About, Projects/Services, Team Members, and Contact. It incorporates smooth navigation, mobile responsiveness, and interactive features to enhance user experience.</p>
                <p>The main objective is to apply web development skills in a real-world context while building a digital presence that reflects professionalism and creativity.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Technologies Used:</h3>
                <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                    <li>HTML5 & CSS3 for structure and styling</li>
                    <li>JavaScript for interactivity</li>
                    <li>Responsive design principles</li>
                    <li>Modern CSS animations and transitions</li>
                </ul>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('orgSiteModal')">Close</a>
            </div>
        </div>
    </div>
    
    <div class="modal" id="madrsModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('madrsModal')">&times;</span>
            <div class="modal-header">
                <h2>MADRS TRACE</h2>
            </div>
            <div class="modal-body">
                <p><strong>Image Scanning:</strong> Find matching images using AI-powered face recognition.</p>
                <p><strong>Privacy Protection:</strong> Detect identity risks and exposure on social platforms.</p>
                <p><strong>Smart Tech:</strong> Powered by object detection and machine learning.</p>
                <p>This tool helps users scan social media for their images, raising awareness of online privacy risks.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Key Features:</h3>
                <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                    <li>Advanced facial recognition algorithms</li>
                    <li>Cross-platform image scanning</li>
                    <li>Privacy risk assessment</li>
                    <li>User-friendly dashboard</li>
                    <li>Customizable privacy settings</li>
                </ul>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Technologies Used:</h3>
                <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                    <li>Python for backend processing</li>
                    <li>OpenCV for image processing</li>
                    <li>Machine learning models</li>
                    <li>Flask/Django for web interface</li>
                </ul>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('madrsModal')">Close</a>
            </div>
        </div>
    </div>
    
    <!-- Team Member Modals -->
    <div class="modal" id="rohitModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('rohitModal')">&times;</span>
            <div class="modal-header" style="text-align: center;">
                <div style="width: 150px; height: 150px; border-radius: 50%; overflow: hidden; margin: 0 auto 1rem; border: 3px solid var(--accent);">
                    <img src="rohit1.jpeg" alt="Rohit Kandel" style="width: 100%; height: 100%; object-fit: cover;">
                </div>
                <h2>Rohit Kandel</h2>
                <p>Front-end Developer</p>
            </div>
            <div class="modal-body">
                <p>Rohit Kandel is a passionate Front-end Developer currently pursuing a Bachelor of Information Technology (BIT). With a strong enthusiasm for creating responsive and user-friendly web interfaces, Rohit combines creativity and technical skills to bring digital experiences to life.</p>
                <p>He specializes in modern front-end technologies including HTML5, CSS3, JavaScript, and popular frameworks like React and Vue.js. Rohit is dedicated to writing clean, efficient code and creating intuitive user experiences.</p>
                <p>Currently enrolled at Sydney Met College with Student ID <strong>SM20231672</strong>, Rohit is continuously expanding his skill set to stay at the forefront of web development trends.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Skills:</h3>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem;">
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">HTML5</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">CSS3</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">JavaScript</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">React</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Vue.js</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Responsive Design</span>
                </div>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Connect:</h3>
                <div style="display: flex; gap: 1rem; margin-top: 0.5rem;">
                    <a href="https://www.linkedin.com/in/rohit-kandel-473b25266/" target="_blank" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('rohitModal')">Close</a>
            </div>
        </div>
    </div>
    
    <div class="modal" id="madanModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('madanModal')">&times;</span>
            <div class="modal-header" style="text-align: center;">
                <div style="width: 150px; height: 150px; border-radius: 50%; overflow: hidden; margin: 0 auto 1rem; border: 3px solid var(--accent);">
                    <img src="Madan.jpeg" alt="Madan Bishowkarma" style="width: 100%; height: 100%; object-fit: cover;">
                </div>
                <h2>Madan Bishowkarma</h2>
                <p>Back-end Developer</p>
            </div>
            <div class="modal-body">
                <p>Madan Bishowkarma is an enthusiastic Back-end Developer currently pursuing a Bachelor of Information Technology (BIT). He is dedicated to building reliable and efficient server-side applications that power modern web experiences.</p>
                <p>With expertise in server-side programming, database management, and API development, Madan ensures that applications are secure, scalable, and performant. He enjoys solving complex problems and optimizing system performance.</p>
                <p>Currently enrolled at Sydney Met College with Student ID <strong>SM20230195</strong>, Madan is continuously expanding his knowledge in cloud computing and distributed systems.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Skills:</h3>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem;">
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Node.js</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Python</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">MongoDB</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">MySQL</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">REST APIs</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">AWS</span>
                </div>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Connect:</h3>
                <div style="display: flex; gap: 1rem; margin-top: 0.5rem;">
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('madanModal')">Close</a>
            </div>
        </div>
    </div>
    
    <div class="modal" id="srijalModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('srijalModal')">&times;</span>
            <div class="modal-header" style="text-align: center;">
                <div style="width: 150px; height: 150px; border-radius: 50%; overflow: hidden; margin: 0 auto 1rem; border: 3px solid var(--accent);">
                    <img src="Srijal.jpeg" alt="Srijal Gautam" style="width: 100%; height: 100%; object-fit: cover;">
                </div>
                <h2>Srijal Gautam</h2>
                <p>Creative Director</p>
            </div>
            <div class="modal-body">
                <p>Srijal Gautam is skilled in Creative Work with a keen interest in web technologies. He is capable of handling both front-end and back-end development, ensuring smooth and efficient project execution.</p>
                <p>With an eye for design and a mind for functionality, Srijal bridges the gap between aesthetics and technology. He specializes in creating visually appealing interfaces that are also highly usable and accessible.</p>
                <p>Currently enrolled at Sydney Met College with Student ID <strong>SM20231664</strong>, Srijal is constantly exploring new design trends and development techniques to create innovative digital experiences.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Skills:</h3>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem;">
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">UI/UX Design</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Adobe Creative Suite</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Figma</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">JavaScript</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Graphic Design</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Branding</span>
                </div>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Connect:</h3>
                <div style="display: flex; gap: 1rem; margin-top: 0.5rem;">
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('srijalModal')">Close</a>
            </div>
        </div>
    </div>
    
    <div class="modal" id="sandeshModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('sandeshModal')">&times;</span>
            <div class="modal-header" style="text-align: center;">
                <div style="width: 150px; height: 150px; border-radius: 50%; overflow: hidden; margin: 0 auto 1rem; border: 3px solid var(--accent);">
                    <img src="Sandesh.jpeg" alt="Sandesh" style="width: 100%; height: 100%; object-fit: cover;">
                </div>
                <h2>Sandesh</h2>
                <p>Technical Assistant</p>
            </div>
            <div class="modal-body">
                <p>Sandesh Kisan is an enthusiastic Assistant currently pursuing a Bachelor of Information Technology (BIT). He is dedicated to supporting and assisting in the smooth operation of student services and activities.</p>
                <p>With strong organizational skills and technical aptitude, Sandesh plays a crucial role in coordinating team efforts and ensuring projects stay on track. He assists with documentation, testing, and quality assurance.</p>
                <p>Currently enrolled at Sydney Met College with Student ID <strong>SM20241601</strong>, Sandesh is developing his technical skills while providing valuable support to the development team.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Skills:</h3>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem;">
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Project Coordination</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Quality Assurance</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Technical Documentation</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Testing</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Problem Solving</span>
                </div>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Connect:</h3>
                <div style="display: flex; gap: 1rem; margin-top: 0.5rem;">
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('sandeshModal')">Close</a>
            </div>
        </div>
    </div>
    
    <div class="modal" id="asthaModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('asthaModal')">&times;</span>
            <div class="modal-header" style="text-align: center;">
                <div style="width: 150px; height: 150px; border-radius: 50%; overflow: hidden; margin: 0 auto 1rem; border: 3px solid var(--accent);">
                    <img src="Astha.jpeg" alt="Astha Sah" style="width: 100%; height: 100%; object-fit: cover;">
                </div>
                <h2>Astha Sah</h2>
                <p>Technical Assistant</p>
            </div>
            <div class="modal-body">
                <p>Astha is an enthusiastic Technical Assistant pursuing a Bachelor of Information Technology (BIT) at Sydney Met College. Focused on building reliable and efficient server-side applications, Astha is dedicated to advancing skills in technology and development..</p>
                <p>With a keen eye for detail and a passion for creating intuitive user experiences, Astha specializes in translating requirements into beautiful, functional interfaces. She believes good design should be both aesthetically pleasing and highly usable.</p>
                <p>Currently enrolled at Sydney Met College with Student ID <strong>SM20233038</strong>, Astha is constantly exploring new design methodologies and tools to enhance her creative process.</p>
                <h3 style="margin-top: 1.5rem; color: var(--accent);">Skills:</h3>
                <div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.5rem;">
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">User Research</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Wireframing</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Prototyping</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Figma</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">Adobe XD</span>
                    <span style="background: rgba(100, 255, 218, 0.1); color: var(--accent); padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.9rem;">User Testing</span>
                </div>

                <h3 style="margin-top: 1.5rem; color: var(--accent);">Connect:</h3>
                <div style="display: flex; gap: 1rem; margin-top: 0.5rem;">
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" style="color: var(--light); width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; background: rgba(255, 255, 255, 0.1); transition: all 0.3s ease;">
                        <i class="fas fa-envelope"></i>
                    </a>
                </div>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn btn-outline" onclick="closeModal('asthaModal')">Close</a>
            </div>
        </div>
    </div>

    
    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random size between 2px and 6px
                const size = Math.random() * 4 + 2;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                // Random position
                particle.style.left = `${Math.random() * 100}vw`;
                particle.style.top = `${Math.random() * 100}vh`;
                
                // Random animation duration between 10s and 20s
                const duration = Math.random() * 10 + 10;
                particle.style.animationDuration = `${duration}s`;
                
                // Random delay
                particle.style.animationDelay = `${Math.random() * 10}s`;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Header scroll effect
        function handleScroll() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        }
        
        // Animate elements on scroll
        function animateOnScroll() {
            const elements = document.querySelectorAll('.animate');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.3;
                
                if (elementPosition < screenPosition) {
                    element.classList.add('show');
                }
            });
        }
        
        // Modal functions
        function openModal(modalId) {
            const modal = document.getElementById(modalId);
            modal.style.display = 'block';
            setTimeout(() => {
                modal.classList.add('show');
            }, 10);
            document.body.style.overflow = 'hidden';
        }
        
        function closeModal(modalId) {
            const modal = document.getElementById(modalId);
            modal.classList.remove('show');
            setTimeout(() => {
                modal.style.display = 'none';
            }, 300);
            document.body.style.overflow = 'auto';
        }
        
        // Mobile menu toggle
        function setupMenuToggle() {
            const menuToggle = document.getElementById('menu-toggle');
            const navMenu = document.getElementById('nav-menu');
            
            menuToggle.addEventListener('click', () => {
                navMenu.classList.toggle('active');
                menuToggle.innerHTML = navMenu.classList.contains('active') ? 
                    '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
            });
            
            // Close menu when clicking on a link
            const navLinks = document.querySelectorAll('#nav-menu a');
            navLinks.forEach(link => {
                link.addEventListener('click', () => {
                    navMenu.classList.remove('active');
                    menuToggle.innerHTML = '<i class="fas fa-bars"></i>';
                });
            });
        }
        
        // Form submission
        function setupForm() {
            const contactForm = document.getElementById('contactForm');
            
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // Get form values
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const subject = document.getElementById('subject').value;
                const message = document.getElementById('message').value;
                
                // Here you would typically send the form data to a server
                // For this example, we'll just show an alert
                alert(`Thank you, ${name}! Your message has been received. We'll get back to you soon.`);
                
                // Reset form
                contactForm.reset();
            });
        }
        
        // Initialize everything when DOM is loaded
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            setupMenuToggle();
            setupForm();
            
            window.addEventListener('scroll', () => {
                handleScroll();
                animateOnScroll();
            });
            
            // Initial check for elements in viewport
            animateOnScroll();
            
            // Close modals when clicking outside content
            const modals = document.querySelectorAll('.modal');
            modals.forEach(modal => {
                modal.addEventListener('click', (e) => {
                    if (e.target === modal) {
                        const modalId = modal.id;
                        closeModal(modalId);
                    }
                });
            });
        });
    </script>
</body>

</html>
