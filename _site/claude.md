# Urnicus Voter Data Blog - Project Documentation

## Project Overview

This is a Jekyll-based blog hosted on GitHub Pages that provides state-by-state information on how to obtain voter registration lists and voter history data across the United States.

**Live URL**: https://urnicus.com/
**Blog URL**: https://urnicus.com/blog/

## Project Structure

```
urnicus/
├── _config.yml              # Jekyll configuration
├── _layouts/                # Custom layouts
│   └── post.html           # Blog post layout template
├── _posts/                 # Blog posts (Markdown files) - 50 state posts
│   ├── 2025-11-17-alabama-voter-data.md
│   ├── 2025-11-17-alaska-voter-data.md
│   ├── ... (all 50 states)
│   └── 2025-11-17-wyoming-voter-data.md
├── blog.md                 # Blog index page (lists all posts)
├── states-overview.md      # Overview page with sortable table and categories
├── README.md               # Project README
├── Gemfile                 # Ruby dependencies
└── CLAUDE.md               # This file - project documentation for Claude
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

All 50 states have been completed as of November 17, 2025:

- [x] Alabama
- [x] Alaska
- [x] Arizona
- [x] Arkansas
- [x] California
- [x] Colorado
- [x] Connecticut
- [x] Delaware
- [x] Florida (Tested)
- [x] Georgia (Tested)
- [x] Hawaii
- [x] Idaho
- [x] Illinois
- [x] Indiana
- [x] Iowa
- [x] Kansas
- [x] Kentucky
- [x] Louisiana
- [x] Maine
- [x] Maryland
- [x] Massachusetts
- [x] Michigan
- [x] Minnesota
- [x] Mississippi (Submitted for testing)
- [x] Missouri
- [x] Montana
- [x] Nebraska
- [x] Nevada
- [x] New Hampshire
- [x] New Jersey
- [x] New Mexico
- [x] New York
- [x] North Carolina (Tested)
- [x] Ohio (Tested)
- [x] Oklahoma
- [x] Oregon
- [x] Pennsylvania (Tested)
- [x] Rhode Island
- [x] South Carolina
- [x] South Dakota
- [x] Tennessee
- [x] Texas
- [x] Utah
- [x] Vermont
- [x] Virginia
- [x] Washington (Tested)
- [x] West Virginia
- [x] Wisconsin
- [x] Wyoming

**Note:** North Dakota was not included as it does not have voter registration (same-day registration state)

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

## States Overview Page

**Location**: `/states-overview.html` (from `states-overview.md`)

A comprehensive landing page featuring:
- **Sortable Table**: Click column headers to sort by State, Cost, Effort, or Tested status
- **Categorized Sections**: States grouped by access type and cost
  - Tested & Verified (6 states)
  - Free & Unrestricted Access (7 states)
  - Extremely Low Cost $0-$50 (9 states)
  - Free/Low Cost with Eligibility Requirements (3 states)
  - Moderate Cost $100-$500 (14 states)
  - Higher Cost $1,000-$5,000 (11 states)
  - Very High Cost or Complex $5,000+ (6 states)
- **Key Insights**: Best values, fastest access, best voter history coverage
- **Practical Guidance**: Recommendations for different user types

## Content Statistics

- **Total States**: 50 (49 + Pennsylvania original)
- **Total Blog Posts**: 50
- **States Tested**: 6 (Ohio, North Carolina, Pennsylvania, Florida, Georgia, Washington)
- **States Pending Test**: 1 (Mississippi - form submitted)
- **Free Access States**: 7 (Ohio, North Carolina, Florida, Mississippi, Vermont, Washington, New York)
- **Lowest Cost**: Arkansas ($2.50)
- **Highest Cost**: Alabama (~$37,000)
- **Most Complex**: Massachusetts (no statewide list - 351 municipalities)

## Key Design Decisions

- **Theme Choice**: Cayman theme selected for clean, centered layout suitable for long-form blog content
- **Permalink Structure**: Posts organized under `/blog/` path to keep blog content separate from potential other pages
- **Future Posts Enabled**: Allows posts dated today or in the future to display immediately
- **Post Layout**: Custom `_layouts/post.html` created with styling for tables, blockquotes, and navigation back to blog index

## Important Notes

- Jekyll only reads `_config.yml` at startup - server must be restarted after configuration changes
- Posts must not have future dates (relative to server time) unless `future: true` is set in config
- The `github-pages` gem in the Gemfile ensures compatibility with GitHub Pages deployment

## Navigation Structure

The site has three main content areas:

1. **Individual State Blog Posts** (`_posts/` directory)
   - One detailed post per state (50 total)
   - URL format: `/blog/2025/11/17/[state-name]-voter-data.html`
   - Each follows the standard blog post structure outlined above

2. **Blog Index** (`blog.md`)
   - Lists all state blog posts
   - URL: `/blog/`

3. **States Overview Page** (`states-overview.md`)
   - Sortable table comparing all 50 states
   - States organized by cost and accessibility categories
   - Quick reference for decision-making
   - URL: `/states-overview.html`
   - This is the recommended landing page for users wanting to compare states

## Future Maintenance

### Regular Updates Needed
- **Cost verification**: Prices may change; verify periodically with state offices
- **Process changes**: States may update request procedures, forms, or portals
- **Testing status**: Update as more states are tested
- **New legislation**: Monitor for law changes affecting voter data access

### Potential Additions
- Add "Last Verified" dates to each state page
- Include sample request letters/forms
- Add state-by-state legal restrictions comparisons
- Document voter history field structures for each state
- Add delivery timeline tracking (actual vs. estimated)

### SEO Considerations
- Each state page targets: "[State] voter data", "[State] voter list", "[State] voter history"
- Overview page targets: "voter data by state", "how to get voter lists"
- Consider adding FAQ page for common questions
- Add state maps/visualizations showing cost tiers

## Quick Links for User

- **Blog Index**: `/blog/`
- **States Overview**: `/states-overview.html`
- **Individual State**: `/blog/2025/11/17/[state-name]-voter-data.html`
- **Example**: `/blog/2025/11/17/ohio-voter-data.html`
