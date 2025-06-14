<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Saksham Anand - Portfolio</title>
    <style>
        :root {
            --bg-gradient-start: #667eea;
            --bg-gradient-end: #764ba2;
            --container-bg: rgba(255, 255, 255, 0.95);
            --text-primary: #2c3e50;
            --text-secondary: #555;
            --border-color: #eee;
            --hover-bg: #f8f9ff;
            --table-bg: white;
            --shadow-color: rgba(0, 0, 0, 0.1);
        }

        [data-theme="dark"] {
            --bg-gradient-start: #1a1a2e;
            --bg-gradient-end: #16213e;
            --container-bg: rgba(30, 30, 30, 0.95);
            --text-primary: #e0e0e0;
            --text-secondary: #b0b0b0;
            --border-color: #444;
            --hover-bg: #333;
            --table-bg: #2a2a2a;
            --shadow-color: rgba(0, 0, 0, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, var(--bg-gradient-start) 0%, var(--bg-gradient-end) 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 30px;
            color: var(--text-primary);
            transition: all 0.3s ease;
        }

        .theme-toggle {
            position: fixed;
            top: 30px;
            right: 30px;
            background: var(--container-bg);
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 15px var(--shadow-color);
            transition: all 0.3s ease;
            z-index: 1000;
        }

        .theme-toggle:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 20px var(--shadow-color);
        }

        .theme-toggle svg {
            width: 28px;
            height: 28px;
            fill: var(--text-primary);
            transition: all 0.3s ease;
        }

        .container {
            background: var(--container-bg);
            border-radius: 25px;
            padding: 60px 50px;
            box-shadow: 0 25px 50px var(--shadow-color);
            backdrop-filter: blur(15px);
            max-width: 900px;
            width: 100%;
            text-align: center;
            animation: slideUp 0.8s ease-out;
            transition: all 0.3s ease;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .profile-photo {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 6px solid #667eea;
            margin-bottom: 40px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeIn 1s ease-out 0.3s both;
        }

        .profile-photo:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .name {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(135deg, #667eea, #764ba2, #f093fb);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 50px;
            animation: slideInLeft 0.8s ease-out 0.5s both, gradientShift 3s ease-in-out infinite;
            transition: all 0.3s ease;
            text-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            letter-spacing: 2px;
            font-family: 'Georgia', serif;
        }

        @keyframes gradientShift {
            0%, 100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }

        .name:hover {
            transform: scale(1.02);
            text-shadow: 0 6px 12px rgba(102, 126, 234, 0.3);
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-bottom: 60px;
            animation: slideInRight 0.8s ease-out 0.7s both;
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .linkedin {
            background: #0077b5;
            color: white;
        }

        .github {
            background: #333;
            color: white;
        }

        .social-link:hover {
            transform: translateY(-8px) scale(1.15);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .social-link:hover::before {
            left: 100%;
        }

        .social-link svg {
            width: 40px;
            height: 40px;
            fill: currentColor;
        }

        .skills-section {
            animation: fadeInUp 0.8s ease-out 0.9s both;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .skills-title {
            font-size: 1.4rem;
            font-weight: 600;
            color: var(--text-secondary);
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 3px;
            transition: color 0.3s ease;
            font-family: 'Arial', sans-serif;
            opacity: 0.8;
        }

        .skills-table {
            width: 100%;
            border-collapse: collapse;
            background: var(--table-bg);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 25px var(--shadow-color);
            transition: all 0.3s ease;
        }

        .skills-table th {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 20px;
            font-size: 1.3rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .skills-table td {
            padding: 20px;
            border-bottom: 1px solid var(--border-color);
            font-size: 1.1rem;
            transition: background-color 0.3s ease;
            color: var(--text-secondary);
        }

        .skills-table tr:hover td {
            background-color: var(--hover-bg);
        }

        .skills-table tr:last-child td {
            border-bottom: none;
        }

        .skill-category {
            font-weight: bold;
            color: #667eea;
            width: 30%;
            font-size: 1.2rem;
        }

        .skill-items {
            color: var(--text-secondary);
            text-align: left;
        }

        .skill-item {
            display: inline-block;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 8px 16px;
            margin: 5px;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: 600;
            transition: transform 0.2s ease;
        }

        .skill-item:hover {
            transform: scale(1.08);
        }

        @media (max-width: 768px) {
            body {
                padding: 20px;
            }

            .container {
                padding: 40px 30px;
                margin: 10px;
            }

            .name {
                font-size: 2.8rem;
                letter-spacing: 1px;
            }

            .profile-photo {
                width: 160px;
                height: 160px;
            }

            .social-links {
                gap: 25px;
            }

            .social-link {
                width: 65px;
                height: 65px;
            }

            .social-link svg {
                width: 32px;
                height: 32px;
            }

            .skills-table th,
            .skills-table td {
                padding: 15px;
                font-size: 1rem;
            }

            .skill-category {
                font-size: 1.1rem;
            }

            .theme-toggle {
                width: 50px;
                height: 50px;
                top: 20px;
                right: 20px;
            }

            .theme-toggle svg {
                width: 24px;
                height: 24px;
            }
        }

        @media (max-width: 480px) {
            .name {
                font-size: 2.2rem;
            }

            .profile-photo {
                width: 140px;
                height: 140px;
            }

            .social-link {
                width: 55px;
                height: 55px;
            }

            .social-link svg {
                width: 28px;
                height: 28px;
            }
        }
    </style>
</head>
<body>
    <!-- Theme Toggle Button -->
    <button class="theme-toggle" id="themeToggle" title="Toggle Dark Mode">
        <svg id="sunIcon" viewBox="0 0 24 24">
            <path d="M12 2.25a.75.75 0 01.75.75v2.25a.75.75 0 01-1.5 0V3a.75.75 0 01.75-.75zM7.5 12a4.5 4.5 0 119 0 4.5 4.5 0 01-9 0zM18.894 6.166a.75.75 0 00-1.06-1.06l-1.591 1.59a.75.75 0 101.06 1.061l1.591-1.59zM21.75 12a.75.75 0 01-.75.75h-2.25a.75.75 0 010-1.5H21a.75.75 0 01.75.75zM17.834 18.894a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 10-1.061 1.06l1.59 1.591zM12 18a.75.75 0 01.75.75V21a.75.75 0 01-1.5 0v-2.25A.75.75 0 0112 18zM7.758 17.303a.75.75 0 00-1.061-1.06l-1.591 1.59a.75.75 0 001.06 1.061l1.591-1.59zM6 12a.75.75 0 01-.75.75H3a.75.75 0 010-1.5h2.25A.75.75 0 016 12zM6.697 7.757a.75.75 0 001.06-1.06l-1.59-1.591a.75.75 0 00-1.061 1.06l1.59 1.591z"/>
        </svg>
        <svg id="moonIcon" viewBox="0 0 24 24" style="display: none;">
            <path d="M9.528 1.718a.75.75 0 01.162.819A8.97 8.97 0 009 6a9 9 0 009 9 8.97 8.97 0 003.463-.69.75.75 0 01.981.98 10.503 10.503 0 01-9.694 6.46c-5.799 0-10.5-4.701-10.5-10.5 0-4.368 2.667-8.112 6.46-9.694a.75.75 0 01.818.162z"/>
        </svg>
    </button>

    <div class="container">
        <!-- Profile Photo -->
        <img src="<a href="https://ibb.co/JFpDPfBZ"><img src="https://i.ibb.co/h1d3vP70/Whats-App-Image-2025-06-14-at-13-15-50-0879963a.jpg" alt="Saksham Anand Profile Photo" class="profile-photo" id="profilePhoto">

        <!-- Name -->
        <h1 class="name" id="nameTitle">Saksham Anand</h1>

        <!-- Social Links -->
        <div class="social-links">
            <a href="https://www.linkedin.com/in/saksham-anand-714008317" target="_blank" class="social-link linkedin" title="LinkedIn Profile">
                <svg viewBox="0 0 24 24">
                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                </svg>
            </a>
            <a href="https://github.com/Code-Ace666" target="_blank" class="social-link github" title="GitHub Profile">
                <svg viewBox="0 0 24 24">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
            </a>
        </div>

        <!-- Technical Skills Section -->
        <div class="skills-section">
            <h2 class="skills-title">Technical Skills</h2>
            <table class="skills-table">
                <thead>
                    <tr>
                        <th>Category</th>
                        <th>Skills</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="skill-category">Languages</td>
                        <td class="skill-items">
                            <span class="skill-item">C</span>
                            <span class="skill-item">C++</span>
                            <span class="skill-item">JavaScript</span>
                        </td>
                    </tr>
                    <tr>
                        <td class="skill-category">Frontend Stuff</td>
                        <td class="skill-items">
                            <span class="skill-item">HTML</span>
                            <span class="skill-item">CSS</span>
                            <span class="skill-item">VS Code</span>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>

    <script>
        // Theme toggle functionality
        const themeToggle = document.getElementById('themeToggle');
        const sunIcon = document.getElementById('sunIcon');
        const moonIcon = document.getElementById('moonIcon');
        const body = document.body;

        // Check for saved theme preference or default to 'light'
        const currentTheme = localStorage.getItem('theme') || 'light';
        body.setAttribute('data-theme', currentTheme);

        // Update icon based on current theme
        function updateThemeIcon(theme) {
            if (theme === 'dark') {
                sunIcon.style.display = 'block';
                moonIcon.style.display = 'none';
            } else {
                sunIcon.style.display = 'none';
                moonIcon.style.display = 'block';
            }
        }

        // Initialize icon
        updateThemeIcon(currentTheme);

        // Theme toggle event listener
        themeToggle.addEventListener('click', function() {
            const currentTheme = body.getAttribute('data-theme');
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
            
            body.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
            updateThemeIcon(newTheme);
            
            // Add a small animation to the toggle button
            this.style.transform = 'scale(0.9) rotate(180deg)';
            setTimeout(() => {
                this.style.transform = 'scale(1) rotate(0deg)';
            }, 200);
        });

        // Add smooth scrolling and interactive effects
        document.addEventListener('DOMContentLoaded', function() {
            // Add click effect to profile photo
            const profilePhoto = document.getElementById('profilePhoto');
            profilePhoto.addEventListener('click', function() {
                this.style.transform = 'scale(0.95)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 150);
            });

            // Add typing effect to name
            const nameTitle = document.getElementById('nameTitle');
            const originalText = nameTitle.textContent;
            nameTitle.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalText.length) {
                    nameTitle.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 100);
                }
            }
            
            // Start typing effect after initial animation
            setTimeout(typeWriter, 1000);

            // Add hover effects to skill items
            const skillItems = document.querySelectorAll('.skill-item');
            skillItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.1) rotate(2deg)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) rotate(0deg)';
                });
            });

            // Add click tracking for social links
            const socialLinks = document.querySelectorAll('.social-link');
            socialLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    // Add a small animation on click
                    this.style.transform = 'scale(0.9)';
                    setTimeout(() => {
                        this.style.transform = 'scale(1.1)';
                    }, 100);
                });
            });

            // Add parallax effect to background
            document.addEventListener('mousemove', function(e) {
                const container = document.querySelector('.container');
                const x = (e.clientX / window.innerWidth) * 10;
                const y = (e.clientY / window.innerHeight) * 10;
                
                container.style.transform = `translate(${x}px, ${y}px)`;
            });
        });

        // Add keyboard navigation
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Enter' || e.key === ' ') {
                const focusedElement = document.activeElement;
                if (focusedElement.classList.contains('social-link')) {
                    focusedElement.click();
                }
                if (focusedElement.id === 'themeToggle') {
                    e.preventDefault();
                    focusedElement.click();
                }
            }
        });
    </script>
</body>
</html>
