🚀 Next.js 15 Project Structure
Welcome to the project! This document outlines the folder structure and architectural principles used in this Next.js 15 project.
The goal is to keep the codebase modular, scalable, and developer-friendly.

📋 Table of Contents
Overview

Folder Structure

Key Concepts

Notes

📖 Overview
This project uses the Next.js 15 App Router with a modular, domain-driven approach.
Each feature or domain (such as auth, user, dashboard) is isolated to keep business logic clean, reusable, and maintainable.

🗂 Folder Structure
bash
Copy
Edit
src/
│
├── app/                    # Next.js 15 App Router (Pages, Layouts, Route Handlers)
│   ├── (public)/            # Public routes (authentication, marketing, landing pages)
│   │   ├── page.tsx
│   │   └── layout.tsx
│   ├── (dashboard)/         # Protected dashboard routes (requires authentication)
│   │   ├── users/
│   │   │   ├── page.tsx
│   │   │   ├── components/  # Page-specific UI components
│   │   │   └── hooks/       # Page-specific hooks
│   │   ├── settings/
│   │   │   ├── page.tsx
│   │   │   ├── components/
│   │   │   └── validation/  # Zod schemas / validation utilities
│   │   └── layout.tsx       # Main dashboard layout (sidebar, header, etc.)
│   ├── api/                 # Route handlers (Next.js API routes)
│   │   └── auth/
│   │       └── login/route.ts
│   └── layout.tsx           # Root/global layout (theme providers, auth guards, etc.)
│
├── modules/                 # Business logic modules (domain-driven design)
│   ├── auth/
│   │   ├── hooks/           # Custom hooks (useLogin, useRegister, etc.)
│   │   ├── services/        # API services (loginUser, registerUser, etc.)
│   │   ├── validation/      # Zod schemas for forms (loginSchema, registerSchema)
│   │   └── types/           # Module-specific types and interfaces
│   ├── user/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── validation/
│   │   └── types/
│   └── dashboard/
│       ├── hooks/
│       ├── services/
│       ├── validation/
│       └── types/
│
├── components/              # Reusable UI components
│   ├── ui/                  # Shared atomic components (Button, Input, Modal)
│   ├── layouts/             # Layout pieces (Header, Sidebar, Footer)
│   └── common/              # Generic reusable components (Avatar, Badge, etc.)
│
├── hooks/                   # Global reusable hooks (e.g., useDebounce, useAuth)
├── lib/                     # Utility libraries (axios client, formatters, date utils)
├── config/                  # App-wide configuration (API URLs, themes, environment vars)
├── constants/               # Application constants and enums (roles, routes, etc.)
├── middlewares/             # Middlewares (auth guards, API middlewares)
├── store/                   # Global state management (Zustand / Redux Toolkit slices)
├── types/                   # Global TypeScript types (env types, user models, etc.)
├── styles/                  # Global styles (CSS, Tailwind CSS configuration)
💡 Key Concepts
Domain-Driven Design (DDD)
Features like auth, user, and dashboard are separated in modules/ with their own hooks, services, types, and validations.

App Router (Next.js 15)
We use the new app/ directory structure with layouts, route handlers (api/), and co-located page-specific components/hooks.

Reusability First
Generic UI components are placed inside components/, while page-specific components live alongside their page.

Validation-Driven Forms
Zod schemas are placed in the validation/ folders to ensure forms are validated properly both on the client and server.

Scalability & Maintainability
Clear separation between pages, business logic, components, utilities, and configurations, making it easy to grow and maintain.

📝 Notes
Add new features by creating a dedicated folder inside modules/ to keep things isolated and organized.

API service functions are grouped in services/ folders and called inside hooks.

Always keep reusable components, hooks, and types in their designated folders to maintain code quality.
