<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Ratandip Constructions</title>
    <style>
        /* General Body Styling */
body {
    margin: 0;
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f8f8f8;
    padding-top: 80px; /* IMPORTANT: Add this to prevent content from going under the fixed header. Adjust value if header height changes. */
}

/* Header Styling */
header {
    background-color: #2c3e50; /* Dark blue/gray */
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    flex-wrap: wrap; /* Allow wrapping on smaller screens */
    /* Add these lines for fixed header */
    position: fixed; /* Makes it stay in place */
    top: 0; /* Sticks to the top of the viewport */
    left: 0; /* Sticks to the left edge */
    width: 100%; /* Ensures it spans full width */
    z-index: 1000; /* Keeps it above other content */
}

        .logo-title {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo {
            height: 60px; /* Slightly larger logo */
            border-radius: 50%; /* Make logo circular if applicable */
            object-fit: cover;
        }

        header h1 {
            margin: 0;
            font-size: 1.8em;
            font-weight: 600;
        }

        /* Navbar Styling */
        .navbar {
            display: flex;
            gap: 25px;
        }

        .navbar a {
            color: #fff;
            text-decoration: none;
            font-size: 1.1em;
            padding: 8px 15px;
            border-radius: 5px;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .navbar a:hover,
        .navbar a:focus {
            background-color: #34495e; /* Slightly lighter dark blue */
            color: #ecf0f1;
            outline: none; /* Remove default focus outline */
        }

        /* Main Content Section Styling */
        main {
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        section {
            padding: 40px 0;
            margin-bottom: 30px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        section h2 {
            text-align: center;
            font-size: 2.5em;
            color: #2c3e50;
            margin-bottom: 40px;
            position: relative;
        }

        section h2::after {
            content: '';
            position: absolute;
            left: 50%;
            bottom: -10px;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background-color: #3498db; /* Blue accent */
            border-radius: 2px;
        }

        /* Hero Section Styling */
        .hero-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 60px 20px;
            background: linear-gradient(to right, #3498db, #2c3e50); /* Gradient background */
            color: #fff;
            text-align: center;
            border-radius: 10px;
            margin-bottom: 30px;
        }

        .hero-section h2 {
            color: #fff;
            font-size: 3em;
            margin-bottom: 25px;
            position: relative;
        }

        .hero-section h2::after {
            background-color: #f39c12; /* Orange accent for hero title */
        }

        .profile-image {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            border: 6px solid #f39c12; /* Orange border */
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
            margin-top: 30px;
            transition: transform 0.4s ease-in-out;
        }

        .profile-image:hover {
            transform: scale(1.05);
        }

        /* About Section Styling */
        .about-block {
            display: flex;
            align-items: center;
            gap: 30px;
            margin-bottom: 30px;
            padding: 0 30px;
        }

        .about-block:nth-child(even) {
            flex-direction: row-reverse; /* Alternate image and text */
        }

        .about-block img {
            width: 250px;
            height: 180px;
            object-fit: cover;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .about-block img:hover {
            transform: translateY(-5px);
        }

        .about-block p {
            flex: 1;
            font-size: 1.1em;
            line-height: 1.8;
            color: #555;
        }

        /* Services Section Styling */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            padding: 0 30px;
        }

        .service-card {
            background-color: #ecf0f1; /* Light gray */
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
        }

        .service-card h3 {
            color: #3498db;
            font-size: 1.6em;
            margin-bottom: 15px;
        }

        .service-card p {
            color: #666;
            font-size: 1em;
        }

        /* Contact Section Styling */
        .contact-section {
            text-align: center;
        }

        .contact-form-container {
            max-width: 600px;
            margin: 0 auto;
            background-color: #ecf0f1;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .contact-form-container form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-form-container input,
        .contact-form-container textarea {
            width: calc(100% - 24px); /* Account for padding and border */
            padding: 12px;
            margin: 0; /* Remove default margin */
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 1em;
            transition: border-color 0.3s ease;
        }

        .contact-form-container input:focus,
        .contact-form-container textarea:focus {
            border-color: #3498db;
            outline: none;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
        }

        .contact-form-container textarea {
            resize: vertical; /* Allow vertical resizing */
            min-height: 120px;
        }

        .contact-form-container button {
            background-color: #3498db;
            color: #fff;
            border: none;
            padding: 15px 25px;
            cursor: pointer;
            border-radius: 5px;
            font-size: 1.1em;
            font-weight: bold;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        .contact-form-container button:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
        }

        /* Footer Styling */
        footer {
            background-color: #2c3e50;
            color: #fff;
            text-align: center;
            padding: 20px;
            margin-top: 50px;
            box-shadow: 0 -2px 5px rgba(0, 0, 0, 0.2);
        }

        footer p {
            margin: 0;
            font-size: 0.9em;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
            }

            .navbar {
                width: 100%;
                justify-content: center;
                margin-top: 15px;
            }

            .navbar a {
                padding: 8px 12px;
                font-size: 1em;
            }

            .hero-section h2 {
                font-size: 2.2em;
            }

            .profile-image {
                width: 200px;
                height: 250px;
            }

            .about-block {
                flex-direction: column;
                text-align: center;
                padding: 0 15px;
            }

            .about-block:nth-child(even) {
                flex-direction: column; /* Reset for small screens */
            }

            .about-block img {
                width: 100%;
                max-width: 300px;
                margin-bottom: 20px;
            }

            .services-grid {
                grid-template-columns: 1fr;
                padding: 0 15px;
            }

            .service-card {
                padding: 25px;
            }

            .contact-form-container {
                padding: 30px 20px;
            }
        }

        @media (max-width: 480px) {
            header h1 {
                font-size: 1.5em;
            }

            .navbar {
                flex-direction: column;
                gap: 10px;
            }

            .navbar a {
                display: block;
                width: calc(100% - 20px);
                text-align: center;
            }

            .hero-section h2 {
                font-size: 1.8em;
            }

            section h2 {
                font-size: 2em;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-title">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRBDjsLDvXTsYdxZONnl08dQIeqeY1AT5_J1Q&s" alt="Ratnadip Construction logo" class="logo">
            <h1>Ratandip Constructions</h1>
        </div>
        <nav class="navbar">
            <a href="#about">About</a>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main>
        <section class="hero-section">
            <h2>Welcome to Ratandip Constructions!</h2>
            <img src="papa.jpg" alt="Mukesh Rathod" class="profile-image">
        </section>

        <section id="about" class="about">
            <h2>About Us</h2>
            <div class="about-block">
                <img src="https://5.imimg.com/data5/ANDROID/Default/2021/12/DT/TD/CI/132127444/product-jpeg-500x500.jpg" alt="construction building" class="about-image">
                <p>Ratandip Constructions is a trusted name in delivering top-quality construction projects across the region. With years of experience and a skilled team, we turn your visions into reality.</p>
            </div>

            <div class="about-block">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRCT6aJEEW0GMJ8ZUjAsgI5YFNvY9q6XVerzg&s" alt="construction blueprint" class="about-image">
                <p>Our commitment to quality and timely delivery has earned us a strong reputation among our clients. We pride ourselves on attention to detail and client satisfaction in every project we undertake.</p>
            </div>
        </section>

        <section id="services" class="services-section">
            <h2>Our Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <h3>Residential Construction</h3>
                    <p>We build durable, stylish, and comfortable homes tailored to your needs and preferences. From custom homes to multi-unit dwellings, we ensure quality craftsmanship.</p>
                </div>

                <div class="service-card">
                    <h3>Commercial Projects</h3>
                    <p>From office buildings to industrial facilities and retail spaces, we cover it all. Our commercial construction services are designed to meet diverse business requirements.</p>
                </div>

                <div class="service-card">
                    <h3>Renovation & Remodeling</h3>
                    <p>Transform your existing space with our expert remodeling solutions. Whether it's a home renovation or a commercial upgrade, we breathe new life into your property.</p>
                </div>
            </div>
        </section>

        <section id="contact" class="contact-section">
            <h2>Contact Us</h2>
            <div class="contact-form-container">
                <form>
                    <input type="text" placeholder="Your Name" required aria-label="Your Name"/>
                    <input type="email" placeholder="Your Email" required aria-label="Your Email"/>
                    <input type="tel" placeholder="Your Mobile No." pattern="[0-9]{10}" required aria-label="Your Mobile Number"/>
                    <textarea rows="5" placeholder="Your Message" aria-label="Your Message"></textarea>
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Ratandip Constructions. All rights reserved.</p>
    </footer>

</body>
</html>
