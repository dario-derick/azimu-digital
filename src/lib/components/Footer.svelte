<script>
  let year = new Date().getFullYear();
</script>

<footer>
  <div class="container">
    <div class="footer-grid">
      <!-- About Section -->
      <div class="footer-col">
        <h3>Azimu Digial</h3>
        <p>
           Empowering organizations with innovative digital solutions. Building
           impactful websites, fostering connections, and helping ministries
            reach more people online.
        </p>
        <div class="social-links">
          <a href="https://www.facebook.com/tasSolutions" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
          <a href="https://twitter.com/" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
          <a href="https://www.instagram.com/dari_dero" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
        </div>
      </div>

      <!-- Quick Links -->
      <div class="footer-col">
        <h3>Quick Links</h3>
        <ul class="footer-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#ministries">Solutions</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="donate.html">Demo</a></li>
        </ul>
      </div>

      <!-- Ministries -->
      <div class="footer-col">
        <h3>Our Solutions</h3>
        <ul class="footer-links">
          <li><a href="#home">Web Development</a></li>
          <li><a href="#about">Content Management</a></li>
          <li><a href="#ministries">Branding</a></li>
          <li><a href="#contact">Performance Marketing</a></li>
          <li><a href="donate.html">Mission</a></li>
        </ul>
      </div>

      <!-- Contact -->
      <div class="footer-col">
        <h3>Contact Us</h3>
        <div class="footer-contact-item">
          <i class="fas fa-map-marker-alt"></i>
          <span>Kisumu, Kenya</span>
        </div>
        <div class="footer-contact-item">
          <i class="fas fa-phone-alt"></i>
          <span>+254 748 800385</span>
        </div>
        <div class="footer-contact-item">
          <i class="fas fa-envelope"></i>
          <span>info@azimudigital.tech</span>
        </div>
        <div class="footer-contact-item">
          <i class="fas fa-clock"></i>
          <span>24/7</span>
        </div>
      </div>
    </div>

    <!-- Copyright -->
    <div class="copyright">
      <p>&copy; {year} Azimu Digital. All Rights Reserved.</p>

    </div>
  </div>

  <!-- WhatsApp Float -->
  <a
    href="https://wa.me/254748800385?text=Hello%20I%20need%20help"
    class="whatsapp-float"
    target="_blank"
    aria-label="WhatsApp Chat"
  >
    <i class="fab fa-whatsapp"></i>
  </a>
</footer>

<style>
  footer {
    background-color: #1C2B39;
    color: #ffffff;
    padding: 50px 40px 30px;
    font-family: "Montserrat", sans-serif;
  }

  .footer-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 40px;
    margin-bottom: 40px;
  }

  .footer-col h3 {
    font-size: 1.3rem;
    margin-bottom: 20px;
    position: relative;
  }

  .footer-col h3::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -8px;
    width: 40px;
    height: 3px;
    background-color: #A66F1C;
  }

  .footer-col p {
    line-height: 1.6;
    margin-bottom: 15px;
    color: rgba(255, 255, 255, 0.85);
  }

  .footer-links {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .footer-links li {
    margin-bottom: 10px;
  }

  .footer-links a {
    color: rgba(255, 255, 255, 0.7);
    text-decoration: none;
    transition: 0.3s;
  }

  .footer-links a:hover {
    color: #A66F1C;
    padding-left: 5px;
  }

  .footer-contact-item {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
    color: rgba(255, 255, 255, 0.85);
  }

  .footer-contact-item i {
    color: #A66F1C;
    margin-right: 10px;
  }

  .social-links {
    display: flex;
    gap: 15px;
    margin-top: 10px;
  }

  .social-links a {
    color: white;
    font-size: 1.2rem;
    transition: 0.3s;
  }

  .social-links a:hover {
    color: #A66F1C;
  }

  .copyright {
    text-align: center;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    padding-top: 20px;
    font-size: 0.9rem;
    color: rgba(255, 255, 255, 0.7);
  }

  
  /* WhatsApp Float */
  .whatsapp-float {
    position: fixed;
    width: 60px;
    height: 60px;
    bottom: 30px;
    right: 30px;
    background-color: #25d366;
    color: white;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 28px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
    transition: all 0.3s ease;
    z-index: 1000;
  }

  .whatsapp-float:hover {
    background-color: #20ba5a;
    transform: scale(1.1);
  }

  @media (max-width: 768px) {
    .footer-grid {
      gap: 30px;
    }

    .footer-col h3 {
      font-size: 1.1rem;
    }

    .social-links a {
      font-size: 1rem;
    }
  }
</style>
