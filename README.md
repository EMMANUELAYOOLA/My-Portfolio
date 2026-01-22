<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Emmanuel Ayoola | Software Developer</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Poppins', sans-serif;
      background: #0f172a;
      color: #e5e7eb;
      scroll-behavior: smooth;
    }

    header {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      background: rgba(15, 23, 42, 0.9);
      backdrop-filter: blur(10px);
      z-index: 1000;
      padding: 15px 50px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    header h1 { color: #38bdf8; font-size: 1.4rem; }

    nav a {
      margin-left: 25px;
      text-decoration: none;
      color: #e5e7eb;
      font-weight: 500;
      transition: 0.3s;
    }

    nav a:hover { color: #38bdf8; }

    section {
      min-height: 100vh;
      padding: 120px 80px 60px;
    }

    .hero {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      align-items: center;
      gap: 40px;
    }

    .hero h2 {
      font-size: 3rem;
      line-height: 1.2;
    }

    .hero span { color: #38bdf8; }

    .hero p {
      margin: 20px 0 30px;
      font-size: 1.1rem;
      max-width: 550px;
      color: #cbd5f5;
    }

    .btn {
      display: inline-block;
      padding: 12px 28px;
      background: linear-gradient(135deg, #38bdf8, #6366f1);
      border-radius: 30px;
      color: white;
      font-weight: 600;
      text-decoration: none;
      transition: 0.3s;
      box-shadow: 0 10px 25px rgba(56,189,248,0.3);
    }

    .btn:hover { transform: translateY(-3px); box-shadow: 0 15px 35px rgba(56,189,248,0.4); }

    .hero-card {
      background: linear-gradient(145deg, #020617, #0f172a);
      padding: 40px;
      border-radius: 25px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.4);
      animation: float 4s ease-in-out infinite;
    }

    @keyframes float {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-12px); }
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
      margin-top: 30px;
    }

    .stat {
      background: #020617;
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      border: 1px solid #1e293b;
    }

    .stat h3 { color: #38bdf8; font-size: 1.6rem; }

    h3.section-title {
      font-size: 2.4rem;
      margin-bottom: 50px;
      text-align: center;
    }

    .about {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 50px;
      align-items: center;
    }

    .about-card {
      background: #020617;
      padding: 40px;
      border-radius: 25px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
    }

    .skills {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 20px;
      margin-top: 25px;
    }

    .skill {
      background: linear-gradient(145deg, #020617, #0f172a);
      padding: 15px;
      border-radius: 12px;
      text-align: center;
      border: 1px solid #1e293b;
      font-weight: 600;
      transition: 0.3s;
    }

    .skill:hover { transform: translateY(-4px); color: #38bdf8; }

    .projects {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
    }

    .project-card {
      background: linear-gradient(145deg, #020617, #0f172a);
      border-radius: 20px;
      padding: 25px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.4);
      border: 1px solid #1e293b;
      transition: 0.3s;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: "";
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(120deg, transparent, rgba(56,189,248,0.15), transparent);
      transition: 0.6s;
    }

    .project-card:hover::before { left: 100%; }

    .project-card:hover { transform: translateY(-6px); }

    .project-card h4 { margin-bottom: 10px; color: #38bdf8; }

    .project-card p { font-size: 0.95rem; color: #cbd5f5; }

    .project-card a {
      display: inline-block;
      margin-top: 15px;
      color: #38bdf8;
      text-decoration: none;
      font-weight: 600;
    }

    .contact {
      max-width: 600px;
      margin: auto;
      background: #020617;
      padding: 40px;
      border-radius: 25px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
    }

    .contact input, .contact textarea {
      width: 100%;
      padding: 12px 15px;
      margin-bottom: 15px;
      border-radius: 10px;
      border: none;
      outline: none;
      background: #0f172a;
      color: white;
      font-size: 0.95rem;
    }

    .contact button {
      width: 100%;
      padding: 12px;
      border-radius: 30px;
      border: none;
      background: linear-gradient(135deg, #38bdf8, #6366f1);
      color: white;
      font-weight: 700;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.3s;
    }

    .contact button:hover { transform: translateY(-2px); }

    footer {
      text-align: center;
      padding: 25px;
      background: #020617;
      color: #94a3b8;
    }

    .fade-in {
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s ease;
    }

    .fade-in.show {
      opacity: 1;
      transform: translateY(0);
    }

    @media(max-width: 900px) {
      .hero, .about { grid-template-columns: 1fr; }
      header { padding: 15px 25px; }
      section { padding: 120px 25px 60px; }
      .hero h2 { font-size: 2.2rem; }
    }
  </style>
</head>
<body>

<header>
  <h1>Emmanuel.dev</h1>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section id="home" class="hero fade-in">
  <div>
    <h2>Hello, I'm <span>Emmanuel Ayoola</span><br>Software Developer & Web Engineer</h2>
    <p>
      I build modern, fast, and scalable web applications using cutting-edge technologies.
      Trained at <b>New Horizon</b> and <b>TS Academy</b>, I specialize in professional website development and software solutions.
    </p>
    <a href="#projects" class="btn">View My Work</a>

    <div class="stats">
      <div class="stat">
        <h3>20+</h3>
        <p>Projects</p>
      </div>
      <div class="stat">
        <h3>3+</h3>
        <p>Years Learning</p>
      </div>
      <div class="stat">
        <h3>100%</h3>
        <p>Commitment</p>
      </div>
    </div>
  </div>

  <div class="hero-card">
    <h3>Core Stack</h3>
    <div class="skills">
      <div class="skill">HTML5</div>
      <div class="skill">CSS3</div>
      <div class="skill">JavaScript</div>
      <div class="skill">Python</div>
      <div class="skill">Flask</div>
      <div class="skill">React</div>
      <div class="skill">Git & GitHub</div>
      <div class="skill">Responsive Design</div>
    </div>
  </div>
</section>

<section id="about" class="fade-in">
  <h3 class="section-title">About Me</h3>
  <div class="about">
    <div class="about-card">
      <h4>Professional Profile</h4>
      <p style="margin-top:15px; color:#cbd5f5; line-height:1.7;">
        I am a passionate software developer and website engineer with strong training from
        <b>New Horizon</b> and <b>TS Academy</b>. I focus on building clean, responsive, and
        high-performance digital solutions for individuals, schools, ministries, and businesses.
        <br><br>
        My goal is to create systems that are not just functional, but elegant, secure, and scalable.
      </p>
    </div>

    <div class="about-card">
      <h4>Skills & Expertise</h4>
      <div class="skills">
        <div class="skill">Frontend Development</div>
        <div class="skill">Backend Development</div>
        <div class="skill">REST APIs</div>
        <div class="skill">UI/UX Design</div>
        <div class="skill">Database Systems</div>
        <div class="skill">Authentication Systems</div>
        <div class="skill">Deployment</div>
        <div class="skill">Version Control</div>
      </div>
    </div>
  </div>
</section>

<section id="projects" class="fade-in">
  <h3 class="section-title">Projects</h3>
  <div class="projects">

    <div class="project-card">
      <h4>School Management System</h4>
      <p>A full-featured web application for managing students, teachers, results, and fees using Python backend.</p>
      <a href="#">View Project →</a>
    </div>

    <div class="project-card">
      <h4>Business Portfolio Website</h4>
      <p>A modern responsive website for businesses with animations, SEO optimization, and performance tuning.</p>
      <a href="#">View Project →</a>
    </div>

    <div class="project-card">
      <h4>Authentication System</h4>
      <p>Secure login, signup, and role-based access system using Flask and modern security practices.</p>
      <a href="#">View Project →</a>
    </div>

    <div class="project-card">
      <h4>REST API Backend</h4>
      <p>Scalable RESTful API service for handling data processing, authentication, and integrations.</p>
      <a href="#">View Project →</a>
    </div>

  </div>
</section>

<section id="contact" class="fade-in">
  <h3 class="section-title">Contact Me</h3>
  <div class="contact">
    <form onsubmit="sendMessage(event)">
      <input type="text" id="name" placeholder="Your Name" required />
      <input type="email" id="email" placeholder="Your Email" required />
      <textarea id="message" rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
  </div>
</section>

<footer>
  © 2026 Emmanuel Ayoola — Software Developer
</footer>

<script>
  // Scroll animations
  const faders = document.querySelectorAll('.fade-in');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('show');
      }
    });
  }, { threshold: 0.2 });

  faders.forEach(el => observer.observe(el));

  // Contact form handler (demo)
  function sendMessage(e) {
    e.preventDefault();
    const name = document.getElementById('name').value;
    alert(`Thank you, ${name}! Your message has been sent.`);
    e.target.reset();
  }
</script>

</body>
</html>

