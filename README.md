# CommandlineOS Landing Page - Maintenance & Customization Guide

A comprehensive guide for maintaining, updating, and customizing the CommandlineOS landing page. This documentation is designed for developers new to HTML and CSS.

---

## Table of Contents

1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [Updating Text Content](#updating-text-content)
4. [Managing Links](#managing-links)
5. [Customizing Styling with Tailwind CSS](#customizing-styling-with-tailwind-css)
6. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
7. [Common Tasks](#common-tasks)
8. [Troubleshooting](#troubleshooting)

---

## Overview

The CommandlineOS landing page is built using:

- **HTML5** - The structure and content of the page
- **Tailwind CSS** - A utility-first CSS framework for styling (loaded via CDN)
- **Font Awesome** - Icons throughout the page
- **Vanilla JavaScript** - Mobile menu and FAQ functionality

### Key Characteristics

- **Responsive Design** - Works on mobile, tablet, and desktop
- **Dark Theme** - Professional dark background with blue accents
- **Component-Based** - Organized into distinct sections (Header, Hero, Features, etc.)
- **No Build Process** - All CSS and JS are inline or via CDN—no compilation needed

---

## File Structure

Your project should be organized like this:

```
your-project-folder/
├── index.html              (Main landing page - the file provided)
├── privacy.html            (Privacy Policy page - you'll create this)
├── terms.html              (Terms of Service page - you'll create this)
├── blog.html               (Blog page - optional, referenced in footer)
└── assets/                 (Optional folder for images, if hosting locally)
    ├── images/
    └── styles/
```

**Note:** The current HTML uses external images from Unsplash and CDN resources. To host images locally, see the [Common Tasks](#common-tasks) section.

---

## Updating Text Content

### Understanding the HTML Structure

The landing page is divided into clear sections using `<section>` tags with `id` attributes:

```html
<section id="home">        <!-- Hero Section -->
<section id="features">    <!-- Features Section -->
<section id="benefits">    <!-- Benefits Section -->
<section id="about">       <!-- About Us Section -->
<section id="testimonials"><!-- Testimonials Section -->
<section id="faq">         <!-- FAQ Section -->
<section id="contact">     <!-- Contact Section -->
```

Each section has an ID that corresponds to navigation links, making it easy to locate content.

---

### 1. Updating the Header/Logo

**Location:** Lines 79-83 (inside the `<header>` tag)

**Current Code:**
```html
<a href="#home" class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">
    <i class="fas fa-terminal mr-2"></i>CommandlineOS
</a>
```

**How to Change:**

1. Open `index.html` in your text editor
2. Find the line containing `CommandlineOS` in the header
3. Replace `CommandlineOS` with your company name
4. To change the icon, visit [Font Awesome Icons](https://fontawesome.com/icons) and replace `fa-terminal` with your chosen icon

**Example - Changing to "MyCompanyCLI":**
```html
<a href="#home" class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">
    <i class="fas fa-code mr-2"></i>MyCompanyCLI
</a>
```

---

### 2. Updating the Hero Section (Main Headline)

**Location:** Lines 155-162

**Current Code:**
```html
<h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight tracking-tight">
    CommandlineOS <br class="hidden md:block" />
    <span class="bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">Build Your Company's Custom CLI</span>
</h1>

<p class="text-xl md:text-2xl lg:text-3xl text-gray-300 mb-12 max-w-3xl mx-auto leading-relaxed">
    Create. Customize. Command — Your CLI, Your Way.
</p>
```

**How to Change:**

- **Main Headline:** Replace `Build Your Company's Custom CLI` with your own headline
- **Tagline:** Replace `Create. Customize. Command — Your CLI, Your Way.` with your tagline

**Example:**
```html
<h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight tracking-tight">
    MyCompanyCLI <br class="hidden md:block" />
    <span class="bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">Streamline Your Development Pipeline</span>
</h1>

<p class="text-xl md:text-2xl lg:text-3xl text-gray-300 mb-12 max-w-3xl mx-auto leading-relaxed">
    Automate. Integrate. Dominate — Your Tools, Your Control.
</p>
```

---

### 3. Updating Feature Cards

**Location:** Lines 199-280 (Features Section)

Each feature card follows this structure:

```html
<div class="feature-card bg-gray-900 p-8 rounded-lg border border-gray-700 hover:border-blue-500">
    <div class="bg-blue-600 bg-opacity-20 w-16 h-16 rounded-lg flex items-center justify-center mb-6">
        <i class="fas fa-tools text-3xl text-blue-400"></i>
    </div>
    <h3 class="text-2xl font-bold mb-4">CLI Builder</h3>
    <p class="text-gray-400 mb-6 leading-relaxed">
        Intuitive drag-and-drop interface...
    </p>
    <ul class="space-y-3 text-gray-300">
        <li class="flex items-start">
            <i class="fas fa-check text-blue-400 mr-3 mt-1"></i>
            <span>Visual command builder</span>
        </li>
        <!-- More list items -->
    </ul>
</div>
```

**How to Change:**

1. **Change the Icon:** Replace `fa-tools` with any Font Awesome icon
2. **Change the Title:** Replace `CLI Builder` with your feature name
3. **Change the Description:** Replace the paragraph text
4. **Update Bullet Points:** Replace each `<span>` text with your features

**Example - Updating First Feature:**
```html
<div class="feature-card bg-gray-900 p-8 rounded-lg border border-gray-700 hover:border-blue-500">
    <div class="bg-blue-600 bg-opacity-20 w-16 h-16 rounded-lg flex items-center justify-center mb-6">
        <i class="fas fa-rocket text-3xl text-blue-400"></i>
    </div>
    <h3 class="text-2xl font-bold mb-4">Quick Deployment</h3>
    <p class="text-gray-400 mb-6 leading-relaxed">
        Launch your CLI in minutes with our streamlined deployment process...
    </p>
    <ul class="space-y-3 text-gray-300">
        <li class="flex items-start">
            <i class="fas fa-check text-blue-400 mr-3 mt-1"></i>
            <span>One-click deployment</span>
        </li>
        <li class="flex items-start">
            <i class="fas fa-check text-blue-400 mr-3 mt-1"></i>
            <span>Automatic scaling</span>
        </li>
        <li class="flex items-start">
            <i class="fas fa-check text-blue-400 mr-3 mt-1"></i>
            <span>Zero downtime updates</span>
        </li>
    </ul>
</div>
```

---

### 4. Updating Testimonials

**Location:** Lines 483-590 (Testimonials Section)

Each testimonial card contains:

```html
<div class="testimonial-card bg-gray-900 p-8 rounded-lg border border-gray-700 hover:border-blue-500">
    <div class="flex items-center mb-4">
        <div class="flex text-yellow-400">
            <i class="fas fa-star"></i>
            <!-- More stars -->
        </div>
    </div>
    <p class="text-gray-300 mb-6 leading-relaxed">
        "Your testimonial text here..."
    </p>
    <div class="flex items-center">
        <div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full flex items-center justify-center mr-4">
            <i class="fas fa-user text-white"></i>
        </div>
        <div>
            <p class="font-bold text-white">Person's Name</p>
            <p class="text-gray-400 text-sm">Job Title, Company Name</p>
        </div>
    </div>
</div>
```

**How to Change:**

1. **Update Testimonial Text:** Replace the quoted text
2. **Update Name:** Replace `Person's Name`
3. **Update Title & Company:** Replace `Job Title, Company Name`

**Example:**
```html
<p class="text-gray-300 mb-6 leading-relaxed">
    "This tool has revolutionized how we manage our internal tools. Setup was effortless and the ROI was immediate. Highly recommended!"
</p>
<div class="flex items-center">
    <div class="w-12 h-12 bg-gradient-to-br from-blue-400 to-blue-600 rounded-full flex items-center justify-center mr-4">
        <i class="fas fa-user text-white"></i>
    </div>
    <div>
        <p class="font-bold text-white">Jessica Thompson</p>
        <p class="text-gray-400 text-sm">CTO, TechVentures Inc.</p>
    </div>
</div>
```

---

### 5. Updating FAQ Items

**Location:** Lines 625-720 (FAQ Section)

Each FAQ item has this structure:

```html
<div class="faq-item bg-gray-800 rounded-lg border border-gray-700 overflow-hidden">
    <button class="faq-toggle w-full px-6 py-4 text-left flex items-center justify-between hover:bg-gray-700 transition duration-300" aria-expanded="false">
        <h3 class="text-lg font-bold text-white">Your question here?</h3>
        <i class="fas fa-chevron-down faq-icon text-blue-400 transition duration-300"></i>
    </button>
    <div class="faq-content px-6 pb-4 text-gray-400">
        <p class="leading-relaxed">
            Your answer here...
        </p>
    </div>
</div>
```

**How to Change:**

1. **Update Question:** Replace `Your question here?`
2. **Update Answer:** Replace the paragraph in `<div class="faq-content">`

**Example:**
```html
<div class="faq-item bg-gray-800 rounded-lg border border-gray-700 overflow-hidden">
    <button class="faq-toggle w-full px-6 py-4 text-left flex items-center justify-between hover:bg-gray-700 transition duration-300" aria-expanded="false">
        <h3 class="text-lg font-bold text-white">Can I integrate with my existing tools?</h3>
        <i class="fas fa-chevron-down faq-icon text-blue-400 transition duration-300"></i>
    </button>
    <div class="faq-content px-6 pb-4 text-gray-400">
        <p class="leading-relaxed">
            Absolutely! Our platform supports integrations with over 200+ popular tools including Slack, GitHub, Jenkins, and more. Custom integrations are also available for enterprise customers.
        </p>
    </div>
</div>
```

---

### 6. Updating Contact Information

**Location:** Lines 767-793 (Contact Section)

**Current Code:**
```html
<a href="mailto:servaas@elitelayouts.co.za" class="text-blue-400 hover:text-blue-300 transition duration-300">
    servaas@elitelayouts.co.za
</a>

<a href="https://elitelayouts.co.za" class="text-blue-400 hover:text-blue-300 transition duration-300">
    elitelayouts.co.za
</a>
```

**How to Change:**

Replace the email address and website URL with your contact information.

**Example:**
```html
<a href="mailto:hello@mycompanycli.com" class="text-blue-400 hover:text-blue-300 transition duration-300">
    hello@mycompanycli.com
</a>

<a href="https://www.mycompanycli.com" class="text-blue-400 hover:text-blue-300 transition duration-300">
    www.mycompanycli.com
</a>
```

---

### 7. Updating Footer Copyright

**Location:** Lines 887-889

**Current Code:**
```html
<p class="text-gray-400">
    &copy; 2024 CommandlineOS. All rights reserved. | 
    <a href="mailto:servaas@elitelayouts.co.za" class="text-blue-400 hover:text-blue-300 transition duration-300">servaas@elitelayouts.co.za</a>
</p>
```

**How to Change:**

Replace `CommandlineOS` with your company name and update the email address.

**Example:**
```html
<p class="text-gray-400">
    &copy; 2024 MyCompanyCLI. All rights reserved. | 
    <a href="mailto:hello@mycompanycli.com" class="text-blue-400 hover:text-blue-300 transition duration-300">hello@mycompanycli.com</a>
</p>
```

---

## Managing Links

### Understanding Links in This Landing Page

Links are created using the `<a>` tag with an `href` attribute:

```html
<a href="destination-here">Link Text</a>
```

There are two types of links in this page:

1. **Internal Links** - Links to sections within the same page (using `#sectionid`)
2. **External Links** - Links to other websites or pages

---

### Current Links Reference

Here's a complete list of all links in the landing page:

| Link Location | Current URL | Type | Purpose |
|---|---|---|---|
| Header - Home | `#home` | Internal | Scroll to hero section |
| Header - Features | `#features` | Internal | Scroll to features |
| Header - Benefits | `#benefits` | Internal | Scroll to benefits |
| Header - About | `#about` | Internal | Scroll to about section |
| Header - Testimonials | `#testimonials` | Internal | Scroll to testimonials |
| Header - FAQ | `#faq` | Internal | Scroll to FAQ |
| Header - Contact | `#contact` | Internal | Scroll to contact |
| Hero - Get Started Button | `https://elitelayouts.co.za` | External | External website |
| Hero - Learn More | `#features` | Internal | Scroll to features |
| Benefits - All Learn More Buttons | `https://elitelayouts.co.za` | External | External website |
| CTA Section - Start Free Trial | `https://elitelayouts.co.za` | External | External website |
| CTA Section - Schedule Demo | `#contact` | Internal | Scroll to contact |
| Contact - Email Link | `mailto:servaas@elitelayouts.co.za` | Email | Send email |
| Contact - Website Link | `https://elitelayouts.co.za` | External | External website |
| Footer - All Product Links | Various (see below) | Mixed | Navigation |
| Footer - Privacy Policy | `privacy.html` | Internal | Privacy page |
| Footer - Terms of Service | `terms.html` | Internal | Terms page |
| Footer - Social Media | Various URLs | External | Social profiles |

---

### How to Update External Links (Step-by-Step)

**Example: Update "Get Started Now" button**

1. **Open** `index.html` in your text editor
2. **Find** the line with `https://elitelayouts.co.za` (appears multiple times)
3. **Replace** with your actual URL

**Current Code (Line ~170):**
```html
<a href="https://elitelayouts.co.za" class="btn-primary inline-block px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-lg shadow-lg transform transition duration-300">
    Get Started Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

**Updated Code (Example):**
```html
<a href="https://www.mycompanycli.com/signup" class="btn-primary inline-block px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-lg shadow-lg transform transition duration-300">
    Get Started Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

---

### How to Update All External Links at Once

**Quick Method Using Find & Replace:**

1. **Open** `index.html` in your text editor
2. **Use Find & Replace** (Ctrl+H on Windows, Cmd+H on Mac)
3. **Find:** `https://elitelayouts.co.za`
4. **Replace with:** Your actual URL (e.g., `https://www.mycompanycli.com`)
5. **Click "Replace All"**

**⚠️ Important:** This will replace ALL instances. If you want different buttons linking to different places, update them individually instead.

---

### How to Update Email Links

**Current Code:**
```html
<a href="mailto:servaas@elitelayouts.co.za">
    servaas@elitelayouts.co.za
</a>
```

**Updated Code:**
```html
<a href="mailto:hello@mycompanycli.com">
    hello@mycompanycli.com
</a>
```

**Note:** The `mailto:` part is essential—don't remove it. It tells the browser to open the user's email client.

---

### How to Update Social Media Links

**Location:** Lines 883-903 (Footer)

**Current Code:**
```html
<a href="https://twitter.com" class="text-gray-400 hover:text-blue-400 transition duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-2xl"></i>
</a>
<a href="https://linkedin.com" class="text-gray-400 hover:text-blue-400 transition duration-300" aria-label="LinkedIn">
    <i class="fab fa-linkedin text-2xl"></i>
</a>
```

**Updated Code (Example):**
```html
<a href="https://twitter.com/mycompanycli" class="text-gray-400 hover:text-blue-400 transition duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-2xl"></i>
</a>
<a href="https://linkedin.com/company/mycompanycli" class="text-gray-400 hover:text-blue-400 transition duration-300" aria-label="LinkedIn">
    <i class="fab fa-linkedin text-2xl"></i>
</a>
```

---

### Testing Your Links

After updating links, test them by:

1. **Opening** the HTML file in a web browser
2. **Clicking** each link to verify it works
3. **Checking** that internal links scroll smoothly to the correct section
4. **Confirming** external links open in a new tab (if desired)

**To make external links open in a new tab**, add `target="_blank"` to the `<a>` tag:

```html
<a href="https://www.mycompanycli.com" target="_blank" class="btn-primary...">
    Get Started Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

---

## Customizing Styling with Tailwind CSS

### What is Tailwind CSS?

Tailwind CSS is a "utility-first" CSS framework. Instead of writing traditional CSS, you apply pre-made classes directly to HTML elements. This landing page uses Tailwind loaded via CDN (no installation needed).

### Understanding Tailwind Classes in This Page

Tailwind classes are always written directly in the `class` attribute. Here are common patterns you'll see:

#### Color Classes

```html
<!-- Text Colors -->
<p class="text-white">White text</p>
<p class="text-gray-300">Light gray text</p>
<p class="text-blue-400">Blue text</p>

<!-- Background Colors -->
<div class="bg-gray-900">Dark gray background</div>
<div class="bg-blue-600">Blue background</div>

<!-- Border Colors -->
<div class="border border-gray-700">Gray border</div>
<div class="border border-blue-500">Blue border</div>
```

#### Spacing Classes

```html
<!-- Padding (internal spacing) -->
<div class="p-8">8 units of padding on all sides</div>
<div class="px-4 py-8">4 units horizontal, 8 units vertical</div>

<!-- Margin (external spacing) -->
<div class="mb-6">6 units margin below</div>
<div class="mt-4">4 units margin above</div>

<!-- Gap (space between items) -->
<div class="gap-8">8 units gap between child elements</div>
```

#### Size Classes

```html
<!-- Width and Height -->
<div class="w-16 h-16">16 units square</div>
<div class="w-full">Full width of parent</div>
<div class="max-w-7xl">Maximum width of 7xl</div>

<!-- Font Size -->
<h1 class="text-4xl">Extra large text</h1>
<p class="text-lg">Large text</p>
<p class="text-sm">Small text</p>
```

#### Responsive Classes

Tailwind uses prefixes for different screen sizes:

```html
<!-- Mobile first (no prefix) -->
<h1 class="text-4xl">4xl on mobile</h1>

<!-- Medium screens and up (md:) -->
<h1 class="text-4xl md:text-5xl">4xl on mobile, 5xl on tablets+</h1>

<!-- Large screens and up (lg:) -->
<h1 class="text-4xl md:text-5xl lg:text-7xl">4xl mobile, 5xl tablet, 7xl desktop</h1>
```

---

### Common Customizations

#### 1. Changing Colors (Dark Theme to Light Theme)

**Current Dark Background:**
```html
<body class="bg-gray-900 text-white">
```

**To Change to Light Theme:**
```html
<body class="bg-white text-gray-900">
```

**Then update all sections:**

**Current:**
```html
<section class="py-24 bg-gray-800 bg-opacity-50">
```

**Light Version:**
```html
<section class="py-24 bg-gray-100">
```

**Update text colors:**

**Current:**
```html
<p class="text-gray-400">Light gray text</p>
```

**Light Version:**
```html
<p class="text-gray-600">Dark gray text</p>
```

---

#### 2. Changing the Primary Color (Blue to Purple)

The page uses blue (`from-blue-400 to-blue-600`) as the primary color. To change it:

**Find all instances of:**
- `from-blue-400` → Replace with `from-purple-400`
- `to-blue-600` → Replace with `to-purple-600`
- `bg-blue-600` → Replace with `bg-purple-600`
- `text-blue-400` → Replace with `text-purple-400`
- `hover:text-blue-400` → Replace with `hover:text-purple-400`
- `border-blue-500` → Replace with `border-purple-500`

**Using Find & Replace:**
1. Press Ctrl+H (Windows) or Cmd+H (Mac)
2. Find: `blue-400`
3. Replace with: `purple-400`
4. Click "Replace All"
5. Repeat for `blue-600` → `purple-600`, etc.

---

#### 3. Changing Button Styles

**Current Button:**
```html
<a href="#" class="btn-primary inline-block px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-lg shadow-lg transform transition duration-300">
    Click Me
</a>
```

**To Make Buttons Larger:**
```html
<!-- Change px-8 py-4 to px-12 py-6 -->
<a href="#" class="btn-primary inline-block px-12 py-6 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-lg shadow-lg transform transition duration-300">
    Click Me
</a>
```

**To Make Buttons More Rounded:**
```html
<!-- Change rounded-lg to rounded-full -->
<a href="#" class="btn-primary inline-block px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-full shadow-lg transform transition duration-300">
    Click Me
</a>
```

**To Remove Shadow:**
```html
<!-- Remove shadow-lg -->
<a href="#" class="btn-primary inline-block px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded-lg transform transition duration-300">
    Click Me
</a>
```

---

#### 4. Changing Spacing Between Sections

**Current:**
```html
<section class="py-24 bg-gray-900">
```

**Meanings:**
- `py-24` = 24 units of padding on top and bottom

**To Increase Spacing:**
```html
<section class="py-32 bg-gray-900">
```

**To Decrease Spacing:**
```html
<section class="py-16 bg-gray-900">
```

---

#### 5. Changing Font Sizes

**Current Hero Title:**
```html
<h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight tracking-tight">
```

**To Make Smaller:**
```html
<h1 class="text-3xl md:text-5xl lg:text-6xl font-bold mb-6 leading-tight tracking-tight">
```

**To Make Larger:**
```html
<h1 class="text-5xl md:text-7xl lg:text-8xl font-bold mb-6 leading-tight tracking-tight">
```

---

#### 6. Changing Grid Layouts

**Current Feature Cards (3 columns):**
```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
```

**To Make 2 Columns:**
```html
<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
```

**To Make 4 Columns:**
```html
<div class="grid grid-cols-1 md:grid-cols-4 gap-8">
```

**Explanation:**
- `grid-cols-1` = 1 column on mobile
- `md:grid-cols-3` = 3 columns on medium screens and up
- `gap-8` = 8 units of space between items

---

### Custom CSS Modifications

The page includes custom CSS in the `<style>` tag (Lines 12-77). Here are common modifications:

#### Changing Hover Effects

**Current Feature Card Hover:**
```css
.feature-card:hover {
    transform: scale(1.05);
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.5);
}
```

**To Make More Dramatic:**
```css
.feature-card:hover {
    transform: scale(1.10);
    box-shadow: 0 30px 35px -5px rgba(0, 0, 0, 0.7);
}
```

**To Remove Scale Effect:**
```css
.feature-card:hover {
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.5);
}
```

#### Changing Transition Speed

**Current (300ms):**
```css
.feature-card {
    transition: all 300ms ease-in-out;
}
```

**To Make Faster (150ms):**
```css
.feature-card {
    transition: all 150ms ease-in-out;
}
```

**To Make Slower (500ms):**
```css
.feature-card {
    transition: all 500ms ease-in-out;
}
```

---

### Tailwind Color Reference

Here are the color options available in Tailwind (used throughout this page):

```
Gray Scale:
- gray-900 (darkest)
- gray-800
- gray-700
- gray-600
- gray-500
- gray-400
- gray-300
- gray-200
- gray-100 (lightest)

Blue Scale:
- blue-900 (darkest)
- blue-800
- blue-700
- blue-600
- blue-500
- blue-400
- blue-300 (lightest)

Yellow (for stars):
- yellow-400

You can also use:
- red, green, purple, pink, indigo, cyan, amber, orange, etc.
```

---

## Adding Privacy and Terms Pages

### Step 1: Create the Privacy Policy Page

1. **Create a new file** in the same folder as `index.html`
2. **Name it** `privacy.html`
3. **Paste this template:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="CommandlineOS - Privacy Policy">
    <meta name="author" content="CommandlineOS">
    <title>Privacy Policy — CommandlineOS</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header & Navigation -->
    <header class="fixed top-0 w-full bg-gray-900 bg-opacity-95 backdrop-blur-md z-50 border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center">
                    <a href="index.html" class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">
                        <i class="fas fa-terminal mr-2"></i>CommandlineOS
                    </a>
                </div>
                <nav class="hidden md:flex space-x-8">
                    <a href="index.html" class="font-medium text-gray-300 hover:text-blue-400">Home</a>
                    <a href="index.html#contact" class="font-medium text-gray-300 hover:text-blue-400">Contact</a>
                </nav>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="pt-32 pb-20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold mb-8">Privacy Policy</h1>
            <p class="text-gray-400 mb-8">Last updated: January 2024</p>

            <div class="prose prose-invert max-w-none space-y-8">
                <section>
                    <h2 class="text-2xl font-bold mb-4">1. Introduction</h2>
                    <p class="text-gray-300 leading-relaxed">
                        CommandlineOS ("we", "us", "our", or "Company") operates the CommandlineOS website and platform. This page informs you of our policies regarding the collection, use, and disclosure of personal data when you use our service and the choices you have associated with that data.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">2. Information Collection and Use</h2>
                    <p class="text-gray-300 leading-relaxed mb-4">
                        We collect several different types of information for various purposes to provide and improve our service to you.
                    </p>
                    <h3 class="text-xl font-semibold mb-3 text-blue-400">Types of Data Collected:</h3>
                    <ul class="list-disc list-inside space-y-2 text-gray-300">
                        <li>Personal identification information (name, email address, phone number, etc.)</li>
                        <li>Usage data (pages visited, time spent, interactions, etc.)</li>
                        <li>Device information (browser type, IP address, operating system, etc.)</li>
                        <li>Cookies and similar tracking technologies</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">3. Use of Data</h2>
                    <p class="text-gray-300 leading-relaxed mb-4">
                        CommandlineOS uses the collected data for various purposes:
                    </p>
                    <ul class="list-disc list-inside space-y-2 text-gray-300">
                        <li>To provide and maintain our service</li>
                        <li>To notify you about changes to our service</li>
                        <li>To allow you to participate in interactive features of our service</li>
                        <li>To provide customer support</li>
                        <li>To gather analysis or valuable information so we can improve our service</li>
                        <li>To monitor the usage of our service</li>
                        <li>To detect, prevent and address technical issues</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">4. Security of Data</h2>
                    <p class="text-gray-300 leading-relaxed">
                        The security of your data is important to us but remember that no method of transmission over the Internet or method of electronic storage is 100% secure. While we strive to use commercially acceptable means to protect your Personal Data, we cannot guarantee its absolute security.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">5. Contact Us</h2>
                    <p class="text-gray-300 leading-relaxed">
                        If you have any questions about this Privacy Policy, please contact us at:
                    </p>
                    <p class="text-blue-400 mt-4">
                        <a href="mailto:servaas@elitelayouts.co.za">servaas@elitelayouts.co.za</a>
                    </p>
                </section>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <p class="text-gray-400">
                    &copy; 2024 CommandlineOS. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 2: Create the Terms of Service Page

1. **Create a new file** in the same folder as `index.html`
2. **Name it** `terms.html`
3. **Paste this template:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="CommandlineOS - Terms of Service">
    <meta name="author" content="CommandlineOS">
    <title>Terms of Service — CommandlineOS</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header & Navigation -->
    <header class="fixed top-0 w-full bg-gray-900 bg-opacity-95 backdrop-blur-md z-50 border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center">
                    <a href="index.html" class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">
                        <i class="fas fa-terminal mr-2"></i>CommandlineOS
                    </a>
                </div>
                <nav class="hidden md:flex space-x-8">
                    <a href="index.html" class="font-medium text-gray-300 hover:text-blue-400">Home</a>
                    <a href="index.html#contact" class="font-medium text-gray-300 hover:text-blue-400">Contact</a>
                </nav>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="pt-32 pb-20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold mb-8">Terms of Service</h1>
            <p class="text-gray-400 mb-8">Last updated: January 2024</p>

            <div class="prose prose-invert max-w-none space-y-8">
                <section>
                    <h2 class="text-2xl font-bold mb-4">1. Agreement to Terms</h2>
                    <p class="text-gray-300 leading-relaxed">
                        By accessing and using CommandlineOS, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">2. Use License</h2>
                    <p class="text-gray-300 leading-relaxed mb-4">
                        Permission is granted to temporarily download one copy of the materials (information or software) on CommandlineOS for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                    </p>
                    <ul class="list-disc list-inside space-y-2 text-gray-300">
                        <li>Modify or copy the materials</li>
                        <li>Use the materials for any commercial purpose or for any public display</li>
                        <li>Attempt to decompile or reverse engineer any software contained on the site</li>
                        <li>Remove any copyright or other proprietary notations from the materials</li>
                        <li>Transfer the materials to another person or "mirror" the materials on any other server</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">3. Disclaimer</h2>
                    <p class="text-gray-300 leading-relaxed">
                        The materials on CommandlineOS are provided on an 'as is' basis. CommandlineOS makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">4. Limitations</h2>
                    <p class="text-gray-300 leading-relaxed">
                        In no event shall CommandlineOS or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on CommandlineOS.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">5. Accuracy of Materials</h2>
                    <p class="text-gray-300 leading-relaxed">
                        The materials appearing on CommandlineOS could include technical, typographical, or photographic errors. CommandlineOS does not warrant that any of the materials on the site are accurate, complete, or current. CommandlineOS may make changes to the materials contained on the site at any time without notice.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">6. Links</h2>
                    <p class="text-gray-300 leading-relaxed">
                        CommandlineOS has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by CommandlineOS of the site. Use of any such linked website is at the user's own risk.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">7. Modifications</h2>
                    <p class="text-gray-300 leading-relaxed">
                        CommandlineOS may revise these terms of service for the website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">8. Governing Law</h2>
                    <p class="text-gray-300 leading-relaxed">
                        These terms and conditions are governed by and construed in accordance with the laws of the jurisdiction in which CommandlineOS operates, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-bold mb-4">9. Contact Us</h2>
                    <p class="text-gray-300 leading-relaxed">
                        If you have any questions about these Terms of Service, please contact us at:
                    </p>
                    <p class="text-blue-400 mt-4">
                        <a href="mailto:servaas@elitelayouts.co.za">servaas@elitelayouts.co.za</a>
                    </p>
                </section>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <p class="text-gray-400">
                    &copy; 2024 CommandlineOS. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Step 3: Verify Links in Footer

The footer already contains links to these pages. Verify they're correct:

**Location:** Lines 851-858 in `index.html`

```html
<li><a href="privacy.html" class="text-gray-400 hover:text-blue-400 transition duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-blue-400 transition duration-300">Terms of Service</a></li>
```

✅ **These links are already correct!** They point to `privacy.html` and `terms.html`.

---

### Step 4: Customize the Policy Pages

After creating the pages, customize them:

1. **Replace company name** - Find `CommandlineOS` and replace with your company name
2. **Update email address** - Find `servaas@elitelayouts.co.za` and replace with your email
3. **Update contact information** - Add your actual company details
4. **Add specific policies** - Tailor the content to match your actual practices

---

### Step 5: Test the Links

1. **Open** `index.html` in your browser
2. **Scroll to the footer**
3. **Click** "Privacy Policy" - should open `privacy.html`
4. **Click** "Terms of Service" - should open `terms.html`
5. **Click the logo** on the policy pages to return to the home page

---

## Common Tasks

### Task 1: Replace All Images

The page uses external images from Unsplash. To use your own images:

**Current Image (Example):**
```html
<img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=1200&h=600&fit=crop" alt="description">
```

**To Use Local Image:**
1. Save your image to a folder (e.g., `assets/images/`)
2. Replace the URL:

```html
<img src="assets/images/my-image.jpg" alt="description">
```

**All Images to Replace:**

| Location | Current URL | Description |
|---|---|---|
| Hero Section Background | `photo-1517694712202-14dd9538aa97` | Office/tech setup |
| CTA Section Background | `photo-1519389950473-47ba0277781c` | Team collaboration |
| Benefit 1 Image | `photo-1552664730-d307ca884978` | Dashboard/analytics |
| Benefit 2 Image | `photo-1454165804606-c3d57bc86b40` | Workflow automation |
| Benefit 3 Image | `photo-1460925895917-adf4e565db7d` | Business growth |
| About Section Image | `photo-1552664730-d307ca884978` | Team photo |

---

### Task 2: Add Google Analytics

To track visitor behavior:

1. **Get a Google Analytics ID** from [analytics.google.com](https://analytics.google.com)
2. **Add this code** before the closing `</head>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_ANALYTICS_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR_ANALYTICS_ID');
</script>
```

**Replace** `YOUR_ANALYTICS_ID` with your actual ID (e.g., `G-XXXXXXXXXX`)

---

### Task 3: Add a Contact Form

Currently, the contact section links to email. To add a working form:

**Replace the contact section (lines 767-793) with:**

```html
<div class="bg-gray-800 p-8 rounded-lg border border-gray-700">
    <h3 class="text-2xl font-bold mb-6">Send us a Message</h3>
    
    <form id="contactForm" class="space-y-4">
        <div>
            <label class="block text-sm font-medium mb-2">Name</label>
            <input type="text" required class="w-full bg-gray-900 border border-gray-700 rounded px-4 py-2 text-white focus:border-blue-500 focus:outline-none">
        </div>
        
        <div>
            <label class="block text-sm font-medium mb-2">Email</label>
            <input type="email" required class="w-full bg-gray-900 border border-gray-700 rounded px-4 py-2 text-white focus:border-blue-500 focus:outline-none">
        </div>
        
        <div>
            <label class="block text-sm font-medium mb-2">Message</label>
            <textarea required class="w-full bg-gray-900 border border-gray-700 rounded px-4 py-2 text-white focus:border-blue-500 focus:outline-none" rows="5"></textarea>
        </div>
        
        <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 rounded-lg transition duration-300">
            Send Message
        </button>
    </form>
</div>
```

**Then add this JavaScript** before the closing `</body>` tag:

```html
<script>
    document.getElementById('contactForm').addEventListener('submit', function(e) {
        e.preventDefault();
        alert('Thank you for your message! We will get back to you soon.');
        this.reset();
    });
</script>
```

**Note:** For a fully functional form, you'll need a backend service or third-party form handler like Formspree, Netlify Forms, or EmailJS.

---

### Task 4: Add a Newsletter Signup

Add this section before the footer:

```html
<!-- Newsletter Section -->
<section class="py-16 bg-blue-600 bg-opacity-20">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h2 class="text-3xl font-bold mb-4">Stay Updated</h2>
        <p class="text-gray-300 mb-8">Subscribe to our newsletter for the latest updates and tips</p>
        
        <form class="flex flex-col sm:flex-row gap-4 max-w-md mx-auto">
            <input type="email" placeholder="Enter your email" required class="flex-1 px-4 py-3 bg-gray-900 border border-gray-700 rounded text-white focus:border-blue-500 focus:outline-none">
            <button type="submit" class="px-6 py-3 bg-blue-600 hover:bg-blue-700 text-white font-bold rounded transition duration-300">
                Subscribe
            </button>
        </form>
    </div>
</section>
```

---

### Task 5: Add a Blog Link

The footer already references `blog.html`. To create it:

1. **Create** `blog.html` in the same folder
2. **Use this template:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="CommandlineOS Blog - Tips and Updates">
    <title>Blog — CommandlineOS</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-gray-900 text-white">
    <!-- Header -->
    <header class="fixed top-0 w-full bg-gray-900 bg-opacity-95 backdrop-blur-md z-50 border-b border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <a href="index.html" class="text-2xl font-bold bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">
                    <i class="fas fa-terminal mr-2"></i>CommandlineOS
                </a>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="pt-32 pb-20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold mb-4">Blog</h1>
            <p class="text-gray-400 mb-12">Stay updated with tips, tutorials, and company news</p>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Blog Post 1 -->
                <article class="bg-gray-800 rounded-lg border border-gray-700 overflow-hidden hover:border-blue-500 transition duration-300">
                    <div class="p-6">
                        <p class="text-blue-400 text-sm font-semibold mb-2">January 15, 2024</p>
                        <h2 class="text-2xl font-bold mb-3">Getting Started with CommandlineOS</h2>
                        <p class="text-gray-400 mb-4">Learn the basics of building your first CLI tool in just 10 minutes...</p>
                        <a href="#" class="text-blue-400 hover:text-blue-300 font-semibold">Read More →</a>
                    </div>
                </article>

                <!-- Blog Post 2 -->
                <article class="bg-gray-800 rounded-lg border border-gray-700 overflow-hidden hover:border-blue-500 transition duration-300">
                    <div class="p-6">
                        <p class="text-blue-400 text-sm font-semibold mb-2">January 10, 2024</p>
                        <h2 class="text-2xl font-bold mb-3">Advanced CLI Patterns</h2>
                        <p class="text-gray-400 mb-4">Explore advanced techniques for building powerful command-line interfaces...</p>
                        <a href="#" class="text-blue-400 hover:text-blue-300 font-semibold">Read More →</a>
                    </div>
                </article>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <p class="text-gray-400">&copy; 2024 CommandlineOS. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
```

---

## Troubleshooting

### Issue 1: Links Not Working

**Problem:** Clicking a link does nothing or shows a 404 error

**Solutions:**

1. **Check the href value:**
   ```html
   <!-- ❌ Wrong - missing # for internal links -->
   <a href="features">Features</a>
   
   <!-- ✅ Correct -->
   <a href="#features">Features</a>
   ```

2. **Check file names match exactly:**
   ```html
   <!-- ❌ Wrong - file is named "privacy.html" -->
   <a href="Privacy.html">Privacy</a>
   
   <!-- ✅ Correct -->
   <a href="privacy.html">Privacy</a>
   ```

3. **Test in browser developer tools:**
   - Right-click the page → "Inspect" or press F12
   - Look for errors in the Console tab

---

### Issue 2: Styling Looks Broken

**Problem:** Colors are off, text is misaligned, or spacing looks wrong

**Solutions:**

1. **Clear browser cache:**
   - Press Ctrl+Shift+Delete (Windows) or Cmd+Shift+Delete (Mac)
   - Clear cached images and files

2. **Check Tailwind CDN is loading:**
   - Open browser DevTools (F12)
   - Go to Network tab
   - Reload page
   - Look for `cdn.tailwindcss.com` - should show status 200

3. **Verify class names are spelled correctly:**
   ```html
   <!-- ❌ Wrong -->
   <div class="bg-gary-900">Wrong color name</div>
   
   <!-- ✅ Correct -->
   <div class="bg-gray-900">Correct</div>
   ```

---

### Issue 3: Mobile Menu Not Working

**Problem:** Mobile menu button doesn't open the menu

**Solutions:**

1. **Check JavaScript is not disabled** in your browser
2. **Verify the script section** (lines 920-980) is present and complete
3. **Check browser console** for errors (F12 → Console tab)

---

### Issue 4: Images Not Loading

**Problem:** Images show broken icon instead of displaying

**Solutions:**

1. **Check image URL is accessible:**
   ```html
   <!-- ❌ Wrong - typo in URL -->
   <img src="https://images.unsplash.com/phto-1517694712202-14dd9538aa97">
   
   <!-- ✅ Correct -->
   <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97">
   ```

2. **For local images, check file path:**
   ```html
   <!-- ❌ Wrong - file doesn't exist -->
   <img src="images/photo.jpg">
   
   <!-- ✅ Correct - file exists in assets/images/ -->
   <img src="assets/images/photo.jpg">
   ```

3. **Check file extension matches:**
   - File is `photo.jpg` but link says `photo.png` ❌
   - File is `photo.JPG` but link says `photo.jpg` ❌ (case-sensitive on some servers)

---

### Issue 5: FAQ Accordion Not Opening

**Problem:** Clicking FAQ questions doesn't expand the answers

**Solutions:**

1. **Verify JavaScript is enabled** in your browser
2. **Check for JavaScript errors:**
   - Press F12 → Console tab
   - Look for red error messages
3. **Ensure the FAQ structure is intact:**
   ```html
   <!-- Must have this exact structure -->
   <div class="faq-item">
       <button class="faq-toggle">
           <h3>Question?</h3>
           <i class="fas fa-chevron-down faq-icon"></i>
       </button>
       <div class="faq-content">
           <p>Answer here</p>
       </div>
   </div>
   ```

---

### Issue 6: Page Looks Different on Mobile

**Problem:** Layout is broken or unreadable on phones

**Solutions:**

1. **Check viewport meta tag** is present (Line 3):
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

2. **Test responsive design:**
   - Open DevTools (F12)
   - Click device icon (top-left of DevTools)
   - Select different devices to test

3. **Check responsive classes** are used:
   ```html
   <!-- ❌ Not responsive -->
   <div class="text-7xl">Text</div>
   
   <!-- ✅ Responsive -->
   <div class="text-4xl md:text-6xl lg:text-7xl">Text</div>
   ```

---

### Issue 7: Colors Not Changing

**Problem:** Changed color classes but colors don't update

**Solutions:**

1. **Hard refresh the page:**
   - Windows: Ctrl+Shift+R
   - Mac: Cmd+Shift+R

2. **Clear browser cache:**
   - Ctrl+Shift+Delete or Cmd+Shift+Delete
   - Select "All time"
   - Check "Cookies and other site data"
   - Click Clear

3. **Check for conflicting CSS:**
   - Search for the element in DevTools (F12)
   - Look for conflicting styles (crossed out)

4. **Verify Tailwind class exists:**
   ```html
   <!-- ❌ This class doesn't exist in Tailwind -->
   <div class="bg-purple-1000">Won't work</div>
   
   <!-- ✅ Use existing colors -->
   <div class="bg-purple-900">Works</div>
   ```

---

### Issue 8: Form Submission Not Working

**Problem:** Contact form doesn't send or shows error

**Solutions:**

1. **For the basic form**, it only shows an alert. To actually send emails:
   - Use a service like [Formspree](https://formspree.io)
   - Or [Netlify Forms](https://www.netlify.com/products/forms/)
   - Or [EmailJS](https://www.emailjs.com/)

2. **Example with Formspree:**
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
       <input type="email" name="email" required>
       <textarea name="message" required></textarea>
       <button type="submit">Send</button>
   </form>
   ```

---

### Issue 9: Performance is Slow

**Problem:** Page takes a long time to load

**Solutions:**

1. **Check Network tab** in DevTools (F12):
   - Look for slow-loading resources
   - Check file sizes

2. **Optimize images:**
   - Use modern formats (WebP instead of PNG)
   - Compress images using tools like [TinyPNG](https://tinypng.com)
   - Specify image dimensions

3. **Minimize CSS/JS:**
   - Remove unused code
   - Combine multiple scripts

4. **Enable caching:**
   - Set proper cache headers on your server

---

### Issue 10: Text Looks Blurry or Pixelated

**Problem:** Text rendering looks poor

**Solutions:**

1. **Add font smoothing CSS:**
   ```css
   body {
       -webkit-font-smoothing: antialiased;
       -moz-osx-font-smoothing: grayscale;
   }
   ```

2. **Use web-safe fonts or Google Fonts:**
   ```html
   <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
   ```

3. **Check zoom level** - Reset browser zoom to 100%

---

## Best Practices

### 1. Keep Backups

Always keep a backup of your original `index.html`:
- Save as `index-backup.html`
- Use version control (Git)
- Store in cloud storage

### 2. Test Changes

After making changes:
1. Test on desktop browser
2. Test on mobile browser
3. Test all links
4. Test on different browsers (Chrome, Firefox, Safari)

### 3. Update Meta Tags

Keep meta tags current for better SEO:

```html
<meta name="description" content="Your updated description">
<meta name="keywords" content="Updated, Keywords, Here">
<meta property="og:title" content="Updated Title">
<meta property="og:description" content="Updated description">
```

### 4. Monitor Performance

Use these tools:
- [Google PageSpeed Insights](https://pagespeed.web.dev)
- [GTmetrix](https://gtmetrix.com)
- [WebPageTest](https://www.webpagetest.org)

### 5. Keep Dependencies Updated

Periodically check for updates:
- Tailwind CSS CDN
- Font Awesome
- Any other external libraries

---

## Quick Reference

### Common Tailwind Classes

```
Spacing:
- p-4 (padding)
- m-4 (margin)
- gap-8 (space between items)

Colors:
- text-white (text color)
- bg-gray-900 (background)
- border-gray-700 (border)

Sizing:
- w-full (100% width)
- max-w-7xl (max width)
- text-4xl (font size)

Responsive:
- md: (medium screens)
- lg: (large screens)
- hidden md:flex (hidden on mobile, flex on medium+)

Hover Effects:
- hover:bg-blue-700
- hover:text-blue-400
- hover:scale-105
```

### File Paths

```
Same folder as index.html:
- privacy.html
- terms.html
- blog.html

Subfolder:
- assets/images/photo.jpg
- images/photo.jpg
- css/custom.css
```

### Common HTML Tags

```html
<!-- Headings -->
<h1>Largest heading</h1>
<h2>Second largest</h2>

<!-- Text -->
<p>Paragraph</p>
<span>Inline text</span>

<!-- Links -->
<a href="url">Link text</a>

<!-- Images -->
<img src="url" alt="description">

<!-- Sections -->
<section id="name">Content</section>
<div>Container</div>

<!-- Lists -->
<ul>
    <li>Item</li>
</ul>
```

---

## Support Resources

- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [Font Awesome Icons](https://fontawesome.com/icons)
- [Web Accessibility Guidelines](https://www.w3.org/WAI/)

---

**Last Updated:** January 2024

**Document Version:** 1.0

For questions or additional help, contact: `servaas@elitelayouts.co.za`