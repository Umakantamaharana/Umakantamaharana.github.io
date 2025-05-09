# Umakanta Maharana's Website

This repository hosts the personal website of Umakanta Maharana, built using the **al-folio** Jekyll theme. The website showcases research, projects, teaching, and other professional activities.

## Features

### Light/Dark Mode

The website supports a built-in light/dark mode. It detects the user's preferred color scheme and automatically switches to it. Users can also manually toggle between light and dark modes.

### Courses

The `/courses/` page provides an overview of courses taught, combining programming fundamentals and applied data science. The page embeds an external Notion page for detailed course content.

### Projects

The `/projects/` page highlights various projects, categorized into "work," "fun," and "funded." Each project has a dedicated page with a flexible 3-column grid format for showcasing images and descriptions.

### Publications

The `/publications/` page is automatically generated from a BibTeX bibliography file located in `_bibliography/papers.bib`. It includes additional metadata like PDFs, DOIs, and links to related resources.

### Blog

The `/blog/` page features posts on various topics, including formatting, diagrams, and code examples. Posts support advanced features like tabs, citations, and interactive plots.

### CV

The `/cv/` page provides a downloadable PDF of the CV and a web-based version generated from a JSON or YAML file.

### Teaching

The `/teaching/` page lists courses taught, such as "Introduction to Data Science" and "Python Programming," with key topics and tools like Matplotlib, Seaborn, and supervised learning basics.

### People

The `/people/` page showcases members of the lab or group, with profile pictures, short bios, and contact information.

### Custom Domain

The website supports custom domains. To configure this, add a `CNAME` file with the domain name to the repository.

## Installation and Deployment

### Local Setup

The repository supports local development using Docker and Development Containers. To set up locally:

1. Install [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/).
2. Run:
   ```bash
   docker compose pull
   docker compose up
   ```
