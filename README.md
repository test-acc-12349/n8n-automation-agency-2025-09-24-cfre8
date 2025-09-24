# n8n Automation Agency Landing Page - Maintenance Guide

This README provides comprehensive guidance for maintaining and customizing the n8n Automation Agency landing page. This guide is designed for beginners with little to no prior HTML or CSS knowledge.

## Table of Contents

1. [Introduction](#introduction)
2. [Page Structure Overview](#page-structure-overview)
3. [Updating Text Content](#updating-text-content)
4. [Modifying Tailwind CSS Classes](#modifying-tailwind-css-classes)
5. [Managing Links](#managing-links)
6. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
7. [Customizing Images](#customizing-images)
8. [Troubleshooting](#troubleshooting)

## Introduction

This landing page is built using:
- HTML5 for structure
- Tailwind CSS for styling (loaded via CDN)
- Alpine.js for interactive components (loaded via CDN)
- Font Awesome for icons
- Google Fonts (Inter font family)

The page is fully responsive and designed to work well on mobile, tablet, and desktop devices.

## Page Structure Overview

The landing page consists of these main sections:

1. **Header Navigation**: The sticky navigation bar at the top
2. **Hero Section**: The main banner with call-to-action buttons
3. **Features Section**: Highlighting key features with icons
4. **Benefits Section**: Benefits with image and text
5. **How It Works Section**: Step-by-step process explanation
6. **CTA Section**: Call-to-action with gradient background
7. **FAQ Section**: Expandable questions and answers
8. **Footer** (not included in the provided HTML, but should be added)

## Updating Text Content

### Header and Navigation

To update the company name in the header:

```html
<!-- Find this in the header section -->
<a href="#" class="text-2xl font-bold text-blue-600 flex items-center">
    <i class="fas fa-bolt mr-2"></i>
    <span>n8n Agency</span>  <!-- Change this text -->
</a>
```

To modify navigation menu items:

```html
<!-- Desktop Navigation -->
<nav class="hidden md:flex space-x-10">
    <a href="#features" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Features</a>  <!-- Change "Features" to your preferred text -->
    <a href="#benefits" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Benefits</a>  <!-- Change "Benefits" to your preferred text -->
    <a href="#faq" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">FAQ</a>  <!-- Change "FAQ" to your preferred text -->
    <a href="#contact" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Contact</a>  <!-- Change "Contact" to your preferred text -->
</nav>
```

Remember to update both the desktop navigation and mobile navigation menus to keep them consistent:

```html
<!-- Mobile Menu -->
<div x-show="open" @click.away="open = false" class="absolute top-20 right-0 left-0 bg-white shadow-md rounded-lg p-4 mx-4">
    <div class="flex flex-col space-y-4">
        <a href="#features" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Features</a>  <!-- Change text here too -->
        <a href="#benefits" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Benefits</a>  <!-- Change text here too -->
        <a href="#faq" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">FAQ</a>  <!-- Change text here too -->
        <a href="#contact" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Contact</a>  <!-- Change text here too -->
    </div>
</div>
```

### Hero Section

To update the main headline:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6 leading-tight tracking-tight">
    n8n Automation Agency  <!-- Change this headline -->
</h1>
```

To update the subheading:

```html
<p class="text-xl md:text-2xl text-gray-700 mb-10 leading-relaxed">
    n8n automation for any business  <!-- Change this subheading -->
</p>
```

To update the call-to-action buttons:

```html
<a href="https://test.com" class="w-full sm:w-auto inline-flex justify-center items-center px-8 py-4 border border-transparent text-base md:text-lg font-medium rounded-md shadow-lg text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 transform hover:scale-105">
    Automate Your Business  <!-- Change this button text -->
    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M10.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L12.586 11H5a1 1 0 110-2h7.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
    </svg>
</a>
```

### Features Section

To update the features section heading and subheading:

```html
<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4 tracking-tight">
    Powerful n8n Automation Features  <!-- Change this heading -->
</h2>
<p class="text-lg md:text-xl text-gray-600">
    Streamline your workflows with our cutting-edge automation solutions  <!-- Change this subheading -->
</p>
```

To update a feature card:

```html
<div class="bg-white rounded-xl shadow-lg hover:shadow-xl p-8 border border-gray-100 transition duration-300 transform hover:scale-105">
    <div class="bg-blue-100 rounded-full w-14 h-14 flex items-center justify-center mb-6">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-blue-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
        </svg>
    </div>
    <h3 class="text-xl font-bold text-gray-900 mb-3">Super Fast</h3>  <!-- Change feature title -->
    <p class="text-gray-600 leading-relaxed">
        Implement automation solutions at lightning speed. Our n8n workflows are optimized for performance and quick deployment, getting you results in days, not months.  <!-- Change feature description -->
    </p>
</div>
```

### FAQ Section

To update a FAQ question and answer:

```html
<div class="mb-5">
    <button 
        @click="selected !== 1 ? selected = 1 : selected = null" 
        class="flex justify-between items-center w-full px-6 py-5 text-left bg-white rounded-lg shadow-md hover:shadow-lg focus:outline-none"
        :class="{'bg-blue-50': selected === 1}"
    >
        <span class="text-lg font-semibold text-gray-900">What is n8n and how can it help my business?</span>  <!-- Change question text -->
        <svg 
            class="w-6 h-6 text-blue-600 transform transition-transform duration-300" 
            :class="{'rotate-180': selected === 1}"
            fill="none" 
            viewBox="0 0 24 24" 
            stroke="currentColor"
        >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
    </button>
    <div 
        x-show="selected === 1" 
        x-transition:enter="transition ease-out duration-300"
        x-transition:enter-start="opacity-0 transform -translate-y-4"
        x-transition:enter-end="opacity-100 transform translate-y-0"
        x-transition:leave="transition ease-in duration-300"
        x-transition:leave-start="opacity-100 transform translate-y-0"
        x-transition:leave-end="opacity-0 transform -translate-y-4"
        class="px-6 py-4 bg-white rounded-b-lg shadow-md mt-1"
    >
        <p class="text-gray-600 leading-relaxed">
            n8n is a powerful workflow automation tool that allows businesses to connect different applications, services, and databases to automate repetitive tasks. It helps businesses save time, reduce errors, and improve overall productivity by creating automated workflows that can run with minimal human intervention.  <!-- Change answer text -->
        </p>
    </div>
</div>
```

To add a new FAQ item, copy the entire question block and:
1. Change the number in the `@click` attribute (e.g., `selected !== 3 ? selected = 3 : selected = null`)
2. Change the number in the `:class` attributes (e.g., `{'bg-blue-50': selected === 3}` and `{'rotate-180': selected === 3}`)
3. Change the number in the `x-show` attribute (e.g., `x-show="selected === 3"`)
4. Update the question and answer text

## Modifying Tailwind CSS Classes

Tailwind CSS uses utility classes to style elements. Here's what some of the common classes in this landing page mean:

### Text Styling

- `text-gray-900`: Dark gray text color
- `text-blue-600`: Blue text color
- `text-white`: White text color
- `text-xl`, `text-2xl`, `text-3xl`: Text size (extra large, 2x extra large, etc.)
- `font-bold`: Bold text
- `font-medium`: Medium weight text
- `tracking-tight`: Tighter letter spacing
- `leading-relaxed`: Relaxed line height

To change text color, replace the color and intensity:
```html
<h1 class="text-gray-900">Dark Gray Heading</h1>
<!-- Change to: -->
<h1 class="text-blue-900">Dark Blue Heading</h1>
```

### Spacing

- `p-8`: Padding on all sides (8 units)
- `px-4`: Horizontal padding (4 units)
- `py-16`: Vertical padding (16 units)
- `m-4`: Margin on all sides (4 units)
- `mb-6`: Bottom margin (6 units)
- `mt-2`: Top margin (2 units)
- `space-x-10`: Horizontal space between child elements (10 units)

### Layout

- `flex`: Flexible box layout
- `grid`: CSS grid layout
- `grid-cols-1 md:grid-cols-3`: 1 column on mobile, 3 columns on medium screens
- `items-center`: Center items vertically
- `justify-center`: Center items horizontally
- `hidden md:flex`: Hidden on mobile, flex on medium screens

### Background and Borders

- `bg-white`: White background
- `bg-blue-600`: Blue background
- `bg-gradient-to-r from-blue-600 to-indigo-700`: Gradient background
- `rounded-lg`: Large border radius
- `shadow-md`: Medium shadow
- `border border-gray-100`: Gray border

### Responsive Design

Tailwind uses prefixes to apply styles at specific breakpoints:
- `sm:`: Small screens (640px and up)
- `md:`: Medium screens (768px and up)
- `lg:`: Large screens (1024px and up)
- `xl:`: Extra large screens (1280px and up)

Example:
```html
<div class="text-base md:text-lg lg:text-xl">
    <!-- Text is base size on mobile, large on medium screens, extra large on large screens -->
</div>
```

### Changing Colors

To change the primary color scheme from blue to another color (e.g., green):

1. Find all instances of `blue` classes (`text-blue-600`, `bg-blue-100`, etc.)
2. Replace with the corresponding green classes (`text-green-600`, `bg-green-100`, etc.)

Example:
```html
<button class="bg-blue-600 hover:bg-blue-700 text-white">
<!-- Change to: -->
<button class="bg-green-600 hover:bg-green-700 text-white">
```

## Managing Links

### Fixing Navigation Links

The navigation menu contains internal links to page sections:

```html
<nav class="hidden md:flex space-x-10">
    <a href="#features" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Features</a>
    <a href="#benefits" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Benefits</a>
    <a href="#faq" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">FAQ</a>
    <a href="#contact" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Contact</a>
</nav>
```

To ensure these links work correctly:

1. Check that each section has the correct `id` attribute matching the link:
   ```html
   <section id="features" class="py-16 md:py-24 bg-white">
   ```

2. If you're adding a new section, add the appropriate `id`:
   ```html
   <section id="testimonials" class="py-16 md:py-24 bg-gray-50">
   ```

3. Then update the navigation links to point to the new section:
   ```html
   <a href="#testimonials" class="text-base font-medium text-gray-700 hover:text-blue-600 transition duration-300">Testimonials</a>
   ```

### Updating External Links

The landing page contains external links like:

```html
<a href="https://test.com" class="inline-flex items-center px-6 py-2 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 transform hover:scale-105">
    Get Started
</a>
```

To update these links:

1. Replace `https://test.com` with your actual URL
2. Make sure to update all instances of this URL throughout the page
3. Common places to check:
   - Header "Get Started" button
   - Hero section buttons
   - CTA section buttons

### Identifying All Links to Update

Here's a list of all the external links in the page that need to be updated:

1. Header "Get Started" button:
   ```html
   <a href="https://test.com" class="inline-flex items-center px-6 py-2 border border-transparent text-base font-medium rounded-md shadow-sm text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 transform hover:scale-105">
   ```

2. Hero section "Automate Your Business" button:
   ```html
   <a href="https://test.com" class="w-full sm:w-auto inline-flex justify-center items-center px-8 py-4 border border-transparent text-base md:text-lg font-medium rounded-md shadow-lg text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 transform hover:scale-105">
   ```

3. CTA section "Get Started Today" button:
   ```html
   <a href="https://test.com" class="w-full sm:w-auto inline-flex justify-center items-center px-8 py-4 border border-transparent text-lg font-medium rounded-md shadow-lg text-blue-700 bg-white hover:bg-blue-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500 transition duration-300 transform hover:scale-105">
   ```

## Adding Privacy and Terms Pages

The landing page doesn't currently have links to Privacy Policy and Terms of Service pages. Here's how to add them:

### 1. Create a Footer Section

First, add a footer section at the end of the body, just before the closing `</body>` tag:

```html
<!-- Footer Section -->
<footer class="bg-gray-800 text-white py-12">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
            <!-- Company Info -->
            <div class="md:col-span-2">
                <a href="#" class="text-xl font-bold text-white flex items-center mb-4">
                    <i class="fas fa-bolt mr-2"></i>
                    <span>n8n Agency</span>
                </a>
                <p class="text-gray-400 mb-4">
                    Streamlining your business processes with powerful n8n automation solutions.
                </p>
                <div class="flex space-x-4">
                    <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                        <i class="fab fa-twitter"></i>
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                        <i class="fab fa-linkedin"></i>
                    </a>
                    <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                        <i class="fab fa-facebook"></i>
                    </a>
                </div>
            </div>
            
            <!-- Quick Links -->
            <div>
                <h3 class="text-lg font-semibold mb-4">Quick Links</h3>
                <ul class="space-y-2">
                    <li><a href="#features" class="text-gray-400 hover:text-white transition duration-300">Features</a></li>
                    <li><a href="#benefits" class="text-gray-400 hover:text-white transition duration-300">Benefits</a></li>
                    <li><a href="#faq" class="text-gray-400 hover:text-white transition duration-300">FAQ</a></li>
                    <li><a href="#contact" class="text-gray-400 hover:text-white transition duration-300">Contact</a></li>
                </ul>
            </div>
            
            <!-- Contact Info -->
            <div>
                <h3 class="text-lg font-semibold mb-4">Contact Us</h3>
                <ul class="space-y-2">
                    <li class="flex items-start">
                        <i class="fas fa-envelope text-gray-400 mt-1 mr-2"></i>
                        <span class="text-gray-400">info@n8nagency.com</span>
                    </li>
                    <li class="flex items-start">
                        <i class="fas fa-phone text-gray-400 mt-1 mr-2"></i>
                        <span class="text-gray-400">+1 (555) 123-4567</span>
                    </li>
                </ul>
            </div>
        </div>
        
        <!-- Legal Links -->
        <div class="border-t border-gray-700 mt-12 pt-8 flex flex-col md:flex-row justify-between items-center">
            <p class="text-gray-400 mb-4 md:mb-0">
                &copy; 2023 n8n Agency. All rights reserved.
            </p>
            <div class="flex space-x-6">
                <a href="privacy.html" class="text-gray-400 hover:text-white transition duration-300">Privacy Policy</a>
                <a href="terms.html" class="text-gray-400 hover:text-white transition duration-300">Terms of Service</a>
            </div>
        </div>
    </div>
</footer>
```

### 2. Create Privacy and Terms Pages

Create two new HTML files in the same directory as your index.html:

**privacy.html**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Privacy Policy | n8n Automation Agency</title>
    <meta name="description" content="Privacy policy for n8n Automation Agency services.">
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="antialiased text-gray-800 bg-white">
    <!-- Copy the header from index.html -->
    
    <!-- Privacy Content -->
    <section class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto">
                <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-8 tracking-tight">
                    Privacy Policy
                </h1>
                
                <!-- Add your privacy policy content here -->
                <div class="prose prose-lg max-w-none">
                    <p>Last updated: [Date]</p>
                    <p>This Privacy Policy describes how n8n Automation Agency ("we", "us", or "our") collects, uses, and discloses your personal information when you visit our website or use our services.</p>
                    
                    <h2>Information We Collect</h2>
                    <p>Add your privacy policy content here...</p>
                    
                    <!-- Continue with the rest of your privacy policy -->
                </div>
            </div>
        </div>
    </section>
    
    <!-- Copy the footer from index.html -->
</body>
</html>
```

**terms.html**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Terms of Service | n8n Automation Agency</title>
    <meta name="description" content="Terms of service for n8n Automation Agency services.">
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="antialiased text-gray-800 bg-white">
    <!-- Copy the header from index.html -->
    
    <!-- Terms Content -->
    <section class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto">
                <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-8 tracking-tight">
                    Terms of Service
                </h1>
                
                <!-- Add your terms of service content here -->
                <div class="prose prose-lg max-w-none">
                    <p>Last updated: [Date]</p>
                    <p>Please read these Terms of Service carefully before using the n8n Automation Agency website or services.</p>
                    
                    <h2>1. Agreement to Terms</h2>
                    <p>Add your terms of service content here...</p>
                    
                    <!-- Continue with the rest of your terms -->
                </div>
            </div>
        </div>
    </section>
    
    <!-- Copy the footer from index.html -->
</body>
</html>
```

### 3. Link to Privacy and Terms Pages

The links to these pages are already included in the footer code above:

```html
<div class="flex space-x-6">
    <a href="privacy.html" class="text-gray-400 hover:text-white transition duration-300">Privacy Policy</a>
    <a href="terms.html" class="text-gray-400 hover:text-white transition duration-300">Terms of Service</a>
</div>
```

## Customizing Images

The landing page uses background images in several sections. To update these:

### Hero Section Background

```html
<div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1579403124614-197f69d8187b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80')] bg-cover bg-center opacity-5"></div>
```

To change this image:
1. Replace the URL in `bg-[url('...')]` with your new image URL
2. You can adjust the opacity by changing `opacity-5` (5% opacity)

### Benefits Section Image

```html
<img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80" alt="n8n Automation Dashboard" class="w-full h-auto rounded-2xl transform transition duration-500 hover:scale-105">
```

To change this image:
1. Replace the `src` attribute with your new image URL
2. Update the `alt` text to describe your new image

### CTA Section Background

```html
<div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1557804506-669a67965ba0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2074&q=80')] bg-cover bg-center opacity-10"></div>
```

To change this image:
1. Replace the URL in `bg-[url('...')]` with your new image URL
2. You can adjust the opacity by changing `opacity-10` (10% opacity)

## Troubleshooting

### Common Issues and Solutions

#### Navigation Links Not Working

If clicking on navigation links doesn't scroll to the correct section:

1. Check that the `href` attribute in your navigation links matches the `id` of the target section:
   ```html
   <a href="#features">Features</a>
   ```
   should match:
   ```html
   <section id="features">...</section>
   ```

2. Make sure there are no duplicate `id` attributes on the page.

#### Mobile Menu Not Working

If the mobile menu doesn't open when clicked:

1. Verify that Alpine.js is properly loaded:
   ```html
   <script src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
   ```

2. Check that the mobile menu toggle has the correct Alpine.js directives:
   ```html
   <div class="md:hidden" x-data="{ open: false }">
       <button @click="open = !open" class="...">
   ```

#### Styling Issues

If styles are not applying correctly:

1. Verify that Tailwind CSS is properly loaded:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```

2. Check for any typos in class names.

3. For responsive issues, test at different screen sizes and check that the appropriate responsive prefixes (`sm:`, `md:`, `lg:`) are being used.

#### Images Not Loading

If images are not displaying:

1. Check that the image URLs are correct and accessible.
2. Verify that the images are not being blocked by CORS policies if using external sources.
3. Consider using relative paths for local images (e.g., `/images/hero.jpg`).

### Getting Help

If you encounter issues beyond the scope of this guide:

1. Refer to the official documentation:
   - [Tailwind CSS Documentation](https://tailwindcss.com/docs)
   - [Alpine.js Documentation](https://alpinejs.dev/start-here)
   - [Font Awesome Documentation](https://fontawesome.com/docs)

2. Inspect the page using browser developer tools (F12 or right-click and select "Inspect") to identify specific issues.

3. Consider using online validators to check your HTML:
   - [W3C HTML Validator](https://validator.w3.org/)