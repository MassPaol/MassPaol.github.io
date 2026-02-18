<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Health Companion | UX Case Study</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #6366f1; /* Modern Indigo */
            --primary-hover: #4f46e5;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --radius: 16px;
            --shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        * { box-sizing: border-box; scroll-behavior: smooth; }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            line-height: 1.7;
            color: var(--text-main);
            background-color: var(--bg);
            margin: 0;
            padding: 0;
        }

        /* Glassmorphism Nav */
        nav {
            position: sticky;
            top: 0;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(0,0,0,0.05);
            padding: 1.2rem;
            z-index: 1000;
            text-align: center;
        }

        nav a {
            margin: 0 1.5rem;
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 0.95rem;
            transition: color 0.3s ease;
        }

        nav a:hover { color: var(--primary); }

        header {
            padding: 8rem 2rem;
            background: radial-gradient(circle at top right, #e0e7ff, transparent), 
                        radial-gradient(circle at bottom left, #f1f5f9, transparent);
            text-align: center;
        }

        header h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 800;
            letter-spacing: -0.04em;
            margin-bottom: 1rem;
            background: linear-gradient(to right, #1e293b, #6366f1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        header p {
            color: var(--text-muted);
            font-size: 1.25rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 2rem;
        }

        section { padding: 6rem 0; }

        h2 { 
            font-size: 2.5rem; 
            font-weight: 800; 
            letter-spacing: -0.02em;
            margin-bottom: 1.5rem;
        }

        .section-intro {
            font-size: 1.1rem;
            color: var(--text-muted);
            max-width: 800px;
            margin-bottom: 3rem;
        }

        /* Modern Artifact Cards */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
        }

        .artifact-card {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
        }

        .artifact-card:hover { transform: translateY(-5px); }

        .artifact-card h3 { margin-top: 0; font-size: 1.25rem; }

        img {
            width: 100%;
            border-radius: 12px;
            margin: 1.5rem 0;
            transition: opacity 0.3s;
        }

        img:hover { opacity: 0.9; }

        /* Badge Styles */
        .badge {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            margin-bottom: 1rem;
        }
        .badge-fail { background: #fee2e2; color: #ef4444; }
        .badge-success { background: #dcfce7; color: #22c55e; }

        .final-mockup-container {
            background: var(--text-main);
            padding: 4rem;
            border-radius: 24px;
            margin-top: 2rem;
        }

        footer {
            text-align: center;
            padding: 4rem;
            color: var(--text-muted);
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

<nav>
    <a href="#discovery">Discovery</a>
    <a href="#ideation">Ideation</a>
    <a href="#iterations">Process</a>
    <a href="#final">Final Design</a>
</nav>

<header>
    <h1>Health Companion</h1>
    <p>A human-centered approach to chronic condition management and caregiving.</p>
</header>

<div class="container">

    <section id="discovery">
        <span class="badge badge-success" style="background: #e0e7ff; color: #6366f1;">Phase 01</span>
        <h2>Discovery & Research</h2>
        <p class="section-intro">I interviewed six users ranging from ages 17 to 75. The goal was to bridge the gap between traditional tools—like physical pillboxes—and a modern digital experience.</p>
        
        <div class="grid">
            <div class="artifact-card">
                <h3>User Personas</h3>
                <p>Developing personas for Gen Z, Millennials, and Boomers to find a convergent UI solution.</p>
                <img src="persona.jpg" alt="Persona Analysis">
            </div>
            <div class="artifact-card">
                <h3>Task Analysis</h3>
                <p>Mapping the "Critical Loop": the journey from notification to medication confirmation.</p>
                <img src="task-analysis.jpg" alt="Task Flow">
            </div>
        </div>
    </section>

    <section id="ideation">
        <h2>Ideation & User Flows</h2>
        <p class="section-intro">Using storyboards and sketches to visualize how the app fits into the daily chaos of a caregiver's life.</p>
        
        <div class="artifact-card" style="margin-bottom: 2rem;">
            <h3>Storyboards & User Journeys</h3>
            <img src="journey-map.jpg" alt="User Journey Map">
        </div>

        <div class="grid">
            <div class="artifact-card">
                <h3>Early Sketches</h3>
                <p>Initial brainstorming focused on a card-based layout for better spatial clarity.</p>
                <img src="sketches.jpg" alt="Hand-drawn sketches">
            </div>
        </div>
    </section>

    <section id="iterations">
        <h2>The Iterative Process</h2>
        <p class="section-intro">Even the failed designs led to the final solution. Here is how testing reshaped the product.</p>

        <div class="grid">
            <div class="artifact-card">
                <span class="badge badge-fail">Version 01: Failed</span>
                <h3>The "Trendy" UI</h3>
                <p>The thin fonts and low contrast looked modern but were unusable for elderly participants.</p>
                <img src="v1.jpg" alt="Failed Wireframe">
            </div>
            <div class="artifact-card">
                <span class="badge badge-success">Version 02: Evolved</span>
                <h3>The Accessible Pivot</h3>
                <p>Introduction of large tap targets, photo-ID features, and bold iconography.</p>
                <img src="v2.jpg" alt="Revised Wireframe">
            </div>
        </div>
    </section>

    <section id="final">
        <h2>Final Mock-ups</h2>
        <p class="section-intro">The final solution: A high-fidelity prototype that balances Gen Z aesthetics with Boomer-level accessibility.</p>
        
        <div class="final-mockup-container">
            <img src="final-1.jpg" alt="Dashboard Mockup">
            <img src="final-2.jpg" alt="Medication Profile Mockup">
        </div>

        <div class="grid" style="margin-top: 3rem;">
            <div class="artifact-card">
                <h3>Multi-Profile Support</h3>
                <p>Seamlessly switch between managing your health and your dependent's needs.</p>
            </div>
            <div class="artifact-card">
                <h3>Photo Identification</h3>
                <p>Visual verification helps reduce errors for users taking multiple medications.</p>
            </div>
        </div>
    </section>

</div>

<footer>
    <p>&copy; 2026 Your Name | UX Design Case Study</p>
</footer>

</body>
