# Chatbot Platform - Admin UI

Modern, responsive administration interface for the enterprise chatbot platform. Built with React, this UI provides organizations with powerful tools to manage their chatbot configurations, knowledge bases, analytics, and user interactions.

## 🚀 Overview

The Chatbot Admin UI is designed for small and medium-sized enterprises (SMEs) who need an intuitive, professional interface to manage their chatbot deployment without requiring technical expertise. It connects to the [Chatbot Platform Core API](https://github.com/your-org/chatbot-platform-core) to provide comprehensive chatbot management capabilities.

### Key Features

- **📊 Real-time Analytics Dashboard** - Monitor conversations, response times, and user engagement
- **📚 Knowledge Base Management** - Upload, organize, and manage documents (PDF, DOCX, TXT, Markdown)
- **🤖 Model Configuration** - Configure and switch between multiple LLM providers (OpenAI, Anthropic, Ollama, local models)
- **🎨 Widget Customization** - Customize chatbot appearance, themes, and behavior
- **👥 Organization Management** - Multi-tenant support with role-based access control
- **📈 Performance Monitoring** - Track system health, costs, and usage metrics
- **🔧 API Key Management** - Secure configuration of LLM provider credentials
- **📱 Mobile-Responsive Design** - Full functionality on desktop, tablet, and mobile devices

## 🛠️ Technology Stack

- **Frontend Framework**: React 18 with TypeScript
- **UI Components**: Ant Design (professional admin interface)
- **State Management**: React Query + Zustand
- **Routing**: React Router v6
- **Build Tool**: Vite (fast development and builds)
- **Styling**: Tailwind CSS + CSS Modules
- **Charts**: Recharts for analytics visualization
- **Authentication**: JWT-based with role-based access control

## 📋 Prerequisites

- Node.js 18+ and npm/yarn
- Running instance of [Chatbot Platform Core](https://github.com/your-org/chatbot-platform-core)
- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)

## 🚀 Quick Start

### 1. Clone and Install

```bash
git clone https://github.com/your-org/chatbot-admin-ui.git
cd chatbot-admin-ui
npm install
```

### 2. Environment Configuration

```bash
cp .env.example .env.local
```

Edit `.env.local` with your configuration:

```env
# Core API Connection
REACT_APP_API_BASE_URL=http://localhost:8000
REACT_APP_WS_URL=ws://localhost:8000/ws

# Authentication
REACT_APP_AUTH_ENABLED=true
REACT_APP_SESSION_TIMEOUT=3600

# Features
REACT_APP_ANALYTICS_ENABLED=true
REACT_APP_MULTI_TENANT=true

# Monitoring (optional)
REACT_APP_SENTRY_DSN=your-sentry-dsn
REACT_APP_GOOGLE_ANALYTICS_ID=your-ga-id
```

### 3. Development Server

```bash
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000) to access the admin interface.

### 4. Production Build

```bash
npm run build
npm run preview
```

## 📁 Project Structure

```
chatbot-admin-ui/
├── public/                     # Static assets
│   ├── favicon.ico
│   └── logos/                  # Default branding assets
├── src/
│   ├── components/             # Reusable UI components
│   │   ├── common/            # Generic components (buttons, modals)
│   │   ├── dashboard/         # Dashboard-specific components
│   │   ├── knowledge-base/    # Document management components
│   │   └── analytics/         # Charts and metrics components
│   ├── pages/                 # Main application pages
│   │   ├── Dashboard.tsx      # Main dashboard
│   │   ├── KnowledgeBase.tsx  # Document management
│   │   ├── ModelConfig.tsx    # LLM configuration
│   │   ├── Analytics.tsx      # Performance metrics
│   │   └── Settings.tsx       # Organization settings
│   ├── hooks/                 # Custom React hooks
│   │   ├── useAuth.ts         # Authentication logic
│   │   ├── useWebSocket.ts    # Real-time updates
│   │   └── useApi.ts          # API communication
│   ├── services/              # API and external services
│   │   ├── api.ts             # Core API client
│   │   ├── websocket.ts       # WebSocket manager
│   │   └── storage.ts         # Local storage utilities
│   ├── types/                 # TypeScript type definitions
│   │   ├── api.ts             # API response types
│   │   ├── components.ts      # Component prop types
│   │   └── auth.ts            # Authentication types
│   ├── utils/                 # Utility functions
│   │   ├── formatters.ts      # Data formatting
│   │   ├── validators.ts      # Form validation
│   │   └── constants.ts       # Application constants
│   ├── styles/                # Global styles and themes
│   │   ├── globals.css        # Global CSS
│   │   ├── themes/            # Customizable themes
│   │   └── components.css     # Component-specific styles
│   ├── App.tsx                # Main application component
│   ├── main.tsx               # Application entry point
│   └── vite-env.d.ts          # Vite type definitions
├── .env.example               # Environment template
├── package.json
├── vite.config.ts             # Vite configuration
├── tailwind.config.js         # Tailwind CSS configuration
├── tsconfig.json              # TypeScript configuration
└── README.md
```

## 🎯 Core Features Guide

### Dashboard Overview
- **Real-time Metrics**: Active conversations, response times, user satisfaction
- **Quick Actions**: Upload documents, configure models, view recent activity
- **System Health**: API status, database connections, LLM provider status

### Knowledge Base Management
- **Document Upload**: Drag-and-drop support for PDF, DOCX, TXT, Markdown files
- **Document Processing**: Automatic chunking, embedding generation, vector storage
- **Content Organization**: Folders, tags, and search functionality
- **Document Preview**: View processed content and chunking results

### Model Configuration
- **Multi-Provider Support**: Configure OpenAI, Anthropic, Ollama, HuggingFace models
- **Routing Rules**: Set up intelligent model routing based on query complexity
- **Fallback Chains**: Configure backup models for reliability
- **Cost Optimization**: Monitor token usage and costs per model

### Analytics & Monitoring
- **Conversation Analytics**: Volume trends, resolution rates, user satisfaction
- **Performance Metrics**: Response times, cache hit rates, error rates
- **Cost Tracking**: Token usage and costs by model and time period
- **User Insights**: Most common queries, conversation patterns

## 🔧 Configuration Options

### Environment Variables

| Variable | Description | Default | Required |
|----------|-------------|---------|----------|
| `REACT_APP_API_BASE_URL` | Core API endpoint | `http://localhost:8000` | ✅ |
| `REACT_APP_WS_URL` | WebSocket endpoint | `ws://localhost:8000/ws` | ✅ |
| `REACT_APP_AUTH_ENABLED` | Enable authentication | `true` | ❌ |
| `REACT_APP_MULTI_TENANT` | Multi-organization support | `true` | ❌ |
| `REACT_APP_ANALYTICS_ENABLED` | Enable analytics features | `true` | ❌ |
| `REACT_APP_MAX_FILE_SIZE` | Max upload size (MB) | `50` | ❌ |
| `REACT_APP_SUPPORTED_FORMATS` | Allowed file types | `pdf,docx,txt,md` | ❌ |

### Customization

#### Branding & Themes
```bash
# Copy default theme
cp src/styles/themes/default.css src/styles/themes/custom.css

# Update branding
# Replace logos in public/logos/
# Modify colors in src/styles/themes/custom.css
```

#### Feature Toggles
```typescript
// src/utils/constants.ts
export const FEATURES = {
  ANALYTICS: process.env.REACT_APP_ANALYTICS_ENABLED === 'true',
  MULTI_TENANT: process.env.REACT_APP_MULTI_TENANT === 'true',
  ADVANCED_CONFIG: process.env.REACT_APP_ADVANCED_CONFIG === 'true',
};
```

## 🐳 Docker Deployment

### Development
```bash
docker build -f Dockerfile.dev -t chatbot-admin-ui:dev .
docker run -p 3000:3000 -v $(pwd):/app chatbot-admin-ui:dev
```

### Production
```bash
docker build -t chatbot-admin-ui:latest .
docker run -p 80:80 \
  -e REACT_APP_API_BASE_URL=https://api.yourdomain.com \
  chatbot-admin-ui:latest
```

### Docker Compose
```yaml
version: '3.8'
services:
  admin-ui:
    build: .
    ports:
      - "3000:80"
    environment:
      - REACT_APP_API_BASE_URL=http://chatbot-api:8000
    depends_on:
      - chatbot-api
```

## 🧪 Testing

### Unit Tests
```bash
npm run test
npm run test:coverage
```

### Integration Tests
```bash
npm run test:integration
```

### E2E Tests (Playwright)
```bash
npm run test:e2e
npm run test:e2e:headed  # With browser UI
```

### Accessibility Testing
```bash
npm run test:a11y
```

## 📦 Available Scripts

| Script | Description |
|--------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |
| `npm run test` | Run unit tests |
| `npm run test:coverage` | Run tests with coverage |
| `npm run lint` | Run ESLint |
| `npm run lint:fix` | Fix ESLint errors |
| `npm run type-check` | Run TypeScript compiler |
| `npm run analyze` | Analyze bundle size |

## 🔐 Security Considerations

- **Authentication**: JWT-based authentication with automatic token refresh
- **HTTPS Only**: All API communications use HTTPS in production
- **CSP Headers**: Content Security Policy headers prevent XSS attacks
- **Input Validation**: All user inputs are validated client and server-side
- **Secure Storage**: Sensitive data stored securely in httpOnly cookies
- **RBAC**: Role-based access control for different user permissions

## 🌐 Browser Support

| Browser | Version |
|---------|---------|
| Chrome | 90+ |
| Firefox | 88+ |
| Safari | 14+ |
| Edge | 90+ |

## 📈 Performance

- **Bundle Size**: < 500KB gzipped
- **First Contentful Paint**: < 1.5s
- **Time to Interactive**: < 3s
- **Lighthouse Score**: > 90

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Style
- Use TypeScript for all new code
- Follow the existing ESLint configuration
- Write tests for new features
- Use semantic commit messages

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

### Documentation
- [API Documentation](https://docs.yourdomain.com/api)
- [User Guide](https://docs.yourdomain.com/user-guide)
- [Deployment Guide](https://docs.yourdomain.com/deployment)

### Getting Help
- [GitHub Issues](https://github.com/your-org/chatbot-admin-ui/issues) - Bug reports and feature requests
- [GitHub Discussions](https://github.com/your-org/chatbot-admin-ui/discussions) - Questions and community
- [Professional Support](https://yourdomain.com/support) - Enterprise support and consulting

### Community
- [Discord Server](https://discord.gg/your-server) - Real-time community chat
- [Newsletter](https://yourdomain.com/newsletter) - Updates and announcements

## 🗺️ Roadmap

### Upcoming Features
- [ ] **Multi-language Support** - Internationalization (i18n)
- [ ] **Advanced Analytics** - Custom dashboards and reports
- [ ] **A/B Testing** - Test different chatbot configurations
- [ ] **Workflow Builder** - Visual conversation flow designer
- [ ] **Integration Hub** - Pre-built integrations with popular tools
- [ ] **Mobile App** - Native iOS/Android admin app

### Version History
- **v1.0.0** - Initial release with core admin features
- **v1.1.0** - Enhanced analytics and monitoring
- **v1.2.0** - Multi-tenant support and RBAC
- **v2.0.0** - Advanced model configuration and routing

---

## 📞 Contact

**Your Organization Name**
- Website: [https://yourdomain.com](https://yourdomain.com)
- Email: [support@yourdomain.com](mailto:support@yourdomain.com)
- Twitter: [@YourHandle](https://twitter.com/YourHandle)

---

*Built with ❤️ for SMEs who want powerful, easy-to-use chatbot solutions.*