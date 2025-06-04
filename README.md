<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nikhil - MERN Stack Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700;800&display=swap');
        
        :root {
            --primary-bg: #0f0f23;
            --secondary-bg: #1a1a2e;
            --accent-bg: #16213e;
            --text-primary: #e94560;
            --text-secondary: #f5f5f5;
            --text-muted: #a0a0a0;
            --gradient-1: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --gradient-3: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            --gradient-4: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
            --neon-blue: #00f5ff;
            --neon-pink: #ff006e;
            --neon-green: #8bf500;
            --neon-purple: #bf00ff;
        }
        
        [data-theme="light"] {
            --primary-bg: #ffffff;
            --secondary-bg: #f8fafc;
            --accent-bg: #e2e8f0;
            --text-primary: #1e293b;
            --text-secondary: #334155;
            --text-muted: #64748b;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: var(--primary-bg);
            color: var(--text-secondary);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        /* Theme Toggle */
        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            background: var(--gradient-1);
            border: none;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        }
        
        .theme-toggle:hover {
            transform: scale(1.1) rotate(180deg);
            box-shadow: 0 8px 40px rgba(0, 0, 0, 0.4);
        }
        
        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }
        
        .hero-text {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 800;
            background: var(--gradient-2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { filter: drop-shadow(0 0 10px var(--neon-pink)); }
            to { filter: drop-shadow(0 0 30px var(--neon-blue)); }
        }
        
        .typing-container {
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 2rem;
        }
        
        .typing-text {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.5rem;
            font-weight: 500;
            color: var(--neon-blue);
            border-right: 3px solid var(--neon-pink);
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 50% { border-color: var(--neon-pink); }
            51%, 100% { border-color: transparent; }
        }
        
        .stats-container {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }
        
        .stat-card {
            background: var(--secondary-bg);
            padding: 1.5rem 2rem;
            border-radius: 15px;
            border: 2px solid transparent;
            background-clip: padding-box;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-3);
            z-index: -1;
            transition: opacity 0.4s ease;
            opacity: 0;
        }
        
        .stat-card:hover::before {
            opacity: 1;
        }
        
        .stat-card:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 20px 60px rgba(0, 245, 255, 0.3);
        }
        
        /* About Section */
        .about-section {
            background: var(--secondary-bg);
            padding: 3rem;
            border-radius: 20px;
            margin-bottom: 4rem;
            position: relative;
            overflow: hidden;
        }
        
        .about-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, var(--neon-blue), var(--neon-pink), var(--neon-green), var(--neon-purple), var(--neon-blue));
            animation: rotate 10s linear infinite;
            z-index: -1;
            opacity: 0.1;
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .code-block {
            background: #1e1e1e;
            border-radius: 15px;
            padding: 2rem;
            margin: 2rem 0;
            font-family: 'JetBrains Mono', monospace;
            position: relative;
            overflow: hidden;
        }
        
        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-4);
            animation: progress 3s ease-in-out infinite;
        }
        
        @keyframes progress {
            0%, 100% { transform: translateX(-100%); }
            50% { transform: translateX(100%); }
        }
        
        .code-line {
            margin: 0.5rem 0;
            animation: typewriter 0.5s ease-in-out;
            animation-fill-mode: both;
        }
        
        .code-line:nth-child(1) { animation-delay: 0.1s; }
        .code-line:nth-child(2) { animation-delay: 0.2s; }
        .code-line:nth-child(3) { animation-delay: 0.3s; }
        .code-line:nth-child(4) { animation-delay: 0.4s; }
        .code-line:nth-child(5) { animation-delay: 0.5s; }
        .code-line:nth-child(6) { animation-delay: 0.6s; }
        .code-line:nth-child(7) { animation-delay: 0.7s; }
        .code-line:nth-child(8) { animation-delay: 0.8s; }
        
        @keyframes typewriter {
            0% { opacity: 0; transform: translateX(-20px); }
            100% { opacity: 1; transform: translateX(0); }
        }
        
        .keyword { color: #569cd6; }
        .string { color: #ce9178; }
        .property { color: #9cdcfe; }
        .value { color: #4fc1ff; }
        
        /* Tech Stack Section */
        .tech-section {
            margin-bottom: 4rem;
        }
        
        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .tech-category {
            background: var(--secondary-bg);
            padding: 2rem;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
        }
        
        .tech-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.2);
        }
        
        .tech-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--gradient-2);
            transform: translateX(-100%);
            transition: transform 0.4s ease;
        }
        
        .tech-category:hover::before {
            transform: translateX(0);
        }
        
        .tech-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .tech-icon {
            width: 60px;
            height: 60px;
            background: var(--accent-bg);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .tech-icon::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-3);
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .tech-icon:hover::before {
            opacity: 1;
        }
        
        .tech-icon:hover {
            transform: scale(1.2) rotate(10deg);
            box-shadow: 0 10px 30px rgba(0, 245, 255, 0.4);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .project-card {
            background: var(--secondary-bg);
            border-radius: 20px;
            padding: 2rem;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, var(--neon-blue) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.4s ease;
            animation: pulse 2s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(0.8); opacity: 0; }
            50% { transform: scale(1.2); opacity: 0.1; }
        }
        
        .project-card:hover::before {
            opacity: 0.1;
        }
        
        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 80px rgba(0, 0, 0, 0.3);
        }
        
        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }
        
        .tech-badge {
            background: var(--gradient-4);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
            animation: float 3s ease-in-out infinite;
        }
        
        .tech-badge:nth-child(odd) { animation-delay: 0.5s; }
        .tech-badge:nth-child(even) { animation-delay: 1s; }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }
        
        /* Experience Timeline */
        .timeline {
            position: relative;
            margin: 3rem 0;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: var(--gradient-1);
            transform: translateX(-50%);
        }
        
        .timeline-item {
            position: relative;
            margin: 3rem 0;
            opacity: 0;
            animation: slideInUp 0.6s ease-out forwards;
        }
        
        .timeline-item:nth-child(odd) { animation-delay: 0.2s; }
        .timeline-item:nth-child(even) { animation-delay: 0.4s; }
        
        @keyframes slideInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .timeline-content {
            background: var(--secondary-bg);
            padding: 2rem;
            border-radius: 15px;
            position: relative;
            width: 45%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .timeline-item:nth-child(odd) .timeline-content {
            margin-left: auto;
        }
        
        .timeline-content:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
        }
        
        /* Contact Section */
        .contact-section {
            text-align: center;
            background: var(--secondary-bg);
            padding: 3rem;
            border-radius: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .social-link {
            width: 80px;
            height: 80px;
            background: var(--gradient-2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            text-decoration: none;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }
        
        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-3);
            border-radius: 50%;
            transform: scale(0);
            transition: transform 0.4s ease;
        }
        
        .social-link:hover::before {
            transform: scale(1);
        }
        
        .social-link:hover {
            transform: translateY(-10px) scale(1.1);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }
        
        /* Floating Animation */
        .floating {
            animation: floating 6s ease-in-out infinite;
        }
        
        @keyframes floating {
            0%, 100% { transform: translate(0, 0px); }
            50% { transform: translate(0, -20px); }
        }
        
        /* Particles Background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--neon-blue);
            border-radius: 50%;
            animation: particleFloat 10s infinite linear;
        }
        
        @keyframes particleFloat {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            .hero-text {
                font-size: 2.5rem;
            }
            
            .stats-container {
                flex-direction: column;
                align-items: center;
            }
            
            .tech-grid {
                grid-template-columns: 1fr;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .timeline::before {
                left: 20px;
            }
            
            .timeline-content {
                width: calc(100% - 60px);
                margin-left: 60px !important;
            }
            
            .social-links {
                flex-wrap: wrap;
            }
        }
    </style>
</head>
<body>
    <!-- Theme Toggle -->
    <button class="theme-toggle" onclick="toggleTheme()">
        <span id="theme-icon">🌙</span>
    </button>
    
    <!-- Particles Background -->
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <h1 class="hero-text floating">👋 Hi, I'm Nikhil</h1>
            <div class="typing-container">
                <div class="typing-text" id="typing-text"></div>
            </div>
            
            <div class="stats-container">
                <div class="stat-card">
                    <div style="font-size: 2rem; color: var(--neon-blue);">🚀</div>
                    <div style="font-weight: 600; margin-top: 0.5rem;">MERN Developer</div>
                </div>
                <div class="stat-card">
                    <div style="font-size: 2rem; color: var(--neon-green);">🎯</div>
                    <div style="font-weight: 600; margin-top: 0.5rem;">Delhi NCR</div>
                </div>
                <div class="stat-card">
                    <div style="font-size: 2rem; color: var(--neon-pink);">⚡</div>
                    <div style="font-weight: 600; margin-top: 0.5rem;">AI Enthusiast</div>
                </div>
            </div>
        </header>
        
        <!-- About Section -->
        <section class="about-section">
            <h2 class="section-title">🚀 About Me</h2>
            <div class="code-block">
                <div class="code-line"><span class="keyword">const</span> <span class="property">nikhil</span> = {</div>
                <div class="code-line">    <span class="property">location</span>: <span class="string">"Delhi NCR, India"</span>,</div>
                <div class="code-line">    <span class="property">role</span>: <span class="string">"MERN Stack Developer"</span>,</div>
                <div class="code-line">    <span class="property">company</span>: <span class="string">"The Entrepreneurship Network"</span>,</div>
                <div class="code-line">    <span class="property">education</span>: <span class="string">"B.Tech CSE - DCRUST University"</span>,</div>
                <div class="code-line">    <span class="property">passions</span>: [<span class="string">"Web Development"</span>, <span class="string">"AI Integration"</span>, <span class="string">"Open Source"</span>],</div>
                <div class="code-line">    <span class="property">currentFocus</span>: <span class="string">"Building scalable web applications"</span>,</div>
                <div class="code-line">    <span class="property">philosophy</span>: <span class="string">"Code with purpose, innovate with passion! 💻✨"</span></div>
                <div class="code-line">};</div>
            </div>
            
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 2rem;">
                <div>
                    <h3 style="color: var(--neon-blue); margin-bottom: 1rem;">🔭 Currently Working</h3>
                    <p>Leading development of Internship Portal & Task Management Platform at The Entrepreneurship Network</p>
                </div>
                <div>
                    <h3 style="color: var(--neon-green); margin-bottom: 1rem;">🌱 Learning</h3>
                    <p>Advanced React patterns, Microservices architecture, AI integration, and modern web technologies</p>
                </div>
                <div>
                    <h3 style="color: var(--neon-pink); margin-bottom: 1rem;">👯 Collaboration</h3>
                    <p>Open source projects, MERN stack applications, and innovative web solutions</p>
                </div>
                <div>
                    <h3 style="color: var(--neon-purple); margin-bottom: 1rem;">⚡ Fun Fact</h3>
                    <p>I optimize UI performance by 30% and love building AI-powered applications!</p>
                </div>
            </div>
        </section>
        
        <!-- Tech Stack Section -->
        <section class="tech-section">
            <h2 class="section-title">🛠️ Tech Stack & Tools</h2>
            <div class="tech-grid">
                <div class="tech-category">
                    <h3 style="color: var(--neon-blue); margin-bottom: 1rem;">Frontend Technologies</h3>
                    <div class="tech-icons">
                        <div class="tech-icon" title="React">⚛️</div>
                        <div class="tech-icon" title="Next.js">▲</div>
                        <div class="tech-icon" title="JavaScript">🟨</div>
                        <div class="tech-icon" title="HTML5">🌐</div>
                        <div class="tech-icon" title="CSS3">🎨</div>
                        <div class="tech-icon" title="Tailwind">💨</div>
                        <div class="tech-icon" title="Bootstrap">🅱️</div>
                    </div>
                </div>
                
                <div class="tech-category">
                    <h3 style="color: var(--neon-green); margin-bottom: 1rem;">Backend Technologies</h3>
                    <div class="tech-icons">
                        <div class="tech-icon" title="Node.js">🟢</div>
                        <div class="tech-icon" title="Express.js">🚀</div>
                        <div class="tech-icon" title="MongoDB">🍃</div>
                        <div class="tech-icon" title="Python">🐍</div>
                        <div class="tech-icon" title="JWT">🔐</div>
                        <div class="tech-icon" title="Socket.IO">🔌</div>
                    </div>
                </div>
                
                <div class="tech-category">
                    <h3 style="color: var(--neon-pink); margin-bottom: 1rem;">Tools & Platforms</h3>
                    <div class="tech-icons">
                        <div class="tech-icon" title="Git">📝</div>
                        <div class="tech-icon" title="GitHub">🐙</div>
                        <div class="tech-icon" title="Postman">📮</div>
                        <div class="tech-icon" title="VS Code">💻</div>
                        <div class="tech-icon" title="Figma">🎯</div>
                        <div class="tech-icon" title="Vercel">▲</div>
                    </div>
                </div>
                
                <div class="tech-category">
                    <h3 style="color: var(--neon-purple); margin-bottom: 1rem;">AI & Innovation</h3>
                    <div class="tech-icons">
                        <div class="tech-icon" title="Gemini API">🤖</div>
                        <div class="tech-icon" title="GSAP">✨</div>
                        <div class="tech-icon" title="WebGL">🎮</div>
                        <div class="tech-icon" title="PWA">📱</div>
                        <div class="tech-icon" title="WebRTC">📹</div>
                        <div class="tech-icon" title="GraphQL">📊</div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Experience Timeline -->
        <section>
            <h2 class="section-title">💼 Professional Journey</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3 style="color: var(--neon-blue); margin-bottom: 1rem;">🚀 The Entrepreneurship Network</h3>
                        <h4 style="color: var(--text-primary);">MERN Stack Developer Intern</h4>
                        <p style="color: var(--text-muted); margin: 0.5rem 0;">March 2025 - Present | Delhi, India</p>
                        <ul style="margin-top: 1rem; line-height: 1.6;">
                            <li>🏗️ Leading development of full-fledged Internship Portal using MERN stack</li>
                            <li>⚡ Implemented API debouncing & UI optimizations - 30% performance boost</li>
                            <li>🔧 Spearheading backend team for Task Management Tool with microservices</li>
                            <li>👥 Cross-functional collaboration for seamless integration</li>
                        </ul>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3 style="color: var(--neon-green); margin-bottom: 1rem;">💻 Business Web Solutions</h3>
                        <h4 style="color: var(--text-primary);">Full Stack Developer Intern</h4>
                        <p style="color: var(--text-muted); margin: 0.5rem 0;">Jan 2024 - Apr 2024 | New Delhi, India</p>
                        <ul style="margin-top: 1rem; line-height: 1.6;">
                            <li>🎨 Developed responsive landing pages with React.js & Tailwind CSS</li>
                            <li>📝 Built Google Keep clone with CRUD functionality & Redux</li>
                            <li>🔄 Integrated real-time updates using Socket.IO</li>
                            <li>🛒 Enhanced MERN e-commerce platform - 30% performance improvement</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Featured Projects -->
        <section>
            <h2 class="section-title">🎯 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">🤖 AI-Powered Quote Generator</div>
                    <p style="color: var(--text-muted); margin-bottom: 1rem;">Dynamic AI-powered web app generating unique quotes based on mood & topics with Gemini API integration</p>
                    <div class="project-tech">
                        <span class="tech-badge">React.js</span>
                        <span class="tech-badge">Node.js</span>
                        <span class="tech-badge">MongoDB</span>
                        <span class="tech-badge">Gemini API</span>
                        <span class="tech-badge">TailwindCSS</span>
                    </div>
                    <ul style="margin-top: 1rem; line-height: 1.6;">
                        <li>🎯 Category/mood selector with authentication system</li>
                        <li>📅 "Quote of the Day" feature with auto-generation</li>
                        <li>📋 One-click copy functionality for easy sharing</li>
                        <li>🚀 Deployed on Vercel & Render for optimal performance</li>
                    </ul>
                </div>
                
                <div class="project-card">
                    <div class="project-title">💼 Internship Portal Web Application</div>
                    <p style="color: var(--text-muted); margin-bottom: 1rem;">Full-stack platform connecting companies and students with secure authentication and real-time features</p>
                    <div class="project-tech">
                        <span class="tech-badge">React.js</span>
                        <span class="tech-badge">JWT</span>
                        <span class="tech-badge">Express.js</span>
                        <span class="tech-badge">MongoDB</span>
                        <span class="tech-badge">Nodemailer</span>
                    </div>
                    <ul style="margin-top: 1rem; line-height: 1.6;">
                        <li>🔐 Secure authentication with JWT & OAuth2</li>
                        <li>🔍 Dynamic search & filter functionality</li>
                        <li>📄 Resume upload feature with Multer integration</li>
                        <li>📧 Real-time email notifications via Nodemailer</li>
                    </ul>
                </div>
                
                <div class="project-card">
                    <div class="project-title">📋 Task Pilot - Project Management Platform</div>
                    <p style="color: var(--text-muted); margin-bottom: 1rem;">Role-based project management with dynamic dashboards and advanced permission controls</p>
                    <div class="project-tech">
                        <span class="tech-badge">RBAC</span>
                        <span class="tech-badge">Timeline Charts</span>
                        <span class="tech-badge">React.js</span>
                        <span class="tech-badge">Node.js</span>
                        <span class="tech-badge">MongoDB</span>
                    </div>
                    <ul style="margin-top: 1rem; line-height: 1.6;">
                        <li>👥 Multi-role system: Intern → TL → COS → Admin</li>
                        <li>📊 Timeline charts & progress tracking visualizations</li>
                        <li>🔒 Permission control using RBAC architecture</li>
                        <li>⚡ Scalable backend APIs with modular architecture</li>
                    </ul>
                </div>
            </div>
        </section>
        
        <!-- GitHub Stats -->
        <section style="text-align: center; margin: 4rem 0;">
            <h2 class="section-title">📊 GitHub Analytics</h2>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-bottom: 2rem;">
                <div class="stat-card" style="padding: 1rem;">
                    <img src="https://github-readme-stats.vercel.app/api?username=Nikhilconnectnow&show_icons=true&theme=radical&hide_border=true&bg_color=0f0f23&title_color=e94560&text_color=f5f5f5&icon_color=00f5ff" alt="GitHub Stats" style="width: 100%; border-radius: 10px;">
                </div>
                <div class="stat-card" style="padding: 1rem;">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=Nikhilconnectnow&theme=radical&hide_border=true&background=0f0f23&stroke=e94560&ring=00f5ff&fire=f5f5f5&currStreakLabel=00f5ff" alt="GitHub Streak" style="width: 100%; border-radius: 10px;">
                </div>
            </div>
            <div class="stat-card" style="padding: 1rem; margin-bottom: 2rem;">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=Nikhilconnectnow&theme=react-dark&hide_border=true&area=true&bg_color=0f0f23&color=e94560&line=00f5ff&point=f5f5f5" alt="Activity Graph" style="width: 100%; border-radius: 10px;">
            </div>
        </section>
        
        <!-- Education & Certifications -->
        <section>
            <h2 class="section-title">🎓 Education & Certifications</h2>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 2rem;">
                <div class="stat-card" style="padding: 2rem;">
                    <h3 style="color: var(--neon-blue); margin-bottom: 1rem;">🎓 Education</h3>
                    <div style="margin-bottom: 1rem;">
                        <h4 style="color: var(--text-primary);">B.Tech in Computer Science & Engineering</h4>
                        <p style="color: var(--text-muted);">DCRUST University, Murthal | 2020-2024</p>
                        <p style="color: var(--neon-green); font-weight: 600;">CGPA: 7.6/10</p>
                    </div>
                </div>
                
                <div class="stat-card" style="padding: 2rem;">
                    <h3 style="color: var(--neon-pink); margin-bottom: 1rem;">📜 Recent Certifications</h3>
                    <ul style="line-height: 1.8;">
                        <li>🌐 Web Development Bootcamp 2024 - Angela Yu</li>
                        <li>🤖 Freedom With AI Masterclass 2025</li>
                        <li>🎨 Figma Essential Training 2025</li>
                        <li>⚛️ React Native Ecosystem and Workflow</li>
                        <li>☁️ Cloud Technical Series - Learn. Build. Grow</li>
                        <li>⚡ Next.js: Creating Full-Stack Sites</li>
                    </ul>
                </div>
            </div>
        </section>
        
        <!-- Contact Section -->
        <section class="contact-section">
            <h2 class="section-title">🤝 Let's Connect!</h2>
            <p style="font-size: 1.2rem; margin-bottom: 2rem; color: var(--text-muted);">
                I'm always open to interesting conversations and collaboration opportunities. 
                Feel free to reach out if you want to discuss technology, share ideas, or work on projects together!
            </p>
            
            <div class="social-links">
                <a href="https://linkedin.com/in/nikhilconnectnow" class="social-link" title="LinkedIn">
                    <span style="position: relative; z-index: 1;">💼</span>
                </a>
                <a href="mailto:nikhil.connectnow@gmail.com" class="social-link" title="Email">
                    <span style="position: relative; z-index: 1;">📧</span>
                </a>
                <a href="https://github.com/Nikhilconnectnow" class="social-link" title="GitHub">
                    <span style="position: relative; z-index: 1;">🐙</span>
                </a>
                <a href="tel:+91-8398934643" class="social-link" title="Phone">
                    <span style="position: relative; z-index: 1;">📱</span>
                </a>
            </div>
            
            <div style="margin-top: 3rem; padding: 2rem; background: var(--accent-bg); border-radius: 15px; font-family: 'JetBrains Mono', monospace;">
                <div style="color: var(--neon-blue); font-size: 1.2rem; margin-bottom: 1rem;">💡 Philosophy</div>
                <div style="font-style: italic; color: var(--text-muted);">
                    "Building the future, one commit at a time! Code with purpose, innovate with passion! 💻✨"
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer style="text-align: center; margin-top: 4rem; padding: 2rem; border-top: 1px solid rgba(255, 255, 255, 0.1);">
            <div style="display: flex; justify-content: center; align-items: center; gap: 1rem; flex-wrap: wrap;">
                <span style="color: var(--text-muted);">Made with</span>
                <span style="color: var(--neon-pink); font-size: 1.2rem; animation: pulse 1s infinite;">❤️</span>
                <span style="color: var(--text-muted);">and</span>
                <span style="color: var(--neon-blue); font-size: 1.2rem;">☕</span>
                <span style="color: var(--text-muted);">by Nikhil</span>
            </div>
            <div style="margin-top: 1rem; color: var(--text-muted); font-size: 0.9rem;">
                © 2025 Nikhil - MERN Stack Developer | Always Learning, Always Growing 🚀
            </div>
        </footer>
    </div>
    
    <script>
        // Theme Toggle Functionality
        function toggleTheme() {
            const body = document.body;
            const themeIcon = document.getElementById('theme-icon');
            
            if (body.getAttribute('data-theme') === 'light') {
                body.removeAttribute('data-theme');
                themeIcon.textContent = '🌙';
                localStorage.setItem('theme', 'dark');
            } else {
                body.setAttribute('data-theme', 'light');
                themeIcon.textContent = '☀️';
                localStorage.setItem('theme', 'light');
            }
        }
        
        // Load saved theme
        document.addEventListener('DOMContentLoaded', function() {
            const savedTheme = localStorage.getItem('theme');
            const themeIcon = document.getElementById('theme-icon');
            
            if (savedTheme === 'light') {
                document.body.setAttribute('data-theme', 'light');
                themeIcon.textContent = '☀️';
            }
        });
        
        // Typing Animation
        const roles = [
            "MERN Stack Developer 🚀",
            "Full-Stack Engineer 💻",
            "AI Enthusiast 🤖",
            "Problem Solver 🧩",
            "Open Source Contributor 🌟",
            "Tech Innovator ⚡"
        ];
        
        let currentRole = 0;
        let currentChar = 0;
        let isDeleting = false;
        
        function typeRole() {
            const typingElement = document.getElementById('typing-text');
            const currentText = roles[currentRole];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, currentChar - 1);
                currentChar--;
            } else {
                typingElement.textContent = currentText.substring(0, currentChar + 1);
                currentChar++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && currentChar === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && currentChar === 0) {
                isDeleting = false;
                currentRole = (currentRole + 1) % roles.length;
                typeSpeed = 500;
            }
            
            setTimeout(typeRole, typeSpeed);
        }
        
        // Start typing animation
        document.addEventListener('DOMContentLoaded', typeRole);
        
        // Particles Animation
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 10 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 5) + 's';
                
                // Random colors
                const colors = ['var(--neon-blue)', 'var(--neon-pink)', 'var(--neon-green)', 'var(--neon-purple)'];
                particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Initialize particles
        document.addEventListener('DOMContentLoaded', createParticles);
        
        // Scroll Animation Observer
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        // Observe elements for scroll animation
        document.addEventListener('DOMContentLoaded', function() {
            const animateElements = document.querySelectorAll('.timeline-item');
            animateElements.forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(50px)';
                el.style.transition = 'all 0.6s ease-out';
                observer.observe(el);
            });
        });
        
        // Tech icon hover effects
        document.addEventListener('DOMContentLoaded', function() {
            const techIcons = document.querySelectorAll('.tech-icon');
            techIcons.forEach(icon => {
                icon.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.2) rotate(10deg)';
                });
                
                icon.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) rotate(0deg)';
                });
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
        
        // Add mouse trail effect
        let mouseTrail = [];
        document.addEventListener('mousemove', function(e) {
            mouseTrail.push({x: e.clientX, y: e.clientY});
            if (mouseTrail.length > 10) {
                mouseTrail.shift();
            }
        });
        
        // Performance optimization: Debounce resize events
        let resizeTimeout;
        window.addEventListener('resize', function() {
            clearTimeout(resizeTimeout);
            resizeTimeout = setTimeout(function() {
                // Recalculate any size-dependent animations
                console.log('Window resized - recalculating animations');
            }, 250);
        });
    </script>
</body>
</html>
