# 🎉 Rajiv & Pradeepa Wedding Invitation Website

A beautiful, fully-animated wedding invitation website with elegant scroll effects, interactive timeline, and mobile-first design.

## 📋 Table of Contents

- [Website Sections](#website-sections)
- [Animation & Effects](#animation--effects)
- [Technical Implementation](#technical-implementation)
- [Color Palette](#color-palette)
- [Typography](#typography)
- [Responsive Design](#responsive-design)
- [Features & Functionality](#features--functionality)
- [Code Snippets for Reuse](#code-snippets-for-reuse)
- [File Structure](#file-structure)
- [Customization Guide](#customization-guide)

---

## 🌐 Website Sections

### 1. **Preloader** 
- Animated loading screen with ring loader
- Progress bar animation
- Floating hearts background
- Smooth fade-out transition

### 2. **Hero Section**
- Full-screen background with `maduraiflip.jpg`
- Animated couple names with heartbeat animation
- Countdown timer (Days, Hours, Minutes, Seconds)
- Decorative lines with shimmer effect
- Scroll indicator with bounce animation
- Tagline with glow effect

### 3. **Couple Introduction**
- Glass-morphism cards
- Alternating slide animations (left/right)
- Person cards with icons
- Heart divider between groom & bride

### 4. **Quote Section**
- Zoom-in animation
- Quote text with emphasis
- Scroll-triggered glow effect

### 5. **Parallax Sections** (x2)
- Fixed background images (Unsplash)
- Overlay with gradient
- Fade-in content
- Smooth parallax scrolling effect

### 6. **Love Story Timeline**
- Vertical timeline with alternating sides
- Timeline markers with pulsing animation
- Icons and dates for each milestone
- Scroll-reveal animations

### 7. **Gallery Section**
- Grid layout with responsive columns
- Images with hover zoom effect
- Date overlays on images
- Special positioning for Oct 15th image

### 8. **Wedding Events**
- Venue card with map integration
- Google Maps "Get Directions" button
- Three event cards (Reception, Ceremony, Nagavalli Mukurtham)
- Staggered animations

### 9. **With Blessings Section**
- Family cards for groom and bride
- "son of" / "daughter of" labels
- Golden divider lines
- Graceful typography

### 10. **Thank You Section**
- Final gratitude message
- "With Love" signature
- Social share buttons (WhatsApp, Instagram)
- Hashtag display

### 11. **Footer**
- Copyright information
- Wedding hashtag

---

## 🎨 Animation & Effects

### Scroll Animations

#### **Fade-In**
```css
.fade-in {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.8s ease, transform 0.8s ease;
}
```

#### **Slide-Left**
```css
.slide-left {
    transform: translateX(-50px);
    opacity: 0;
    transition: all 1s ease;
}
```

#### **Slide-Right**
```css
.slide-right {
    transform: translateX(50px);
    opacity: 0;
    transition: all 1s ease;
}
```

#### **Zoom-In**
```css
.zoom-in-effect {
    transform: scale(0.8);
    opacity: 0;
    transition: all 1s ease;
}
```

#### **Stagger Animations**
- Delay classes: `stagger-1`, `stagger-2`, `stagger-3`, `stagger-4`
- Progressive delay: 0.1s, 0.2s, 0.3s, 0.4s

### Hover Effects

#### **Glass-Card Glow**
```css
.glass-card:hover {
    background: rgba(255, 255, 255, 0.35);
    box-shadow: 0 20px 60px rgba(255, 107, 157, 0.3);
    transform: translateY(-5px);
}
```

#### **Button Scale**
```css
button:hover {
    transform: scale(1.05);
}
```

#### **Image Zoom**
```css
.gallery-item img:hover {
    transform: scale(1.15);
}
```

### Keyframe Animations

#### **Heartbeat**
```css
@keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.15); }
}
```

#### **Shimmer**
```css
@keyframes shimmer {
    0%, 100% { opacity: 0.6; }
    50% { opacity: 1; }
}
```

#### **Float**
```css
@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}
```

#### **Bounce**
```css
@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}
```

#### **Rotate Border**
```css
@keyframes rotating-border {
    0% { border-image-source: linear-gradient(0deg, gold, pink, gold); }
    100% { border-image-source: linear-gradient(360deg, gold, pink, gold); }
}
```

---

## 💻 Technical Implementation

### Scroll Detection
```javascript
const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
};

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('show');
        }
    });
}, observerOptions);
```

### Scroll Progress Bar
```css
.scroll-progress {
    position: fixed;
    top: 0;
    left: 0;
    width: 0%;
    height: 4px;
    background: linear-gradient(90deg, 
        var(--primary-pink), 
        var(--deep-purple), 
        var(--accent-rose), 
        var(--gold)
    );
    z-index: 9999;
    transition: width 0.1s ease;
}
```

### Cursor Effects (Disabled on Mobile)
- Custom heart cursor
- Particle trail effect
- Sparkle animation

### Countdown Timer
```javascript
function updateCountdown() {
    const weddingDate = new Date('2025-11-23T06:00:00').getTime();
    const now = new Date().getTime();
    const distance = weddingDate - now;
    
    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    // Updates every second
}
```

---

## 🎨 Color Palette

### Primary Colors
```css
--primary-pink: #FFB6C1;
--secondary-pink: #FFC2D1;
--accent-rose: #E91E63;
--deep-rose: #C2185B;
```

### Background Colors
```css
--light-pink: #FFE5EC;
--blush: #FFF0F5;
--baby-pink: #FFD1DC;
--ivory: #FFFFF0;
--cream: #FFF8F0;
```

### Accent Colors (Purple & Gold)
```css
--soft-purple: #C8B5E0;
--lavender: #B19CD9;
--deep-purple: #9370DB;
--gold: #D4AF37;
--soft-gold: #F4E4C1;
```

### Body Background
```css
background: linear-gradient(135deg, #F8F5FF 0%, #F0E6FF 50%, #F8F5FF 100%);
/* Very light purple gradient */
```

---

## 📝 Typography

### Font Families
```css
/* Headings */
Playfair Display - Serif, elegant

/* Body Text */
Cormorant Garamond - Serif, graceful

/* Details & Labels */
Montserrat - Sans-serif, clean

/* Special Titles */
Great Vibes - Script, romantic
```

### Responsive Typography
Using `clamp()` for fluid scaling:
```css
font-size: clamp(1.5rem, 4vw, 2.5rem);
/* Scales from 1.5rem (mobile) to 2.5rem (desktop) */
```

### Text Shadows (for visibility)
```css
text-shadow: 2px 2px 8px rgba(255, 255, 255, 0.9), 
             0 0 20px rgba(255, 255, 255, 0.7);
```

---

## 📱 Responsive Design

### Breakpoints
```css
/* Mobile */
@media (max-width: 768px) { }

/* Small Mobile */
@media (max-width: 480px) { }
```

### Mobile Optimizations

#### Hero Section
- Background image changes to `portrait.jpg`
- Font sizes reduced
- Padding adjusted
- `background-attachment: scroll` (no fixed, for performance)

#### Smooth Scrolling
- Hardware acceleration enabled
- Transform optimizations
- Reduced animations on mobile

#### Buttons
- Larger touch targets (10px 16px)
- Simplified hover states

#### Gallery
- Single column layout
- Full-width images

---

## ⚙️ Features & Functionality

### 1. **Preloader**
- Auto-hide after 3 seconds
- Progress bar animation
- Fade transition

### 2. **Custom Cursor**
- Pink heart cursor
- Particle trail
- Disabled on mobile/touch devices

### 3. **Scroll Progress Bar**
- Top of page
- Gradient colors
- Width updates on scroll

### 4. **Intersection Observer**
- Reveals elements on scroll
- Adds `.show` class
- Smooth transitions

### 5. **Countdown Timer**
- Real-time updates
- 4 time units (Days, Hours, Minutes, Seconds)
- PadStart for double digits

### 6. **Background Music Toggle**
- Fixed position button (bottom-right)
- Music toggle functionality
- Pulsing animation

### 7. **Language Toggle** (Tamil/English)
- Top-right button
- Google Translate integration
- Works on deployed URLs only

### 8. **Social Share Buttons**
- WhatsApp
- Instagram
- Pre-filled messages

### 9. **Google Maps Integration**
- "Get Directions" button
- Opens in new tab
- Pre-filled with venue address

---

## 🔧 Code Snippets for Reuse

### Glass-Morphism Card
```css
.glass-card {
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(255, 107, 157, 0.15);
}
```

### Scroll Reveal Animation
```javascript
const scrollRevealElements = document.querySelectorAll('.scroll-reveal');
scrollRevealElements.forEach(element => {
    element.addEventListener('animationend', () => {
        element.classList.add('animated');
    });
});
```

### Rotating Border Effect
```css
.rotating-border {
    border: 3px solid;
    border-image: linear-gradient(var(--gold), var(--primary-pink)) 1;
    animation: rotating-border 3s linear infinite;
}
```

### Gradient Text
```css
.gradient-text-scroll {
    background: linear-gradient(135deg, 
        var(--primary-pink), 
        var(--lavender), 
        var(--gold)
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}
```

### Parallax Effect
```css
.parallax-section {
    background-attachment: fixed; /* Desktop */
    background-size: cover;
    background-position: center;
}

@media (max-width: 768px) {
    .parallax-section {
        background-attachment: scroll; /* Mobile */
    }
}
```

### Timeline Markers
```css
.timeline-item::before {
    content: '';
    position: absolute;
    left: -25px;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: linear-gradient(135deg, 
        var(--primary-pink), 
        var(--lavender), 
        var(--accent-rose)
    );
    box-shadow: 0 0 20px rgba(147, 112, 219, 0.3);
    animation: pulse 2s ease-in-out infinite;
}
```

---

## 📂 File Structure

```
rajivwedding/
├── index.html              # Single-page application (HTML + CSS + JS)
├── README.md              # This documentation
├── Vazhithunaiye.mp3      # Background music
├── maduraiflip.jpg        # Hero background
├── portrait.jpg           # Mobile hero background
├── August 10th 2025.jpeg # Gallery image 1
├── Aug 29th 2025.jpeg    # Gallery image 2
├── Oct 15th 2025.jpeg    # Gallery image 3
└── Oct 26th 2025.jpeg    # Gallery image 4
```

---

## 🎯 Customization Guide

### Change Colors
Edit the CSS variables in `:root`:
```css
:root {
    --primary-pink: #YOUR_COLOR;
    --gold: #YOUR_GOLD_COLOR;
}
```

### Change Wedding Date
```javascript
const weddingDate = new Date('YOUR_DATE_HERE').getTime();
// Format: YYYY-MM-DDTHH:MM:SS
```

### Update Images
Replace image file names in HTML:
```html
<img src="YOUR_IMAGE.jpg" alt="Description">
```

### Modify Animations
Adjust timing in CSS:
```css
.scroll-reveal {
    transition-duration: YOUR_DURATION;
}
```

### Add/Remove Sections
1. Copy an existing section HTML
2. Modify content
3. Add appropriate classes: `scroll-reveal`, `fade-in`, etc.

---

## 🚀 Performance Optimizations

### 1. **Throttled Scroll Events**
```javascript
let ticking = false;
window.addEventListener('scroll', () => {
    if (!ticking) {
        window.requestAnimationFrame(() => {
            // Your code
            ticking = false;
        });
        ticking = true;
    }
}, { passive: true });
```

### 2. **Hardware Acceleration**
```css
.hero-section {
    transform: translateZ(0);
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
}
```

### 3. **Mobile Background Optimization**
```css
@media (max-width: 768px) {
    background-attachment: scroll !important;
    /* Prevents performance lag */
}
```

### 4. **Intersection Observer**
- Only animates visible elements
- Reduces unnecessary calculations

---

## 🎵 Audio Features

### Background Music
- **File**: `Vazhithunaiye.mp3`
- **Control**: Toggle button (bottom-right)
- **Loop**: Enabled
- **Auto-play**: Disabled (user must click)

### Mobile Considerations
- Hidden on mobile (< 768px)
- Requires user interaction

---

## 📱 Language Toggle

### Implementation
- Uses Google Translate API
- Works on deployed URLs (not localhost)
- Button fixed top-right
- Detects translated pages

### Button States
- **On English page**: "தமிழ்" button
- **On Tamil page**: "English" button

---

## 🎨 Decorative Elements

### Floating Hearts Background
- Multiple heart emojis floating
- Different animations per heart
- Background layer (z-index: -1)

### Decorative Lines
- Gradient lines with stars (✦)
- Shimmer animation
- Used as section separators

### Scroll Indicator
- Chevron down icon
- Bounce animation
- Auto-hides after scroll

---

## 🔗 External Integrations

### Google Maps
```html
<a href="https://www.google.com/maps/search/?api=1&query=VENUE" 
   target="_blank">Get Directions</a>
```

### Social Sharing
```html
<!-- WhatsApp -->
<a href="https://wa.me/?text=YOUR_TEXT">Share</a>

<!-- Instagram -->
<a href="https://www.instagram.com/create/story/">Share</a>
```

---

## 💡 Tips for Reusing This Code

### For Other Wedding Websites
1. Replace couple names
2. Update images and dates
3. Modify color palette
4. Update event details
5. Change venue information

### For Different Event Types
1. Remove/replace wedding-specific sections
2. Modify timeline content
3. Update social share messages
4. Change theme colors

### Animation Library
The scroll-reveal animations can be reused:
- `.fade-in`
- `.slide-left`
- `.slide-right`
- `.zoom-in-effect`
- `.stagger-1`, `.stagger-2`, etc.

### Glass-Morphism Cards
Useful for modern UI:
```css
.glass-card {
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(10px);
}
```

---

## 📊 Browser Support

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ✅ Mobile browsers
- ⚠️ IE11 (graceful degradation)

---

## 🐛 Known Issues & Fixes

### Mobile Scrolling Lag
**Issue**: Laggy scrolling on first page  
**Fix**: Disabled `background-attachment: fixed` on mobile

### Google Translate Bar
**Issue**: Bar appears on translated pages  
**Fix**: Hide with CSS (display: none)

### Image Bleaching
**Issue**: Background too bright  
**Fix**: Adjusted overlay opacity

---

## 📝 License

Created with ❤️ for Rajiv & Pradeepa's wedding  
© 2025 Rajiv & Pradeepa Wedding

---

## 🔖 Tags

`#WeddingInvitation` `#HTML5` `#CSS3` `#JavaScript` `#ResponsiveDesign` `#Animations` `#WeddingWebsite`

---

**#RajivWedsPradeepa #TwoStatesOneLove**
