# Ahmed Othman — Technology & Automation Consulting Website
### Production Deployment, Configuration & Brand Architecture Handbook

This repository contains the complete, production-ready source code for the independent consulting website of **Ahmed Othman — Independent Technology & Automation Consultant**.

---

## 1. Project Overview & Architecture

* **Design Philosophy:** Corporate Technology Consulting (Light Theme, clean whitespace, emerald green accents, deep slate typography, WCAG-compliant contrast).
* **Target Audience:** Business owners, C-level executives, department managers, and enterprise organizations seeking ERP consulting (Dynamics 365 F&O), business process automation, Microsoft Power Platform solutions, and applied AI.
* **Technology Stack:**
  * **HTML5:** Semantic, accessible, SEO-optimized structure.
  * **Tailwind CSS (v3.4):** Responsive utilities, custom brand palette, and fluid typography.
  * **Google Fonts:** *Plus Jakarta Sans* (executive headings) + *Inter* (readable body) + *JetBrains Mono* (technical tags).
  * **Font Awesome 6:** Vector iconography for enterprise tools, platforms, and contact channels.
  * **Pure Vanilla JavaScript:** Fast, dependency-free interactive category filtering, modal state management, toast notifications, and client-side form validation.

---

## 2. Directory Structure

```text
othconsultations.com/
├── index.html              # Main single-file production website
├── CNAME                   # Custom domain pointer (othconsultations.com)
├── .nojekyll               # Disables Jekyll processing on GitHub Pages
├── README.md               # Complete operational and configuration guide
└── assets/
    └── profile.jpg         # High-resolution consultant portrait photo
```

---

## 3. Customizing Your Information

### A. Updating Contact Details & Channels
In `index.html`, search for the following entries and replace them with your updated credentials if they change:

1. **WhatsApp Number & Message:**
   * Search for: `wa.me/201025359978`
   * Replace `201025359978` with your international country code and number without plus signs or spaces (e.g., `201025359978` for Egypt or `96650xxxxxxx` for KSA).
   * Update the URL-encoded pre-filled greeting after `?text=`.

2. **Email Address:**
   * Search for: `ahmedothman206@gmail.com`
   * Replace with your custom domain corporate email once established (e.g., `contact@othconsultations.com` or `ahmed@othconsultations.com`).

3. **Phone Number:**
   * Search for: `(+20) 01025359978` and `tel:+2001025359978`.

4. **LinkedIn & GitHub Profiles:**
   * Search for `linkedin.com/in/ahmed-othman-468253169` and `github.com/ahmedothman206`.

---

## 4. Connecting Lead Generation & Booking Services

### Option A: Microsoft Bookings Integration (Recommended for M365 Users)
If your organization uses Microsoft 365 Business / Enterprise:
1. Navigate to [portal.office.com](https://portal.office.com) → **Bookings**.
2. Create a new service titled **"30-Minute Technology Consultation"**.
3. Set your buffer times, business hours (e.g., 10:00 AM – 6:00 PM Cairo/Riyadh time), and Teams meeting link auto-generation.
4. Copy your public booking URL (e.g., `https://outlook.office365.com/owa/calendar/yourname@yourcompany/bookings/`).
5. In `index.html`, look for `#consultation` and update the `btn-open-booking-modal` action or replace the modal trigger directly with your link:
   ```html
   <a href="YOUR_MICROSOFT_BOOKINGS_URL" target="_blank" rel="noopener noreferrer" class="px-5 py-2.5 rounded-xl bg-brand-600 hover:bg-brand-700 text-white font-semibold text-xs shadow-sm transition-all flex items-center gap-1.5">
       <i class="fa-regular fa-calendar-days"></i>
       <span>Schedule on Microsoft Bookings</span>
   </a>
   ```

### Option B: Calendly Integration
1. Create a free account at [calendly.com](https://calendly.com).
2. Create a **30 Minute Meeting** event type.
3. You can either link directly or embed the widget by adding Calendly's script in the `<head>` and placing the inline widget inside `#consultation`.

---

## 5. Connecting the Contact Form to Your Email

The contact form currently validates inputs and opens a structured `mailto:` draft with all client fields filled in. To receive submissions silently directly in your inbox without opening the client's email client:

### Using Formspree (Free & Takes 2 Minutes)
1. Sign up at [formspree.io](https://formspree.io).
2. Click **Create Form** and name it `Consulting Inquiries`.
3. Copy your unique Formspree endpoint (e.g., `https://formspree.io/f/mqkvyqpw`).
4. In `index.html`, update the `<form>` tag:
   ```html
   <form id="consulting-contact-form" action="https://formspree.io/f/YOUR_ENDPOINT_ID" method="POST" class="space-y-4">
   ```
5. Remove the `e.preventDefault()` mailto fallback in the `<script>` section or let Formspree handle the POST request via `fetch()`.

---

## 6. Deployment & Domain Setup Guide

### Method 1: GitHub Pages with Custom Domain (Recommended & 100% Free)
Since your repository `ahmedothman206/othconsultations.com` is already configured on GitHub:
1. Upload the files (`index.html`, `CNAME`, `.nojekyll`, and `assets/profile.jpg`) to the root of your repository on GitHub.
2. In your GitHub repository, click **Settings** → **Pages** (in the left sidebar).
3. Under **Build and deployment**:
   * **Source:** Deploy from a branch
   * **Branch:** `main` (or `master`), Folder: `/(root)`
   * Click **Save**.
4. Under **Custom domain**:
   * Enter: `othconsultations.com`
   * Check the box: **Enforce HTTPS** (GitHub provides a free SSL certificate automatically).

### DNS Records Configuration (at Namecheap, GoDaddy, or Cloudflare)
To connect `othconsultations.com` to your GitHub Pages site, add these DNS records at your domain registrar:

| Type | Host / Name | Target / Value | TTL |
| :--- | :--- | :--- | :--- |
| **A** | `@` | `185.199.108.153` | Automatic / 300 |
| **A** | `@` | `185.199.109.153` | Automatic / 300 |
| **A** | `@` | `185.199.110.153` | Automatic / 300 |
| **A** | `@` | `185.199.111.153` | Automatic / 300 |
| **CNAME** | `www` | `ahmedothman206.github.io.` | Automatic / 300 |

---

## 7. Strategic Recommendations for Domain & Brand Growth

1. **Primary Domain:** `othconsultations.com` is clean, professional, and establishes an enterprise entity brand rather than just a personal resume.
2. **Branded Email:** Configure Google Workspace or Microsoft 365 Exchange with your domain:
   * `ahmed@othconsultations.com` (personal executive contact)
   * `inquiries@othconsultations.com` or `consulting@othconsultations.com` (proposals & RFPs)
3. **LinkedIn Synergy:** Update your LinkedIn profile headline to match the site:
   * *"Independent Technology & Automation Consultant | Dynamics 365 F&O • Power Platform • RPA & UiPath"*
   * Place `https://othconsultations.com` prominently in your LinkedIn profile link section.
