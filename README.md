<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hanif Patel</title>

    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            transition: background-color 0.5s;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1em;
            text-align: center;
        }

        nav {
            display: flex;
            justify-content: space-around;
            background-color: #444;
            padding: 1em;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #ff9900;
        }

        section {
            padding: 2em;
            text-align: center;
        }
        
        .left{
            position: relative;
        }
        
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 1em;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        .dark-mode {
            background-color: #222;
            color: #fff;
        }
        
    </style>
</head>
<body>

    <header>
        <h1>Hanif Patel</h1>
        <div3>
        <left> 
            <button onClick="toggleDarkMode()"><img src="dark.jpg" width="15px" height="15px" /></button> 
        </left>
    </div3>
    </header>

    <nav>
        <a href="#home">Home</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#contact">Contact</a>
    </nav>

    <section id="home">
        <h2>Welcome to my website!</h2>
        <p>This is the home section. Feel free to explore the rest of the site.</p>
    </section>

    <section id="portfolio">
        <h2>Portfolio</h2>
        <p>Check out some of my work below:</p>
        <!-- Add portfolio items here -->
    </section>

    <section id="contact">
        <h2>Contact Me</h2>
        <p>Feel free to reach out to me through the contact form below:</p>
        <!-- Add contact form here -->
    </section>

    <footer>
       All rights reserved
    </footer>

    <script>
        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
        }
    </script>

</body>
</html>
