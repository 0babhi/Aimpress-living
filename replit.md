# AImpress Living - AI-Powered Furniture Marketplace

## Overview

AImpress Living is a modern e-commerce platform for AI-powered furniture. The application features voice-controlled furniture, AR visualization, and an anonymous vendor system. It's built with React + TypeScript on the frontend, Express.js on the backend, and PostgreSQL with Drizzle ORM for the database.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui components
- **State Management**: TanStack React Query for server state
- **Routing**: Wouter for client-side routing
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Replit Auth with OpenID Connect
- **Session Management**: Express session with PostgreSQL store
- **API Design**: RESTful endpoints under `/api` prefix

### Database Design
- **ORM**: Drizzle with PostgreSQL dialect
- **Schema Location**: `shared/schema.ts` for type safety across client/server
- **Session Storage**: Built-in session table for Replit Auth
- **Key Tables**: users, vendors, products, orders, reviews, support_tickets, messages

## Key Components

### Authentication System
- **Provider**: Replit Auth using OpenID Connect
- **Strategy**: Passport.js integration with custom verification
- **Session Management**: PostgreSQL-backed sessions with configurable TTL
- **User Roles**: customer, vendor, admin support

### Product Management
- **Features**: AI-powered furniture with voice commands
- **Categories**: Tables, chairs, storage, lighting
- **Search**: Full-text search with category and price filtering
- **Media**: Image galleries with AR/3D visualization support

### Order System
- **Workflow**: Cart → Checkout → Order Management
- **Status Tracking**: Multiple order states (pending, processing, shipped, delivered)
- **Vendor Management**: Anonymous vendor system with order fulfillment

### AI Features
- **Voice Commands**: Product-specific voice interactions
- **AR Visualization**: Camera-based AR viewing of furniture
- **Material Calculator**: Dynamic pricing based on material selection
- **Chat Support**: Real-time customer support with WebSocket integration

### UI/UX Components
- **Design System**: shadcn/ui components with custom theming
- **Responsive Design**: Mobile-first approach with Tailwind breakpoints
- **Accessibility**: ARIA labels and keyboard navigation support
- **Loading States**: Skeleton components and proper error handling

## Data Flow

### Authentication Flow
1. User visits landing page if not authenticated
2. Login redirects to Replit Auth provider
3. OpenID Connect callback processes user claims
4. Session established with PostgreSQL store
5. User redirected to dashboard based on role

### Product Discovery Flow
1. Products fetched with optional filters (category, price, AI features)
2. Search functionality queries product names and descriptions
3. Product details include AI capabilities and voice commands
4. AR viewer launches camera interface for furniture visualization

### Order Management Flow
1. Cart items stored in client state
2. Checkout process validates inventory and pricing
3. Order created with vendor assignment
4. Status updates tracked through order lifecycle
5. Support tickets can be created for order issues

## External Dependencies

### Database
- **Provider**: Neon PostgreSQL (serverless)
- **Connection**: WebSocket-based with connection pooling
- **Migrations**: Drizzle Kit for schema management

### Authentication
- **Provider**: Replit Auth service
- **Protocol**: OpenID Connect with JWT tokens
- **Session Store**: PostgreSQL with connect-pg-simple

### Payment Processing
- **Provider**: Stripe integration (configured but not fully implemented)
- **Components**: React Stripe.js components available

### Development Tools
- **Replit Integration**: Development banner and cartographer plugin
- **Error Handling**: Runtime error modal for development
- **Hot Reload**: Vite HMR with Express middleware

## Deployment Strategy

### Development Environment
- **Server**: Express with Vite middleware for HMR
- **Database**: Environment variable `DATABASE_URL` required
- **Session**: `SESSION_SECRET` environment variable required
- **Auth**: `REPL_ID` and `ISSUER_URL` for Replit Auth

### Production Build
- **Frontend**: Vite builds to `dist/public`
- **Backend**: esbuild bundles server to `dist/index.js`
- **Static Files**: Served from build output directory
- **Database**: Drizzle migrations applied via `db:push` script

### Environment Configuration
- **Required Variables**: DATABASE_URL, SESSION_SECRET, REPL_ID
- **Optional Variables**: ISSUER_URL (defaults to Replit OIDC endpoint)
- **Development**: NODE_ENV=development enables dev tools
- **Production**: NODE_ENV=production optimizes for deployment

The application follows a modern full-stack architecture with strong typing throughout, proper separation of concerns, and scalable patterns for both development and production environments.