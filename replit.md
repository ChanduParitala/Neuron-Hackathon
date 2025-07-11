# Neuron Challenge Hub

## Overview

This is a full-stack web application built as a coding challenge platform similar to LeetCode. The application combines algorithmic problem-solving with a Wordle-style game, featuring user progress tracking, daily challenges, and a leaderboard system.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for development and build processes
- **Styling**: Tailwind CSS with custom dark theme
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ESM modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **API Pattern**: RESTful endpoints under `/api` prefix
- **Development**: Hot module replacement via Vite middleware

### Build and Development
- **Monorepo Structure**: Shared code between client and server
- **Development Server**: Express with Vite middleware for HMR
- **Production Build**: Vite builds client, esbuild bundles server
- **TypeScript**: Strict mode with path mapping for clean imports

## Key Components

### Database Schema
- **Users**: Profile data, streaks, points, and statistics
- **Problems**: Coding challenges with test cases and solutions
- **Submissions**: User code submissions with execution results
- **Daily Challenges**: Rotating daily problem selection
- **Wordle Games**: Gaming component with word puzzles
- **User Progress**: Tracking problem completion status

### API Endpoints
- User management and statistics
- Problem CRUD operations with progress tracking
- Submission system with code execution
- Daily challenge rotation
- Wordle game mechanics
- Leaderboard generation

### Frontend Pages
- **Home**: Dashboard with daily challenge, problem grid, leaderboard
- **Problem Detail**: Individual problem view with code editor
- **404**: Error handling for missing routes

### UI Components
- Responsive design with mobile-first approach
- Dark theme with custom color scheme
- Interactive components (accordions, dialogs, tooltips)
- Form controls with validation
- Progress tracking visualizations

## Data Flow

1. **User Authentication**: Demo mode returns static user (ID: 1)
2. **Problem Loading**: Fetch problems with user progress overlay
3. **Code Submission**: POST to `/api/submissions` with validation
4. **Progress Updates**: Automatic user statistics recalculation
5. **Daily Content**: Time-based challenge and Wordle word rotation
6. **Leaderboard**: Real-time ranking based on user performance

## External Dependencies

### Core Libraries
- **Database**: `drizzle-orm`, `@neondatabase/serverless`
- **UI**: `@radix-ui/*` components, `tailwindcss`
- **Forms**: `react-hook-form`, `@hookform/resolvers`
- **State**: `@tanstack/react-query`
- **Utilities**: `date-fns`, `zod`, `clsx`

### Development Tools
- **Replit Integration**: Custom plugins for development environment
- **Build Tools**: `vite`, `esbuild`, `tsx`
- **Type Checking**: `typescript` with strict configuration

## Deployment Strategy

### Development
- Vite dev server with Express middleware
- Hot module replacement for both client and server
- Automatic TypeScript compilation
- Database migrations via Drizzle Kit

### Production
- Client build output to `dist/public`
- Server bundle to `dist/index.js`
- Static file serving from build directory
- Environment-based configuration

### Database Management
- Schema defined in `shared/schema.ts`
- Migrations stored in `./migrations`
- Connection via `DATABASE_URL` environment variable
- Drizzle Kit for schema management

The application is designed as a modern, type-safe full-stack solution with clear separation of concerns and efficient development workflows.