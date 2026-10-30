HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 9.3 — Combine Flexbox and Grid Responsively</title>
    <!-- Link to External Stylesheet -->
    <link rel="stylesheet" href="hybrid-style.css">
</head>
<body>

    <!-- --- 1 & 5. Navigation Bar (Flexbox) --- -->
    <header class="site-header">
        <nav class="navbar">
            <div class="nav-logo">
                <a href="#">HybridCloud</a>
            </div>
            <ul class="nav-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#solutions">Solutions</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="nav-cta">
                <a href="#get-started" class="btn-primary">Get Started</a>
            </div>
        </nav>
    </header>

    <!-- Main Content Area -->
    <main class="main-container">
        
        <!-- --- 2 & 5. Hero Section (Flexbox Alignment & Layout) --- -->
        <section id="hero" class="hero-section">
            <div class="hero-content">
                <span class="hero-badge">Next-Gen Architecture</span>
                <h1>Combine Grid and Flexbox for Maximum Layout Power</h1>
                <p>
                    Build robust web applications by pairing CSS Grid for macro-level page skeletons with Flexbox for micro-level component alignment.
                </p>
                <div class="hero-buttons">
                    <a href="#features" class="btn-primary btn-large">Explore Features</a>
                    <a href="#demo" class="btn-secondary btn-large">Watch Demo</a>
                </div>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1551434678-e076c223a692?w=600&auto=format&fit=crop&q=80" alt="Team collaborating on responsive design">
            </div>
        </section>

        <!-- --- 3, 4, 6. Features Section (CSS Grid Macro Layout & Single-Column Mobile Reflow) --- -->
        <section id="features" class="features-section">
            <div class="section-header">
                <h2>Why Choose Our Platform</h2>
                <p>Engineered with modern CSS standards for ultimate flexibility and responsiveness.</p>
            </div>

            <!-- CSS Grid Container for Features -->
            <div class="features-grid">
                
                <!-- Feature Card 1 -->
                <article class="feature-card">
                    <div class="card-icon">⚡</div>
                    <h3>Grid Macro Layouts</h3>
                    <p>Define major structural page regions effortlessly using CSS Grid templates and named areas.</p>
                </article>

                <!-- Feature Card 2 -->
                <article class="feature-card">
                    <div class="card-icon">🎯</div>
                    <h3>Flexbox Micro Alignment</h3>
                    <p>Align buttons, icons, and card elements with precision using Flexbox distribution properties.</p>
                </article>

                <!-- Feature Card 3 -->
                <article class="feature-card">
                    <div class="card-icon">📱</div>
                    <h3>Mobile-First Collapse</h3>
                    <p>Seamlessly collapse multi-column layouts into clean single-column stacks on mobile devices.</p>
                </article>

            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Hybrid Architecture Lab. All rights reserved.</p>
    </footer>

</body>
</html>
File 2: hybrid-style.css
CSS
/* --- Global Reset & Design Tokens --- */
:root {
    --primary-color: #0f172a;
    --accent-color: #2563eb;
    --bg-color: #f8fafc;
    --card-bg: #ffffff;
    --text-main: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-main);
    line-height: 1.6;
}

/* ==========================================
   1 & 5. NAVIGATION BAR (Flexbox)
   ================================---------- */
.site-header {
    background-color: var(--card-bg);
    border-bottom: 1px solid var(--border-color);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.navbar {
    max-width: 1200px;
    margin: 0 auto;
    padding: 1rem 1.5rem;
    display: flex;                  /* Flexbox for navbar */
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
}

.nav-logo a {
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--primary-color);
    text-decoration: none;
}

.nav-links {
    list-style: none;
    display: flex;
    gap: 1.5rem;
}

.nav-links a {
    text-decoration: none;
    color: var(--text-muted);
    font-weight: 500;
    font-size: 0.95rem;
    transition: color 0.2s ease;
}

.nav-links a:hover {
    color: var(--accent-color);
}

/* --- Main Container --- */
.main-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1.5rem;
}

/* ==========================================
   2 & 5. HERO SECTION (Flexbox Alignment & Layout)
   ================================---------- */
.hero-section {
    padding: 4rem 0;
    display: flex;                  /* Flexbox for hero layout */
    align-items: center;            /* Vertical centering */
    justify-content: space-between;
    flex-wrap: wrap;                /* 6. Reflows into single column on mobile */
    gap: 3rem;
}

.hero-content {
    flex: 1 1 450px;                /* Responsive basis */
}

.hero-badge {
    display: inline-block;
    background-color: #dbeafe;
    color: #1e40af;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 0.25rem 0.75rem;
    border-radius: 50px;
    text-transform: uppercase;
    margin-bottom: 1rem;
}

.hero-content h1 {
    font-size: clamp(2rem, 4vw, 2.8rem);
    color: var(--primary-color);
    line-height: 1.25;
    margin-bottom: 1rem;
}

.hero-content p {
    font-size: 1.05rem;
    color: var(--text-muted);
    margin-bottom: 1.75rem;
}

.hero-buttons {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
}

.hero-image {
    flex: 1 1 450px;
    text-align: center;
}

.hero-image img {
    width: 100%;                    /* Fluid image */
    height: auto;
    max-width: 500px;
    border-radius: 12px;
    box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
}

/* ==========================================
   3, 4, 6. FEATURES SECTION (CSS Grid Macro Layout)
   ================================---------- */
.features-section {
    padding: 4rem 0 6rem 0;
}

.section-header {
    text-align: center;
    margin-bottom: 3rem;
}

.section-header h2 {
    font-size: 2rem;
    color: var(--primary-color);
    margin-bottom: 0.5rem;
}

.section-header p {
    color: var(--text-muted);
}

/* 4. CSS Grid for Features Main Layout */
.features-grid {
    display: grid;                          /* CSS Grid container */
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* 6. Responsive auto-columns */
    gap: 2rem;                              /* Consistent spacing */
}

.feature-card {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    padding: 2rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
    
    /* 5. Flexbox for card internal content alignment */
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.feature-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.08);
}

.card-icon {
    font-size: 2rem;
    background-color: #f1f5f9;
    width: 50px;
    height: 50px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1.25rem;
}

.feature-card h3 {
    font-size: 1.2rem;
    color: var(--primary-color);
    margin-bottom: 0.5rem;
}

.feature-card p {
    font-size: 0.95rem;
    color: var(--text-muted);
}

/* ==========================================
   SHARED BUTTON STYLES (Micro Flexbox)
   ================================---------- */
.btn-primary {
    background-color: var(--accent-color);
    color: #ffffff;
    font-weight: 600;
    text-decoration: none;
    padding: 0.6rem 1.25rem;
    border-radius: 6px;
    transition: background-color 0.2s ease;
    display: inline-block;
}

.btn-primary:hover {
    background-color: #1d4ed8;
}

.btn-secondary {
    background-color: #ffffff;
    color: var(--text-main);
    font-weight: 600;
    text-decoration: none;
    padding: 0.6rem 1.25rem;
    border: 1px solid var(--border-color);
    border-radius: 6px;
    transition: background-color 0.2s ease;
    display: inline-block;
}

.btn-secondary:hover {
    background-color: var(--bg-color);
}

.btn-large {
    padding: 0.75rem 1.5rem;
    font-size: 0.95rem;
}

/* --- Footer --- */
footer {
    text-align: center;
    padding: 2.5rem 1.5rem;
    background-color: var(--primary-color);
    color: #94a3b8;
    font-size: 0.9rem;
}