# Academic Personal Website

### Showcase your research and academic work

This repository gives you the code you'll need to kickstart a professional academic website that showcases your research, publications, teaching, and scholarly contributions. When managed in a GitHub repository, it automatically renders a webpage with your profile information, publications, teaching experience, and research projects.

**Enhanced for Academia**: This version includes specialized features for researchers, including:
- 📚 Publications management with DOI, arXiv, and PDF links
- 🎓 Teaching experience showcase
- 🔬 Research project highlights
- 📊 Academic social media integration (Google Scholar, ORCID, ResearchGate)
- 📝 Enhanced blog posts with abstract, keywords, and citation metadata
- 🎨 Professional typography optimized for academic content
- ✨ Smooth animations and modern design
- 📱 Fully responsive design for all devices
- 🔍 Enhanced SEO with Schema.org structured data

It's all possible using the combination of [Jekyll](https://jekyllrb.com/docs/) (for building your website), [GitHub Pages](https://pages.github.com/) (for hosting your website), and [GitHub's API](https://developer.github.com/v3/) (for automatically populating your website with content).

![](https://user-images.githubusercontent.com/221550/110506678-51906280-80cd-11eb-803a-c41984bd9312.png)

## Installation

### Fork the `github/personal-website` repo

You'll be making your own copy of the "personal website starter" repository so you have your own project to customize. A "fork" is a copy of a repository. So select "Fork" atop [the `github/personal-website` repository](https://github.com/github/personal-website).

Once you've found a home for your forked repository, it's yours. You're the owner, so you're ready to publish, if you wish.

### Install in your local development environment

If you want to manage your website in a local web development environment, you'll be using [Ruby](https://jekyllrb.com/docs/installation/).

Once you've found a home for your forked repository, **[clone it](https://help.github.com/articles/cloning-a-repository/)**.

#### Install Jekyll

Jekyll is a [Ruby Gem](https://jekyllrb.com/docs/ruby-101/#gems) that can be installed on most systems.

1. Install a full [Ruby development environment](https://jekyllrb.com/docs/installation/)
2. Install Jekyll and [bundler](https://jekyllrb.com/docs/ruby-101/#bundler) [gems](https://jekyllrb.com/docs/ruby-101/#gems)
```
gem install jekyll bundler
```
3. Change into your new directory
```
cd personal-website
```
4. Install missing gems
```
bundle install
```
5. Build the site and make it available on a local server
```
bundle exec jekyll serve
```

You should see something like:

```
Configuration file: /octocat/personal-website/_config.yml
            Source: /octocat/personal-website
       Destination: /octocat/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
                    done in 14.729 seconds.
 Auto-regeneration: enabled for '/octocat/personal-website'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```

Don't worry about the "No GitHub API authentication could be found" message. [API authentication is only necessary](https://github.com/jekyll/github-metadata/blob/master/docs/authentication.md) if you intend to display more detailed metadata, like a branch name.

6. Now browse to [http://localhost:4000](http://localhost:4000)

### Publish

When you host your personal website's code on GitHub, you get the support of free hosting through GitHub Pages.

**The fastest approach** is to rename your repository `username.github.io`, where `username` is your GitHub username (or organization name). Then, the next time you push any changes to your repository's `master` branch, they'll be accessible on the web at your `username.github.io` address.

**If you want to use a custom domain**, you'll want to add it to your repository's "Custom domain" settings on github.com. And then register and/or [configure your domain with a DNS provider](https://help.github.com/articles/quick-start-setting-up-a-custom-domain/).

## Customization

It's your website, and you control the source code. So you can customize everything, if you like. But we've provided a handful of quick customizations for you to consider as you get your website off the ground.

### Quick configuration changes

Most customizations can be done in a matter of seconds, by revising your repository's `_config.yml` file. Just remember to restart your local server each time you save new changes so your Jekyll-powered website rebuilds correctly:

1. Shut down your server by entering the keyboard command <kbd>CTRL</kbd>+<kbd>c</kbd>
2. Restart your server: `bundle exec jekyll serve`


#### Layout

Your website will display in a two-column layout by default on larger-screen devices, with your photo, name, and basic information displayed in a left-aligned "sidebar." You can quickly switch to a "stacked" single-column layout by changing the line in your `_config.yml` file that reads `layout: sidebar` to `layout: stacked`.

#### Style

Your website appears with a "light" white and gray background by default, with dark text. You can quickly switch to a "dark" background with white text by changing the line in your `_config.yml` file that reads `style: light` to `style: dark`.

#### Research Projects

The "Research Projects" section displays your GitHub repositories, highlighting your open-source research software and tools. By default, it shows your nine most recently updated repositories, excluding forks. Customize these settings in `_config.yml`:

```yaml
projects:
  sort_by: pushed  # Options: pushed, stars
  limit: 9
  exclude:
    forks: true
    projects:
      # - repo-name  # List specific repos to exclude
```

#### Publications

Add your academic publications to showcase your research contributions. In `_config.yml`, uncomment and configure the publications section:

```yaml
publications:
  - title: "Your Paper Title Here"
    authors: "Author1, Author2, Author3"
    venue: "Conference/Journal Name"
    year: 2024
    url: https://doi.org/your-doi
    doi: 10.1234/example.doi
    arxiv: 2401.12345
    pdf: /path/to/paper.pdf
    abstract: "Brief description of your research paper..."
```

Each publication card displays:
- Paper title (linked to DOI/URL if provided)
- Author list
- Venue and year
- Abstract (optional)
- Quick links to DOI, arXiv, and PDF

#### Teaching Experience

Showcase your teaching and mentoring activities:

```yaml
teaching:
  - title: "Course Name"
    role: "Teaching Assistant / Instructor / Lecturer"
    institution: "University Name"
    semester: "Fall 2024"
    description: "Brief description of the course and your role..."
    url: https://course-website.edu
```

#### Research Interests

The "Research Interests" section highlights your areas of academic focus. Configure in `_config.yml`:

```yaml
topics:
  - name: Machine Learning
    web_url: https://github.com/topics/machine-learning
    image_url: https://raw.githubusercontent.com/.../machine-learning.png
```

Parameters:
- `name`: The topic name
- `web_url`: Optional link to topic page
- `image_url`: Optional square image for the topic

#### Social Media & Academic Profiles

Your website now supports both traditional social media and academic platforms:

**Academic Platforms:**
- **Google Scholar**: `scholar: your_google_scholar_id`
- **ORCID**: `orcid: 0000-0000-0000-0000`
- **ResearchGate**: `researchgate: Your_Name`
- **Academia.edu**: `academia: institution.edu/YourName`
- **arXiv**: `arxiv: lastname_f_1`
- **Semantic Scholar**: `semanticscholar: 123456789`
- **dblp**: `dblp: 12/3456`

**Professional Platforms:**
- LinkedIn, Twitter, GitHub, personal website, etc.

**Other Services:**
- Behance, Dribbble, Facebook, Instagram, Medium, Stack Overflow, YouTube, and more

Example configuration in `_config.yml`:

```yaml
social_media:
  # Academic platforms
  scholar: your_google_scholar_id
  orcid: 0000-0000-0000-0000
  researchgate: Your_Name

  # Professional platforms
  linkedin: your_username
  twitter: your_username
  github: your_username

  # Other platforms
  medium: your_username
  stackoverflow: your_user_id
```

Links to your profiles will appear in your bio section with appropriate icons. Academic profiles integrate with Schema.org structured data for better discoverability by search engines and academic databases.

**Note**: This feature is supported by two files in your repository:

- `/_data/social_media.yml`: Defines each of the supported services, including variable name, display name, URL path, and SVG icon.
- `/_includes/social_media_share_url.html`: Outputs the share URL required for any of the supported social media services that support sharing URLs.

If you're interested in adding a social media service that's not already supported in this repo, you can edit these two files to build that support.

## Adding pages

To **add a page** to your website (e.g. detailed resume):

1. Create a new `.html` or `.md` file at the root of your repository.
2. Give it a filename that you want to be used in the page's URL (e.g. `http://yoursite.dev/filename`).
3. At the start of your file, include the following [front matter](https://jekyllrb.com/docs/front-matter/):

```
---
layout: default
---
```

## Adding Research Notes / Blog Posts

Your academic website includes enhanced support for research notes and blog posts with academic metadata.

To **add a research note** to your website:

1. Create a new `.md` file in your repository's `/_posts/` directory.
2. Give it a filename using the following format:

```
YEAR-MONTH-DAY-title.md
```

3. At the start of your file, include enhanced [front matter](https://jekyllrb.com/docs/front-matter/) with academic metadata:

```yaml
---
title: "Understanding Neural Networks: A Comprehensive Introduction"
authors: "Your Name, Co-Author Name"
published: true
abstract: "Brief description of your research article or blog post..."
keywords:
  - Neural Networks
  - Deep Learning
  - Machine Learning
doi: 10.1234/example.doi  # Optional
---
```

**Enhanced Front Matter Options:**

- `title`: (Required) The title of your post
- `authors`: (Optional) Author names for academic attribution
- `published`: Set to `true` to publish, `false` to keep as draft
- `abstract`: (Optional) A brief summary displayed prominently
- `keywords`: (Optional) List of keywords/tags for categorization
- `doi`: (Optional) Digital Object Identifier for citation
- `updated`: (Optional) Date of last update (format: YYYY-MM-DD)

**Academic Features:**

Your posts now include:
- 📄 **Abstract display**: Highlighted abstract box for quick overview
- 🏷️ **Keyword tags**: Visual keyword labels for easy categorization
- 👥 **Author attribution**: Multiple author support
- 📅 **Publication and update dates**: Clear temporal metadata
- 📚 **Citation metadata**: Automatic generation of citation tags for Google Scholar and other academic search engines
- 🔗 **Schema.org markup**: Enhanced SEO with structured data

**Example Post Structure:**

See `/_posts/2024-01-15-sample-research-note.md` for a complete example with:
- Mathematical equations
- Code syntax highlighting
- Figures and tables
- Citations and references
- BibTeX citation format

Jekyll's conventions for authoring and managing blog posts are very flexible. You can [learn more in Jekyll's documentation for "Posts."](https://jekyllrb.com/docs/posts/)

## Content and templates

To give you a sound foundation for your academic website, your repository includes dynamic `.html` files ("includes") that are re-used throughout your website. They're all stored in the `/_includes/` directory.

**Standard Components:**
- `header.html`: Page header with enhanced metadata and Schema.org markup
- `footer.html`: Page footer
- `masthead.html`: Your avatar, name, bio, and professional links

**Academic Components:**
- `publications.html`: Dynamic list of your academic publications with DOI/arXiv/PDF links
- `teaching.html`: Showcase of your teaching experience and courses
- `projects.html`: "Research Projects" section populated from your GitHub repositories
- `interests.html`: "Research Interests" highlighting your academic focus areas
- `thoughts.html`: "Research Notes" listing your latest academic blog posts

**Card Components:**
- `repo-card.html`: Compact repository presentation with hover animations
- `publication-card.html`: Professional publication display with metadata
- `teaching-card.html`: Teaching experience presentation
- `post-card.html`: Blog post summary with metadata
- `topic-card.html`: Research interest/topic presentation

### Layouts

Your repository comes with three layouts:

- **default**: Not used by any of the built-in pages or posts, but useful for any new pages you create.
- **home**: Used by your `index.html` homepage to display listings of your projects, interests, and (optionally) your blog posts.
- **post**: Used by default by the posts in your `/_posts/` directory.

Jekyll's convention for defining layouts is very flexible. You can [learn more about customizing your layouts in the Jekyll "Layouts" docs.](https://jekyllrb.com/docs/layouts/)

## Styles

Your academic website features a professional, modern design built on [GitHub's Primer CSS framework](https://styleguide.github.com/primer/) with extensive enhancements for academic content.

**Typography:**
- **Inter**: Modern sans-serif for headings and UI (enhanced readability)
- **Merriweather**: Elegant serif font for article content (academic papers)
- **JetBrains Mono**: Professional monospace for code blocks

**Enhanced Features:**
- ✨ Smooth animations with staggered fade-in effects
- 🎨 Professional color scheme with CSS custom properties
- 📱 Fully responsive design for mobile, tablet, and desktop
- 🌓 Dark mode support (configurable in `_config.yml`)
- 🖨️ Print-optimized styles for academic papers
- 🎯 Enhanced hover effects on cards and links
- 📐 Optimized spacing and visual hierarchy

**Custom Styling:**

The `/assets/styles.scss` file includes:
- CSS custom properties (variables) for easy theming
- Academic-optimized article styles (justified text, proper spacing)
- Card animations and transitions
- Enhanced blockquotes and code blocks
- Professional table styling
- Responsive typography

**Customization:**

You can customize colors, fonts, and spacing by editing the CSS variables in `styles.scss`:

```scss
:root {
  --primary-color: #0366d6;
  --accent-color: #6f42c1;
  --font-sans: 'Inter', -apple-system, ...;
  --font-serif: 'Merriweather', Georgia, serif;
  // ... and more
}
```

The framework includes Primer utility classes for layout, which work seamlessly with the custom academic styles.


## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
