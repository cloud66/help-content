# Cloud 66 Documentation Writing Guide

Welcome to the Cloud 66 documentation! This guide will help you write, format, and structure documentation for our products using MDX.

## Quick Start

1. Create MDX files in appropriate product directories: `rails/`, `deploy/`, `sites/`, `node/`, or `common/`
2. Add proper frontmatter with title, description, lead, and products
3. Use available components to enhance your content
4. Test locally with `yarn dev`
5. Validate with `yarn validate:mdx` before submitting

## File Structure & Organization

```
/src/docs/
├── rails/              # Rails-specific documentation
├── deploy/             # Deploy-specific documentation 
│   ├── 1/             # Deploy v1 legacy content
│   └── 2/             # Deploy v2 content (v3 uses base folder)
├── sites/              # Sites-specific documentation
├── node/               # Node-specific documentation (legacy product)
├── common/             # Shared documentation across all products
└── partials/           # Reusable content snippets (not directly accessible)
```

### File Naming Conventions

- Use lowercase kebab-case: `building-your-service.mdx`
- Be descriptive and specific: `connecting-between-containerized-services.mdx`
- Avoid abbreviations unless well-known: `api-keys.mdx` not `api-keys.mdx`

### Navigation Order Control

Use `_order.yaml` files to control the order of documents within categories:

```yaml
# /src/docs/getting-started/_order.yaml
- quick-start
- deploy-your-first-app
- migrate-from-heroku
- migrate-from-forge
```

**Rules:**
- Place `_order.yaml` in each category directory
- List file names (without `.mdx` extension) in desired order
- Files not listed in `_order.yaml` will appear after ordered files
- Categories themselves are ordered by the `sequence` field in `/src/config/products.ts`

## MDX Frontmatter

Every MDX file must include frontmatter metadata at the top:

### Basic Frontmatter

```yaml
---
title: "Your Page Title"
description: "Brief description for SEO (150-160 characters ideal)"
lead: "Extended description shown at top of page (optional)"
products: ['rails', 'deploy']
---
```

### Product Targeting Options

**Specific products:**
```yaml
products: ['rails', 'deploy']  # Only accessible on Rails and Deploy
```

**All products:**
```yaml
products: 'all'  # Accessible from all product routes
```

**Common (no products field):**
```yaml
# No products field = accessible on all products + /common/ routes
```

### Version Control (Deploy Only)

**Hide from specific versions:**
```yaml
excludeVersions: ['2']  # Hide from Deploy v2, show on v1 and v3
```

**Show only in specific versions:**
```yaml
includeVersions: ['1']  # Only show in Deploy v1
```

**Important:** `excludeVersions` and `includeVersions` are mutually exclusive.

### Multi-Version Documents

For Deploy product, you can create version-specific content:

```
/src/docs/category/
  └── page.mdx           # Default/latest version (v3)
  └── 1/
      └── page.mdx       # Version 1 specific content
  └── 2/
      └── page.mdx       # Version 2 specific content (optional)
```

The system will automatically serve the appropriate version based on the URL.

## Available Components

### Content Organization

#### PerProduct
Show/hide content based on the active product:

```mdx
<PerProduct includes={["rails"]}>
This content only shows for Rails users.
</PerProduct>

<PerProduct includes={["deploy", "node"]}>
This content shows for Deploy and Node users.
</PerProduct>

<PerProduct excludes={["sites"]}>
This content shows for all products except Sites.
</PerProduct>

<PerProduct includeVersions={["1"]}>
This content only shows for Deploy v1 users.
</PerProduct>

<PerProduct excludeVersions={["2"]}>
This content shows for all Deploy versions except v2.
</PerProduct>
```

#### Tabs
Create tabbed content for different scenarios:

```mdx
<Tabs defaultValue="rails">
  <TabsList>
    <TabsTrigger value="rails">Rails</TabsTrigger>
    <TabsTrigger value="express">Express</TabsTrigger>
    <TabsTrigger value="django">Django</TabsTrigger>
  </TabsList>
  
  <TabsContent value="rails">
    Rails-specific content here.
  </TabsContent>
  
  <TabsContent value="express">
    Express-specific content here.
  </TabsContent>
  
  <TabsContent value="django">
    Django-specific content here.
  </TabsContent>
</Tabs>
```

#### FilteredContentBox
Create content with a dropdown filter:

```mdx
<FilteredContentBox labels={["AWS", "GCP", "Azure"]} defaultFilter="AWS">
  <FilteredContent filter="AWS">
    AWS-specific instructions here.
  </FilteredContent>
  
  <FilteredContent filter="GCP">
    Google Cloud specific instructions here.
  </FilteredContent>
  
  <FilteredContent filter="Azure">
    Azure-specific instructions here.
  </FilteredContent>
</FilteredContentBox>
```

### Alerts & Callouts

#### Callout
Highlight important information:

```mdx
<Callout type="info" title="Information">
General information or tips.
</Callout>

<Callout type="warning" title="Important">
Something users should be careful about.
</Callout>

<Callout type="error" title="Warning">
Critical information or potential issues.
</Callout>
```

#### Alert
Basic alert component:

```mdx
<Alert>
  <AlertTitle>Notice</AlertTitle>
  <AlertDescription>
    Basic alert with optional title and description.
  </AlertDescription>
</Alert>
```

### Interactive Elements

#### Collapsible
Expandable content sections:

```mdx
<Collapsible title="Advanced Configuration">
  This content is hidden by default and can be expanded by clicking the title.
  
  You can include any markdown or components here.
</Collapsible>
```

#### Hint
Tooltips for additional context:

```mdx
<Hint caption="hover me">
  Additional information shown on hover.
</Hint>
```

### Visual Elements

#### Figure
Images with captions:

```mdx
<Figure 
  src="/path/to/image.png" 
  alt="Descriptive alt text"
  caption="Optional caption explaining the image" 
/>
```

#### Badge
Small status indicators:

```mdx
<Badge variant="default">New</Badge>
<Badge variant="secondary">Beta</Badge>
<Badge variant="destructive">Deprecated</Badge>
<Badge variant="outline">Optional</Badge>
```

#### Pill
Rounded status indicators:

```mdx
<Pill>Status</Pill>
```

#### Button
Interactive buttons (use sparingly):

```mdx
<Button variant="default">Primary Action</Button>
<Button variant="outline">Secondary Action</Button>
<Button variant="ghost">Subtle Action</Button>
```

### Specialized Components

#### ComponentVersion
Display version-specific information:

```mdx
<ComponentVersion version="2.1.0" />
```

#### IpList
Display Cloud 66 IP addresses:

```mdx
<IpList />
```

#### Glyph
Special typography elements:

```mdx
<Glyph>Special symbol or icon</Glyph>
```

#### CodeBlock
Enhanced code blocks with syntax highlighting:

```mdx
<CodeBlock language="bash" title="Installation">
npm install @cloud66/cli
</CodeBlock>
```

## Smart Links

Links automatically adapt to the current product and version context:

```mdx
[Getting Started](/:product/:version?/getting-started/quick-start)
[API Reference](/:product/api/overview)
[Common Guide](/common/shared-guide)
```

**Placeholders:**
- `:product` - Current product (rails, deploy, sites, node)
- `:version` - Current version (includes version in path if set)
- `:version?` - Optional version (includes version only if viewing a specific version)

## Markdown Features

### Standard Markdown
All GitHub Flavored Markdown is supported:

- **Bold** and *italic* text
- `inline code`
- [Links](https://cloud66.com)
- Lists (ordered and unordered)
- Headers (H1-H6)
- Tables
- Blockquotes
- Horizontal rules

### Code Blocks
Fenced code blocks with syntax highlighting:

```bash
# This is a bash command
kubectl get pods
```

```yaml
# YAML configuration
apiVersion: v1
kind: Service
metadata:
  name: my-service
```

```javascript
// JavaScript code
const config = {
  apiKey: process.env.API_KEY,
  timeout: 5000
};
```

### Tables
Standard Markdown tables with enhanced styling:

| Feature | Rails | Deploy | Sites |
|---------|-------|--------|-------|
| SSL | ✅ | ✅ | ✅ |
| Auto-scaling | ✅ | ✅ | ❌ |
| Databases | ✅ | ✅ | ❌ |

## Importing Partials

Reuse content across multiple pages by importing partials:

```mdx
import GitPartial from '../partials/_git.mdx';
import SshKeysPartial from '../partials/_ssh_keys.mdx';

<GitPartial />

## Next Steps

<SshKeysPartial />
```

**Partial naming:** Always prefix with underscore (`_git.mdx`, `_ssh_keys.mdx`)

## Writing Best Practices

### Content Structure

1. **Start with context:** Explain what the reader will learn
2. **Use clear headings:** Structure content hierarchically
3. **Include prerequisites:** List what readers need before starting
4. **Provide examples:** Show real code and configurations
5. **End with next steps:** Guide readers to related content

### Writing Style

- **Be concise:** Get to the point quickly
- **Use active voice:** "Click the button" not "The button should be clicked"
- **Write for your audience:** Assume technical competency but explain Cloud 66-specific concepts
- **Be consistent:** Use the same terminology throughout

### Technical Guidelines

- **Test all code:** Ensure examples work as documented
- **Use realistic examples:** Avoid `foo`, `bar`, `example.com`
- **Include error handling:** Show what can go wrong and how to fix it
- **Update regularly:** Remove outdated information

### Accessibility

- **Alt text:** Always include descriptive alt text for images
- **Link text:** Use descriptive link text, not "click here"
- **Headings:** Use proper heading hierarchy (don't skip levels)
- **Lists:** Use proper list markup for sequential steps

## SEO Guidelines

### Frontmatter SEO

```yaml
---
title: "Specific, descriptive title (50-60 chars)"
description: "Clear description with target keywords (150-160 chars)"
lead: "Engaging lead paragraph that expands on the description"
---
```

### Content SEO

- **Use headers:** Structure content with H2, H3, etc.
- **Internal linking:** Link to related Cloud 66 documentation
- **Keywords naturally:** Use relevant terms without keyword stuffing
- **Meta descriptions:** Write compelling descriptions for search results

## Validation & Testing

### Before Submitting

1. **Test locally:** Run `yarn dev` and verify your content renders correctly
2. **Validate MDX:** Run `yarn validate:mdx` to check for syntax errors
3. **Check links:** Run `yarn validate:links` to verify internal links
4. **Test components:** Ensure all components render and function properly
5. **Review product targeting:** Verify content appears on correct products

### Common Issues

- **Missing frontmatter:** Every file needs title and description
- **Broken imports:** Check partial paths are correct
- **Component props:** Ensure all required props are provided
- **Link validation:** Use correct paths for internal links
- **Version conflicts:** Don't use both `includeVersions` and `excludeVersions`

## Getting Help

- **Technical issues:** Check the main project README for development commands
- **Component questions:** Refer to component source code in `/src/components/`
- **Style guide:** Follow existing documentation patterns
- **Questions:** Ask the development team for clarification

---

Happy writing! 🚀