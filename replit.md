# Overview

This is a personalized birthday surprise website application built as a full-stack TypeScript project for Aaddii's birthday. The application creates an interactive birthday experience with password protection, animated photo galleries, personal messages, and decorative visual effects. It's designed as a special gift website with multiple pages including welcome screens, photo memories, and heartfelt messages.

## Recent Changes (Aug 6, 2025)
- Added all 11 user photos to the gallery without cropping
- Fixed "Happy Birthday" text visibility on welcome page
- Restructured as frontend-only application for Vercel deployment
- Moved all components from client/src to root src/ directory
- Created clean package.json and vite.config.ts for frontend-only build
- Removed server/, client/, and shared/ folders for simple deployment

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The frontend is built with React and TypeScript using Vite as the build tool. The application follows a component-based architecture with:
- **React Router**: Uses Wouter for lightweight client-side routing
- **State Management**: React hooks for local state management with TanStack Query for server state
- **Animation Framework**: Framer Motion for smooth page transitions and floating animations
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming

## Backend Architecture
The backend uses Express.js with TypeScript in a minimal REST API structure:
- **Server Framework**: Express.js with custom middleware for logging and error handling
- **Development Setup**: Vite middleware integration for hot reloading in development
- **Static Serving**: Serves the built React application in production
- **Storage Interface**: Abstract storage layer with in-memory implementation (expandable to database)

## Database Layer
The application is configured for PostgreSQL using Drizzle ORM:
- **ORM**: Drizzle ORM with TypeScript-first schema definitions
- **Database Provider**: Neon serverless PostgreSQL (configured but not actively used)
- **Schema Management**: Drizzle migrations with shared schema between client and server
- **Validation**: Zod schemas for runtime type validation

## Authentication System
Simple password-based access control:
- **Gate Pattern**: Password challenge before accessing the main application
- **Client-Side Protection**: Password verification happens on the frontend
- **Session Management**: Basic state-based authentication without persistent sessions

## Visual Design System
Cohesive birthday theme with custom styling:
- **Color Palette**: Pink, rose, and blue themed colors with CSS custom properties
- **Typography**: Dancing Script font for decorative headings, Inter for body text
- **Animations**: Floating roses, smooth page transitions, and hover effects
- **Responsive Design**: Mobile-first approach with responsive layouts

## File Organization
- `client/`: React frontend application
- `server/`: Express.js backend API
- `shared/`: Shared TypeScript types and schemas
- `attached_assets/`: Static image assets for the photo gallery
- Root-level configuration files for build tools and development setup

## Build and Development
- **Development**: Concurrent client and server development with hot reloading
- **Production Build**: Vite builds the frontend, esbuild bundles the backend
- **Type Safety**: Full TypeScript coverage across frontend, backend, and shared code