# PromptPro - AI Prompt Optimization Platform

## Overview

PromptPro is a full-stack web application that helps users optimize their AI prompts through advanced analysis and intelligent suggestions. The platform provides real-time prompt evaluation, scoring metrics, and actionable recommendations to improve prompt effectiveness.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Changes

- **January 15, 2025**: Added PostgreSQL database with persistent storage
- **January 15, 2025**: Migrated from MemStorage to DatabaseStorage for all data operations
- **January 15, 2025**: Successfully deployed database schema with users, prompts, and chat_sessions tables
- **January 15, 2025**: Application ready for production deployment

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight React router)
- **State Management**: TanStack Query (React Query) for server state
- **Styling**: Tailwind CSS with Radix UI components (shadcn/ui)
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon serverless PostgreSQL
- **Authentication**: Mock authentication middleware (development setup)
- **API Integration**: OpenAI GPT-4o for prompt analysis

### Key Technologies
- **Language**: TypeScript throughout the stack
- **Package Manager**: npm with lockfile version 3
- **Module System**: ES modules
- **Runtime**: Node.js

## Key Components

### Database Schema
The application uses three main tables:
- **users**: User accounts with subscription plans (free, pro, enterprise)
- **prompts**: User-generated prompts with analysis results and scores
- **chat_sessions**: AI chat interactions for user assistance

### API Endpoints
- `/api/analyze-prompt`: Analyzes prompts using OpenAI and stores results
- `/api/chat`: Handles AI assistant conversations
- `/api/user-stats`: Provides user analytics and usage statistics
- `/api/prompts`: CRUD operations for user prompts

### UI Components
- **PromptAnalyzer**: Main tool for prompt analysis with scoring display
- **ChatWidget**: AI assistant for real-time help
- **Dashboard**: User analytics and prompt management
- **Navbar/Footer**: Navigation and branding components

## Data Flow

1. **Prompt Analysis Flow**:
   - User inputs prompt in the analyzer
   - Frontend sends request to `/api/analyze-prompt`
   - Backend processes with OpenAI GPT-4o
   - Analysis results stored in database
   - Scores and suggestions returned to frontend

2. **Chat Assistance Flow**:
   - User interacts with chat widget
   - Messages sent to `/api/chat` endpoint
   - AI assistant provides contextual help
   - Chat history maintained in sessions

3. **User Management Flow**:
   - Mock authentication provides user context
   - User data tracked across sessions
   - Analytics and usage stats calculated

## External Dependencies

### Core Dependencies
- **OpenAI**: GPT-4o model for prompt analysis
- **Stripe**: Payment processing (configured but not fully implemented)
- **Neon Database**: Serverless PostgreSQL hosting
- **Radix UI**: Accessible component primitives
- **Drizzle ORM**: Type-safe database operations

### Development Tools
- **Vite**: Fast development server and build tool
- **Replit Integration**: Development environment support
- **ESBuild**: Production bundling for backend
- **TailwindCSS**: Utility-first styling

## Deployment Strategy

### Build Process
- **Frontend**: Vite builds React app to `dist/public`
- **Backend**: ESBuild bundles Node.js server to `dist/index.js`
- **Database**: Drizzle migrations in `migrations/` directory

### Environment Configuration
- **Development**: Uses `NODE_ENV=development` with Vite dev server
- **Production**: Serves static files from Express with `NODE_ENV=production`
- **Database**: Requires `DATABASE_URL` environment variable

### Hosting Requirements
- Node.js runtime for Express server
- PostgreSQL database (Neon recommended)
- Environment variables for OpenAI API key and database connection
- Static file serving capability

### Key Features
- Real-time prompt analysis with AI scoring
- User dashboard with analytics
- Chat-based AI assistance
- Responsive design with dark mode support
- Subscription-based pricing tiers
- Prompt library and management system

The application is designed as a modern SaaS platform with scalable architecture and user-friendly interface for AI prompt optimization.