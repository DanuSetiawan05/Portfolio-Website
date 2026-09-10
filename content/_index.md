---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-01-05
type: landing

sections:
  # Developer Hero - Gradient background with name, role, social, and CTAs
  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I create"
        strings:
            - "smart data-driven solutions"
            - "models that learn and predict"
            - "insights that actually matter"
            - "clean and functional web apps"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#fafafa"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]
  
  # Filterable Portfolio - Alpine.js powered project filtering
  - block: portfolio
    id: projects
    content:
      title: "Featured Projects"
      subtitle: "A selection of my recent work"
      count: 0
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: Data Science
          tag: Data Science
        - name: Data Analysis
          tag: Data Analysis
        - name: Web Development
          tag: Web Development
        - name: Other Projects
          tag: Other Projects
      default_button_index: 0
      # Archive link auto-shown if more projects exist than 'count' above
      # archive:
      #   enable: false  # Set to false to explicitly hide
      #   text: "Browse All"  # Customize text
      #   link: "/work/"  # Custom URL
    design:
      columns: 3
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Visual Tech Stack - Icons organized by category
  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I use to build things"
      categories:
        - name: Languages
          items:
            - name: C++
              icon: devicon/cplusplus
            - name: Python
              icon: devicon/python
            - name: SQL
              icon: custom/sql
            - name: PHP
              icon: devicon/php
        - name: Data Science & Data Analysis
          items:
            - name: Pandas
              icon: devicon/pandas
            - name: NumPy
              icon: devicon/numpy
            - name: Scikit-Learn
              icon: devicon/scikitlearn
            - name: Jupyter
              icon: devicon/jupyter
            - name: Power BI
              icon: custom/powerbi
        - name: Web Development
          items:
            - name: HTML
              icon: custom/html
            - name: CSS
              icon: custom/css
            - name: Laravel
              icon: devicon/laravel
            - name: Bootstrap
              icon: devicon/bootstrap
            - name: Hugo
              icon: devicon/hugo
            - name: Vercel
              icon: devicon/vercel
        - name: Databases & Tools
          items:
            - name: Mysql
              icon: devicon/mysql
            - name: SQLite
              icon: devicon/sqlite
            - name: Git
              icon: devicon/git
            - name: GitHub
              icon: devicon/github
            - name: Figma
              icon: devicon/figma
            - name: Blender
              icon: devicon/blender
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Experience Timeline
  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: ''
      items:
        - title: Laravel Developer
          company: Winnicode Garuda Teknologi
          company_url: ''
          company_logo: ''
          location: West Java, Indonesia
          date_start: '2025-03-17'
          date_end: '2025-07-17'
          description: |2-
            * Designed and developed a full-stack Employee Attendance Management System using Laravel and MySQL, architecting a dual-role structure with dedicated authentication and access control for Employee and Admin users.. 
            * Built real-time attendance tracking, a leave request module with an approval workflow, and an admin dashboard with 
            attendance data visualizations, giving management clear visibility into workforce activity. 
            * Automated PDF export for daily and monthly attendance reports, streamlining a previously manual reporting process  
            * Managed end-to-end CRUD operations across employee, attendance, and leave data, and collaborated closely with a 
            mentor on debugging, testing, and performance optimization to deliver a stable, production-ready application. 
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Recent Blog Posts
  - block: collection
    id: certifications
    content:
      title: Certifications 
      subtitle: 'My professional credentials and achievements'
      text: ''
      filters:
        folders:
          - certifications
        exclude_featured: false
      count: 3
      order: asc
    design:
      view: article-grid
      columns: 3
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Contact Section
  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's build something amazing together"
      text: |-
        I'm always interested in hearing about new projects and opportunities.
        Whether you're looking to hire, collaborate, or just want to say hi, feel free to reach out!
      email: danumuhammad085@gmail.com
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # CTA Card
  - block: cta-card
    content:
      title: "Open to Opportunities"
      text: |-
        I'm currently looking for **Data Scientist Intern** or **Data Analyst Intern** roles.
        
        Let's connect and discuss how I can help your team.
      button:
        text: 'Download Resume'
        url: "/uploads/resume-Muhammad-Danu-Setiawan.pdf"
        new_tab: true
    design:
      card:
        # Light mode: soft pastel theme gradient | Dark mode: rich deep gradient
        css_class: 'bg-gradient-to-br from-primary-200 via-primary-100 to-secondary-200 dark:from-primary-600 dark:via-primary-700 dark:to-secondary-700'
        text_color: dark
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "6rem", "0"]
---
