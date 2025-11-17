# Urnicus Voter Data Blog - Project Documentation

## Project Overview

This is a Jekyll-based blog hosted on GitHub Pages that provides state-by-state information on how to obtain voter registration lists and voter history data across the United States.

**Live URL**: https://urnicus.com/
**Blog URL**: https://urnicus.com/blog/

## Project Structure

```
urnicus/
├── _config.yml           # Jekyll configuration
├── _layouts/             # Custom layouts
│   └── post.html        # Blog post layout template
├── _posts/              # Blog posts (Markdown files)
│   └── 2025-11-17-pennsylvania-voter-data.md
├── blog.md              # Blog index page (lists all posts)
├── README.md            # Project README
├── Gemfile              # Ruby dependencies
└── claude.md            # This file - project documentation for Claude
```

## Theme

**Current Theme**: `jekyll-theme-cayman`

The Cayman theme provides a clean, centered layout that works well for blog content. Previously used `jekyll-theme-minimal` which had sidebar formatting issues with blog posts.

## Configuration Details

### _config.yml Settings

- **Theme**: `jekyll-theme-cayman`
- **Title**: `Urnicus Inc.`
- **Description**: `Voter Data Access Guide`
- **Future Posts**: `future: true` (allows posts with today's/future dates to display)
- **Permalink Structure**: `/blog/:year/:month/:day/:title.html`

### Blog Post Format

All blog posts must follow this naming convention:
```
YYYY-MM-DD-state-name-voter-data.md
```

Example: `2025-11-17-pennsylvania-voter-data.md`

### Blog Post Template (Front Matter)

```yaml
---
layout: post
title: "How to Get Voter Data in [State Name]"
date: YYYY-MM-DD
tags: [state-name, voter-data, voter-list, voter-history]
---
```

## Blog Post Structure

Each state blog post should follow this structure:

1. **Introduction** - Brief overview of the state's voter data accessibility
2. **Quick Summary Table** - Key facts including:
   - Statewide Cost
   - Voter List Access
   - Voter History Access
   - Delivery Method
   - Processing Time
3. **Voter List Section** - How to access, what's included, step-by-step instructions
4. **Voter History Section** - Historical coverage, what's included
5. **Cost Section** - Detailed pricing information
6. **Restrictions and Permitted Uses** - Legal requirements (use blockquotes for important restrictions)
7. **Technical Notes** (if applicable) - Browser compatibility, file formats, etc.
8. **Additional Resources** - Links to official documentation

## States Completed

- [x] Pennsylvania (2025-11-17)

## States Remaining (49)

### States with Research Data Available

The following states have been researched and data is available in the source document:

- [ ] Alabama
- [ ] Alaska
- [ ] Arizona
- [ ] Arkansas
- [ ] California
- [ ] Colorado
- [ ] Connecticut
- [ ] Delaware
- [ ] Florida
- [ ] Georgia
- [ ] Hawaii
- [ ] Idaho
- [ ] Illinois
- [ ] Indiana
- [ ] Iowa
- [ ] Kansas
- [ ] Kentucky
- [ ] Louisiana
- [ ] Maine
- [ ] Maryland
- [ ] Massachusetts
- [ ] Michigan
- [ ] Minnesota
- [ ] Mississippi
- [ ] Missouri
- [ ] Montana
- [ ] Nebraska
- [ ] Nevada
- [ ] New Hampshire
- [ ] New Jersey
- [ ] New Mexico
- [ ] New York
- [ ] North Carolina
- [ ] North Dakota
- [ ] Ohio
- [ ] Oklahoma
- [ ] Oregon
- [ ] Rhode Island
- [ ] South Carolina
- [ ] South Dakota
- [ ] Tennessee
- [ ] Texas
- [ ] Utah
- [ ] Vermont
- [ ] Virginia
- [ ] Washington
- [ ] West Virginia
- [ ] Wisconsin
- [ ] Wyoming

## Local Development

To run the site locally:

```bash
bundle exec jekyll serve
```

Then visit [http://localhost:4000](http://localhost:4000) in your browser.

## Deployment

Changes are automatically deployed to GitHub Pages when pushed to the `main` branch:

```bash
git add .
git commit -m "Your commit message"
git push
```

GitHub Pages will build and deploy the site automatically (usually within 1-2 minutes).

## Source Data

All state research data is available in the original research document provided by the user. Each state entry includes:
- Voter List access method
- Voter History access method
- Cost information
- Restrictions on use
- Testing status
- Direct links to request forms/portals

## Next Steps for Content Creation

To create the remaining 49 blog posts:

1. Use the Pennsylvania post as a template
2. Extract data from the research document for each state
3. Follow the established blog post structure
4. Create one post per state with filename: `YYYY-MM-DD-state-name-voter-data.md`
5. Place all posts in the `_posts/` directory

## Key Design Decisions

- **Theme Choice**: Cayman theme selected for clean, centered layout suitable for long-form blog content
- **Permalink Structure**: Posts organized under `/blog/` path to keep blog content separate from potential other pages
- **Future Posts Enabled**: Allows posts dated today or in the future to display immediately
- **Post Layout**: Custom `_layouts/post.html` created with styling for tables, blockquotes, and navigation back to blog index

## Important Notes

- Jekyll only reads `_config.yml` at startup - server must be restarted after configuration changes
- Posts must not have future dates (relative to server time) unless `future: true` is set in config
- The `github-pages` gem in the Gemfile ensures compatibility with GitHub Pages deployment
