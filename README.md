# Cloud66 Documentation Content Repository

This repository contains all MDX documentation files for the Cloud66 documentation site. It is used as a git submodule in the main documentation platform.

## 📁 Repository Structure

```
/                       # Repository root
├── rails/              # Rails product documentation
├── deploy/             # Deploy product documentation
│   └── 1/             # Version 1 specific docs (legacy)
├── sites/              # Sites product documentation  
├── node/               # Node.js product documentation
├── common/             # Shared docs across all products
└── partials/           # Reusable content snippets (not directly accessible)
```

## 🔗 How Files Map to URLs

When this repository is used as a submodule in the main site, files map to URLs as follows:

### Basic Routing Pattern

- **File in this repo**: `/[product]/[category]/[page].mdx`
- **URL on site**: `https://help.cloud66.com/[product]/[category]/[page]`

### Examples

| File Path (in this repo) | URL (on live site) |
|-----------|-----|
| `/rails/getting-started/introduction.mdx` | `/rails/getting-started/introduction` |
| `/deploy/containers/docker-basics.mdx` | `/deploy/containers/docker-basics` |
| `/common/integrations/github.mdx` | `/rails/integrations/github` (redirects to last visited product) |

### Special Routing Rules

1. **Common Pages**: Files in `/common/` are accessible from any product URL
   - `/common/integrations/github.mdx` → `/rails/integrations/github`, `/deploy/integrations/github`, etc.
   - Direct `/common/*` URLs redirect to the user's last visited product

2. **Toolbelt Commands**: Files starting with `_` in `toolbelt/` folder get special layout
   - `/rails/toolbelt/_command-name.mdx` → Special command reference layout

3. **Partials**: Files in `partials/` folders cannot be accessed directly
   - Used for reusable content snippets included in other pages

## 🔢 Version Support (Deploy Product Only)

Deploy is the only product that supports multiple documentation versions.

### Version URL Structure

- **Latest/Default**: `/deploy/getting-started/guide`
- **Version 1**: `/deploy/1/getting-started/guide`

### Creating Version-Specific Documentation

#### Option 1: Version Folders
```
/deploy/
├── getting-started/
│   ├── guide.mdx           # Default (latest version)
│   └── 1/
│       └── guide.mdx       # Version 1 specific
```

#### Option 2: Frontmatter Filters
```yaml
---
title: "Legacy Feature"
excludeVersions: ['2']  # Hide from version 2
# OR
includeVersions: ['1']  # Only show in version 1
---
```

## 📝 MDX Frontmatter

Every MDX file must include frontmatter metadata:

```yaml
---
title: "Page Title"                    # Required: Page title
description: "SEO description"         # Required: Meta description
lead: "Extended intro text"            # Optional: Shown at top of page
products: ['rails', 'deploy']         # Optional: Which products this applies to
                                      # Can be array, 'all', or omitted (common)
excludeVersions: ['2']                # Optional: Hide from these versions
includeVersions: ['1']                # Optional: Only show in these versions
                                      # Note: excludeVersions and includeVersions are mutually exclusive
---
```

### Product Filtering Options

- **Specific products**: `products: ['rails', 'deploy']` - Only accessible from these products
- **All products**: `products: 'all'` - Accessible from all product URLs  
- **No products field**: Common documentation, accessible from all products

## 🧩 Available Components

### PerProduct - Product-Specific Content

Show content only for specific products:

```mdx
<PerProduct product="rails">
This content only shows when viewing Rails documentation.
</PerProduct>

<PerProduct product={['deploy', 'sites']}>
This shows for both Deploy and Sites products.
</PerProduct>

<PerProduct exclude={['rails']}>
This shows for all products except Rails.
</PerProduct>
```

### Tabs - Multi-Product/Multi-Option Content

Display tabbed content for different contexts:

```mdx
<TabsWrapper>
  <Tab title="Rails" product="rails">
    Rails-specific instructions here
  </Tab>
  <Tab title="Deploy" product="deploy">
    Deploy-specific instructions here
  </Tab>
  <Tab title="Node" product="node">
    Node-specific instructions here
  </Tab>
</TabsWrapper>
```

For non-product tabs:

```mdx
<TabsWrapper>
  <Tab title="macOS">
    macOS installation steps
  </Tab>
  <Tab title="Linux">
    Linux installation steps
  </Tab>
  <Tab title="Windows">
    Windows installation steps
  </Tab>
</TabsWrapper>
```

### Callout - Important Information

Highlight important information, warnings, or tips:

```mdx
<Callout type="info">
This is an informational note.
</Callout>

<Callout type="warning">
This is a warning message.
</Callout>

<Callout type="danger">
This is a critical warning.
</Callout>

<Callout type="success">
This indicates success or completion.
</Callout>
```

### Figure - Images with Captions

Display images with optional captions:

```mdx
<Figure src="/images/dashboard.png" alt="Cloud66 Dashboard" caption="The main Cloud66 dashboard showing all your stacks" />

<!-- Without caption -->
<Figure src="/images/settings.png" alt="Settings page" />
```

### Code Blocks - Syntax-Highlighted Code

**PREFERRED:** Use standard markdown triple backticks for code blocks:

```ruby
class User < ApplicationRecord
  validates :email, presence: true
end
```

```yaml
production:
  database: myapp_production
  host: localhost
```

Note: The `<CodeBlock>` component is available but markdown syntax is preferred.

### Tables - Data Display

**PREFERRED:** Use standard markdown table syntax:

```markdown
| Command | Description |
|---------|-------------|
| cx stacks list | List all your stacks |
| cx deploy | Deploy your application |
```

Which renders as:

| Command | Description |
|---------|-------------|
| cx stacks list | List all your stacks |
| cx deploy | Deploy your application |

Note: The `<Table>` component is available for complex tables but markdown syntax is preferred for simple tables.

### SmartLink - Dynamic Product/Version Links

Links that automatically adapt to the current product and version:

```mdx
<!-- Use placeholders in links -->
[View guide](/:product/:version?/getting-started/guide)

<!-- Becomes -->
<!-- /rails/getting-started/guide (for Rails) -->
<!-- /deploy/2/getting-started/guide (for Deploy v2) -->
<!-- /deploy/getting-started/guide (for Deploy latest) -->
```

**Placeholders:**
- `:product` - Current product (rails, deploy, etc.)
- `:version` - Current version with number (includes version in path)
- `:version?` - Optional version (only includes if version is set)

### InlineCode - Inline Code Snippets

For inline code within text:

```mdx
Use the `cx deploy` command to deploy your application.
```

### Pre - Preformatted Text

For terminal output or logs:

```mdx
<Pre>
$ cx stacks list
NAME          ENVIRONMENT    STATUS
my-app        production     Live
staging-app   staging        Live
</Pre>
```

## ⚠️ Important Notes

### Component Usage

**DO NOT import components in MDX files!** All components are automatically available through the MDX context system. Simply use them directly:

```mdx
<!-- ✅ CORRECT -->
<Callout type="info">
  This is the right way
</Callout>

<!-- ❌ WRONG -->
import { Callout } from '@/components/Callout'
<Callout type="info">
  Don't do this
</Callout>
```

### Navigation Ordering

1. Categories are ordered by the `sequence` field in the main site's config
2. Pages within categories are ordered by `_order.yaml` files in each category folder
3. Create an `_order.yaml` file to control page order:

```yaml
# /rails/getting-started/_order.yaml
- introduction
- quick-start
- installation
- configuration
```

### File Naming Conventions

- Use lowercase with hyphens: `getting-started.mdx`, not `GettingStarted.mdx`
- Toolbelt commands start with underscore: `_cx-deploy.mdx`
- Partials go in `partials/` subfolder: `partials/_common-steps.mdx`
- Version-specific files go in version folder: `1/legacy-feature.mdx`

## 🔍 Testing Your Documentation

Since this is a content repository, testing requires the main documentation site:

1. **Clone this repo as a submodule** in the main site
2. **Preview locally**: Run the main site's development server
3. **Test all products**: If your page has `products: ['rails', 'deploy']`, test both URLs
4. **Check navigation**: Ensure your page appears in the sidebar correctly
5. **Validate MDX**: The main site's build process validates MDX syntax
6. **Test links**: Click all links to ensure they work
7. **Test components**: Verify all components render correctly
8. **Mobile view**: Check responsiveness on mobile viewport

## 💡 Best Practices

1. **Use semantic headings**: Start with `##` (h2) for main sections
2. **Add IDs to headings** for deep linking: `## Installation {#install}`
3. **Keep paragraphs short**: Aim for 2-3 sentences max
4. **Use lists** for step-by-step instructions
5. **Include code examples** where relevant
6. **Add alt text** to all images
7. **Use product-specific content** sparingly - prefer common documentation
8. **Test your links** with the SmartLink placeholders
9. **Provide context** in the `lead` frontmatter field
10. **Keep file names descriptive** but concise
11. **Prefer markdown syntax** for code blocks (triple backticks) and tables over components
12. **Use standard markdown** features where possible for better readability and maintainability

## 🆘 Getting Help

- Check existing documentation for examples
- Review component usage in this README
- Test your changes using the main documentation site
- Validate MDX syntax through the main site's build process
- Ask in the development channel for complex routing questions

## 📦 Working with This Repository

### As a Content Writer

1. **Clone this repository**: `git clone [repo-url]`
2. **Create a new branch**: `git checkout -b feature/new-documentation`
3. **Add or edit MDX files** following the guidelines above
4. **Commit your changes**: `git commit -m "Add documentation for [feature]"`
5. **Push to remote**: `git push origin feature/new-documentation`
6. **Create a pull request** for review

### Integration with Main Site

This repository is integrated as a git submodule in the main documentation platform. When your changes are merged:

1. The main site's submodule reference will be updated
2. The site will be rebuilt with your new content
3. Your documentation will be live on help.cloud66.com