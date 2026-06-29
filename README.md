#  Unirent - AI-Powered Student Roommate Matching Platform

> ** Interview Showcase Note:** This repository contains the complete frontend architecture and core matching engineering for *Unirent*. The dynamic dashboard calculates profile similarities in real-time on the client side using structured mathematical weights.

---

##  Project Vision
Finding the right roommate is traditionally driven by luck or rigid, shallow filters. **Unirent** transforms this experience by introducing a data-driven approach to student housing. By evaluating lifestyle compatibility across multi-dimensional profiles, the platform guarantees reduced interpersonal friction and optimal living arrangements for students.

##  How the AI Matching Engine Works
The core logic evaluates compatibility dynamically based on **6 distinct lifestyle dimensions** visible in the user profile vectors:
1. **Sleep Schedule** (Circadian alignment)
2. **Noise Tolerance** (Study vs. social environments)
3. **Cleanliness Standards** (Shared space maintenance)
4. **Social Activity** (Guest frequency and hosting habits)
5. **Budget Constraints** (Financial compatibility)
6. **Guest Preferences** (Interpersonal comfort boundaries)

###  Mathematical Approach: Weighted Cosine Similarity
Instead of simple binary matching, the system calculates a geometric distance between student profiles using a **Weighted Cosine Similarity** algorithm:

* **Vectorization:** User inputs and habits are mapped into multi-dimensional numerical arrays.
* **Dynamic Weighting:** The algorithm applies user-defined weights (e.g., if Cleanliness matters more to a user than Sleep schedules, that vector dimension is prioritized).
* **Angle Calculation:** It measures the cosine of the angle between the two profile vectors in the vector space, returning a highly accurate compatibility percentage from **0% to 100%**.

---

## 📸 Interface Showcase

### Interactive Roommate Matches Dashboard
Below is the live operational interface showcasing the dynamic filtering sidebar, personal algorithm weight tuning, and the animated SVG high-match dynamic hero slots.

![Unirent Roommate Matches Dashboard](assets/unirent-dashboard.png)

---

##  Tech Stack & Architecture

### Frontend Layer
* **React.js + Vite:** Ultra-fast, component-driven reactive architecture.
* **Custom Hooks (`useMatching.js`):** Centralized state engine managing real-time mathematical filtering and profile ranking.
* **Animated SVG Components (`ScoreRing.jsx`):** High-performance mathematical layout rendering for the compatibility scores.

### Core Processing Layer
* **Matching Engine (`matchingEngine.js`):** Pure, zero-dependency JavaScript file isolated for algorithmic execution and unit testing readiness.
* **Mock Vector Layer (`profiles.js`):** Structured dataset containing multi-point student vectors used to simulate production-grade API responses.

---

##  Key Architectural Patterns Implemented
* **Container/Presenter Pattern:** `Dashboard.jsx` acts as the intelligent state owner (Smart Component), keeping layout nodes like `FilterSidebar.jsx` and `ProfileCard.jsx` highly reusable and lightweight (Dumb Components).
* **Pure Logic Isolation:** The complete mathematical similarity scoring system resides outside of the UI rendering cycle, making the engine fully modular and enterprise-ready.
