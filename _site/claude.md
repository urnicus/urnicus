# Urnicus Voter Data Guide - Project Documentation

## Project Overview

This is a Jekyll-based site hosted on GitHub Pages that provides state-by-state information on how to obtain voter registration lists and voter history data across the United States.

**Live URL**: https://urnicus.com/

## Project Structure

```
urnicus/
├── _config.yml              # Jekyll configuration
├── _includes/               # Reusable partials
│   ├── key.html            # Key/legend for state categories
│   └── states/             # Individual state content partials (50 files)
│       ├── alabama.md
│       ├── alaska.md
│       └── ... (all 50 states)
├── states/                  # Individual state pages (50 files)
│   ├── alabama.md
│   ├── alaska.md
│   └── ... (all 50 states)
├── index.md                 # Home page
├── states-overview.md       # Comprehensive overview with table + all state details
├── README.md                # Project README
├── Gemfile                  # Ruby dependencies
└── CLAUDE.md                # This file - project documentation for Claude
```

## Theme

**Current Theme**: `jekyll-theme-cayman`

The Cayman theme provides a clean, centered layout that works well for documentation content.

## Configuration Details

### _config.yml Settings

- **Theme**: `jekyll-theme-cayman`
- **Title**: `Urnicus Inc.`
- **Description**: `Voter Data Access Guide`

### State Page Format

All state pages are in the `states/` directory with simple naming:
```
states/ohio.md
states/pennsylvania.md
states/north-carolina.md
```

### State Page Template (Front Matter)

```yaml
---
layout: default
title: "[State] Voter Data"
state: "[State]"
status: "Tested/Pending/Untested"
access_method: "Online/Email/Mail in/etc"
cost: "FREE/$/$$/$$$"
category: "Accessible/Barriers/Leg Work/Relatively Expensive"
permalink: /states/[state-slug]/
---
```

## State Page Structure

Each state page follows this simple structure:

1. **Status Table** - Clean 3-column table with Status, Access, Expense
2. **Voter List Access** - Links and basic instructions
3. **Voter History** - What's included
4. **Cost** - Pricing details
5. **Key Legend** - Included via `{% include key.html %}`
6. **Last Updated** - Timestamp

Example:
```markdown
# Ohio

| Status | Access | Expense |
|:-------|:-------|:--------|
| Tested | Online | FREE |

**Voter List Access**

[Link to portal]

Brief description

**Voter History**

Brief description

**Cost**

Cost details

---

{% include key.html %}

*Last updated: November 21, 2025*
```

## States Completed

All 50 states completed as of November 21, 2025:

- [x] Alabama - [x] Alaska - [x] Arizona - [x] Arkansas
- [x] California - [x] Colorado - [x] Connecticut - [x] Delaware
- [x] Florida (Pending) - [x] Georgia (Tested)
- [x] Hawaii - [x] Idaho - [x] Illinois - [x] Indiana - [x] Iowa
- [x] Kansas - [x] Kentucky - [x] Louisiana
- [x] Maine - [x] Maryland - [x] Massachusetts - [x] Michigan - [x] Minnesota
- [x] Mississippi (Tested) - [x] Missouri - [x] Montana
- [x] Nebraska - [x] Nevada - [x] New Hampshire - [x] New Jersey
- [x] New Mexico - [x] New York - [x] North Carolina (Tested) - [x] North Dakota
- [x] Ohio (Tested) - [x] Oklahoma - [x] Oregon
- [x] Pennsylvania (Tested) - [x] Rhode Island
- [x] South Carolina - [x] South Dakota
- [x] Tennessee - [x] Texas - [x] Utah
- [x] Vermont - [x] Virginia - [x] Washington (Tested)
- [x] West Virginia - [x] Wisconsin - [x] Wyoming

**Note:** North Dakota included but has no voter registration (same-day registration state)

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

## Content Statistics

- **Total States**: 50
- **States Tested**: 6 (Ohio, North Carolina, Pennsylvania, Florida, Georgia, Washington)
- **States Pending Test**: 1 (Mississippi - form submitted)
- **Free Access States**: 7 (Ohio, North Carolina, Florida, Mississippi, Vermont, Washington, Oklahoma)
- **Lowest Cost**: Arkansas ($2.50)
- **Highest Cost**: Alabama (~$37,000)
- **Most Complex**: Massachusetts (no statewide list - 351 municipalities)

## Key Design Decisions

- **Simplified Structure**: No date-based permalinks, direct `/states/ohio/` URLs
- **Single Source of Truth**: State content in `_includes/states/` can be reused
- **Table Format**: Clean Status/Access/Expense table instead of bold text
- **Jekyll Includes**: Reusable partials for key and state content
- **Comprehensive Overview**: One page with both comparison table and full details

## Important Notes

- Jekyll only reads `_config.yml` at startup - server must be restarted after configuration changes
- The `github-pages` gem in the Gemfile ensures compatibility with GitHub Pages deployment
- State include files (`_includes/states/`) are the source of truth and can be included in multiple places

## Navigation Structure

The site has three main areas:

1. **Home Page** (`index.md`)
   - Welcome message
   - Links to states overview
   - URL: `/`

2. **States Overview** (`states-overview.md`)
   - Comparison table with all 50 states (sortable, with clickable state links)
   - Key legend
   - Full details for all 50 states (via includes)
   - URL: `/states-overview/`
   - **This is the main resource page**

3. **Individual State Pages** (`states/` directory)
   - One page per state (50 total)
   - URL format: `/states/[state-name]/`
   - Examples: `/states/ohio/`, `/states/pennsylvania/`

## Jekyll Includes System

We use Jekyll includes for reusable content:

### `_includes/key.html`
The key/legend explaining state categories and cost symbols. Included at bottom of each state page.

### `_includes/states/[state].md`
Each state's content (extracted from the main state page). These can be included anywhere, currently used in:
- Individual state pages (the source)
- States overview page (shows all 50 states in one place)

To include: `{% include states/ohio.md %}`

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

## Quick Links

- **Home**: `/`
- **States Overview**: `/states-overview/`
- **Individual State**: `/states/[state-name]/`
- **Examples**: `/states/ohio/`, `/states/north-carolina/`, `/states/pennsylvania/`

## Adding/Updating State Information

To update a state's information:

1. Edit the state file: `states/[state-name].md`
2. The changes will automatically update:
   - The individual state page at `/states/[state-name]/`
   - The states overview page (if you regenerate includes)

To regenerate the include files after editing a state page:
```bash
for state in states/*.md; do
  state_name=$(basename "$state" .md)
  awk '/^---$/{f++; next} f==2' "$state" > "_includes/states/${state_name}.md"
done
```
