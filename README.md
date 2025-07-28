# Seamphony Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the Seamphony landing page. Whether you're new to web development or need a quick reference, follow these steps to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the company logo and navigation menu. To update:

1. **Company Name/Logo**
```html
<!-- Find this line in the header section -->
<a href="/" class="text-2xl font-bold text-indigo-600">Seamphony</a>
```
- Replace "Seamphony" with your company name
- Adjust text size using `text-2xl` (options: text-lg, text-xl, text-3xl)
- Change color using `text-indigo-600` (options: text-blue-600, text-green-600)

2. **Navigation Menu Items**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-indigo-600">Features</a>
    <!-- Additional menu items -->
</div>
```
- Update text between `<a>` tags
- Maintain the `hidden md:flex` class for proper mobile responsiveness
- `space-x-8` controls spacing between items (adjust number as needed)

### Hero Section
Located at the top of the page:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
    Smart CRM for Philippine Food Businesses—Costing, Pricing & Analytics
</h1>
```
- Update heading text while maintaining the multi-line structure
- Text sizes are responsive:
  - Mobile: `text-4xl`
  - Tablet: `md:text-5xl`
  - Desktop: `lg:text-6xl`

### Features Section
Each feature card follows this structure:
```html
<div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow duration-300">
    <!-- Icon container -->
    <div class="w-14 h-14 bg-indigo-100 rounded-xl flex items-center justify-center mb-6">
        <!-- SVG icon -->
    </div>
    <h3 class="text-xl font-semibold text-gray-900 mb-4">Feature Title</h3>
    <p class="text-gray-600">Feature description text here.</p>
</div>
```
- Update feature titles in `<h3>` tags
- Modify descriptions in `<p>` tags
- Maintain the class structure for consistent styling

## Fixing Broken Links

### Navigation Menu Links
Current internal links in the navigation:
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
<a href="#contact">Contact</a>
```
To update:
1. For internal page sections:
   - Keep the `#` prefix
   - Ensure the ID matches your section: `<section id="features">`
2. For external pages:
   - Replace `#section-name` with full URL
   - Example: `href="https://example.com/page"`

### Call-to-Action Buttons
```html
<a href="https://seamphonycrm.com" class="inline-block px-8 py-4 bg-indigo-600">
    Start Your Free Trial
</a>
```
- Replace `https://seamphonycrm.com` with your actual signup URL
- Test links after updating to ensure they work

## Linking Privacy and Terms Pages

### Footer Legal Links
Current placeholder links:
```html
<div>
    <h4 class="text-lg font-semibold text-white mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To update:
1. Create your policy pages (privacy.html, terms.html)
2. Update the href attributes:
```html
<li><a href="privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues and Solutions

1. **Broken Responsive Layout**
- Check that you haven't removed important Tailwind classes like `md:` or `lg:` prefixes
- Verify that `container` and `mx-auto` classes remain on parent elements

2. **Inconsistent Spacing**
- Look for missing `mb-` (margin-bottom) or `p-` (padding) classes
- Maintain the spacing hierarchy: sections use `py-24`, elements use `mb-4` to `mb-16`

3. **Missing Styles**
- Ensure the Tailwind CSS CDN link remains in the `<head>`:
```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
```

4. **Mobile Menu Issues**
- Verify Alpine.js is properly loaded:
```html
<script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
```
- Check that `x-data` and `x-show` directives remain intact

Remember to always test your changes across different screen sizes using browser developer tools before deploying updates.