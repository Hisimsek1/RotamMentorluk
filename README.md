# Rotam Mentorluk - Web Application

A marketing and lead generation website for **Rotam Mentorluk**, a Turkish educational mentoring service that connects students preparing for standardized university and high school entrance exams with experienced mentors.

---

## Overview

Rotam Mentorluk offers personalized coaching for students preparing for two major Turkish national exams:

- **YKS** (Yükseköğretim Kurumları Sınavı) — University Entrance Exam
- **LGS** (Liselere Giriş Sınavı) — High School Entrance Exam

The website presents the service's mentor roster, coaching packages, student testimonials, live exam countdown timers, and a WhatsApp-integrated contact form.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3, Bootstrap 5.3.3 |
| Scripting | Vanilla JavaScript (ES6+) |
| Icons | Font Awesome 6.5.2 |
| Fonts | Google Fonts — Poppins |
| Analytics | Google Analytics (G-8P52C60PYJ) |
| Contact | WhatsApp Business API (`wa.me`) |

All dependencies are loaded from CDN. There is no build step, no package manager, and no server-side code.

---

## Project Structure

```
Rotam_Kod/
├── index.html          Main HTML document (single page)
├── style.css           All styles, CSS variables, responsive rules
├── script.js           All JavaScript logic
├── images/
│   ├── logo.jpg
│   ├── fatih-avatar.jpg
│   ├── halil-avatar.jpg
│   ├── abdülhalik-avatar.png
│   ├── nazile-avatar.jpg
│   └── favicon-*.png   Multiple favicon sizes
└── .vscode/
    └── launch.json     Chrome debug launch configuration
```

---

## Features

### Mentor Showcase
A responsive carousel displays four mentor profiles. Clicking a mentor card opens a modal with a full biography, educational background, and areas of expertise. On mobile, the carousel shows one card at a time; on desktop it shows multiple.

**Mentors:**
- Mehmet Fatih Alkan
- Halil Ibrahim Simsek
- Abdulhalik Say
- Nazile Akkaya

### Live Exam Countdown Timers
Two real-time countdown clocks count down to the official exam dates:
- LGS 2026 — June 7, 2026 at 09:30
- YKS 2026 — June 14, 2026 at 10:15

Each timer displays days, hours, minutes, and seconds, updating every second.

### Coaching Packages
Four pricing tiers with itemized feature lists:

| Package | Target | Price |
|---|---|---|
| LGS Package | 8th Grade | 2500 TRY/month |
| YKS Package | 12th Grade | 2000 TRY/month |
| Classes 9–11 Package | Grades 9–11 | 1799 TRY/month |
| Classes 6–7 Package | Grades 6–7 | 1799 TRY/month |

### Testimonials Carousel
An auto-rotating slider cycles through six student and parent testimonials every four seconds. Manual navigation is available via arrows and dot indicators.

### WhatsApp Contact Form
A contact form collects the visitor's name, email, subject, and message. On submission, the data is formatted and the user is redirected to a WhatsApp chat (`wa.me/905523472917`) with the message pre-filled. This requires no backend.

### Floating WhatsApp Button
A fixed-position WhatsApp button is visible on all scroll positions, providing a direct contact shortcut at all times.

### About Section
Presents the organization's founding story, mission statement, and vision.

---

## Running the Project

There is no build or install step.

**Option 1 — Open directly in a browser**

Double-click `index.html` or drag it into any modern browser. All resources load from CDN so an internet connection is required.

**Option 2 — Local development server (recommended)**

Serving over HTTP avoids potential browser restrictions on local file access.

Using the VS Code Live Server extension:
1. Open the project folder in VS Code.
2. Right-click `index.html` in the Explorer panel.
3. Select **Open with Live Server**.

Using Python's built-in server:
```bash
# Python 3
python -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

**Option 3 — VS Code Chrome debugger**

The `.vscode/launch.json` is pre-configured to attach Chrome to `http://localhost:8080`. Start a local server on that port, then press **F5** in VS Code to launch a debuggable Chrome session.

---

## Design Tokens

Key CSS custom properties defined in `style.css`:

```css
--primary-color:   #DC2626  /* Brand red */
--secondary-color: #991B1B  /* Dark red */
--light-color:     #FFFFFF  /* White */
--text-color:      #333333  /* Body text */
--light-gray:      #f8f9fa  /* Background sections */
```

Responsive breakpoints:
- Mobile: `max-width: 768px`
- Small mobile: `max-width: 576px`

---

## JavaScript Architecture

All JavaScript is contained in `script.js` and runs after the DOM is ready. Key functions:

| Function | Purpose |
|---|---|
| `startCountdown(targetDate, elementId)` | Drives a live countdown timer for a given exam date |
| `showMentor(index)` | Renders the mentor at the given carousel index |
| `changeMentor(direction)` | Advances or retreats the mentor carousel |
| `initializeMentorDots()` | Rebuilds carousel dots based on viewport width |
| `showTestimonial(index)` | Renders a specific testimonial slide |
| `changeTestimonial(direction)` | Advances or retreats the testimonials carousel |
| Contact form handler | Validates input and constructs a `wa.me` redirect URL |

---

## Contact & Social

| Channel | Value |
|---|---|
| WhatsApp | +90 552 347 2917 |
| Instagram | @rotammentorluk |

---

## Browser Compatibility

The site targets all modern evergreen browsers: Chrome, Firefox, Safari, and Edge. No polyfills are included; IE is not supported.
