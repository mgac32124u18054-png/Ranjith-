<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Digital Marketing Portfolio</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    background-color: #f9f9f9;
    color: #333;
  }
  header {
    background-color: #0077cc;
    color: white;
    padding: 20px 0;
    text-align: center;
  }
  header h1 {
    margin: 0;
    font-weight: 700;
  }
  nav {
    margin: 20px auto;
    text-align: center;
  }
  nav button {
    background-color: #0077cc;
    border: none;
    color: white;
    padding: 10px 18px;
    margin: 0 8px;
    font-size: 16px;
    cursor: pointer;
    border-radius: 6px;
    transition: background-color 0.3s ease;
  }
  nav button:hover {
    background-color: #005fa3;
  }
  section {
    max-width: 900px;
    margin: 20px auto;
    background: white;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 0 10px rgb(0 0 0 / 0.1);
  }
  h2 {
    color: #0077cc;
  }
  .skills-list {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .skill-item {
    background-color: #d0e7ff;
    margin: 8px;
    padding: 15px 25px;
    border-radius: 12px;
    font-weight: 600;
    box-shadow: 1px 1px 4px rgba(0,0,0,0.1);
  }
  .projects-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
  }
  .project-card {
    padding: 16px;
    border: 1px solid #0077cc;
    border-radius: 10px;
  }
  .project-title {
    font-weight: 700;
    font-size: 1.2em;
    margin-bottom: 8px;
  }
  .project-desc {
    font-size: 0.95em;
    margin-bottom: 10px;
  }
  footer {
    background-color: #0077cc;
    color: white;
    text-align: center;
    padding: 15px 0;
    margin-top: 30px;
  }
  form {
    max-width: 600px;
    margin: 20px auto;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  input, textarea {
    font-size: 1em;
    padding: 10px;
    border: 2px solid #0077cc;
    border-radius: 8px;
  }
  button.submit-btn {
    width: 150px;
    align-self: center;
    background-color: #0077cc;
    color: white;
    border: none;
    padding: 12px 0;
    cursor: pointer;
    border-radius: 8px;
    font-size: 1em;
    font-weight: 600;
  }
  button.submit-btn:hover {
    background-color: #005fa3;
  }
</style>
</head>
<body>

<header>
  <h1>ranjith - Digital Marketing Portfolio</h1>
</header>

<nav>
  <button onclick="showSection('skills-section')">Skills</button>
  <button onclick="showSection('projects-section')">Projects</button>
  <button onclick="showSection('contact-section')">Contact</button>
</nav>

<section id="skills-section">
  <h2>Skills</h2>
  <div class="skills-list">
    <div class="skill-item">SEO</div>
    <div class="skill-item">Content Marketing</div>
    <div class="skill-item">Google Ads</div>
    <div class="skill-item">Social Media Marketing</div>
    <div class="skill-item">Email Marketing</div>
    <div class="skill-item">Analytics & Reporting</div>
  </div>
</section>

<section id="projects-section" style="display:none;">
  <h2>Projects</h2>
  <div class="projects-container" id="projects-container">
    <!-- Projects will be dynamically inserted here -->
  </div>
</section>

<section id="contact-section" style="display:none;">
  <h2>Contact Me</h2>
  <form id="contact-form" onsubmit="submitForm(event)">
    <input type="text" id="name" placeholder="Your Name" required />
    <input type="email" id="email" placeholder="Your Email" required />
    <textarea id="message" rows="5" placeholder="Your Message" required></textarea>
    <button type="submit" class="submit-btn">Send</button>
  </form>
</section>

<footer>
  &copy; 2025 ranjith - Digital Marketing Portfolio
</footer>

<script>
// Sample projects data
const projects = [
  {
    title: 'SEO Optimization for Local Business',
    description: 'Improved organic traffic by 40% within 3 months through on-page and off-page SEO techniques.'
  },
  {
    title: 'Google Ads Campaign Management',
    description: 'Managed PPC campaigns with a budget of $5,000/month resulting in 20% higher conversion rates.'
  },
  {
    title: 'Social Media Growth Strategy',
    description: 'Developed content calendar & ads strategy that increased Instagram followers by 60%.'
  }
];

// Function to show selected section and hide others
function showSection(sectionId) {
  const sections = ['skills-section', 'projects-section', 'contact-section'];
  sections.forEach(id => {
    document.getElementById(id).style.display = id === sectionId ? 'block' : 'none';
  });
}

// Dynamically render projects
function renderProjects() {
  const container = document.getElementById('projects-container');
  container.innerHTML = '';
  projects.forEach(proj => {
    const card = document.createElement('div');
    card.className = 'project-card';
    const title = document.createElement('div');
    title.className = 'project-title';
    title.textContent = proj.title;
    const desc = document.createElement('div');
    desc.className = 'project-desc';
    desc.textContent = proj.description;
    card.appendChild(title);
    card.appendChild(desc);
    container.appendChild(card);
  });
}

// Handle contact form submission
function submitForm(event) {
  event.preventDefault();
  alert('Thank you for contacting! I will get back to you soon.');
  document.getElementById('contact-form').reset();
}

// Initialize page with projects loaded
renderProjects();
</script>

</body>
</html>
