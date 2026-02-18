<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Health Companion | UX Case Study</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            /* High Contrast AAA Palette */
            --bg-color: #ffffff;
            --text-color: #000000;
            --accent-color: #0056b3;
            --secondary-bg: #f4f4f4;
            --border-color: #222222;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--bg-color);
            margin: 0;
            padding: 0;
        }

        header {
            padding: 4rem 2rem;
            background: var(--text-color);
            color: var(--bg-color);
            text-align: center;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 2rem;
        }

        nav {
            position: sticky;
            top: 0;
            background: var(--bg-color);
            border-bottom: 2px solid var(--border-color);
            padding: 1rem;
            z-index: 100;
            text-align: center;
        }

        nav a {
            margin: 0 1rem;
            text-decoration: none;
            color: var(--text-color);
            font-weight: bold;
            font-size: 1.1rem;
        }

        section { padding: 4rem 0; border-bottom: 1px solid #ddd; }
        h1 { font-size: 3.5rem; margin-bottom: 1rem; }
        h2 { font-size: 2.2rem; border-left: 8px solid var(--accent-color); padding-left: 1rem; margin-bottom: 2rem; }
        h3 { font-size: 1.5rem; margin-top: 2rem; }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .artifact-card {
            border: 2px solid var(--border-color);
            padding: 1rem;
            background: var(--secondary-bg);
        }

        img {
            max-width: 100%;
            height: auto;
            display: block;
            margin: 1.5rem 0;
            border: 1px solid #ccc;
        }

        .iteration-label {
            display: inline-block;
            background: #e74c3c;
            color: white;
            padding: 0.2rem 0.6rem;
            font-size: 0.8rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .success-label { background: #27ae60; }

        footer {
            text-align: center;
            padding: 3rem;
            background: var(--secondary-bg);
        }
    </style>
</head>
<body>

<header>
    <h1>Health Companion</h1>
    <p style="font-size: 1.4rem;">Bridging the gap between medication management and digital accessibility.</p>
</header>

<nav>
    <a href="#discovery">Discovery</a>
    <a href="#ideation">Ideation</a>
    <a href="#iterations">Process</a>
    <a href="#final">Final Design</a>
</nav>

<div class="container">

    <section id="discovery">
        <h2>01. Discovery & Research</h2>
        <p>Most health apps fail by locking safety features behind paywalls or ignoring the caregiver's reality. Through interviews with users aged 17–75, I discovered that an app must serve as a bridge from physical tools (like pillboxes) to digital ones.</p>
        
        <div class="grid">
            <div class="artifact-card">
                <h3>User Personas</h3>
                <p>Representing Gen Z, Millennials, and Boomers to ensure cross-generational utility.</p>
                <img src="persona-image.jpg" alt="User Persona Document">
            </div>
            <div class="artifact-card">
                <h3>Task Analysis</h3>
                <p>Breaking down the critical loop: from realizing a dose is needed to confirming it was taken.</p>
                <img src="task-analysis.jpg" alt="Task Analysis Flowchart">
            </div>
        </div>
    </section>

    <section id="ideation">
        <h2>02. Ideation & Flows</h2>
        <p>I focused on high-contrast accessibility from the very first sketch, ensuring navigation remained clear for users with varying technical confidence.</p>
        
        <h3>Storyboards & User Journeys</h3>
        <p>Mapping the emotional and functional journey of a caregiver managing an elderly parent's profile.</p>
        <img src="user-journey.jpg" alt="User Journey Map">

        <h3>Early Sketches</h3>
        <p>Initial "messy" thoughts where I explored the card-based layout and emergency button placement.</p>
        <img src="sketches.jpg" alt="Hand-drawn sketches of the app">
    </section>

    <section id="iterations">
        <h2>03. The Iterative Process</h2>
        <p>Design is a disciplined listening exercise. Here is how the app evolved through failure and feedback.</p>

        <div class="grid">
            <div>
                <span class="iteration-label">FAILED DESIGN: V1</span>
                <h3>The "Trendy" Phase</h3>
                <p>Early wireframes used thin fonts and muted colors. Testing showed these were unreadable for older users.</p>
                <img src="v1-wireframe.jpg" alt="Initial failed wireframe">
            </div>
            <div>
                <span class="iteration-label success-label">ITERATION: V2</span>
                <h3>The Accessibility Pivot</h3>
                <p>Applied AAA standards. Increased hit targets and switched to a high-contrast card system.</p>
                <img src="v2-wireframe.jpg" alt="Improved accessible wireframe">
            </div>
        </div>
    </section>

    <section id="final">
        <h2>04. Final Mock-ups</h2>
        <p>The result is a design that is visually polished for Gen Z, functional for Millennials, and spatially clear for Boomers.</p>
        
        <img src="final-mockup-1.jpg" alt="Final High-Fidelity Screen: Dashboard">
        <img src="final-mockup-2.jpg" alt="Final High-Fidelity Screen: Medication ID">
        
        <div class="grid">
            <div class="artifact-card">
                <h3>Key Feature: Multi-Profile</h3>
                <p>One account to support both the user and their dependents.</p>
            </div>
            <div class="artifact-card">
                <h3>Key Feature: Photo-ID</h3>
                <p>Visual confirmation of pills to prevent errors.</p>
            </div>
        </div>
    </section>

</div>

<footer>
    <p>&copy; 2026 [Your Name] | Built for the Health Companion Project</p>
</footer>

</body>
</html>
