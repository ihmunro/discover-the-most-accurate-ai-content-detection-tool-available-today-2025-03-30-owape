# Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the AI Content Detection Tool landing page. Whether you're new to web development or need a quick reference, follow these steps to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains your brand name and navigation menu. To update:

1. **Brand Name**
```html
<!-- Located in the header section -->
<a href="/" class="text-2xl font-bold">Sense</a>
```
Simply replace "Sense" with your brand name. The `text-2xl` class controls the size, and `font-bold` controls the weight.

2. **Navigation Menu Items**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-gray-900 transition-colors duration-200">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-gray-900 transition-colors duration-200">Benefits</a>
    <a href="#faq" class="text-gray-600 hover:text-gray-900 transition-colors duration-200">FAQ</a>
</div>
```
- To add new menu items, copy an existing `<a>` tag and modify the `href` and text content
- The `hidden md:flex` class hides the menu on mobile and shows it on medium screens
- `space-x-8` adds horizontal spacing between items

### Hero Section
```html
<h1 class="text-4xl md:text-6xl font-bold leading-tight mb-6">
    Discover the Most Accurate AI Content Detection Tool Available Today
</h1>
```
- Update the heading text between the `<h1>` tags
- `text-4xl` sets mobile size, `md:text-6xl` sets desktop size
- `mb-6` adds bottom margin spacing

### Features Section
To add or modify features:
```html
<div class="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all duration-300 transform hover:scale-105">
    <div class="text-blue-600 mb-4">
        <i class="fas fa-bolt text-4xl"></i>
    </div>
    <h3 class="text-xl font-bold mb-4">Real-Time Detection</h3>
    <p class="text-gray-600">Instant analysis and detection...</p>
</div>
```
- Copy this entire block to add new features
- Change the icon by updating the `fa-bolt` class to any [Font Awesome](https://fontawesome.com/icons) icon
- Update the heading and description text

## Fixing Broken Links

### Current Link Inventory
1. Navigation Menu Links:
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
```
These are internal anchor links. Ensure the `href` matches the `id` of the target section.

2. Call-to-Action Links:
```html
<a href="https://stripe.com/buynow" class="bg-blue-600 text-white px-6 py-2 rounded-full">
    Buy Now
</a>
```
Replace `https://stripe.com/buynow` with your actual payment or signup URL.

3. Footer Links:
```html
<div class="flex space-x-4 mt-4">
    <a href="#" class="hover:text-blue-400">
        <i class="fab fa-twitter"></i>
    </a>
</div>
```
Replace `#` with your actual social media profile URLs.

### Updating Links Step-by-Step
1. Locate the link you want to update
2. Replace the `href="#"` or existing URL with your new URL
3. Test the link by clicking it
4. For external links, consider adding `target="_blank"` to open in a new tab:
```html
<a href="https://twitter.com/yourprofile" target="_blank" rel="noopener">
```

## Linking Privacy and Terms Pages

### Adding Policy Links
In the footer section, locate:
```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="#" class="hover:text-blue-400 transition-colors duration-200">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-blue-400 transition-colors duration-200">Terms of Service</a></li>
    </ul>
</div>
```

Update the links:
```html
<li><a href="privacy.html" class="hover:text-blue-400 transition-colors duration-200">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-blue-400 transition-colors duration-200">Terms of Service</a></li>
```

### Creating Policy Pages
1. Create new files named `privacy.html` and `terms.html` in the same directory
2. Copy the header and footer from `index.html` to maintain consistent styling
3. Add your policy content between the header and footer

## Troubleshooting

### Common Issues and Solutions

1. **Broken Responsive Design**
- If elements look wrong on mobile, check for proper responsive classes
- Ensure you have `md:` prefixes for desktop-specific styles
- Example: `class="text-4xl md:text-6xl"` means size 4xl on mobile, 6xl on desktop

2. **Missing Icons**
- If Font Awesome icons don't appear, verify the CDN link in the header:
```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
```

3. **Incorrect Spacing**
- Use Tailwind's spacing utilities:
  - `p-` for padding (p-4 = 1rem)
  - `m-` for margin (m-4 = 1rem)
  - `space-x-` for horizontal spacing between elements
  - `space-y-` for vertical spacing between elements

Remember to always test your changes across different screen sizes using browser developer tools (F12 in most browsers).