
# AImpress Living - AI-Powered Furniture Marketplace

A modern e-commerce platform for AI-powered furniture with voice controls, AR visualization, and intelligent vendor management.

## 🚀 Features

### Core Features
- **AI-Powered Furniture**: Smart furniture with integrated voice controls and IoT capabilities
- **Voice Commands**: Hands-free shopping with natural language processing
- **AR Visualization**: Virtual furniture placement using camera-based AR
- **Anonymous Vendor System**: Streamlined vendor management and order fulfillment
- **Real-time Chat Support**: WebSocket-based customer support system
- **Multi-role Authentication**: Customer, vendor, and admin dashboards

### AI & Smart Features
- Voice-controlled product search ("Show me sofas", "Add to cart")
- AR furniture viewer with screenshot/share capabilities
- Dynamic material calculator for custom pricing
- Smart home integration ready
- AI-powered product recommendations

## 🛠 Tech Stack

### Frontend
- **React 18** with TypeScript
- **Tailwind CSS** with shadcn/ui components
- **TanStack React Query** for server state management
- **Wouter** for client-side routing
- **Vite** for development and build

### Backend
- **Express.js** with TypeScript
- **PostgreSQL** with Drizzle ORM
- **Replit Auth** with OpenID Connect
- **WebSocket** for real-time messaging
- **JWT** for session management

### Database
- **PostgreSQL** (Neon serverless)
- **Drizzle ORM** for type-safe database operations
- **Session storage** with PostgreSQL backend

## 🚦 Getting Started

### Prerequisites
- Node.js (18+ recommended)
- PostgreSQL database
- Replit account (for authentication)

### Environment Variables
Create a `.env` file with:
```
DATABASE_URL=your_postgresql_connection_string
SESSION_SECRET=your_session_secret_key
REPL_ID=your_replit_id
```

### Installation & Setup

1. **Clone and Install**
   ```bash
   npm install
   ```

2. **Database Setup**
   ```bash
   npm run db:push
   ```

3. **Development**
   ```bash
   npm run dev
   ```

4. **Production Build**
   ```bash
   npm run build
   npm start
   ```

## 📁 Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Route components
│   │   ├── hooks/         # Custom React hooks
│   │   └── lib/           # Utilities and helpers
├── server/                # Express backend
│   ├── routes.ts          # API endpoints
│   ├── storage.ts         # Database operations
│   └── replitAuth.ts      # Authentication setup
├── shared/                # Shared types and schemas
│   └── schema.ts          # Database schema definitions
└── README.md
```

## 🎯 Key Components

### Voice Demo (`voice-demo.tsx`)
Interactive voice command demonstration with real-time feedback and visual indicators.

### AR Viewer (`ar-viewer.tsx`)
Camera-based augmented reality furniture placement with screenshot capabilities.

### Order Management (`order-management.tsx`)
Comprehensive order tracking with status updates, pricing details, and timeline management.

### Chat Support (`chat-support.tsx`)
Real-time WebSocket-based customer support with agent assignment and message history.

### Product Card (`product-card.tsx`)
Dynamic product display with AI features, voice commands, and AR integration.

## 🔐 Authentication

The application uses Replit Auth with OpenID Connect:
- **Login Flow**: Replit OAuth → JWT token → Session management
- **User Roles**: Customer, Vendor, Admin
- **Session Storage**: PostgreSQL-backed sessions
- **Route Protection**: Middleware-based authentication

## 📊 Database Schema

### Core Tables
- `users` - User accounts and profiles
- `vendors` - Vendor information and capabilities
- `products` - AI furniture catalog with voice commands
- `orders` - Order management and tracking
- `reviews` - Product reviews and ratings
- `support_tickets` - Customer support requests
- `messages` - Real-time chat messages

## 🚀 Deployment

### Replit Deployment
The application is configured for Replit deployment:
- Automatic dependency installation
- Environment variable management
- Built-in database hosting
- One-click deployment

### Production Configuration
- **Build**: `npm run build`
- **Start**: `npm start`
- **Port**: 5000 (forwarded to 80/443)
- **Environment**: NODE_ENV=production

## 🎨 UI/UX Features

### Design System
- **shadcn/ui** components with custom theming
- **Responsive design** with mobile-first approach
- **Accessibility** with ARIA labels and keyboard navigation
- **Loading states** with skeleton components
- **Error handling** with user-friendly messages

### Animations & Effects
- Floating animations for hero elements
- Voice pulse effects for active listening
- Card hover transitions
- Smooth scroll behaviors
- Gradient backgrounds and effects

## 🔧 API Endpoints

### Authentication
- `GET /api/auth/user` - Get current user
- `POST /api/auth/logout` - Logout user

### Products
- `GET /api/products` - List products with filters
- `GET /api/products/:id` - Get product details
- `POST /api/products` - Create product (vendors)

### Orders
- `GET /api/orders` - List user orders
- `POST /api/orders` - Create new order
- `PUT /api/orders/:id` - Update order status

### Support
- `GET /api/support-tickets` - List support tickets
- `POST /api/support-tickets` - Create support ticket
- `WebSocket /ws` - Real-time messaging

## 🎵 Voice Commands

### Supported Commands
- "Show me [category]" - Filter products
- "Add to cart" - Add current product
- "What can this do?" - Show AI features
- "Take a photo" - Capture AR screenshot
- "Start demo" - Begin voice interaction

### Implementation
- Speech Recognition API
- Natural language processing
- Real-time feedback with visual indicators
- Error handling for unsupported commands

## 🔮 AR Features

### Capabilities
- Camera-based furniture placement
- Real-time rendering with device orientation
- Screenshot capture and sharing
- Multiple viewing angles
- Lighting simulation

### Browser Support
- WebRTC camera access
- Device orientation API
- Canvas rendering
- File download API

## 🛡 Security Features

- **CSRF Protection**: Express middleware
- **Session Security**: Secure cookies with TTL
- **Input Validation**: Zod schema validation
- **SQL Injection Prevention**: Parameterized queries
- **Authentication**: JWT with OpenID Connect

## 🎯 Performance Optimizations

- **Code Splitting**: React lazy loading
- **Image Optimization**: Responsive images with srcset
- **Database**: Connection pooling and query optimization
- **Caching**: React Query with stale-while-revalidate
- **Bundle Size**: Tree shaking and dead code elimination

## 🧪 Development Features

- **Hot Module Replacement**: Vite HMR
- **TypeScript**: Full type safety across stack
- **ESLint**: Code quality and consistency
- **Error Boundaries**: Graceful error handling
- **Development Banner**: Replit integration

## 📱 Mobile Features

- **Progressive Web App** ready
- **Touch Gestures** for AR viewer
- **Responsive Design** for all screen sizes
- **Offline Support** with service workers (ready)
- **Push Notifications** infrastructure ready

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For technical support or questions:
- Use the in-app chat support
- Check the documentation in `replit.md`
- Review the component examples in `/client/src/components`

---

**AImpress Living** - Transforming furniture shopping with AI, voice controls, and augmented reality.
