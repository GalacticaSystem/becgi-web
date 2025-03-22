# Be-cGi Consulting Website

A professional website for Be-cGi, a customer experience consulting firm specializing in leveraging data and AI to improve business relationships and economic outcomes.

## About This Site

This website was created using Jekyll and is designed to be hosted on GitHub Pages. It features sections for:

- Company overview and services
- Portfolio/case studies
- Blog posts about CX, AI, and data analytics
- Team members information
- Contact form

## Development Environment Setup

### Prerequisites
- Ruby (with devkit for Windows users)
- Jekyll
- Bundler

### Installation

1. Clone this repository:
```bash
git clone https://github.com/GalacticaSystem/becgi-web.git
cd becgi-web
```

2. Install dependencies:
```bash
bundle install
```

3. Run the development server:
```bash
bundle exec jekyll serve
```

4. View the site at: http://localhost:4000/becgi-web/

## Site Structure

```
becgi-website/
├── _layouts/               # HTML templates
├── _posts/                 # Blog posts in markdown
├── _projects/              # Case studies in markdown
├── assets/                 # Static files
│   ├── css/
│   ├── docs/
│   └── images/
├── blog.md                 # Blog listing page
├── contact.md              # Contact page
├── index.md                # Homepage
├── portfolio.md            # Portfolio listing page
└── team.md                 # Team page
```

## Contributing

1. This site is based on Jekyll and uses Liquid templating
2. All paths should include `{{ site.baseurl }}` prefix since this is hosted at a subdirectory on GitHub Pages
3. CSS is implemented using Sass (SCSS)
4. Images should be placed in the appropriate subdirectories under assets/images/

## Deployment

The site is configured to be automatically deployed to GitHub Pages when changes are pushed to the main branch of the repository.

## License

This website and its content are property of Be-cGi Consulting.

## Technical Notes

- The site uses Jekyll collections for projects and blog posts
- The design is based on the company's branding guidelines
- The site is fully responsive for mobile and desktop viewing
