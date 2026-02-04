# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML/CSS/vanilla JS prototype for Pennsylvania DHS Medicaid work requirement waivers. It demonstrates the user flow for medical frailty verification — how applicants self-report medical conditions and allow doctors to verify them online.

There is no build system, no external dependencies, no backend, and no tests. All interactions are simulated client-side.

## Running Locally

Open `index.html` directly in a browser, or serve the directory with any static HTTP server:

```
python -m http.server
```

## Architecture

Three HTML pages with a single shared stylesheet (`styles.css`):

- **index.html** — Landing page linking to the two main flows
- **client.html** — 4-screen multi-step applicant form (medical condition question → consent → doctor email → confirmation). Uses inline vanilla JS for screen navigation, progress dots, and form validation.
- **doctor.html** — 2-screen provider verification form with placeholder tokens (`[DOCTOR NAME]`, `[PATIENT NAME]`) for dynamic values. Inline JS handles form submission and screen transitions.

All page navigation between screens is done by toggling visibility of `<div>` sections within each HTML file. No routing library is used.

The CSS uses a card-based layout with a 480px max-width centered container, blue primary color (#2563eb), and custom-styled radio buttons.
