# Comparing AI Tools

**Independent reviews and side-by-side comparisons of AI tools.**

[Visit AI TOOL CLUB](https://aitoolclub.xyz) · [Browse comparisons](https://aitoolclub.xyz/posts/) · [Contact the author](mailto:jubrilbabatunde2001@gmail.com)

AI TOOL CLUB helps readers compare AI products for coding, writing, chat, image generation, video, audio, research, and other practical tasks. Reviews and head-to-head articles explain what tools offer, where their trade-offs are, and which use cases may suit them.

The site is built and maintained as an individual project by **Babatunde Jubril**.

## What the site does

- **Reviews** take a closer look at individual AI products, their features, pricing, strengths, and limitations.
- **Comparisons** put two or more tools side by side to make differences easier to evaluate.
- **Category guides** collect options for a particular task, such as coding or image generation.
- **Alternatives guides** help readers explore products similar to a tool they already know.
- **Scoring and verdicts** summarize an article's assessment using category-specific dimensions and weights where provided.
- **Sources and disclosures** provide context for claims and identify affiliate links where applicable.

The site is an editorial guide, not a tool directory API, AI model, or interactive product-comparison engine. Product plans, capabilities, availability, and prices can change. Check the linked vendor source before making a purchase or relying on a time-sensitive claim. A comparison's score or test result should be read with its methodology and data-source notes; it is not a guarantee of results for every reader.

## About the author

**Babatunde Jubril** is the independent creator and maintainer of AI TOOL CLUB. He researches and writes the site's AI tool reviews and comparisons to help readers make more informed choices. The project is published under his own editorial judgment rather than as a team or company publication.

- **Website:** [aitoolclub.xyz](https://aitoolclub.xyz)
- **GitHub:** [@jubrilbabatundecodes](https://github.com/jubrilbabatundecodes)
- **Repository:** [jubrilbabatundecodes/ComparingAItools](https://github.com/jubrilbabatundecodes/ComparingAItools)
- **Email:** [jubrilbabatunde2001@gmail.com](mailto:jubrilbabatunde2001@gmail.com)

## How comparisons are assessed

The site's published methodology describes a combination of:

1. **Public benchmarks** relevant to the category.
2. **Community feedback** from forums and professional communities.
3. **Hands-on testing** when an article says the tools were tested directly.
4. **Official documentation** for product capabilities, plans, and pricing.

Scoring dimensions and weights depend on the category. For example, coding comparisons may consider code generation, project context, and debugging, while image comparisons may focus on image quality, prompt adherence, and creative range. Where an article publishes weighted scores, its scoring table and any weight adjustments explain how the summary was reached.

Sources, test descriptions, scores, and verdicts are article-specific. Do not assume that every article uses the same tests or that every product was independently tested. Plans and features should be rechecked against current vendor documentation because they can change after publication.

## Technology

- **[Hugo](https://gohugo.io/):** builds the Markdown content into a static website.
- **[PaperMod](https://github.com/adityatelange/hugo-PaperMod):** Hugo theme included as a Git submodule.
- **Markdown and YAML:** articles and page content live in `content/`; site-wide settings live in `hugo.yaml`.
- **HTML templates and CSS:** custom layouts and comparison components extend the theme.
- **GitHub Actions and GitHub Pages:** the workflow builds the site and deploys it when changes are pushed to `main`.

The site is statically generated; there is no application server or project database to run.

## Repository map

```text
.
├── archetypes/                 # Starter front matter/content for new Hugo pages
├── assets/
│   └── css/extended/           # Custom styles for comparison tables and components
├── content/
│   ├── about.md                # Project and methodology overview
│   ├── contact.md              # Contact and comparison requests
│   ├── editorial-policy.md     # Research, corrections, and editorial standards
│   ├── privacy.md              # Privacy information
│   ├── terms.md                # Terms of use
│   └── posts/                  # Reviews, comparisons, category guides, alternatives
├── layouts/
│   ├── _default/               # Custom list and article templates
│   └── partials/               # FAQ structured data, footer, related articles
├── promo/                      # Draft promotional copy for external platforms
├── static/                     # Favicons, domain mapping, and verification files
├── themes/PaperMod/            # Theme submodule (initialize before building)
├── .github/workflows/          # GitHub Pages build/deployment workflow
├── hugo.yaml                   # Site identity, menus, SEO, search, and Hugo settings
└── README.md
```

### Main content areas

- `content/posts/` is the primary editorial section. Each article is a Markdown file with YAML front matter for fields such as title, date, author, categories, tags, and description.
- `content/about.md`, `content/editorial-policy.md`, `content/privacy.md`, and `content/terms.md` describe the project and its policies.
- `archetypes/` contains templates for creating new default pages and comparison articles. New articles should identify **Babatunde Jubril** as author and include relevant source notes.
- `layouts/` contains Hugo templates that add site-specific page rendering, FAQ structured data, related posts, and footer links.
- `assets/css/extended/comparison-tables.css` styles comparison tables and related visual components.
- `static/` contains files copied directly to the generated site, including the custom-domain `CNAME` file and favicons.
- `promo/` contains draft launch and announcement material; it is not part of the published site content.

## Run the site locally

### Requirements

- Hugo **Extended** edition. The deployment workflow installs the latest Extended release.
- Git, to clone the repository and initialize the PaperMod theme submodule.

### Setup and preview

```powershell
git clone --recurse-submodules https://github.com/jubrilbabatundecodes/ComparingAItools.git
cd ComparingAItools
hugo server
```

Hugo prints the local preview URL in the terminal (normally `http://localhost:1313/`). Leave the server running while editing; Hugo rebuilds the preview as files change.

If you already cloned without submodules, initialize the theme before starting Hugo:

```powershell
git submodule update --init --recursive
hugo server
```

To produce a local production-style build:

```powershell
hugo --minify --gc --buildFuture
```

The generated site is written to `public/`, which is build output and should not be committed.

## Add or update an article

1. Create a Markdown file in `content/posts/`, using a suitable archetype as a starting point.
2. Set the title, publication date, author, description, categories, and tags in the YAML front matter. Use `author: Babatunde Jubril`.
3. Organize the article around the reader's decision: a clear verdict, relevant comparison criteria, product details, trade-offs, and a practical recommendation.
4. Cite sources for time-sensitive details such as pricing, model availability, features, and usage limits. Include the source and date checked; do not describe an unverified claim as current.
5. Explain the basis for scores and any category-specific weight adjustments. Distinguish hands-on tests from research based on documents, public benchmarks, or community reports.
6. Preserve affiliate disclosures where applicable and verify that links point to the intended destination.
7. Preview locally with `hugo server`, then submit changes through a pull request.

The site includes a public edit link on articles to make corrections and suggestions easier. Readers can also report errors or request a comparison through the [contact page](https://aitoolclub.xyz/contact/) or by email.

## Deployment

The GitHub Actions workflow at `.github/workflows/hugo.yaml` runs on pushes to `main` and can also be started manually. It checks out the theme submodule, installs Hugo Extended, runs:

```text
hugo --minify --gc --buildFuture
```

Then it uploads the generated `public/` directory and deploys it to GitHub Pages. The repository's Pages environment and custom domain must be configured on GitHub for deployment to publish successfully.

## Policies and contact

- [About and methodology](https://aitoolclub.xyz/about/)
- [Editorial policy and corrections](https://aitoolclub.xyz/editorial-policy/)
- [Privacy policy](https://aitoolclub.xyz/privacy/)
- [Terms of use](https://aitoolclub.xyz/terms/)
- [Contact](https://aitoolclub.xyz/contact/)

For questions, corrections, or comparison suggestions, contact **Babatunde Jubril** at [jubrilbabatunde2001@gmail.com](mailto:jubrilbabatunde2001@gmail.com).
