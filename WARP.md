# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a Jekyll-based documentation and blog site for RAG4j/p (Retrieval Augmented Generation for Java/Python). The site provides documentation, examples, blog posts, and references for two companion projects focused on teaching RAG concepts through simplified frameworks.

**Key characteristics:**
- Static site built with Jekyll 4.3.3 and the Minima theme
- Hosted on GitHub Pages at https://rag4j.org
- Content includes technical documentation, workshop announcements, and educational material about RAG systems
- Primary audience: developers learning or teaching RAG (Retrieval Augmented Generation) concepts

## Essential Commands

### Development Server
```bash
bundle exec jekyll serve
```
Starts local development server at http://localhost:4000. Jekyll auto-regenerates pages on file changes, but `_config.yml` changes require server restart.

### Build Site
```bash
bundle exec jekyll build
```
Generates static site to `_site/` directory.

### Build with Drafts
```bash
bundle exec jekyll serve --drafts
```
Includes posts from `_drafts/` folder in local preview.

### Build for Production
```bash
bundle exec jekyll build --destination _site
```
Explicit destination flag for production builds.

## Ruby Environment Setup

This project requires Ruby 3.3.5 (or compatible version). The README documents the macOS setup using chruby:

```bash
brew install chruby ruby-install
ruby-install ruby 3.3.5

# Add to ~/.zshrc:
source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh
source $(brew --prefix)/opt/chruby/share/chruby/auto.sh
chruby ruby-3.3.5

export GEM_HOME=$HOME/.gem
export PATH=$HOME/.gem/bin:$PATH

# Install Jekyll
gem install jekyll --user-install
```

## Site Architecture

### Content Structure

**Core Pages** (`*.markdown` in root):
- `index.markdown` - Homepage introducing RAG4j/p concept and philosophy
- `documentation.markdown` - Comprehensive technical documentation with architecture diagrams
- `about.markdown` - Team and company information
- `examples.markdown` - Code samples for both Java and Python implementations
- `references.markdown` - Third-party tools and services (OpenAI, Ollama, Weaviate)

**Blog Posts** (`_posts/`):
- Follow Jekyll naming convention: `YYYY-MM-DD-title.markdown`
- Use front matter with `layout: post`, `title`, `date`, and `categories`
- Recent posts cover workshops, new features, and technical articles

**Custom Includes** (`_includes/`):
- `header.html` - Custom header with RAG4j logo integration
- `footer.html` - Custom footer with social links
- `google-analytics.html` - GA4 tracking (ID: G-8F82VTL4WZ)
- `head.html` - Custom CSS references

**Assets** (`assets/`):
- `images/` - Contains logos, diagrams, profile pictures
- `style/custom.css` - Site-specific styling overrides

### Configuration Details

**Site Settings** (`_config.yml`):
- Uses Minima theme with custom includes overrides
- Plugins: `jekyll-feed`, `jekyll-sitemap`
- Excludes: `CNAME`, `README.md`, `diagrams/` directory
- Custom variables: `linkedin_username_jettro`, `linkedin_username_daniel`

**Content Organization Philosophy:**
- Documentation is comprehensive with detailed architecture explanations
- Three-part RAG system: Retrieval → Generation → Quality
- Emphasizes teaching and learning with simplified, extendable components

## Working with Content

### Adding Blog Posts

Create file in `_posts/` with format `YYYY-MM-DD-title.markdown`:

```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS +0100
categories: [category-name]
---

Your content here
```

Common categories: `examples`, workshop announcements

### Documentation Updates

When editing `documentation.markdown`:
- Maintain three main sections: Retrieval, Generation, Quality
- Use image references: `/assets/images/filename.png`
- Keep class/component descriptions focused on architecture, not implementation details
- Document both Java and Python naming conventions (e.g., `find_relevant_chunks` vs `findRelevantChunks`)

### Code Examples

When adding code examples:
- Provide both Java and Python versions side-by-side (see `examples.markdown`)
- Use triple backticks with language identifiers
- Keep examples focused on single components to demonstrate modularity
- Reference appropriate data files (e.g., `jfall/sessions.jsonl`, Vasa corpus)

## Content Guidelines

### Technical Accuracy
- RAG4j targets Java developers; RAG4P targets Python developers
- Main components: Retriever, RetrievalStrategy, IndexingService, ContentReader, Splitter, Embedder, ContentStore, AnswerGenerator, Quality Services
- Supported embedders: OpenAI, Ollama (local), ONNX (Python)
- Supported content stores: InternalContentStore (in-memory), WeaviateContentStore

### Terminology Consistency
- Use "RAG4j" for Java, "RAG4p" for Python (also written as "RAG4j/p" collectively)
- "Chunks" not "segments" or "fragments"
- "ContentStore" not "vector store" or "embedding store"
- Quality metrics: Precision (0-1), Contextual Accuracy (1-5), Answer Completeness (1-5)

### Writing Style
- Educational and accessible tone (target: developers learning RAG)
- Explain "why" behind architectural decisions
- Emphasize simplicity and extensibility over feature completeness
- Reference inspiration sources (Langchain, Langchain4j, TruLens)

## Jekyll-Specific Notes

### Configuration Changes
After modifying `_config.yml`, restart the development server - changes are NOT hot-reloaded.

### Excluded Content
The following are excluded from site generation (see `_config.yml`):
- `CNAME` (used for GitHub Pages custom domain)
- `README.md` (repository documentation)
- `diagrams/` (source files for architecture diagrams)

### Theme Customization
Site uses Minima theme with custom includes. To modify layout:
1. Check if custom include exists in `_includes/`
2. If not, copy from Minima gem location and customize
3. Custom CSS goes in `assets/style/custom.css`

## Common Workflows

### Adding a Workshop Announcement
1. Create post in `_posts/` with workshop date in filename
2. Include workshop details, registration links, and topics covered
3. Add to `categories: [workshops]` or appropriate category
4. Test locally with `bundle exec jekyll serve`

### Updating Architecture Documentation
1. If diagrams change, update images in `assets/images/`
2. Update corresponding explanations in `documentation.markdown`
3. Ensure component names match between Java (PascalCase methods) and Python (snake_case methods)

### Publishing Changes
1. Commit changes to Git
2. Push to main branch
3. GitHub Pages automatically rebuilds and deploys
4. Verify at https://rag4j.org

## Project Context

**Maintainers**: Jettro Coenradie and Daniel Spee from Luminis
**Purpose**: Educational framework for teaching RAG concepts through workshops
**Sister Projects**: 
- RAG4J: https://github.com/RAG4J/rag4j
- RAG4P: https://github.com/RAG4J/rag4p

This documentation site serves as the central knowledge hub for both projects.
