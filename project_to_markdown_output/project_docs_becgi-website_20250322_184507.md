Project Documentation Summary
=========================
Root Directory: C:\Users\ronal\APPs\becgi-website
Files Analyzed: 14
Total Size: 68.54 KB
Timestamp: 2025-03-22 18:45:07

Skipped Files Sample:
-------------------
- excluded lock file or similar: Gemfile.lock
- binary file (3 files):
  • assets\css\style.scss
  • assets\docs\BE-cGi-Presentación.pdf
  • assets\docs\be-cgi-logo.jpeg

Directory Structure
==================

becgi-website
├── .gitignore
├── Gemfile
├── Gemfile.lock
├── _config.yml
├── _layouts/
│   ├── default.html
│   ├── post.html
│   └── project.html
├── _posts/
│   └── 2025-03-15-ai-insights.md
├── _projects/
│   └── case_study_1.md
├── assets/
│   ├── css/
│   │   └── style.scss
│   ├── docs/
│   │   ├── BE-cGi-Presentación.pdf
│   │   └── be-cgi-logo.jpeg
│   └── images/
│       ├── blog/
│       ├── clients/
│       ├── portfolio/
│       └── team/
├── blog.md
├── contact.md
├── index.md
├── portfolio.md
├── readme.md
└── team.md

File Contents
=============


================================================================================
File: .gitignore
================================================================================

# Jekyll site
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata
Gemfile.lock

# Windows files
Thumbs.db
ehthumbs.db
Desktop.ini
$RECYCLE.BIN/

# Mac files
.DS_Store
.AppleDouble
.LSOverride
Icon
._*

# IDE files
.idea/
.vscode/
*.swp
*.swo

# Logs
*.log

# Temp directories
tmp/
temp/

# Files that might appear in the root of a volume
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns




================================================================================
File: Gemfile
================================================================================

source 'https://rubygems.org'

gem 'jekyll'
gem 'webrick'
gem 'jekyll-sitemap'
gem 'jekyll-feed'
gem 'jekyll-seo-tag'
gem 'csv'
gem 'base64'
gem 'wdm', '>= 0.1.0' if Gem.win_platform?




================================================================================
File: _config.yml
================================================================================

title: Be-cGi - Customer Experience Consulting
description: Consultora especializada en Customer Experience apalancada en Data e Inteligencia Artificial. A través del capital relacional aumentamos el capital económico de las organizaciones.
logo: /assets/images/logo.png
favicon: /assets/images/favicon.png
social_links:
  linkedin: becgi-consulting
  twitter: BecGiConsulting
github_username: GalacticaSystem
repository: GalacticaSystem/becgi-web
baseurl: "/becgi-web" # Necesario para GitHub Pages en repo que no es username.github.io

# Collections configuration
collections:
  projects:
    output: true
    permalink: /portfolio/:path/

# Build settings
markdown: kramdown
permalink: /blog/:year/:month/:day/:title/

# Defaults for posts and projects
defaults:
  - scope:
      path: ""
      type: "posts"
    values:
      layout: "post"
  - scope:
      path: ""
      type: "projects"
    values:
      layout: "project"
  - scope:
      path: ""
    values:
      layout: default



================================================================================
File: _layouts\default.html
================================================================================

<!-- _layouts/default.html -->
<!DOCTYPE html>
<html lang="{{ site.lang | default: "en-US" }}">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="{{ site.description }}">
    <title>{{ site.title }}</title>
    <!-- Favicon -->
    <link rel="icon" type="image/png" sizes="32x32" href="/assets/images/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/assets/images/favicon-16x16.png">
    <link rel="stylesheet" href="{{ "/assets/css/style.css?v=" | append: site.github.build_revision | relative_url }}">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  </head>
  <body>
    <nav class="main-nav">
      <div class="nav-container">
        <a href="/" class="nav-logo">
          <img src="/assets/images/logo.png" alt="Be-cGi" class="nav-logo-img">
        </a>
        <button class="nav-toggle" aria-label="toggle navigation">
          <span class="hamburger"></span>
        </button>
        <div class="nav-links">
          <a href="/" class="nav-link">Home</a>
          <a href="/portfolio" class="nav-link">Portfolio</a>
          <a href="/blog" class="nav-link">Blog</a>
          <a href="/team" class="nav-link">Our Team</a>
          <a href="/contact" class="nav-link">Contact</a>
        </div>
      </div>
    </nav>
    <div class="wrapper">
      <main>
        {{ content }}
      </main>
      <footer>
        <div class="footer-content">
          <div class="footer-logo">
            <img src="/assets/images/logo.png" alt="Be-cGi" class="footer-logo-img">
            <p class="footer-tagline">"A través del capital relacional aumentamos el capital económico de las organizaciones"</p>
          </div>
          <div class="footer-links">
            <h3>Quick Links</h3>
            <a href="/">Home</a>
            <a href="/portfolio">Portfolio</a>
            <a href="/blog">Blog</a>
            <a href="/team">Our Team</a>
            <a href="/contact">Contact</a>
          </div>
          <div class="footer-contact">
            <h3>Contact Us</h3>
            <p><i class="fas fa-envelope"></i> info@becgi.com</p>
            <p><i class="fas fa-phone"></i> +1 (123) 456-7890</p>
            <div class="social-icons">
              <a href="https://linkedin.com/company/becgi-consulting" target="_blank"><i class="fab fa-linkedin"></i></a>
              <a href="https://twitter.com/BecGiConsulting" target="_blank"><i class="fab fa-twitter"></i></a>
            </div>
          </div>
        </div>
        <div class="footer-bottom">
          <p class="text-center">
            © {{ site.time | date: '%Y' }} {{ site.title }}. All Rights Reserved.
          </p>
        </div>
      </footer>
    </div>
    <script>
      document.addEventListener('DOMContentLoaded', function() {
        const navToggle = document.querySelector('.nav-toggle');
        const navLinks = document.querySelector('.nav-links');
        
        if (navToggle && navLinks) {
          navToggle.addEventListener('click', function() {
            navLinks.classList.toggle('nav-active');
            navToggle.classList.toggle('active');
            document.body.classList.toggle('menu-open');
          });
        
          // Cierra el menú cuando se hace clic en un enlace
          document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function() {
              navLinks.classList.remove('nav-active');
              navToggle.classList.remove('active');
              document.body.classList.remove('menu-open');
            });
          });
          
          // Cierra el menú cuando se hace clic fuera de él
          document.addEventListener('click', function(event) {
            const isClickInsideNav = navLinks.contains(event.target);
            const isClickOnToggle = navToggle.contains(event.target);
            
            if (!isClickInsideNav && !isClickOnToggle && navLinks.classList.contains('nav-active')) {
              navLinks.classList.remove('nav-active');
              navToggle.classList.remove('active');
              document.body.classList.remove('menu-open');
            }
          });
          
          // Ajusta el padding-top del contenido principal
          const mainContent = document.querySelector('main');
          if (mainContent) {
            const navHeight = document.querySelector('.main-nav').offsetHeight;
            mainContent.style.paddingTop = navHeight + 'px';
          }
        }
      });
    </script>
  </body>
</html>



================================================================================
File: _layouts\post.html
================================================================================

---
layout: default
---

<article class="post">
  <header class="post-header">
    {% if page.cover_image %}
    <div class="post-cover">
      <img src="{{ page.cover_image }}" alt="{{ page.title }}">
    </div>
    {% endif %}
    
    {% unless page.hide_title %}
    <h1 class="post-title">{{ page.title }}</h1>
    {% endunless %}
    
    <div class="post-meta">
      <span class="post-date">
        <i class="fas fa-calendar"></i>
        {{ page.date | date: "%B %d, %Y" }}
      </span>
      
      {% if page.reading_time %}
      <span class="reading-time">
        <i class="fas fa-clock"></i>
        {{ page.reading_time }} min read
      </span>
      {% endif %}
      
      {% if page.tags %}
      <div class="post-tags">
        {% for tag in page.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>
  </header>

  <div class="post-content">
    {{ content }}
  </div>
  
  <footer class="post-footer">
    <div class="share-buttons">
      <a href="https://twitter.com/intent/tweet?text={{ page.title | url_encode }}&url={{ site.url }}{{ page.url }}" 
         target="_blank" class="share-button twitter">
        <i class="fab fa-twitter"></i> Share
      </a>
      <a href="https://www.linkedin.com/shareArticle?mini=true&url={{ site.url }}{{ page.url }}&title={{ page.title | url_encode }}" 
         target="_blank" class="share-button linkedin">
        <i class="fab fa-linkedin"></i> Share
      </a>
    </div>
    
    <div class="cta-box">
      <h3>Want to improve your customer experience?</h3>
      <p>Let our experts help you leverage data and AI to create meaningful connections with your customers.</p>
      <a href="/contact" class="cta-button">Contact Us</a>
    </div>
  </footer>
</article>



================================================================================
File: _layouts\project.html
================================================================================

---
layout: default
---
<article class="project">
  <header class="project-header">
    {% if page.cover_image %}
    <div class="project-cover">
      <img src="{{ page.cover_image }}" alt="{{ page.title }}">
    </div>
    {% endif %}
    
    <h1 class="project-title">{{ page.title }}</h1>
    
    <div class="project-meta">
      {% if page.client %}
      <div class="client-info">
        <span class="meta-label">Client:</span>
        <span class="meta-value">{{ page.client }}</span>
      </div>
      {% endif %}
      
      {% if page.industry %}
      <div class="industry-info">
        <span class="meta-label">Industry:</span>
        <span class="meta-value">{{ page.industry }}</span>
      </div>
      {% endif %}
      
      {% if page.duration %}
      <div class="duration-info">
        <span class="meta-label">Duration:</span>
        <span class="meta-value">{{ page.duration }}</span>
      </div>
      {% endif %}
      
      {% if page.tags %}
      <div class="project-tags">
        {% for tag in page.tags %}
        <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>
  </header>

  <div class="project-content">
    {{ content }}
  </div>
  
  <footer class="project-footer">
    <div class="project-nav">
      <div class="prev-next-links">
        {% if page.previous.url %}
        <a href="{{ page.previous.url }}" class="prev-link">
          <i class="fas fa-arrow-left"></i> Previous Case Study
        </a>
        {% endif %}
        
        {% if page.next.url %}
        <a href="{{ page.next.url }}" class="next-link">
          Next Case Study <i class="fas fa-arrow-right"></i>
        </a>
        {% endif %}
      </div>
    </div>
    
    <div class="contact-cta">
      <h3>Interested in similar results for your business?</h3>
      <p>Let's discuss how we can help improve your customer experience through data-driven strategies.</p>
      <a href="/contact" class="cta-button">Get in Touch</a>
    </div>
  </footer>
</article>



================================================================================
File: _posts\2025-03-15-ai-insights.md
================================================================================

---
layout: post
title: "How AI is Reshaping Customer Experience in 2025"
date: 2025-03-15
cover_image: /assets/images/blog/post-1.jpg
tags: [AI, CX, Technology, Innovation, Business Growth]
reading_time: 8
---

# How AI is Reshaping Customer Experience in 2025

Artificial Intelligence has evolved from a futuristic concept to an essential component of successful customer experience strategies. As we move through 2025, the impact of AI on how businesses interact with their customers has become more profound and sophisticated than ever before.

## The Evolution of AI in Customer Experience

The journey of AI in customer experience has been remarkable. From basic chatbots and recommendation engines to today's sophisticated predictive analytics and personalization systems, AI has transformed every aspect of the customer journey. 

In 2025, we're seeing several key trends that are redefining the possibilities of customer experience:

### 1. Hyper-Personalization at Scale

Today's AI systems can analyze vast amounts of customer data in real-time to deliver truly personalized experiences. Unlike the rudimentary personalization of previous years, modern AI considers:

- **Contextual awareness**: Understanding a customer's current situation, including location, device, time of day, and recent interactions
- **Emotional intelligence**: Detecting sentiment and emotional states to adjust tone and approach
- **Predictive behavior modeling**: Anticipating needs before they're expressed
- **Cross-channel consistency**: Maintaining personalized experiences across all touchpoints

**Real-world example:** A leading telecom provider implemented our AI-driven hyper-personalization system and saw a 45% increase in offer acceptance rates and a 28% reduction in churn by delivering the right message at precisely the right moment across all channels.

### 2. Autonomous Customer Service

AI-powered service has moved beyond simple task automation to handle complex customer issues with minimal human intervention:

- **Self-learning knowledge bases** that continuously improve through customer interactions
- **Multimodal communication** capabilities that seamlessly blend text, voice, and visual elements
- **Proactive issue resolution** that identifies and addresses potential problems before customers notice
- **Human-AI collaboration** models where AI handles routine inquiries and augments human agents for complex cases

**Case study impact:** For a major banking client, our autonomous customer service implementation reduced resolution times by 67% while increasing customer satisfaction scores from 72% to 91%.

### 3. Predictive Experience Design

Rather than reacting to customer needs, leading companies are using AI to anticipate and design experiences proactively:

- **Journey anticipation** algorithms that predict likely paths and friction points
- **Real-time experience adaptation** based on emerging patterns
- **Sentiment prediction** to preemptively address negative experiences
- **Next-best-action recommendations** for customers and employees

This predictive approach has fundamentally changed how businesses design customer experiences, moving from reactive to proactive models.

## The Convergence of AI and Relational Capital

At Be-cGi, we view AI not as a replacement for human connection but as an enhancer of relational capital. The most successful implementations we've deployed combine technological sophistication with human-centered design.

![AI and Relational Capital](/assets/images/blog/ai-relational-capital.jpg)

### Building Trust Through Transparent AI

As AI becomes more integrated into customer experiences, transparency has emerged as a critical factor in building trust:

- **Explainable AI** that can communicate the reasoning behind recommendations
- **Clear disclosure** of AI involvement in customer interactions
- **Customer control** over AI-driven personalization and data usage
- **Ethical guidelines** for AI implementation that prioritize customer interests

### Measuring AI's Impact on Customer Experience

Quantifying the return on AI investments in customer experience requires a sophisticated approach to measurement:

| Metric | Traditional Approach | AI-Enhanced Approach |
|--------|----------------------|----------------------|
| Customer Satisfaction | Periodic surveys | Real-time sentiment analysis across all channels |
| Retention | Historical churn analysis | Predictive churn models with intervention recommendations |
| Lifetime Value | Segment-based estimates | Individual-level dynamic LTV predictions |
| Journey Effectiveness | Conversion metrics | End-to-end journey optimization with predictive pathing |

## Implementing AI-Driven CX: Lessons from the Field

Through our work with organizations across industries, we've identified key success factors for AI-driven customer experience transformation:

### 1. Start with Strategy, Not Technology

The most successful implementations begin with clear CX objectives rather than technology capabilities. Identify your highest-value customer pain points and opportunities before selecting AI solutions.

### 2. Invest in Data Infrastructure

AI is only as good as the data it consumes. Organizations seeing the greatest returns have invested in creating unified customer data platforms that integrate information from all touchpoints.

### 3. Build Cross-Functional Teams

Effective AI implementation requires collaboration between data scientists, CX professionals, IT, legal, and business leaders. Create integrated teams with diverse perspectives.

### 4. Prioritize Ethical Considerations

Establish clear ethical guidelines for AI use, particularly regarding data privacy, algorithmic bias, and transparency. These considerations should be built into your implementation from the start.

### 5. Focus on Augmentation, Not Replacement

The most successful AI implementations augment human capabilities rather than replacing them. Look for opportunities to free employees from routine tasks so they can focus on higher-value interactions.

## The Future of AI in Customer Experience

Looking ahead, several emerging technologies are poised to further transform customer experience:

- **Emotion AI** that can detect and respond to subtle emotional signals
- **Immersive AI** blending augmented and virtual reality with intelligent assistance
- **Ambient intelligence** that provides seamless support across physical and digital environments
- **Federated learning** that enhances personalization while preserving privacy

## Conclusion: The Human-AI Partnership

As we've seen throughout our client engagements, the most powerful customer experiences emerge when AI and human intelligence work in harmony. While technology can process vast amounts of data and identify patterns beyond human capability, the emotional intelligence and creativity of human teams remain essential.

The future of customer experience isn't about choosing between technological efficiency and human connection—it's about leveraging AI to create deeper, more meaningful relationships between people and brands.

---

*Interested in exploring how AI can transform your customer experience? [Contact our team](/contact) for a consultation.*





================================================================================
File: _projects\case_study_1.md
================================================================================

---
layout: project
title: "Retail CX Transformation: Global Retail Chain"
description: "How we helped a major retailer reimagine their customer experience across digital and in-store touchpoints"
cover_image: /assets/images/portfolio/case-study-1.jpg
client: Global Retail Inc.
industry: Retail
duration: 8 months
tags: [Retail, Omnichannel, AI Implementation, Data Analytics]
---

# Retail CX Transformation: Reimagining the Customer Journey

## The Challenge

Global Retail Inc., a multinational retail chain with over 500 stores worldwide, was facing significant challenges in adapting to the rapidly evolving retail landscape:

- **Declining in-store traffic** and increasing competition from e-commerce platforms
- **Disconnected customer experiences** across online and offline channels
- **Limited customer insights** despite collecting vast amounts of data
- **Decreasing customer loyalty** and increasing acquisition costs
- **Operational inefficiencies** affecting customer satisfaction

The company needed a comprehensive transformation of its customer experience strategy to remain competitive in a digital-first retail environment while leveraging its physical store presence as a strategic advantage.

## Our Approach

We implemented a multi-phase approach to transform Global Retail's customer experience:

### 1. Discovery & Assessment

- Conducted extensive customer journey mapping across all touchpoints
- Analyzed existing customer data from multiple sources (POS, CRM, online behavior, loyalty program)
- Performed competitive analysis against industry leaders
- Identified key pain points and opportunities through customer interviews and surveys
- Assessed current technology stack and data infrastructure capabilities

### 2. Strategy Development

- Created a unified omnichannel CX strategy aligned with business objectives
- Designed personalized customer journeys based on segmentation analysis
- Developed a roadmap for digital transformation of in-store experiences
- Established data governance framework to ensure data quality and compliance
- Defined clear KPIs for measuring CX success

### 3. Implementation

- **Data Integration Platform**: Deployed a unified customer data platform integrating online and offline data sources
- **AI-Powered Personalization**: Implemented machine learning algorithms for real-time personalization across channels
- **Mobile App Enhancement**: Redesigned the mobile app with in-store navigation, scan-and-go, and personalized recommendations
- **Store Associate Empowerment**: Equipped store associates with clienteling tools linked to customer profiles
- **Loyalty Program Reimagination**: Transformed the loyalty program to offer personalized rewards based on individual preferences

### 4. Measurement & Optimization

- Established a real-time CX dashboard tracking key metrics
- Implemented A/B testing framework for continuous optimization
- Created feedback loops for iterative improvements
- Conducted regular CX audits to ensure consistent implementation
- Provided ongoing training and support for frontline employees

## The Results

After 8 months of implementation, Global Retail experienced significant improvements across key metrics:

![Results Dashboard](/assets/images/portfolio/case-study-1-results.jpg)

### Quantitative Impact

- **32% increase** in customer satisfaction scores (CSAT)
- **28% growth** in mobile app engagement 
- **45% improvement** in cross-channel purchase frequency
- **18% reduction** in customer acquisition costs
- **22% increase** in average transaction value
- **5.8x ROI** on CX technology investments within the first year

### Qualitative Outcomes

- Seamless experience across digital and physical touchpoints
- Improved employee satisfaction and reduced turnover
- Enhanced brand perception as an innovative retailer
- Stronger competitive positioning against pure e-commerce players
- Better decision-making based on comprehensive customer insights

## Key Insights

Through this transformation, we identified several critical factors for retail CX success:

1. **Data Integration is Foundational**: Breaking down data silos between online and offline channels is essential for a unified customer view.

2. **Employee Experience Drives Customer Experience**: Empowering store associates with the right tools and information directly impacts customer satisfaction.

3. **Personalization at Scale Requires AI**: Machine learning capabilities are necessary to deliver truly personalized experiences to millions of customers.

4. **Physical Stores Can Be a Competitive Advantage**: When integrated with digital capabilities, brick-and-mortar locations offer unique experiential opportunities.

5. **Continuous Measurement is Critical**: Real-time feedback and performance tracking enable agile adaptation to changing customer needs.

## Client Testimonial

> "Be-cGi's comprehensive approach to our CX transformation has fundamentally changed how we think about retail. They helped us turn our physical store footprint from what we feared was becoming a liability into our greatest asset in an omnichannel world. The results have exceeded our expectations, not just in customer metrics but in tangible business outcomes."
> 
> **John Smith**, Chief Customer Officer, Global Retail Inc.

## Next Steps

Following the success of this transformation, we're now working with Global Retail on:

- Expanding AI capabilities for predictive inventory management
- Implementing AR/VR experiences in flagship stores
- Developing a next-generation loyalty program leveraging blockchain technology
- Creating a customer-centric organizational structure

---

*Interested in transforming your customer experience? [Contact us](/contact) to discuss how we can help your organization.*




================================================================================
File: blog.md
================================================================================

---
layout: default
title: Blog - Be-cGi
---

<div class="hero-banner">
  <div class="banner-content">
    <h1>Blog</h1>
    <p class="tagline">Insights and perspectives on customer experience, data analytics, and AI</p>
  </div>
</div>

<div class="blog-filters">
  <div class="container">
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">All Topics</button>
      <button class="filter-btn" data-filter="cx">Customer Experience</button>
      <button class="filter-btn" data-filter="data">Data Analytics</button>
      <button class="filter-btn" data-filter="ai">Artificial Intelligence</button>
    </div>
    <div class="search-container">
      <input type="text" id="blog-search" class="search-input" placeholder="Search articles...">
      <i class="fas fa-search search-icon"></i>
    </div>
  </div>
</div>

<div class="posts-container">
  <div class="container">
    <div class="posts-grid">
      <article class="post-card" 
        data-category="ai"
        data-title="how ai is reshaping customer experience in 2025"
        data-tags="ai artificial intelligence customer experience cx trends technology"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-1.jpg" alt="Customer Experience Trends">
        </div>
        <div class="post-content">
          <span class="post-date">March 15, 2025</span>
          <h3><a href="/blog/2025/03/15/ai-insights">How AI is Reshaping Customer Experience in 2025</a></h3>
          <p>Discover the latest AI technologies that are transforming how businesses interact with their customers and creating more personalized, efficient, and meaningful experiences.</p>
          <div class="post-tags">
            <span class="tag">AI</span>
            <span class="tag">CX</span>
            <span class="tag">Technology</span>
          </div>
          <a href="/blog/2025/03/15/ai-insights" class="read-more">Read More</a>
        </div>
      </article>
      
      <article class="post-card"
        data-category="cx"
        data-title="building relational capital in a digital world"
        data-tags="relational capital customer experience cx strategy relationships"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-2.jpg" alt="Relational Capital">
        </div>
        <div class="post-content">
          <span class="post-date">March 10, 2025</span>
          <h3><a href="/blog/2025/03/10/relational-capital">Building Relational Capital in a Digital World</a></h3>
          <p>Learn strategies to build and leverage relational capital to drive business growth and customer loyalty in today's increasingly digital business environment.</p>
          <div class="post-tags">
            <span class="tag">Strategy</span>
            <span class="tag">CX</span>
            <span class="tag">Relationships</span>
          </div>
          <a href="/blog/2025/03/10/relational-capital" class="read-more">Read More</a>
        </div>
      </article>
      
      <article class="post-card"
        data-category="cx"
        data-title="5 critical elements of a successful cx strategy"
        data-tags="customer experience cx strategy business growth"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-3.jpg" alt="CX Strategy">
        </div>
        <div class="post-content">
          <span class="post-date">March 1, 2025</span>
          <h3><a href="/blog/2025/03/01/customer-experience">5 Critical Elements of a Successful CX Strategy</a></h3>
          <p>Explore the key components that make up an effective customer experience strategy for modern businesses and how to implement them for maximum impact.</p>
          <div class="post-tags">
            <span class="tag">Strategy</span>
            <span class="tag">CX</span>
            <span class="tag">Business</span>
          </div>
          <a href="/blog/2025/03/01/customer-experience" class="read-more">Read More</a>
        </div>
      </article>
      
      <article class="post-card"
        data-category="data"
        data-title="leveraging customer data for business growth"
        data-tags="data analytics business growth strategy"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-4.jpg" alt="Data Analytics">
        </div>
        <div class="post-content">
          <span class="post-date">February 15, 2025</span>
          <h3><a href="#">Leveraging Customer Data for Business Growth</a></h3>
          <p>Discover how to effectively collect, analyze, and utilize customer data to drive strategic decision-making and business growth in your organization.</p>
          <div class="post-tags">
            <span class="tag">Data</span>
            <span class="tag">Analytics</span>
            <span class="tag">Business</span>
          </div>
          <a href="#" class="read-more">Coming Soon</a>
        </div>
      </article>
      
      <article class="post-card"
        data-category="ai"
        data-title="implementing ai-powered customer service"
        data-tags="ai artificial intelligence customer service cx implementation"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-5.jpg" alt="AI Customer Service">
        </div>
        <div class="post-content">
          <span class="post-date">February 1, 2025</span>
          <h3><a href="#">Implementing AI-Powered Customer Service: A Step-by-Step Guide</a></h3>
          <p>A comprehensive guide to implementing AI solutions in your customer service operations, from chatbots to predictive analytics and personalization.</p>
          <div class="post-tags">
            <span class="tag">AI</span>
            <span class="tag">Implementation</span>
            <span class="tag">Service</span>
          </div>
          <a href="#" class="read-more">Coming Soon</a>
        </div>
      </article>
      
      <article class="post-card"
        data-category="data"
        data-title="measuring cx roi: metrics that matter"
        data-tags="roi metrics data analytics cx measurement"
      >
        <div class="post-image">
          <img src="/assets/images/blog/post-6.jpg" alt="CX Metrics">
        </div>
        <div class="post-content">
          <span class="post-date">January 20, 2025</span>
          <h3><a href="#">Measuring CX ROI: Metrics That Matter</a></h3>
          <p>Learn which customer experience metrics provide the most insight into ROI and how to effectively track and analyze them for business impact.</p>
          <div class="post-tags">
            <span class="tag">Metrics</span>
            <span class="tag">ROI</span>
            <span class="tag">Analytics</span>
          </div>
          <a href="#" class="read-more">Coming Soon</a>
        </div>
      </article>
    </div>
  </div>
</div>

<div class="pagination">
  <div class="container">
    <div class="pagination-links">
      <a href="#" class="pagination-link disabled"><i class="fas fa-chevron-left"></i> Previous</a>
      <a href="#" class="pagination-link active">1</a>
      <a href="#" class="pagination-link">2</a>
      <a href="#" class="pagination-link">3</a>
      <a href="#" class="pagination-link">Next <i class="fas fa-chevron-right"></i></a>
    </div>
  </div>
</div>

<div class="newsletter-signup">
  <div class="container">
    <div class="newsletter-content">
      <div class="newsletter-info">
        <h2>Subscribe to Our Newsletter</h2>
        <p>Stay updated with the latest insights and trends in customer experience, data analytics, and AI.</p>
      </div>
      <form class="newsletter-form">
        <div class="form-group">
          <input type="email" placeholder="Your email address" required class="form-input">
          <button type="submit" class="form-button">Subscribe</button>
        </div>
        <div class="form-disclaimer">
          <small>We respect your privacy. Your information will never be shared.</small>
        </div>
      </form>
    </div>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    // Filtrado por categorías
    const filterButtons = document.querySelectorAll('.filter-btn');
    const postCards = document.querySelectorAll('.post-card');
    const searchInput = document.getElementById('blog-search');
    
    function filterPosts() {
      const searchTerm = searchInput.value.toLowerCase().trim();
      const activeFilter = document.querySelector('.filter-btn.active').dataset.filter;
      
      postCards.forEach(card => {
        const postTitle = card.dataset.title;
        const postTags = card.dataset.tags;
        const postCategory = card.dataset.category;
        
        const matchesSearch = searchTerm === '' || 
                             postTitle.includes(searchTerm) || 
                             postTags.includes(searchTerm);
                             
        const matchesCategory = activeFilter === 'all' || postCategory === activeFilter;
        
        if (matchesSearch && matchesCategory) {
          card.style.display = 'block';
          setTimeout(() => {
            card.classList.add('fade-in');
          }, 100);
        } else {
          card.style.display = 'none';
          card.classList.remove('fade-in');
        }
      });
    }
    
    filterButtons.forEach(button => {
      button.addEventListener('click', function() {
        filterButtons.forEach(btn => btn.classList.remove('active'));
        this.classList.add('active');
        filterPosts();
      });
    });
    
    searchInput.addEventListener('input', filterPosts);
  });
</script>

<style>
  .blog-filters {
    margin-bottom: 3rem;
    padding: 1.5rem 0;
    border-bottom: 1px solid #e0e7f1;
  }
  
  .filter-buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  
  .search-container {
    position: relative;
    max-width: 500px;
    margin: 0 auto;
  }
  
  .search-input {
    width: 100%;
    padding: 0.8rem 1rem 0.8rem 2.5rem;
    border: 1px solid #e0e7f1;
    border-radius: 30px;
    font-size: 0.95rem;
    transition: all 0.3s ease;
  }
  
  .search-input:focus {
    outline: none;
    border-color: #26486e;
    box-shadow: 0 0 0 3px rgba(38, 72, 110, 0.1);
  }
  
  .search-icon {
    position: absolute;
    left: 1rem;
    top: 50%;
    transform: translateY(-50%);
    color: #666666;
  }
  
  .posts-container {
    margin-bottom: 4rem;
  }
  
  .pagination {
    margin-bottom: 4rem;
  }
  
  .pagination-links {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
  }
  
  .pagination-link {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem 1rem;
    border: 1px solid #e0e7f1;
    border-radius: 4px;
    color: #666666;
    font-size: 0.9rem;
    transition: all 0.3s ease;
  }
  
  .pagination-link:hover:not(.disabled) {
    background-color: rgba(38, 72, 110, 0.1);
    color: #26486e;
    border-color: #26486e;
  }
  
  .pagination-link.active {
    background-color: #26486e;
    color: white;
    border-color: #26486e;
  }
  
  .pagination-link.disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }
  
  .pagination-link i {
    font-size: 0.8rem;
    margin: 0 0.3rem;
  }
  
  .newsletter-signup {
    background-color: #f8f9fc;
    padding: 4rem 0;
  }
  
  .newsletter-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
  }
  
  .newsletter-info {
    flex: 1;
  }
  
  .newsletter-info h2 {
    font-size: 1.8rem;
    margin-bottom: 1rem;
    color: #1a1a1a;
  }
  
  .newsletter-info p {
    font-size: 1.1rem;
    color: #4a4a4a;
  }
  
  .newsletter-form {
    flex: 1;
  }
  
  .newsletter-form .form-group {
    display: flex;
    margin-bottom: 0.5rem;
  }
  
  .form-input {
    flex: 1;
    padding: 0.8rem 1rem;
    border: 1px solid #e0e7f1;
    border-right: none;
    border-radius: 4px 0 0 4px;
    font-size: 0.95rem;
  }
  
  .form-button {
    padding: 0 1.5rem;
    background-color: #26486e;
    color: white;
    border: 1px solid #26486e;
    border-radius: 0 4px 4px 0;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  .form-button:hover {
    background-color: #1c3a5e;
  }
  
  .form-disclaimer {
    color: #666666;
    font-size: 0.85rem;
  }
  
  @media (max-width: 768px) {
    .newsletter-content {
      flex-direction: column;
      text-align: center;
    }
    
    .newsletter-info {
      margin-bottom: 1.5rem;
    }
  }
</style>




================================================================================
File: contact.md
================================================================================

---
layout: default
title: Contact Us - Be-cGi
---

<div class="hero-banner">
  <div class="banner-content">
    <h1>Contact Us</h1>
    <p class="tagline">Let's discuss how we can help transform your customer experience</p>
  </div>
</div>

<div class="contact-section">
  <div class="container">
    <div class="contact-grid">
      <div class="contact-info">
        <h3>Get in Touch</h3>
        
        <div class="info-item">
          <i class="fas fa-map-marker-alt"></i>
          <div class="info-content">
            <h4>Office Location</h4>
            <p>123 Business Avenue, Suite 456<br>Panama City, Panama</p>
          </div>
        </div>
        
        <div class="info-item">
          <i class="fas fa-phone-alt"></i>
          <div class="info-content">
            <h4>Phone</h4>
            <p><a href="tel:+50761234567">+507 6123-4567</a></p>
          </div>
        </div>
        
        <div class="info-item">
          <i class="fas fa-envelope"></i>
          <div class="info-content">
            <h4>Email</h4>
            <p><a href="mailto:info@becgi.com">info@becgi.com</a></p>
          </div>
        </div>
        
        <div class="info-item">
          <i class="fas fa-clock"></i>
          <div class="info-content">
            <h4>Working Hours</h4>
            <p>Monday - Friday: 9:00 AM - 6:00 PM<br>Saturday - Sunday: Closed</p>
          </div>
        </div>
        
        <div class="social-links">
          <a href="https://linkedin.com/company/becgi-consulting" target="_blank"><i class="fab fa-linkedin"></i></a>
          <a href="https://twitter.com/BecGiConsulting" target="_blank"><i class="fab fa-twitter"></i></a>
          <a href="https://facebook.com/BecGiConsulting" target="_blank"><i class="fab fa-facebook"></i></a>
          <a href="https://instagram.com/becgi_consulting" target="_blank"><i class="fab fa-instagram"></i></a>
        </div>
      </div>
      
      <div class="contact-form">
        <h3>Send Us a Message</h3>
        <form id="contact-form" action="https://formspree.io/f/yourformid" method="POST">
          <div class="form-row">
            <div class="form-group">
              <label for="name">Your Name</label>
              <input type="text" id="name" name="name" required>
            </div>
            <div class="form-group">
              <label for="email">Your Email</label>
              <input type="email" id="email" name="email" required>
            </div>
          </div>
          
          <div class="form-group">
            <label for="subject">Subject</label>
            <input type="text" id="subject" name="subject" required>
          </div>
          
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="6" required></textarea>
          </div>
          
          <div class="form-group">
            <label class="checkbox-container">
              <input type="checkbox" required>
              <span class="checkmark"></span>
              I consent to Be-cGi collecting and storing my data from this form.
            </label>
          </div>
          
          <button type="submit" class="submit-btn">Send Message <i class="fas fa-paper-plane"></i></button>
        </form>
      </div>
    </div>
  </div>
</div>

<div class="map-section">
  <div class="container">
    <div class="map-container">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3941.5351125813686!2d-79.52997532584485!3d8.983190189708088!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8faca8f1fbe3d947%3A0xafd57ced9b4d5264!2sBusiness%20Park%20Panama!5e0!3m2!1sen!2spa!4v1710281234567!5m2!1sen!2spa" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
  </div>
</div>

<div class="faq-section">
  <div class="container">
    <h2 class="text-center">Frequently Asked Questions</h2>
    
    <div class="faq-container">
      <div class="faq-item">
        <div class="faq-question">
          <h4>What industries do you specialize in?</h4>
          <i class="fas fa-chevron-down"></i>
        </div>
        <div class="faq-answer">
          <p>We have extensive experience across retail, banking, telecommunications, healthcare, and hospitality industries. Our team brings industry-specific knowledge to each project, ensuring that our solutions address the unique challenges and opportunities in your sector.</p>
        </div>
      </div>
      
      <div class="faq-item">
        <div class="faq-question">
          <h4>How do you measure the success of your customer experience strategies?</h4>
          <i class="fas fa-chevron-down"></i>
        </div>
        <div class="faq-answer">
          <p>We establish clear KPIs at the beginning of each engagement, which typically include metrics such as Net Promoter Score (NPS), Customer Satisfaction (CSAT), Customer Effort Score (CES), retention rates, conversion rates, and ROI. We provide regular reporting on these metrics and adjust strategies as needed to ensure optimal results.</p>
        </div>
      </div>
      
      <div class="faq-item">
        <div class="faq-question">
          <h4>What is your approach to data privacy and security?</h4>
          <i class="fas fa-chevron-down"></i>
        </div>
        <div class="faq-answer">
          <p>We take data privacy and security very seriously. Our practices comply with global standards including GDPR and local regulations. We implement robust data protection measures, conduct regular security audits, and ensure that all client data is handled with the utmost care and confidentiality.</p>
        </div>
      </div>
      
      <div class="faq-item">
        <div class="faq-question">
          <h4>How long does a typical project take?</h4>
          <i class="fas fa-chevron-down"></i>
        </div>
        <div class="faq-answer">
          <p>Project timelines vary depending on the scope and complexity. A comprehensive CX transformation might take 6-12 months, while targeted interventions can be implemented in 2-3 months. During our initial consultation, we'll provide a detailed timeline based on your specific needs and objectives.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="cta-section">
  <div class="cta-content">
    <h2>Ready to Transform Your Customer Experience?</h2>
    <p>Contact us today to schedule a free consultation and discover how we can help your business grow through strategic customer experience management.</p>
    <a href="#contact-form" class="cta-btn">Get Started</a>
  </div>
</div>

<style>
  .map-section {
    padding: 4rem 0;
    background-color: #f8f9fc;
  }
  
  .map-container {
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
  }
  
  .faq-section {
    padding: 5rem 0;
  }
  
  .faq-container {
    max-width: 800px;
    margin: 3rem auto 0;
  }
  
  .faq-item {
    margin-bottom: 1.5rem;
    border: 1px solid #e0e7f1;
    border-radius: 8px;
    overflow: hidden;
  }
  
  .faq-question {
    padding: 1.5rem;
    background-color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  .faq-question:hover {
    background-color: rgba(38, 72, 110, 0.05);
  }
  
  .faq-question h4 {
    margin: 0;
    font-size: 1.1rem;
    color: #1a1a1a;
  }
  
  .faq-question i {
    color: #26486e;
    transition: all 0.3s ease;
  }
  
  .faq-answer {
    padding: 0 1.5rem;
    max-height: 0;
    overflow: hidden;
    transition: all 0.3s ease;
  }
  
  .faq-item.active .faq-question {
    background-color: rgba(38, 72, 110, 0.05);
  }
  
  .faq-item.active .faq-question i {
    transform: rotate(180deg);
  }
  
  .faq-item.active .faq-answer {
    padding: 1.5rem;
    max-height: 1000px;
  }
  
  .checkbox-container {
    display: flex;
    align-items: center;
    position: relative;
    padding-left: 35px;
    margin-bottom: 12px;
    cursor: pointer;
    font-size: 0.95rem;
    user-select: none;
  }
  
  .checkbox-container input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
  }
  
  .checkmark {
    position: absolute;
    top: 0;
    left: 0;
    height: 20px;
    width: 20px;
    background-color: #eee;
    border: 1px solid #ddd;
    border-radius: 3px;
  }
  
  .checkbox-container:hover input ~ .checkmark {
    background-color: #ccc;
  }
  
  .checkbox-container input:checked ~ .checkmark {
    background-color: #26486e;
    border-color: #26486e;
  }
  
  .checkmark:after {
    content: "";
    position: absolute;
    display: none;
  }
  
  .checkbox-container input:checked ~ .checkmark:after {
    display: block;
  }
  
  .checkbox-container .checkmark:after {
    left: 7px;
    top: 3px;
    width: 5px;
    height: 10px;
    border: solid white;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    // FAQ accordion
    const faqItems = document.querySelectorAll('.faq-item');
    
    faqItems.forEach(item => {
      const question = item.querySelector('.faq-question');
      
      question.addEventListener('click', function() {
        // Toggle active class on clicked item
        item.classList.toggle('active');
        
        // Close other items
        faqItems.forEach(otherItem => {
          if (otherItem !== item) {
            otherItem.classList.remove('active');
          }
        });
      });
    });
    
    // Form submission handling
    const contactForm = document.getElementById('contact-form');
    
    if (contactForm) {
      contactForm.addEventListener('submit', function(e) {
        const submitButton = this.querySelector('.submit-btn');
        submitButton.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Sending...';
        submitButton.disabled = true;
      });
    }
    
    // Smooth scroll to form when Get Started is clicked
    const ctaButton = document.querySelector('.cta-btn');
    if (ctaButton && ctaButton.getAttribute('href') === '#contact-form') {
      ctaButton.addEventListener('click', function(e) {
        e.preventDefault();
        const formElement = document.getElementById('contact-form');
        if (formElement) {
          formElement.scrollIntoView({ behavior: 'smooth' });
          setTimeout(() => {
            formElement.querySelector('input').focus();
          }, 800);
        }
      });
    }
  });
</script>




================================================================================
File: index.md
================================================================================

---
layout: default
title: Be-cGi - Customer Experience Consulting
permalink: /
---

<div class="hero-banner">
  <div class="banner-content">
    <h1>Be-cGi</h1>
    <h2 class="headline">Customer Experience Experts</h2>
    <p class="tagline">"A través del capital relacional aumentamos el capital económico de las organizaciones"</p>
  </div>
</div>

<div class="services-section">
  <div class="container">
    <h2 class="text-center">Our Services</h2>
    <div class="services-grid">
      <div class="service-card">
        <i class="fas fa-users"></i>
        <h3>Customer Experience Strategy</h3>
        <p>We design comprehensive strategies that transform how your customers interact with your brand, increasing loyalty and driving business growth.</p>
      </div>
      <div class="service-card">
        <i class="fas fa-chart-line"></i>
        <h3>Data Analysis & Insights</h3>
        <p>Convert your customer data into actionable insights that drive strategic decision-making and measurable business outcomes.</p>
      </div>
      <div class="service-card">
        <i class="fas fa-robot"></i>
        <h3>AI-Driven Solutions</h3>
        <p>Leverage artificial intelligence to enhance customer interactions, predict behavior, and deliver personalized experiences at scale.</p>
      </div>
    </div>
  </div>
</div>

<div class="clients-section">
  <div class="container">
    <h2 class="text-center">Trusted By</h2>
    <div class="clients-grid">
      <img src="/assets/images/clients/client-logo-1.png" alt="Client 1" class="client-logo">
      <img src="/assets/images/clients/client-logo-2.png" alt="Client 2" class="client-logo">
      <img src="/assets/images/clients/client-logo-3.png" alt="Client 3" class="client-logo">
      <img src="/assets/images/clients/client-logo-4.png" alt="Client 4" class="client-logo">
      <img src="/assets/images/clients/client-logo-5.png" alt="Client 5" class="client-logo">
    </div>
  </div>
</div>

<div class="testimonials-section">
  <div class="container">
    <h2 class="text-center">What Our Clients Say</h2>
    <div class="testimonials-slider">
      <div class="testimonial-card">
        <div class="testimonial-content">
          "Be-cGi transformed our customer experience strategy. Their data-driven approach and AI solutions helped us increase customer retention by 35% in just six months."
        </div>
        <div class="testimonial-author">
          <img src="/assets/images/team/testimonial-1.jpg" alt="John Smith" class="author-image">
          <div class="author-info">
            <h4>John Smith</h4>
            <p>CEO, Global Retail Inc.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="portfolio-section">
  <div class="container">
    <h2 class="text-center">Featured Case Studies</h2>
    <div class="portfolio-grid">
      <div class="portfolio-item">
        <img src="/assets/images/portfolio/case-study-1.jpg" alt="Retail CX Transformation">
        <div class="portfolio-overlay">
          <h3>Retail CX Transformation</h3>
          <p>How we helped a major retailer reimagine their customer experience</p>
          <a href="/portfolio/case_study_1" class="btn">Read Case Study</a>
        </div>
      </div>
      <div class="portfolio-item">
        <img src="/assets/images/portfolio/case-study-2.jpg" alt="Banking Customer Journey">
        <div class="portfolio-overlay">
          <h3>Banking Customer Journey</h3>
          <p>Creating seamless digital experiences for banking customers</p>
          <a href="/portfolio/case_study_2" class="btn">Read Case Study</a>
        </div>
      </div>
      <div class="portfolio-item">
        <img src="/assets/images/portfolio/case-study-3.jpg" alt="Telecom AI Implementation">
        <div class="portfolio-overlay">
          <h3>Telecom AI Implementation</h3>
          <p>Reducing churn with predictive AI solutions</p>
          <a href="/portfolio/case_study_3" class="btn">Read Case Study</a>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="blog-section">
  <div class="container">
    <h2 class="text-center">Latest Insights</h2>
    <div class="posts-grid">
      <div class="post-card">
        <div class="post-image">
          <img src="/assets/images/blog/post-1.jpg" alt="Customer Experience Trends">
        </div>
        <div class="post-content">
          <span class="post-date">March 15, 2025</span>
          <h3><a href="/blog/2025/03/15/ai-insights">How AI is Reshaping Customer Experience in 2025</a></h3>
          <p>Discover the latest AI technologies that are transforming how businesses interact with their customers.</p>
          <a href="/blog/2025/03/15/ai-insights" class="read-more">Read More</a>
        </div>
      </div>
      <div class="post-card">
        <div class="post-image">
          <img src="/assets/images/blog/post-2.jpg" alt="Relational Capital">
        </div>
        <div class="post-content">
          <span class="post-date">March 10, 2025</span>
          <h3><a href="/blog/2025/03/10/relational-capital">Building Relational Capital in a Digital World</a></h3>
          <p>Learn strategies to build and leverage relational capital to drive business growth and customer loyalty.</p>
          <a href="/blog/2025/03/10/relational-capital" class="read-more">Read More</a>
        </div>
      </div>
      <div class="post-card">
        <div class="post-image">
          <img src="/assets/images/blog/post-3.jpg" alt="CX Strategy">
        </div>
        <div class="post-content">
          <span class="post-date">March 1, 2025</span>
          <h3><a href="/blog/2025/03/01/customer-experience">5 Critical Elements of a Successful CX Strategy</a></h3>
          <p>Explore the key components that make up an effective customer experience strategy for modern businesses.</p>
          <a href="/blog/2025/03/01/customer-experience" class="read-more">Read More</a>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="cta-section">
  <div class="cta-content">
    <h2>Ready to Transform Your Customer Experience?</h2>
    <p>Let's discuss how we can help you leverage data and AI to create meaningful connections with your customers.</p>
    <a href="/contact" class="cta-btn">Get in Touch</a>
  </div>
</div>




================================================================================
File: portfolio.md
================================================================================

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
        <img src="/assets/images/portfolio/case-study-1.jpg" alt="Retail CX Transformation">
        <div class="portfolio-overlay">
          <h3>Retail CX Transformation</h3>
          <p>How we helped a major retailer reimagine their customer experience</p>
          <a href="/portfolio/case_study_1" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="banking">
        <img src="/assets/images/portfolio/case-study-2.jpg" alt="Banking Customer Journey">
        <div class="portfolio-overlay">
          <h3>Banking Customer Journey</h3>
          <p>Creating seamless digital experiences for banking customers</p>
          <a href="/portfolio/case_study_2" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="telecom">
        <img src="/assets/images/portfolio/case-study-3.jpg" alt="Telecom AI Implementation">
        <div class="portfolio-overlay">
          <h3>Telecom AI Implementation</h3>
          <p>Reducing churn with predictive AI solutions</p>
          <a href="/portfolio/case_study_3" class="btn">Read Case Study</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="retail">
        <img src="/assets/images/portfolio/case-study-4.jpg" alt="Retail Loyalty Program">
        <div class="portfolio-overlay">
          <h3>Retail Loyalty Program</h3>
          <p>Designing a data-driven loyalty program that increased repeat purchases by 45%</p>
          <a href="#" class="btn">Coming Soon</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="banking">
        <img src="/assets/images/portfolio/case-study-5.jpg" alt="Digital Banking Transformation">
        <div class="portfolio-overlay">
          <h3>Digital Banking Transformation</h3>
          <p>Revamping the mobile banking experience for a leading financial institution</p>
          <a href="#" class="btn">Coming Soon</a>
        </div>
      </div>
      
      <div class="portfolio-item" data-category="telecom">
        <img src="/assets/images/portfolio/case-study-6.jpg" alt="Telecom Customer Service">
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
          <img src="/assets/images/team/testimonial-1.jpg" alt="John Smith" class="author-image">
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
    <a href="/contact" class="cta-btn">Contact Us</a>
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




================================================================================
File: readme.md
================================================================================

# Be-cGi Website

A professional website for Be-cGi Consulting, specializing in Customer Experience, Data Analytics, and AI solutions. This website is built with Jekyll and hosted on GitHub Pages.

## Site Structure

```
becgi-website/
├── .gitignore
├── Gemfile
├── Gemfile.lock
├── _config.yml
├── _layouts/
│   ├── default.html
│   ├── post.html
│   └── project.html
├── _posts/
│   ├── 2025-03-15-ai-insights.md
│   └── more blog posts...
├── _projects/
│   ├── case_study_1.md
│   └── more case studies...
├── assets/
│   ├── css/
│   │   └── style.scss
│   ├── docs/
│   │   └── files...
│   └── images/
│       ├── logo.png
│       ├── favicon.png
│       ├── team/
│       ├── clients/
│       ├── blog/
│       └── portfolio/
├── index.md
├── portfolio.md
├── blog.md
├── team.md
├── contact.md
└── README.md
```

## Local Development Setup

### Prerequisites
- Ruby (with devkit for Windows users)
- Bundler
- Jekyll

### Installation Steps

1. Clone this repository:
```bash
git clone https://github.com/GalacticaSystem/becgi-web.git
cd becgi-web
```

2. Install dependencies:
```bash
bundle install
```

3. Start the local development server:
```bash
bundle exec jekyll serve
```

4. Access the local site:
   - Open your browser and go to `http://localhost:4000/becgi-web/`
   - Note: The `/becgi-web/` path is necessary because the site is configured to be hosted at `GalacticaSystem.github.io/becgi-web`

## Customizing the Site

### Content Updates

#### Blog Posts
To add a new blog post, create a new Markdown file in the `_posts/` directory with the filename format: `YYYY-MM-DD-title.md`. Include the following front matter:

```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD
cover_image: /assets/images/blog/your-image.jpg
tags: [Tag1, Tag2, Tag3]
reading_time: X
---

Your content here...
```

#### Portfolio/Case Studies
To add a new case study, create a new Markdown file in the `_projects/` directory. Include the following front matter:

```yaml
---
layout: project
title: "Case Study Title"
description: "Brief description of the case study"
cover_image: /assets/images/portfolio/image.jpg
client: Client Name
industry: Industry Name
duration: X months
tags: [Tag1, Tag2, Tag3]
---

Your content here...
```

### Images and Assets
- Place blog post images in `/assets/images/blog/`
- Place portfolio/case study images in `/assets/images/portfolio/`
- Place team member photos in `/assets/images/team/`
- Place client logos in `/assets/images/clients/`

### Styling
The main styling is in `/assets/css/style.scss`. This file uses SCSS syntax for styling the site.

## GitHub Pages Deployment

The site is configured to be automatically deployed to GitHub Pages when changes are pushed to the main branch.

### Deployment URL
Once deployed, the site will be available at: `https://galacticasystem.github.io/becgi-web/`

## Development Notes

- The site uses Jekyll's collection feature for organizing blog posts and case studies
- FontAwesome is used for icons
- The site is fully responsive with mobile-friendly design

## Contributing

1. Create a new branch for your changes
2. Make your modifications
3. Test your changes locally
4. Submit a pull request to the main branch

## License

This project is proprietary and all rights are reserved to Be-cGi Consulting.




================================================================================
File: team.md
================================================================================

---
layout: default
title: Our Team - Be-cGi
---

<div class="hero-banner">
  <div class="banner-content">
    <h1>Our Team</h1>
    <p class="tagline">Meet the experts behind our innovative customer experience solutions</p>
  </div>
</div>

<div class="team-section">
  <div class="container">
    <h2 class="text-center">Leadership Team</h2>
    <p class="section-intro text-center">Our leadership team brings together decades of experience in customer experience, data analytics, and AI implementation across diverse industries.</p>
    
    <div class="team-grid">
      <div class="team-card">
        <img src="/assets/images/team/team-member-1.jpg" alt="María Rodriguez" class="team-image">
        <h3 class="team-name">María Rodriguez</h3>
        <p class="team-position">CEO & Founder</p>
        <p class="team-bio">With over 20 years of experience in customer experience strategy, María has led transformative CX initiatives for Fortune 500 companies across retail, banking, and telecommunications.</p>
        <div class="social-links">
          <a href="#" target="_blank"><i class="fab fa-linkedin"></i></a>
          <a href="#" target="_blank"><i class="fab fa-twitter"></i></a>
        </div>
      </div>
      
      <div class="team-card">
        <img src="/assets/images/team/team-member-2.jpg" alt="Carlos Mendoza" class="team-image">
        <h3 class="team-name">Carlos Mendoza</h3>
        <p class="team-position">Chief Data Officer</p>
        <p class="team-bio">Carlos specializes in translating complex data into actionable business insights. His background includes leading data science teams at major technology companies and consulting firms.</p>
        <div class="social-links">
          <a href="#" target="_blank"><i class="fab fa-linkedin"></i></a>
          <a href="#" target="_blank"><i class="fab fa-twitter"></i></a>
        </div>
      </div>
      
      <div class="team-card">
        <img src="/assets/images/team/team-member-3.jpg" alt="Sofia Pérez" class="team-image">
        <h3 class="team-name">Sofia Pérez</h3>
        <p class="team-position">Head of AI Solutions</p>
        <p class="team-bio">Sofia leads our AI implementation team, bringing cutting-edge machine learning and natural language processing solutions to enhance customer experiences for our clients.</p>
        <div class="social-links">
          <a href="#" target="_blank"><i class="fab fa-linkedin"></i></a>
          <a href="#" target="_blank"><i class="fab fa-twitter"></i></a>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="values-section">
  <div class="container">
    <h2 class="text-center">Our Values</h2>
    
    <div class="values-grid">
      <div class="value-card">
        <i class="fas fa-handshake"></i>
        <h3>Relational Focus</h3>
        <p>We believe in the power of relationships. Our work begins and ends with understanding the connections between people, brands, and experiences.</p>
      </div>
      
      <div class="value-card">
        <i class="fas fa-chart-pie"></i>
        <h3>Data-Driven Decisions</h3>
        <p>We let data guide our recommendations while maintaining a human-centered approach to customer experience design.</p>
      </div>
      
      <div class="value-card">
        <i class="fas fa-lightbulb"></i>
        <h3>Innovative Solutions</h3>
        <p>We constantly push boundaries, exploring new technologies and methodologies to solve complex customer experience challenges.</p>
      </div>
      
      <div class="value-card">
        <i class="fas fa-users"></i>
        <h3>Collaborative Approach</h3>
        <p>We work as an extension of your team, ensuring knowledge transfer and sustainable results that last beyond our engagement.</p>
      </div>
    </div>
  </div>
</div>

<div class="principles-section">
  <div class="container">
    <h2 class="text-center">Guiding Principles</h2>
    
    <div class="principles-grid">
      <div class="principle-item">
        <h3><span>01</span> Asertividad</h3>
        <p>Adaptar nuestra comunicación al contexto y a las personas, manteniendo siempre transparencia, coherencia, respeto y autenticidad, y asegurando claridad en nuestras decisiones y acciones.</p>
      </div>
      
      <div class="principle-item">
        <h3><span>02</span> Capital Relacional</h3>
        <p>A través del capital relacional aumentamos el capital económico de las organizaciones, creando conexiones significativas que generan valor duradero.</p>
      </div>
      
      <div class="principle-item">
        <h3><span>03</span> Transparencia</h3>
        <p>Operamos con transparencia y coherencia en todas nuestras decisiones y acciones, comunicando la verdad con claridad y en el momento oportuno.</p>
      </div>
    </div>
  </div>
</div>

<div class="join-team-section">
  <div class="container">
    <div class="join-team-content">
      <div class="join-team-text">
        <h2>Join Our Team</h2>
        <p>We're always looking for talented professionals who are passionate about customer experience, data analytics, and AI. If you're interested in joining our team, check out our current openings or send us your resume.</p>
        <a href="/contact" class="btn">View Opportunities</a>
      </div>
      <div class="join-team-image">
        <img src="/assets/images/team/team-working.jpg" alt="Team working together">
      </div>
    </div>
  </div>
</div>

<div class="cta-section">
  <div class="cta-content">
    <h2>Ready to Work With Our Team?</h2>
    <p>Let's discuss how our experts can help you transform your customer experience strategy.</p>
    <a href="/contact" class="cta-btn">Contact Us</a>
  </div>
</div>

<style>
  .values-section {
    padding: 5rem 0;
    background-color: #f8f9fc;
  }
  
  .values-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2rem;
    margin-top: 3rem;
  }
  
  .value-card {
    text-align: center;
    padding: 2rem;
    background: white;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
    transition: all 0.3s ease;
  }
  
  .value-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.1);
  }
  
  .value-card i {
    font-size: 3rem;
    color: #26486e;
    margin-bottom: 1.5rem;
  }
  
  .value-card h3 {
    margin-bottom: 1rem;
    font-size: 1.3rem;
    color: #1a1a1a;
  }
  
  .value-card p {
    font-size: 0.95rem;
    color: #4a4a4a;
  }
  
  .principles-section {
    padding: 5rem 0;
  }
  
  .principles-grid {
    margin-top: 3rem;
  }
  
  .principle-item {
    padding: 2rem 0;
    border-bottom: 1px solid #e0e7f1;
  }
  
  .principle-item:last-child {
    border-bottom: none;
  }
  
  .principle-item h3 {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
    font-size: 1.5rem;
    color: #1a1a1a;
  }
  
  .principle-item h3 span {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: #26486e;
    color: white;
    border-radius: 50%;
    margin-right: 1rem;
    font-size: 1.2rem;
    font-weight: 600;
  }
  
  .principle-item p {
    font-size: 1.1rem;
    color: #4a4a4a;
    line-height: 1.6;
    padding-left: calc(50px + 1rem);
  }
  
  .join-team-section {
    padding: 5rem 0;
    background-color: #f8f9fc;
  }
  
  .join-team-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
  }
  
  .join-team-text h2 {
    margin-bottom: 1.5rem;
    font-size: 2rem;
    color: #1a1a1a;
  }
  
  .join-team-text p {
    margin-bottom: 2rem;
    font-size: 1.1rem;
    color: #4a4a4a;
    line-height: 1.6;
  }
  
  .join-team-text .btn {
    display: inline-block;
    padding: 0.8rem 2rem;
    background-color: #26486e;
    color: white;
    border-radius: 4px;
    font-weight: 500;
    transition: all 0.3s ease;
  }
  
  .join-team-text .btn:hover {
    background-color: #1c3a5e;
    transform: translateY(-3px);
  }
  
  .join-team-image img {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.1);
  }
  
  @media (max-width: 1024px) {
    .values-grid {
      grid-template-columns: repeat(2, 1fr);
    }
    
    .join-team-content {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
    
    .join-team-text {
      order: 2;
    }
    
    .join-team-image {
      order: 1;
    }
  }
  
  @media (max-width: 768px) {
    .values-grid {
      grid-template-columns: 1fr;
    }
    
    .principle-item h3 {
      flex-direction: column;
      align-items: flex-start;
    }
    
    .principle-item h3 span {
      margin-bottom: 1rem;
    }
    
    .principle-item p {
      padding-left: 0;
    }
  }
</style>


