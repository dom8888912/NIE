# NIE Appointment Automation via Playwright
**Date:** July 2025

---

## Abstract

This project automates the process of booking an N.I.E. (Número de Identidad de Extranjero) appointment via Spain's governmental web platform. Built using Python and Playwright, the system simulates realistic user behavior to bypass anti-bot protection and capture changes in appointment availability. Through this experience, I acquired deep insights into headless browser automation, JavaScript DOM manipulation, anti-bot evasion strategies, and containerized deployment using Docker.

---

## Project Goal

The core goal is to automate and optimize the appointment scheduling workflow for foreign residents seeking an N.I.E. number. The application mimics human input to fill forms, manage sessions, and detect page changes, optionally triggering user notifications when new appointment slots become available.

---

## Requirements

### Functional Requirements

- Selection of province, procedure, and document type via dropdowns  
- Simulated human typing, mouse movement, and scrolling  
- Bypass intermediate pages with restricted direct access  
- HTML change detection via hash comparison  
- Persistent browser context and cookie handling  

### Non-Functional Requirements

- Configurable via YAML file (e.g. for name, ID number, nationality)  
- Supports both headless and visible modes for debugging  
- Fault-tolerant execution with clear logging  
- Packaged in a Docker image with required Linux dependencies  
- Extendable for future dynamic form updates  

---

## Key Technical Insights

| Topic            | Insight                                                                                      |
|------------------|----------------------------------------------------------------------------------------------|
| DOM Interaction  | Required use of JavaScript `evaluate()` to correctly fill inputs when `fill()` failed         |
| Anti-bot Evasion | Implemented randomized scrolling, delays, and cursor movement to simulate human behavior      |
| Access Constraints | Government page blocked direct entry; workaround implemented using an external referrer page |
| Docker Environment | Installed missing libraries such as `libx11`, `libglib2.0`, `libnss3` during image build     |
| State Change Detection | Generated SHA-256 hashes of final HTML to detect updates and trigger screenshots          |

---

## Challenges and Solutions

- **Broken Selectors:** Many form inputs didn’t react to standard input methods — solved via custom JS and error handling.  
- **Changing Page Structure:** Frequent updates to form layouts required resilient code with logging and fallback mechanisms.  
- **Anti-bot Limitations:** Mitigated by emulating realistic user interaction patterns (typing delay, hover effects).  
- **Network Access:** Entry to the .gov page only possible through a specific intermediate site to avoid session rejection.  
- **Missing Libraries in Docker:** Extended Dockerfile to include GUI and media-related libraries.  

---

## Detailed Learnings

| Area                 | What I Learned                                                                                       |
|----------------------|----------------------------------------------------------------------------------------------------|
| Browser Automation    | Deep understanding of [Playwright](https://playwright.dev), including selectors, context management, headless vs. headed modes, and browser events. |
| Anti-Bot Strategies   | Learned how to simulate human interaction: randomized delays, scrolls, hover, and typing to bypass bot detection. |
| DOM Manipulation      | Gained hands-on experience in injecting and evaluating JavaScript directly into the browser's DOM when conventional automation failed. |
| Error Handling & Resilience | Built robust try-except structures, timeout logic, and logging to handle dynamic or unstable page structures.           |
| State Management      | Implemented persistent browser sessions and cookie storage to maintain state across runs.           |
| Change Detection      | Applied cryptographic hashing (SHA-256) on HTML content to detect changes in page content – a lightweight alternative to full scraping. |
| Cross-Platform Deployment | Packaged the script inside a Docker container and solved compatibility issues with headless Linux environments (missing fonts, X11 libraries, etc.). |
| Configuration & Modularity | Designed the app to be fully configurable via `config.yaml`, allowing flexible input without changing the core code.         |
| Logging & Debugging   | Learned structured logging to both console and file, useful for debugging long-running automation tasks. |
| Business Thinking     | Identified market demand, user pain points, and developed a monetizable SaaS concept based on real-world inefficiencies. |
| CI/CD Readiness       | Project is containerized and could easily be hooked into a GitHub Actions pipeline for scheduled deployment or monitoring. |

---

## Outlook

This script requires continuous maintenance as selectors, page layouts, and form validation logic change regularly. Adding automated version detection, dynamic selector lookup, or AI-assisted element targeting could improve long-term robustness.

---

## Business Analysis

The script offers strong potential for a commercial SaaS notification service. By continuously checking for available appointments and notifying users when slots open, the tool can save time and frustration for foreign residents. The system can be extended with:

- Email and SMS notifications when appointments are found  
- Subscription-based priority scanning (e.g. hourly for premium users)  
- User dashboard to manage profiles and regions  
- Affiliate partnerships with relocation services and immigration consultants  

---

## Market Analysis

In Spain, demand for N.I.E. appointments often exceeds supply due to bureaucratic bottlenecks and limited appointment slots. This leads to a high willingness to pay among expats, freelancers, and immigrants needing quick access to appointments. There is currently no official notification system, leaving room for:

- First-mover advantage in providing structured appointment monitoring  
- Recurring revenue model with low infrastructure cost  
- Geographic scalability to include additional Spanish provinces or consulates abroad  

---

## Conclusion

This automation project showcases advanced skills in browser scripting, real-world interaction modeling, API-less data extraction, and technical resilience in unstable environments. It bridges the gap between personal utility and commercial potential, combining programming expertise with real market needs.


