# Mohammed Zaid's Professional Portfolio

A clean, modern, and fully responsive personal portfolio designed to showcase my background in Computer Science, my technical skills, and my practical projects. This portfolio was specifically tailored with a sleek, European aesthetic in preparation for my application to the MSc in Information Technology Management and Data Analytics program at GBS Malta.

## 🚀 About This Portfolio

This project is lightweight, fast, and built without heavy JavaScript frameworks. The tech stack includes:
- **HTML5 & CSS3** with **Tailwind CSS** (via CDN) for rapid, responsive styling.
- **Vanilla JavaScript** for interactive elements like intersection observers (scroll reveal animations), continuous scrolling marquee, and image modal handling.
- **Print-friendly styling** (`resume.html`) utilizing custom `@media print` directives to ensure the digital resume exports perfectly to an A4 PDF without any unnecessary UI elements.

## 🛠️ Challenges, Mistakes, & How I Solved Them

During the development and refinement of this portfolio, I encountered several technical and design challenges. Here is how I iterated and solved them:

### 1. The Marquee Animation Z-Index Issue
- **The Challenge:** I wanted a massive, infinite scrolling text ("MOHAMMED ZAID") to sit perfectly *behind* the footer content as a faint watermark layer. Initially, placing the marquee container caused it to either push the footer down, overlap the interactive links, or disappear completely behind the background.
- **The Solution:** I redesigned the footer structure by wrapping it in a `relative overflow-hidden` container. I positioned the marquee absolutely (`absolute inset-0`) with `z-index: 0` and an opacity of `0.05`. Crucially, I added `pointer-events-none` to the marquee so it wouldn't block clicks, and applied `relative z-10` to the actual footer text. This achieved the perfect, non-intrusive watermark effect.

### 2. A4 Resume Printing Layout
- **The Challenge:** The `resume.html` page looked great on a screen, but when users (or recruiters) tried to print it to PDF, web-only elements like the navigation bar, clickable link icons, and background colors looked unprofessional and broke the standard A4 dimensions.
- **The Solution:** I implemented a specialized `@media print` CSS block. I created a `no-print` class to aggressively hide navigation, buttons, and decorative link vectors. I also forced standard A4 dimensions (`210mm x 297mm`) and adjusted the margins natively in CSS, ensuring the browser's print dialog exports a clean, highly professional document.

### 3. Responsive Grid Alignment for Projects
- **The Challenge:** When displaying an uneven number of projects (e.g., 8 projects in a 3-column desktop grid), the bottom row would align to the left by default. This left an awkward, asymmetrical empty space on the right side of the screen.
- **The Solution:** I refactored the rigid CSS Grid layout into a flexible wrapping layout (`flex flex-wrap justify-center`). By dynamically calculating the widths of the cards using `calc(33.333% - 1.5rem)` and utilizing `flex-grow` for the card text, the project cards now perfectly align in the center on all screen sizes, ensuring the last row is beautifully symmetrical.

### 4. Certificate Image Integration
- **The Challenge:** The portfolio initially used placeholder images for the certifications section. I needed to integrate real certificate images while maintaining the aspect ratio and ensuring they look good within the responsive grid.
- **The Solution:** I updated the image sources to point to the `Certificates/` directory. By using the `aspect-video` and `object-cover` classes from Tailwind, I ensured that all certificate images maintain a uniform layout, regardless of their original dimensions. I also implemented an `onerror` fallback to a clean placeholder in case of missing assets, and a modal system (via `script.js`) that allows users to click and view the full-size certificate.

## 💻 How to Run Locally

Because this project uses zero build tools, running it is incredibly simple:
1. Clone this repository to your local machine.
2. Open `index.html` in any modern web browser.
3. No `npm install`, no local server required! 

## 🔗 Projects Included

The portfolio connects to several of my live, working projects:
- M-Plus Shoes
- DRIP CHECK Website
- ARZ DIGITAL NEXUS
- OnTimeTech by ARZ
- Amaranth Website
- Saga Store Annual Data Analysis Report 2024
- Data Cleaning & Salary Update (Python)
- ZenCafe (Prompt Engineering)
