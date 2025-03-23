---
layout: default
title: Portfolio - Be-cGi
---

<div class="hero-banner">
  <div class="banner-content">
    <h1>Our Portfolio</h1>
    <p class="tagline">Discover how we've helped organizations transform their customer experience</p>
  </div>
</div>

<div class="portfolio-section">
  <div class="container">
    <div class="portfolio-filters">
      <button class="filter-btn active" data-filter="all">All</button>
      <button class="filter-btn" data-filter="retail">Retail</button>
      <button class="filter-btn" data-filter="banking">Banking</button>
      <button class="filter-btn" data-filter="telecom">Telecom</button>
    </div>
    
    <div class="portfolio-grid">
      <div class="portfolio-item" data-category="retail">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-1.jpg" alt="Retail CX Transformation">
        <div class="portfolio-title">Transformación CX en Retail</div>
        <div class="portfolio-overlay">
          <h3>Retail CX Transformation</h3>
          <p>How we helped a major retailer reimagine their customer experience</p>
          <a href="{{ site.baseurl }}/portfolio/case_study_1" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="banking">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-2.jpg" alt="Banking Customer Journey">
        <div class="portfolio-title">Experiencia Digital en Banca</div>
        <div class="portfolio-overlay">
          <h3>Banking Customer Journey</h3>
          <p>Creating seamless digital experiences for banking customers</p>
          <a href="{{ site.baseurl }}/portfolio/case_study_2" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="telecom">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-3.jpg" alt="Telecom AI Implementation">
        <div class="portfolio-title">IA Predictiva en Telecomunicaciones</div>
        <div class="portfolio-overlay">
          <h3>Telecom AI Implementation</h3>
          <p>Reducing churn with predictive AI solutions</p>
          <a href="{{ site.baseurl }}/portfolio/case_study_3" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="retail">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-4.jpg" alt="Retail Loyalty Program">
        <div class="portfolio-title">Programa de Lealtad Data-Driven</div>
        <div class="portfolio-overlay">
          <h3>Retail Loyalty Program</h3>
          <p>Designing a data-driven loyalty program that increased repeat purchases by 45%</p>
          <a href="#" class="btn">Coming Soon</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="banking">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-5.jpg" alt="Digital Banking Transformation">
        <div class="portfolio-title">Transformación de Banca Digital</div>
        <div class="portfolio-overlay">
          <h3>Digital Banking Transformation</h3>
          <p>Revamping the mobile banking experience for a leading financial institution</p>
          <a href="#" class="btn">Coming Soon</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="telecom">
        <img src="{{ site.baseurl }}/assets/images/portfolio/case-study-6.jpg" alt="Telecom Customer Service">
        <div class="portfolio-title">Servicio al Cliente Impulsado por IA</div>
        <div class="portfolio-overlay">
          <h3>Telecom Customer Service</h3>
          <p>Implementing AI-powered customer service solutions that reduced response time by 65%</p>
          <a href="#" class="btn">Coming Soon</a>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="testimonials-section">
  <div class="container">
    <h2 class="text-center">Client Success Stories</h2>
    <div class="testimonials-slider">
      <div class="testimonial-card">
        <div class="testimonial-content">
          "Working with Be-cGi has been transformative for our business. Their deep understanding of customer experience and innovative approach to data analytics helped us identify opportunities we hadn't even considered. The results have been outstanding."
        </div>
        <div class="testimonial-author">
          <img src="{{ site.baseurl }}/assets/images/team/testimonial-1.jpg" alt="John Smith" class="author-image">
          <div class="author-info">
            <h4>John Smith</h4>
            <p>CEO, Global Retail Inc.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="cta-section">
  <div class="cta-content">
    <h2>Ready to Create Your Success Story?</h2>
    <p>Let's discuss how we can help you transform your customer experience and drive business growth.</p>
    <a href="{{ site.baseurl }}/contact" class="cta-btn">Contact Us</a>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const filterButtons = document.querySelectorAll('.filter-btn');
    const portfolioItems = document.querySelectorAll('.portfolio-item');
    
    filterButtons.forEach(button => {
      button.addEventListener('click', function() {
        // Remove active class from all buttons
        filterButtons.forEach(btn => btn.classList.remove('active'));
        
        // Add active class to clicked button
        this.classList.add('active');
        
        const filter = this.dataset.filter;
        
        portfolioItems.forEach(item => {
          if (filter === 'all' || item.dataset.category === filter) {
            item.style.display = 'block';
            setTimeout(() => {
              item.classList.add('fade-in');
            }, 100);
          } else {
            item.style.display = 'none';
            item.classList.remove('fade-in');
          }
        });
      });
    });
  });
</script>
