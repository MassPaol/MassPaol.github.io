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
