🎉 Next.js 15 Project Structure

Welcome to the project! This document outlines the folder structure and architectural principles used in this Next.js 15 project. The goal is to keep the codebase modular, scalable, and developer-friendly.

📂 Table of Contents
- Overview
- Folder Structure
- Key Concepts
- Notes

📁 Overview
This project uses the Next.js 15 App Router with a modular, domain-driven approach. Each feature or domain (such as auth, user, dashboard) is isolated to keep business logic clean, reusable, and maintainable.

📂 Folder Structure

```bash
src/
  app/
    (public)/         # Public routes (authentication, marketing, landing pages)
      layout.tsx      # Layout for public pages
      page.tsx        # Landing page
    (dashboard)/      # Protected dashboard routes (requires authentication)
      layout.tsx      # Dashboard layout (sidebar, header, etc.)
      page.tsx        # Dashboard home page
      users/
        page.tsx
        components/   # Page-specific UI components
        hooks/        # Page-specific hooks
        settings/     # Users settings page
    api/
      auth/           # Auth route handlers (Next.js API routes)
        login/route.ts
    layout.tsx        # Root/global layout (theme providers, auth guards, etc.)

  modules/            # Business logic modules (Domain-Driven Design)
    auth/
      hooks/          # Custom hooks (useLogin, useRegister, etc.)
      services/       # API services (loginUser, registerUser, etc.)
      validation/     # Zod schemas for forms (loginSchema, registerSchema)
      types/          # Module-specific types and interfaces
    user/
      hooks/
      services/
      validation/
      types/

  components/         # Reusable UI components
    ui/               # Shared atomic components (Button, Input, Modal)
    layouts/          # Layout pieces (Header, Sidebar, Footer)
    common/           # Generic reusable components (Avatar, Badge, etc.)

  hooks/              # Global reusable hooks (useDebounce, useLocalStorage)

  lib/                # Utility libraries (cookies, formatters, date utils)

  config/             # App-wide configuration (API URLs, themes, environment vars)

  constants/          # Application constants and enums (roles, routes, etc.)

  middlewares/        # Middlewares (auth guards, API middlewares)

  store/              # Global state management (Redux Toolkit slices)

  types/              # Global TypeScript types (env types, global types)

  styles/             # Global styles (CSS, Tailwind CSS configuration)
```

🔍 Key Concepts
- **Domain-Driven Design (DDD):** Features like auth, user, and dashboard are separated in modules with their own hooks, services, types, and validations.
- **App Router (Next.js 15):** We use the new `app/` directory structure with layouts, route handlers (`api/`), and co-located page-specific components/hooks.

---

💪 Happy Coding!

---
