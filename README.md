# GeoNavigator

An interactive decision tree that mirrors the consultation process used by UC GIS Librarians to guide researchers through geospatial research needs.

## 🎯 Project Status

**This is an experimental proof of concept.** The tool demonstrates a branching scenario approach to online GIS consultations but is not yet production-ready.

## 📋 Overview

UC GIS Librarians conduct consultations that follow predictable pathways and decision points. This tool transforms that consultation expertise into an interactive, self-guided experience where users navigate through questions and resources based on their specific needs.

## ✨ Features

- **Branching Decision Trees**: Users navigate through questions based on their responses
- **Resource Pages**: Actionable how-to guides with clear steps
- **Graph-Based Architecture**: Any question or resource can link to any other, supporting non-linear consultation flows
- **Visual Distinction**: Clear differentiation between decision points (questions) and actionable content (resources)
- **Responsive Design**: Works seamlessly across desktop, tablet, and mobile devices

## 🛠️ Technical Stack

- **Static Site Generator**: Jekyll 3.10
- **Theme**: Just the Docs 0.8
- **Hosting**: GitHub Pages
- **Icons**: Lucide Icons
- **Styling**: Custom SCSS with UC brand colors

## 🏗️ Architecture

### Collections

The tool uses two Jekyll collections:

- **`_questions/`**: Decision points that branch to other questions or resources
- **`_resources/`**: How-to guides and tutorials with actionable steps

### Content Structure

Each content page uses front matter to define relationships:

```yaml
---
title: "Page Title"
sub-title: "Optional subtitle"
next-steps:
  - label: "Button text"
    type: question  # or 'resource'
    ref: filename-without-extension
---
```

### Navigation Pattern

- **Forward navigation**: Through cards and "next steps"
- **Back navigation**: Browser back button
- **Start over**: Link to return to homepage
- No traditional site map - navigation is context-driven

## 🚀 Getting Started

### Prerequisites

- Ruby 3.x
- Bundler

### Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd uc-gis
```

2. Install dependencies:
```bash
bundle install
```

3. Run the development server:
```bash
bundle exec jekyll serve
```

4. Visit `http://localhost:4000` in your browser

## 📁 Project Structure

```
uc-gis/
├── _questions/          # Question/decision pages
├── _resources/          # How-to guide pages
├── _layouts/            # Custom page layouts
│   ├── question.html
│   └── resource.html
├── _includes/           # Reusable components
│   └── head_custom.html
├── _sass/               # Custom styling
│   └── color_schemes/
│       └── uc.scss
├── assets/
│   └── css/
│       └── custom.scss  # Main custom styles
├── _config.yml          # Jekyll configuration
├── index.md             # Homepage
└── README.md
```

## ✏️ Adding Content

### Adding images

1. Go to your repo
2. Click Add file → Upload files
3. Upload your image (e.g., map.png)
save in /assets/images/<br></br>
Include this code:
<img src="{{ '/assets/images/graph2.png' | relative_url }}"
     alt="Table showing county with ethnicity expanded out into types"
     style="max-width:600px; width:100%; height:auto;"> 

### Creating a Question Page

1. Create a new file in `_questions/` (e.g., `your-question.md`)
2. Add front matter:

```yaml
---
title: "Your Question Here?"
sub-title: "Brief context"
parent: "previous page"
permalink: "test-test"
next-steps:
  - label: "Option 1"
    type: question
    ref: next-question-filename
  - label: "Option 2"
    type: resource
    ref: resource-filename
---

<nav class="breadcrumbs">
  <a href="{{ '/' | relative_url }}">Home</a>
  {% if page.parent %}
    /
    <a href="{{ page.parent_url | relative_url }}">{{ page.parent }}</a>
  {% endif %}
  /
  <span>{{ page.title }}</span>
</nav>

Optional description content here.

<!-- Expand / Collapse Controls -->
<div style="margin: 1.5rem 0;">
  <button onclick="expandAll()">Expand all</button>
  <button onclick="collapseAll()">Collapse all</button>
</div>
<details class="collapsible">
<summary><strong>title</strong></summary>

<script>
function expandAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = true);
}

function collapseAll() {
  document.querySelectorAll('details.collapsible')
    .forEach(d => d.open = false);
}
</script>
```

### Creating a Resource Page

1. Create a new file in `_resources/` (e.g., `your-guide.md`)
2. Add front matter:

```yaml
---
title: "How to Do Something"
sub-title: "Brief description"
jobs_to_be_done:
  - "Goal 1"
  - "Goal 2"
steps:
  - "Step 1 instructions"
  - "Step 2 instructions"
next-steps:
  - label: "Next action"
    type: question
    ref: related-question
---

Additional detailed content in markdown format.
```

## 🎨 Customization

### Colors

UC brand colors are defined in `_sass/color_schemes/uc.scss`:
- **UC Blue**: `#2774AE`
- **UC Gold**: `#FFB511`

### Styling

Custom styles are in `assets/css/custom.scss`. The file is organized by component for easy navigation.

## 🧪 Proof of Concept Scope

This Proof of Concept demonstrates:
- ✅ Branching decision tree functionality
- ✅ Question and resource content types
- ✅ Non-linear navigation (graph structure)
- ✅ Visual design system
- ✅ Responsive layout
- ✅ UC brand integration

**Not yet implemented:**
- ❌ User analytics/tracking
- ❌ Multi-language support
- ❌ User feedback mechanism
- ❌ Complete content library

## 🤝 Contributing

This is a proof of concept for UC GIS Librarians. If you'd like to contribute content or provide feedback:

1. Review existing question and resource examples
2. Follow the content structure outlined above
3. Test your changes locally before submitting
4. Ensure content follows UC brand guidelines

## 📝 License

[Add appropriate license information]

## 👥 Credits

**Developed by**: UC San Diego Library Digital Experience Team  
**For**: UC GIS Librarians  
**Theme**: Just the Docs by Patrick Marsceill  
**Icons**: Lucide Icons

## 📧 Contact

For questions or feedback about this proof of concept, contact [your contact info].

---

**Note**: This is an experimental proof of concept and is under active development. Content and features are subject to change.
