# 📁 PROJECT STRUCTURE GUIDE
## Link-in-Bio Platform (Tumbuh Ide Indonesia)

**Framework:** Next.js 14 dengan App Router  
**Approach:** Mobile-First Web Application  
**Organization:** Feature-based dengan pemisahan Backend/Frontend/Routes

---

## 🎯 STRUKTUR OVERVIEW

\`\`\`
linkinbio-platform/
├── 📁 docs/                     # Documentation files
├── 📁 public/                   # Static assets
├── 📁 src/                      # Source code
├── 📄 .env.local                # Environment variables
├── 📄 .env.example              # Environment template
├── 📄 .gitignore               # Git ignore rules
├── 📄 next.config.js           # Next.js configuration
├── 📄 package.json             # Dependencies
├── 📄 tailwind.config.js       # Tailwind configuration
├── 📄 middleware.js            # Next.js middleware
└── 📄 README.md                # Project documentation
\`\`\`

---

## 📚 DOCUMENTATION STRUCTURE

\`\`\`
docs/
├── 📋 WAJIB_BACA_PERTAMA.md     # AI must read first
├── 📝 requirements.md            # Complete requirements
├── 🗄️ database_schema.md        # SQL commands ready
├── 🎨 ui_components.md           # Design system & components
├── 📊 dev_progress.md            # Development tracker
├── 📁 project_structure.md       # This file
└── 🚨 common_issues.md           # Troubleshooting guide
\`\`\`

**AI Instructions:**
- **ALWAYS** read `WAJIB_BACA_PERTAMA.md` first
- Check `dev_progress.md` for current status
- Reference other files as needed

---

## 🌐 PUBLIC ASSETS

\`\`\`
public/
├── 📁 images/
│   ├── logo.png                 # App logo
│   ├── logo-dark.png           # Dark mode logo
│   ├── favicon.ico             # Favicon
│   ├── og-image.png            # Open Graph image
│   └── 📁 placeholders/        # Placeholder images
│       ├── avatar.png          # Default avatar
│       └── link-logo.png       # Default link logo
├── 📁 icons/
│   ├── icon-192.png            # PWA icon 192x192
│   ├── icon-512.png            # PWA icon 512x512
│   └── apple-touch-icon.png    # Apple touch icon
├── 📄 manifest.json             # PWA manifest
├── 📄 robots.txt               # SEO robots
└── 📄 sitemap.xml              # SEO sitemap
\`\`\`

---

## 🏗️ SOURCE CODE STRUCTURE

### 📱 APP DIRECTORY (Next.js 14 App Router)

\`\`\`
src/app/
├── 📄 layout.jsx                # Root layout
├── 📄 page.jsx                 # Landing page
├── 📄 globals.css              # Global styles
├── 📄 not-found.jsx            # 404 page
├── 📄 loading.jsx              # Global loading
├── 📄 error.jsx                # Global error boundary
├── 📁 (auth)/                  # Auth route group
│   ├── 📄 layout.jsx           # Auth layout
│   ├── 📁 login/
│   │   └── 📄 page.jsx         # Login page
│   ├── 📁 register/
│   │   └── 📄 page.jsx         # Register page
│   ├── 📁 forgot-password/
│   │   └── 📄 page.jsx         # Forgot password page
│   ├── 📁 update-password/
│   │   └── 📄 page.jsx         # Update password page
│   └── 📁 complete/
│       └── 📄 page.jsx         # Complete profile page
├── 📁 (dashboard)/             # Dashboard route group
│   ├── 📄 layout.jsx           # Dashboard layout
│   └── 📁 dashboard/
│       ├── 📄 page.jsx         # Dashboard home
│       ├── 📁 profile/
│       │   └── 📄 page.jsx     # Profile management
│       ├── 📁 social-links/
│       │   └── 📄 page.jsx     # Social links management
│       ├── 📁 custom-links/
│       │   └── 📄 page.jsx     # Custom links management
│       ├── 📁 analytics/
│       │   └── 📄 page.jsx     # Analytics dashboard
│       └── 📁 settings/
│           └── 📄 page.jsx     # Settings page
├── 📁 (admin)/                 # Admin route group
│   ├── 📄 layout.jsx           # Admin layout
│   └── 📁 admin/
│       ├── 📄 page.jsx         # Admin dashboard
│       ├── 📁 users/
│       │   ├── 📄 page.jsx     # Users management
│       │   └── 📁 [id]/
│       │       └── 📄 page.jsx # User detail
│       ├── 📁 content/
│       │   └── 📄 page.jsx     # Content management
│       ├── 📁 system/
│       │   └── 📄 page.jsx     # System settings
│       └── 📁 analytics/
│           └── 📄 page.jsx     # System analytics
├── 📁 (public)/                # Public pages route group
│   ├── 📁 about/
│   │   └── 📄 page.jsx         # About page
│   ├── 📁 contact/
│   │   └── 📄 page.jsx         # Contact page
│   └── 📁 terms/
│       └── 📄 page.jsx         # Terms page
├── 📁 [username]/              # Dynamic public profile
│   ├── 📄 page.jsx             # Public profile page
│   ├── 📄 loading.jsx          # Profile loading
│   └── 📄 not-found.jsx        # Profile not found
└── 📁 api/                     # API routes
    ├── 📁 auth/                # Authentication endpoints
    │   ├── 📁 register/
    │   │   └── 📄 route.js     # POST /api/auth/register
    │   ├── 📁 login/
    │   │   └── 📄 route.js     # POST /api/auth/login
    │   ├── 📁 logout/
    │   │   └── 📄 route.js     # POST /api/auth/logout
    │   ├── 📁 complete/
    │   │   └── 📄 route.js     # POST /api/auth/complete
    │   └── 📁 resend-verification/
    │       └── 📄 route.js     # POST /api/auth/resend-verification
    ├── 📁 user/                # User management endpoints
    │   ├── 📁 profile/
    │   │   └── 📄 route.js     # GET/PUT /api/user/profile
    │   ├── 📁 social-links/
    │   │   └── 📄 route.js     # GET/POST/PUT/DELETE /api/user/social-links
    │   ├── 📁 custom-links/
    │   │   └── 📄 route.js     # GET/POST/PUT/DELETE /api/user/custom-links
    │   ├── 📁 analytics/
    │   │   └── 📄 route.js     # GET /api/user/analytics
    │   └── 📁 settings/
    │       └── 📄 route.js     # PUT /api/user/settings
    ├── 📁 admin/               # Admin endpoints
    │   ├── 📁 users/
    │   │   └── 📄 route.js     # GET/PUT/DELETE /api/admin/users
    │   ├── 📁 content/
    │   │   └── 📄 route.js     # GET/POST/PUT/DELETE /api/admin/content
    │   └── 📁 system/
    │       └── 📄 route.js     # GET/PUT /api/admin/system
    ├── 📁 public/              # Public endpoints
    │   ├── 📁 profile/
    │   │   └── 📁 [username]/
    │   │       └── 📄 route.js # GET /api/public/profile/[username]
    │   └── 📁 analytics/
    │       └── 📄 route.js     # POST /api/public/analytics
    └── 📁 upload/              # File upload endpoints
        ├── 📁 profile-image/
        │   └── 📄 route.js     # POST /api/upload/profile-image
        └── 📁 link-logo/
            └── 📄 route.js     # POST /api/upload/link-logo
\`\`\`

---

## 🧩 COMPONENTS STRUCTURE

\`\`\`
src/components/
├── 📁 ui/                      # Base UI components
│   ├── 📄 Button.jsx           # Button component dengan variants
│   ├── 📄 Input.jsx            # Input component dengan validation
│   ├── 📄 Card.jsx             # Card component dengan variants
│   ├── 📄 Modal.jsx            # Modal component
│   ├── 📄 Toast.jsx            # Toast notification
│   ├── 📄 Loading.jsx          # Loading components (spinner, skeleton)
│   ├── 📄 Dropdown.jsx         # Dropdown dengan search
│   ├── 📄 FileUpload.jsx       # File upload component
│   ├── 📄 Badge.jsx            # Badge component
│   └── 📄 index.js             # Export all UI components
├── 📁 forms/                   # Form components
│   ├── 📄 RegisterForm.jsx     # Registration form
│   ├── 📄 LoginForm.jsx        # Login form
│   ├── 📄 ForgotPasswordForm.jsx # Forgot password form
│   ├── 📄 CompleteProfileForm.jsx # Complete profile form
│   ├── 📄 ProfileForm.jsx      # Profile edit form
│   ├── 📄 SocialLinkForm.jsx   # Social link form
│   ├── 📄 CustomLinkForm.jsx   # Custom link form
│   ├── 📄 PasswordChangeForm.jsx # Password change form
│   └── 📄 index.js             # Export all forms
├── 📁 dashboard/               # Dashboard specific components
│   ├── 📄 DashboardHeader.jsx  # Dashboard header
│   ├── 📄 DashboardSidebar.jsx # Desktop sidebar
│   ├── 📄 DashboardFooter.jsx  # Dashboard footer
│   ├── 📄 StatsCard.jsx        # Statistics card
│   ├── 📄 QuickActions.jsx     # Quick action buttons
│   ├── 📄 ProfileSummary.jsx   # Profile summary card
│   └── 📄 index.js             # Export dashboard components
├── 📁 mobile/                  # Mobile-specific components
│   ├── 📄 BottomNavigation.jsx # Bottom tab navigation
│   ├── 📄 MobileHeader.jsx     # Mobile header
│   ├── 📄 PullToRefresh.jsx    # Pull to refresh
│   ├── 📄 SwipeActions.jsx     # Swipe actions
│   ├── 📄 TouchFriendlyButton.jsx # Touch-friendly button
│   └── 📄 index.js             # Export mobile components
├── 📁 public/                  # Public page components
│   ├── 📄 PublicProfile.jsx    # Public profile layout
│   ├── 📄 SocialLinksGrid.jsx  # Social links grid
│   ├── 📄 CustomLinksList.jsx  # Custom links list
│   ├── 📄 ProfileHeader.jsx    # Profile header
│   ├── 📄 ShareButton.jsx      # Share profile button
│   └── 📄 index.js             # Export public components
├── 📁 admin/                   # Admin specific components
│   ├── 📄 AdminHeader.jsx      # Admin header
│   ├── 📄 AdminSidebar.jsx     # Admin sidebar
│   ├── 📄 UserTable.jsx        # Users table
│   ├── 📄 SystemStats.jsx      # System statistics
│   ├── 📄 ContentModeration.jsx # Content moderation
│   └── 📄 index.js             # Export admin components
├── 📁 analytics/               # Analytics components
│   ├── 📄 AnalyticsChart.jsx   # Charts component
│   ├── 📄 StatsOverview.jsx    # Stats overview
│   ├── 📄 VisitorInsights.jsx  # Visitor insights
│   ├── 📄 LinkPerformance.jsx  # Link performance
│   └── 📄 index.js             # Export analytics components
└── 📁 common/                  # Common/shared components
    ├── 📄 Header.jsx           # Main header
    ├── 📄 Footer.jsx           # Main footer
    ├── 📄 ThemeToggle.jsx      # Theme toggle button
    ├── 📄 SEOHead.jsx          # SEO meta tags
    ├── 📄 ErrorBoundary.jsx    # Error boundary
    ├── 📄 ConfirmDialog.jsx    # Confirmation dialog
    └── 📄 index.js             # Export common components
\`\`\`

---

## 🔧 LIBRARY & UTILITIES

\`\`\`
src/lib/
├── 📄 supabase.js              # Supabase client configuration
├── 📄 auth.js                  # Authentication utilities
├── 📄 validation.js            # Form validation schemas
├── 📄 sanitize.js              # Input sanitization
├── 📄 upload.js                # File upload utilities
├── 📄 analytics.js             # Analytics tracking
├── 📄 rate-limit.js            # Rate limiting utilities
├── 📄 constants.js             # App constants
├── 📄 utils.js                 # General utilities
├── 📄 api.js                   # API client utilities
├── 📄 seo.js                   # SEO utilities
└── 📄 index.js                 # Export all utilities
\`\`\`

---

## 🎣 HOOKS STRUCTURE

\`\`\`
src/hooks/
├── 📄 useAuth.js               # Authentication hook
├── 📄 useProfile.js            # Profile management hook
├── 📄 useTheme.js              # Theme management hook
├── 📄 useAnalytics.js          # Analytics hook
├── 📄 useLocalStorage.js       # Local storage hook
├── 📄 useDebounce.js           # Debounce hook
├── 📄 useMediaQuery.js         # Media query hook
├── 📄 useToast.js              # Toast notification hook
├── 📄 useFileUpload.js         # File upload hook
└── 📄 index.js                 # Export all hooks
\`\`\`

---

## 🌐 CONTEXTS STRUCTURE

\`\`\`
src/contexts/
├── 📄 AuthContext.jsx          # Authentication context
├── 📄 ThemeContext.jsx         # Theme context
├── 📄 ToastContext.jsx         # Toast notification context
├── 📄 AnalyticsContext.jsx     # Analytics context
└── 📄 index.js                 # Export all contexts
\`\`\`

---

## 🛡️ MIDDLEWARE STRUCTURE

\`\`\`
src/middleware/
├── 📄 auth.js                  # Authentication middleware
├── 📄 admin.js                 # Admin access middleware
├── 📄 rate-limit.js            # Rate limiting middleware
└── 📄 index.js                 # Export all middleware
\`\`\`

---

## 🎨 STYLES STRUCTURE

\`\`\`
src/styles/
├── 📄 globals.css              # Global styles
├── 📄 components.css           # Component-specific styles
├── 📄 dashboard.css            # Dashboard styles
├── 📄 public-profile.css       # Public profile styles
├── 📄 mobile.css               # Mobile-specific styles
└── 📄 animations.css           # Custom animations
\`\`\`

---

## ⚙️ CONFIGURATION FILES

### Root Level Configuration

\`\`\`
# Next.js Configuration
next.config.js
\`\`\`
\`\`\`javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    appDir: true,
  },
  images: {
    domains: ['api.dicebear.com', 'your-supabase-project.supabase.co'],
  },
  env: {
    CUSTOM_KEY: process.env.CUSTOM_KEY,
  },
}

module.exports = nextConfig
\`\`\`

### Tailwind Configuration

\`\`\`
# Tailwind CSS Configuration
tailwind.config.js
\`\`\`
\`\`\`javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './src/pages/**/*.{js,ts,jsx,tsx,mdx}',
    './src/components/**/*.{js,ts,jsx,tsx,mdx}',
    './src/app/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#faf5ff',
          500: '#8b5cf6',
          600: '#7c3aed',
          700: '#6d28d9',
        },
        secondary: {
          50: '#fefce8',
          500: '#eab308',
          600: '#d97706',
        }
      },
      fontFamily: {
        primary: ['Inter', 'sans-serif'],
        display: ['Poppins', 'sans-serif'],
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
}
\`\`\`

### Middleware Configuration

\`\`\`
# Next.js Middleware
middleware.js (root level)
\`\`\`
\`\`\`javascript
import { createMiddlewareClient } from '@supabase/auth-helpers-nextjs'
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const res = NextResponse.next()
  const supabase = createMiddlewareClient({ req, res })
  
  const {
    data: { user },
  } = await supabase.auth.getUser()

  // Auth protection logic
  if (req.nextUrl.pathname.startsWith('/dashboard') && !user) {
    return NextResponse.redirect(new URL('/login', req.url))
  }

  // Admin protection logic
  if (req.nextUrl.pathname.startsWith('/admin')) {
    // Check admin role
  }

  return res
}

export const config = {
  matcher: ['/dashboard/:path*', '/admin/:path*']
}
\`\`\`

---

## 📝 FILE NAMING CONVENTIONS

### Components
- **PascalCase** untuk component files: `UserProfile.jsx`
- **camelCase** untuk utility files: `validateInput.js`
- **kebab-case** untuk page files: `social-links/page.jsx`

### API Routes
- **kebab-case** untuk route folders: `social-links/route.js`
- **camelCase** untuk function names: `getUserProfile()`

### Constants
- **SCREAMING_SNAKE_CASE** untuk constants: `API_ENDPOINTS.js`
- **camelCase** untuk config objects: `supabaseConfig`

---

## 🔗 IMPORT/EXPORT PATTERNS

### Component Imports
\`\`\`javascript
// UI Components
import { Button, Input, Card } from '@/components/ui'

// Form Components
import { LoginForm, RegisterForm } from '@/components/forms'

// Dashboard Components
import { DashboardHeader, StatsCard } from '@/components/dashboard'

// Mobile Components
import { BottomNavigation, PullToRefresh } from '@/components/mobile'
\`\`\`

### Utility Imports
\`\`\`javascript
// Utilities
import { supabase } from '@/lib/supabase'
import { validateEmail, sanitizeInput } from '@/lib/validation'
import { uploadFile } from '@/lib/upload'

// Hooks
import { useAuth, useTheme, useToast } from '@/hooks'

// Constants
import { API_ENDPOINTS, ROUTES } from '@/lib/constants'
\`\`\`

### Absolute Imports Configuration
\`\`\`javascript
// jsconfig.json or tsconfig.json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"],
      "@/components/*": ["./src/components/*"],
      "@/lib/*": ["./src/lib/*"],
      "@/hooks/*": ["./src/hooks/*"],
      "@/contexts/*": ["./src/contexts/*"]
    }
  }
}
\`\`\`

---

## 📱 MOBILE-FIRST ORGANIZATION

### Mobile Component Priority
1. **BottomNavigation** - Primary navigation untuk mobile
2. **TouchFriendlyButton** - Minimum 44px touch targets
3. **PullToRefresh** - Native-like refresh gesture
4. **SwipeActions** - Swipe untuk edit/delete actions

### Responsive Layout Pattern
\`\`\`javascript
// Layout Component Example
const ResponsiveLayout = ({ children }) => {
  const isMobile = useMediaQuery('(max-width: 768px)')
  
  return (
    <div className="min-h-screen">
      {/* Header - Always visible */}
      <Header />
      
      <div className="flex">
        {/* Sidebar - Desktop only */}
        {!isMobile && <Sidebar />}
        
        {/* Main content */}
        <main className="flex-1 pb-16 md:pb-0">
          {children}
        </main>
      </div>
      
      {/* Bottom Navigation - Mobile only */}
      {isMobile && <BottomNavigation />}
    </div>
  )
}
\`\`\`

---

## 🛣️ ROUTE STRUCTURE DETAIL

### Authentication Routes
\`\`\`
/login                  → Login page
/register               → Registration page
/forgot-password        → Forgot password page
/update-password        → Update password page (from email link)
/complete               → Complete profile page
\`\`\`

### Dashboard Routes
\`\`\`
/dashboard              → Dashboard home
/dashboard/profile      → Profile management
/dashboard/social-links → Social links management
/dashboard/custom-links → Custom links management
/dashboard/analytics    → Analytics dashboard
/dashboard/settings     → Settings page
\`\`\`

### Admin Routes
\`\`\`
/admin                  → Admin dashboard
/admin/users            → Users management
/admin/users/[id]       → User detail page
/admin/content          → Content management
/admin/system           → System settings
/admin/analytics        → System analytics
\`\`\`

### Public Routes
\`\`\`
/                       → Landing page
/about                  → About page
/contact                → Contact page
/terms                  → Terms of service
/[username]             → Public profile page
\`\`\`

### API Routes
\`\`\`
POST /api/auth/register           → User registration
POST /api/auth/login              → User login
POST /api/auth/logout             → User logout
POST /api/auth/complete           → Complete profile
POST /api/auth/resend-verification → Resend verification email

GET  /api/user/profile            → Get user profile
PUT  /api/user/profile            → Update user profile
GET  /api/user/social-links       → Get social links
POST /api/user/social-links       → Create social link
PUT  /api/user/social-links       → Update social link
DELETE /api/user/social-links     → Delete social link

GET  /api/public/profile/[username] → Get public profile
POST /api/public/analytics          → Track analytics

POST /api/upload/profile-image    → Upload profile image
POST /api/upload/link-logo        → Upload link logo
\`\`\`

---

## 📋 DEVELOPMENT WORKFLOW

### File Creation Order
1. **Setup project structure** sesuai folder di atas
2. **Create base UI components** di `src/components/ui/`
3. **Setup authentication** di `src/app/(auth)/`
4. **Build dashboard** di `src/app/(dashboard)/`
5. **Create public profiles** di `src/app/[username]/`
6. **Add admin panel** di `src/app/(admin)/`

### Component Development Pattern
\`\`\`javascript
// 1. Create component file
// 2. Import dependencies
import { useState } from 'react'
import { Button, Input } from '@/components/ui'
import { useAuth } from '@/hooks'

// 3. Define component
const ComponentName = ({ prop1, prop2 }) => {
  // 4. State and hooks
  const { user } = useAuth()
  const [state, setState] = useState(null)

  // 5. Event handlers
  const handleAction = () => {
    // Logic here
  }

  // 6. Render
  return (
    <div className="component-container">
      {/* JSX here */}
    </div>
  )
}

// 7. Export
export default ComponentName
\`\`\`

---

## ⚠️ CRITICAL REMINDERS

### For AI Assistants
1. **ALWAYS** follow this exact folder structure
2. **USE** absolute imports dengan @ prefix
3. **SEPARATE** backend logic di `/api` routes
4. **IMPLEMENT** mobile-first approach
5. **VALIDATE** all inputs di both client dan server
6. **REFERENCE** ui_components.md untuk styling consistency

### Security Guidelines
- **NO** direct database calls dari frontend
- **ALWAYS** validate inputs di API routes
- **USE** Supabase RLS policies
- **IMPLEMENT** rate limiting
- **SANITIZE** all user inputs

### Performance Guidelines
- **LAZY LOAD** components where appropriate
- **OPTIMIZE** images dengan Next.js Image component
- **USE** proper caching strategies
- **MINIMIZE** bundle sizes

---

**Remember:** This structure is designed untuk 3-day development dengan AI assistance. Ikuti struktur ini exactly untuk consistency dan efficiency.
\`\`\`
