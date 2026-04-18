To ensure the **Sterling Tutoring Group** website remains high-impact across all devices, the layout must shift its information density based on screen size. Below is the technical and structural map for optimizing the brief across the five key device categories.

### **Responsive Breakpoint Map**

| Device            | Breakpoint          | Layout Strategy                                                                                                                            |
| :---------------- | :------------------ | :----------------------------------------------------------------------------------------------------------------------------------------- |
| **Phone**   | `< 640px`         | **Single Column.** High-contrast headings. CTA is always within thumb-reach.                                                         |
| **Tablet**  | `640px - 1024px`  | **Two-Column Grids.** Text and images/forms move side-by-side.                                                                       |
| **Laptop**  | `1024px - 1280px` | **Standard Desktop.** Horizontal navigation and full-width feature sections.                                                         |
| **Desktop** | `> 1280px`        | **Contained Max-Width.** Use generous whitespace to prevent text lines from becoming too long (ideal line length: 60-80 characters). |

---

### **Section-by-Section Mobile Optimization**

#### **SECTION 1 — HERO**

* **Phone:** Headline and Subtext are centered. The **Lead Capture Form** sits directly below the subtext. Ensure input fields are at least 48px high for "fat-finger" accessibility.
* **Laptop/Desktop:** Move to a 2-column split. Headline/Subtext on the left, Lead Capture Form in a high-contrast card on the right.

#### **SECTION 2 — COMPELLING QUESTION**

* **Phone:** Keep the background Black to act as a "Scroll Stopper." Use a vertical stack: Headline → Body → CTA.
* **Tablet/Desktop:** Increase the padding (e.g., `py-32`) to create a "cinematic" break in the white background of the surrounding sections.

#### **SECTION 3 — THE SERVICE**

* **Phone:** A simple vertical list of subjects with Light Blue bullet points.
* **Tablet:** Use a 2-column grid for subjects.
* **Laptop/Desktop:** A 3 or 5-column horizontal grid to show the breadth of subjects at a glance.

#### **SECTION 4 — THE SYSTEM (INCLUSIONS)**

* **Phone:** Use a **Vertical Stack.** Each inclusion card should be full-width with a subtle Light Blue border.
* **Tablet:** Transition to a **2x2 Grid** for the four inclusion points.
* **Laptop/Desktop:** A **4-Column Row.** This allows the user to see the "Entire Support System" without scrolling.

#### **SECTION 5 — CLIENT PROOF**

* **Phone:** Implement a **Horizontal Swipe Carousel.** This allows users to see many testimonials without creating a "long scroll" that leads to drop-off.
* **Desktop:** A **3-Column Masonry Grid** (similar to Instagram) to showcase the screenshots of results and "win cards."

---

### **Global Mobile-First CSS Principles**

To implement these "clear breaks" technically, use the following CSS structure (or Tailwind equivalents):

```css
/* 1. Typography Scaling */
h1 { font-size: 2.5rem; } /* Mobile */
@media (min-width: 1024px) { h1 { font-size: 4rem; } } /* Desktop */

/* 2. Container Constraints */
.container {
  width: 100%;
  padding-left: 20px;
  padding-right: 20px;
  margin-left: auto;
  margin-right: auto;
}
@media (min-width: 1280px) {
  .container { max-width: 1200px; } /* Prevents text stretching on wide screens */
}

/* 3. Button Accessibility */
.cta-button {
  width: 100%; /* Full width on mobile for easy clicking */
  padding: 18px;
}
@media (min-width: 768px) {
  .cta-button { width: auto; } /* Natural width on larger screens */
}
```

### **Developer Implementation Check**

* **Touch Targets:** Ensure the "I'm Ready to Act" button is not too close to other links.
* **Readability:** On mobile, ensure the Light Blue accents have high enough contrast against white for outdoor readability (students often check sites on their phones between classes).
* **Fast Load:** Use SVGs for the Sterling logo to ensure it stays crisp even on high-density "Retina" phone displays.
