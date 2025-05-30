# Blog-website
#A simple and responsive blog website built with Html,CSS and javascript featuring a clean layout to display and explore blog posts. Designed for a smooth user experience with locally managed content.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Responsive Blog Layout</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    header {
      background: #333;
      color: white;
      padding: 1em;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    nav {
      display: flex;
      gap: 1em;
    }

    nav a {
      color: white;
      text-decoration: none;
      cursor: pointer;
    }

    .menu-toggle {
      display: none;
      font-size: 1.5em;
      cursor: pointer;
    }

    .container {
      display: flex;
      flex: 1;
    }

    .sidebar {
      width: 250px;
      background: #f4f4f4;
      padding: 1em;
      display: block;
      position: relative;
    }

    .close-sidebar {
      position: absolute;
      top: 10px;
      right: 10px;
      background: none;
      border: none;
      font-size: 1.2em;
      cursor: pointer;
    }

    .main-content {
      flex: 1;
      padding: 1em;
    }

    section {
      display: none;
    }

    section.active {
      display: block;
    }

    .blog-posts {
      display: flex;
      flex-wrap: wrap;
      gap: 2em;
      justify-content: center;
    }

    .blog-post {
      width: 400px;
      background: #fff;
      border: 1px solid #ccc;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
      transition: transform 0.3s;
    }

    .blog-post:hover {
      transform: translateY(-5px);
    }

    .blog-post img {
      width: 100%;
      height: 250px;
      object-fit: cover;
    }

    .blog-post-content {
      padding: 1.5em;
    }

    .blog-post-content h3 {
      margin-bottom: 0.5em;
    }

    .blog-post-content p {
      margin: 0.5em 0;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 1em;
      max-width: 400px;
    }

    form input, form textarea {
      padding: 0.75em;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    form button {
      background-color: #333;
      color: white;
      padding: 0.75em;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    footer {
      background: #333;
      color: white;
      text-align: center;
      padding: 3em;
      margin-top: auto;
    }

    footer p {
      margin-bottom: 1em;
    }

    footer .footer-columns {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      color: #ccc;
    }

    footer .footer-column {
      margin: 1em;
      min-width: 200px;
    }

    @media (max-width: 768px) {
      .container {
        flex-direction: column;
      }

      .sidebar {
        display: none;
        width: 100%;
      }

      .menu-toggle {
        display: block;
      }

      nav {
        display: none;
        flex-direction: column;
        background: #444;
        padding: 1em;
      }

      nav a {
        padding: 0.5em 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>My Blog</h1>
    <span class="menu-toggle" onclick="toggleMenu()">&#9776;</span>
    <nav id="navbar">
      <a onclick="showSection('home')">Home</a>
      <a onclick="showSection('about')">About</a>
      <a onclick="showSection('contact')">Contact</a>
    </nav>
  </header>

  <div class="container">
    <aside class="sidebar" id="sidebar">
      <button class="close-sidebar" onclick="toggleSidebar()">&times;</button>
      <h3>Sidebar</h3>
      <p>Useful links or widgets can go here.</p>
    </aside>

    <main class="main-content">
      <section id="home" class="active">
        <div class="blog-posts">
          <div class="blog-post">
            <img src="photo2.png"Mastering Flexbox" />
            <div class="blog-post-content">
              <h3>Mastering Flexbox</h3>
              <p>A guide to CSS Flexbox layout.</p>
              <p><strong>Author:</strong> Jane Doe</p>
              <p><strong>Date:</strong> May 25, 2025</p>
            </div>
          </div>
          <div class="blog-post">
            <img src="photo1.png" alt="Understanding JavaScript Closures" />
            <div class="blog-post-content">
              <h3>Understanding JavaScript Closures</h3>
              <p>How closures work in JavaScript with examples.</p>
              <p><strong>Author:</strong> John Smith</p>
              <p><strong>Date:</strong> May 24, 2025</p>
            </div>
          </div>
          <div class="blog-post">
            <img src="photo3.png" alt="Responsive Design Tips" />
            <div class="blog-post-content">
              <h3>Responsive Design Tips</h3>
              <p>Best practices for building responsive websites.</p>
              <p><strong>Author:</strong> Emily White</p>
              <p><strong>Date:</strong> May 23, 2025</p>
            </div>
          </div>
          <div class="blog-post">
            <img src="photo4.jpg" alt="Getting Started with React" />
            <div class="blog-post-content">
              <h3>Getting Started with React</h3>
              <p>A beginner's guide to building apps with React.</p>
              <p><strong>Author:</strong> Alex Green</p>
              <p><strong>Date:</strong> May 22, 2025</p>
            </div>
          </div>
          <div class="blog-post">
            <img src="photo5.webp" alt="What is Node.js?" />
            <div class="blog-post-content">
              <h3>What is Node.js?</h3>
              <p>Learn what Node.js is and why it's popular.</p>
              <p><strong>Author:</strong> Sam Lee</p>
              <p><strong>Date:</strong> May 21, 2025</p>
            </div>
          </div>
          <div class="blog-post">
            <img src="photo2.png" alt="CSS Grid vs Flexbox" />
            <div class="blog-post-content">
              <h3>CSS Grid vs Flexbox</h3>
              <p>Comparison between CSS Grid and Flexbox.</p>
              <p><strong>Author:</strong> Rachel Kim</p>
              <p><strong>Date:</strong> May 20, 2025</p>
            </div>
          </div>
        </div>
      </section>

      <section id="about">
        <h2>About Us</h2>
        <p>Welcome to our blog! We share web development tips, tutorials, and project ideas to help you grow your skills.</p>
      </section>

      <section id="contact">
        <h2>Contact Us</h2>
        <form>
          <input type="text" placeholder="Your Name" required />
          <input type="email" placeholder="Your Email" required />
          <textarea rows="5" placeholder="Your Message" required></textarea>
          <button type="submit">Send Message</button>
        </form>
      </section>
    </main>
  </div>

  <footer>
    <p>&copy; 2025 My Blog. All rights reserved.</p>
    <div class="footer-columns">
      <div class="footer-column">
        <h4>Quick Links</h4>
        <p>Home</p>
        <p>About</p>
        <p>Contact</p>
      </div>
      <div class="footer-column">
        <h4>Resources</h4>
        <p>Privacy Policy</p>
        <p>Terms of Service</p>
        <p>FAQs</p>
      </div>
      <div class="footer-column">
        <h4>Connect</h4>
        <p>Facebook</p>
        <p>Twitter</p>
        <p>Instagram</p>
      </div>
    </div>
  </footer>

  <script>
    function toggleMenu() {
      const nav = document.getElementById('navbar');
      nav.style.display = nav.style.display === 'flex' ? 'none' : 'flex';
    }

    function toggleSidebar() {
      const sidebar = document.getElementById('sidebar');
      sidebar.style.display = sidebar.style.display === 'none' ? 'block' : 'none';
    }

    function showSection(sectionId) {
      document.querySelectorAll('main section').forEach(section => {
        section.classList.remove('active');
      });
      document.getElementById(sectionId).classList.add('active');
    }
  </script>
</body>
</html>

