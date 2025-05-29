# 🚀 AI DEVELOPMENT INSTRUCTIONS
## Link-in-Bio Platform (Tumbuh Ide Indonesia)

**Framework:** Next.js 14 + Supabase  
**Approach:** Mobile-First Web Application  
**Timeline:** 3-Day Development Sprint

---

## 📋 QUICK START FOR AI ASSISTANTS

### 🎯 FIRST THINGS FIRST
1. **READ** `docs/WAJIB_BACA_PERTAMA.md` - MANDATORY first read
2. **CHECK** `docs/dev_progress.md` - Current development status
3. **FOLLOW** exact folder structure from `docs/project_structure.md`
4. **REFERENCE** other docs as needed

### 🗂️ DOCUMENTATION MAP
\`\`\`
docs/
├── 📋 WAJIB_BACA_PERTAMA.md     # MUST READ FIRST - Project overview
├── 📝 requirements.md            # Complete technical requirements
├── 🗄️ database_schema.md        # SQL schema & commands (ready to use)
├── 🎨 ui_components.md           # Design system & component specs
├── 📊 dev_progress.md            # Development tracker & task breakdown
├── 📁 project_structure.md       # Exact folder structure to follow
└── 🚨 common_issues.md           # Troubleshooting & solutions
\`\`\`

---

## ⚡ CORE DEVELOPMENT PRINCIPLES

### 📱 MOBILE-FIRST MANDATORY
- **Touch targets:** Minimum 44px
- **Bottom navigation:** Primary mobile navigation
- **Responsive breakpoints:** Mobile → Tablet → Desktop
- **Performance:** Optimize for mobile networks

### 🏗️ ARCHITECTURE RULES
- **Next.js 14 App Router** - NO Pages Router
- **Feature-based organization** - Group by functionality
- **Absolute imports** - Use `@/` prefix always
- **API separation** - Backend logic ONLY in `/api` routes
- **Component isolation** - Reusable components in `/components`

### 🔐 SECURITY FIRST
- **Input validation** - Both client AND server
- **Supabase RLS** - Row Level Security policies
- **Rate limiting** - Implement on all API routes
- **Input sanitization** - Clean all user inputs
- **Authentication** - Protect all dashboard routes

---

## 🛠️ TECHNICAL STACK

### Frontend
- **Next.js 14** (App Router)
- **React 18** (Server Components priority)
- **Tailwind CSS** (Mobile-first utility classes)
- **Lucide React** (Icons only - NO custom SVGs)

### Backend
- **Supabase** (Database + Auth + Storage)
- **Next.js API Routes** (Server-side logic)
- **Server Actions** (Form handling)

### Development Tools
- **ESLint + Prettier** (Code formatting)
- **Absolute imports** (`@/` paths)
- **Environment variables** (Secure config)

---

## 📁 FOLDER STRUCTURE QUICK REFERENCE

\`\`\`
src/
├── app/                    # Next.js 14 App Router
│   ├── (auth)/            # Auth pages group
│   ├── (dashboard)/       # Dashboard pages group
│   ├── (admin)/           # Admin pages group
│   ├── (public)/          # Public pages group
│   ├── [username]/        # Dynamic public profiles
│   └── api/               # API routes
├── components/            # Reusable components
│   ├── ui/               # Base UI components
│   ├── forms/            # Form components
│   ├── dashboard/        # Dashboard components
│   ├── mobile/           # Mobile-specific components
│   ├── public/           # Public page components
│   ├── admin/            # Admin components
│   ├── analytics/        # Analytics components
│   └── common/           # Shared components
├── lib/                  # Utilities & configurations
├── hooks/                # Custom React hooks
├── contexts/             # React contexts
├── middleware/           # Next.js middleware
└── styles/               # CSS files
\`\`\`

---

## 🎯 DEVELOPMENT WORKFLOW

### File Creation Priority
1. **Base UI components** (`src/components/ui/`)
2. **Authentication system** (`src/app/(auth)/`)
3. **Dashboard functionality** (`src/app/(dashboard)/`)
4. **Public profiles** (`src/app/[username]/`)
5. **Admin panel** (`src/app/(admin)/`)
6. **Analytics & optimization**

### Component Development Pattern
\`\`\`javascript
// 1. Import dependencies
import { useState } from 'react'
import { Button, Input } from '@/components/ui'
import { useAuth } from '@/hooks'

// 2. Define component with props
const ComponentName = ({ prop1, prop2 }) => {
  // 3. Hooks and state
  const { user } = useAuth()
  const [state, setState] = useState(null)

  // 4. Event handlers
  const handleAction = () => {
    // Logic here
  }

  // 5. Mobile-first JSX
  return (
    <div className="mobile-first-classes md:desktop-classes">
      {/* Content */}
    </div>
  )
}

export default ComponentName
\`\`\`

---

## 🚨 CRITICAL REMINDERS

### ❌ NEVER DO
- Use Pages Router (App Router only)
- Create custom SVG icons (use Lucide React)
- Direct database calls from frontend
- Skip input validation
- Ignore mobile-first approach
- Use inline styles (Tailwind only)

### ✅ ALWAYS DO
- Follow exact folder structure
- Use absolute imports (`@/`)
- Validate inputs client + server
- Implement mobile-first design
- Use Supabase for backend
- Reference documentation files
- Test on mobile viewport first

---

## 📱 MOBILE-FIRST CHECKLIST

### UI/UX Requirements
- [ ] Touch targets ≥ 44px
- [ ] Bottom navigation for mobile
- [ ] Swipe gestures where appropriate
- [ ] Pull-to-refresh functionality
- [ ] Loading states for all actions
- [ ] Error handling with user-friendly messages
- [ ] Responsive design (mobile → desktop)

### Performance Requirements
- [ ] Image optimization (Next.js Image)
- [ ] Lazy loading for components
- [ ] Minimal bundle size
- [ ] Fast loading on mobile networks
- [ ] Proper caching strategies

---

## 🔗 IMPORT PATTERNS

### Standard Imports
\`\`\`javascript
// UI Components
import { Button, Input, Card } from '@/components/ui'

// Form Components  
import { LoginForm, RegisterForm } from '@/components/forms'

// Utilities
import { supabase } from '@/lib/supabase'
import { validateEmail } from '@/lib/validation'

// Hooks
import { useAuth, useTheme } from '@/hooks'

// Constants
import { API_ENDPOINTS } from '@/lib/constants'
\`\`\`

### API Route Pattern
\`\`\`javascript
// API Route Structure
export async function GET(request) {
  // Handle GET request
}

export async function POST(request) {
  // Handle POST request
}
\`\`\`

---

## 🗄️ DATABASE QUICK REFERENCE

### Supabase Client
\`\`\`javascript
import { supabase } from '@/lib/supabase'

// Query example
const { data, error } = await supabase
  .from('table_name')
  .select('*')
  .eq('column', 'value')
\`\`\`

### Authentication
\`\`\`javascript
// Sign up
const { data, error } = await supabase.auth.signUp({
  email: 'user@example.com',
  password: 'password'
})

// Sign in
const { data, error } = await supabase.auth.signInWithPassword({
  email: 'user@example.com', 
  password: 'password'
})
\`\`\`

---

## 🎨 STYLING QUICK REFERENCE

### Tailwind Mobile-First Classes
\`\`\`css
/* Mobile first, then larger screens */
.class-name {
  @apply text-sm p-4;           /* Mobile */
  @apply md:text-base md:p-6;   /* Tablet+ */
  @apply lg:text-lg lg:p-8;     /* Desktop+ */
}
\`\`\`

### Color Scheme
\`\`\`css
/* Primary Colors */
primary-50, primary-500, primary-600, primary-700

/* Secondary Colors */  
secondary-50, secondary-500, secondary-600

/* Status Colors */
green-500 (success), red-500 (error), yellow-500 (warning)
\`\`\`

---

## 🔧 ENVIRONMENT VARIABLES

### Required Variables
\`\`\`bash
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# Custom
CUSTOM_KEY=your_custom_key
\`\`\`

---

## 📞 SUPPORT & TROUBLESHOOTING

### When Stuck
1. **Check** `docs/common_issues.md` for solutions
2. **Review** `docs/dev_progress.md` for current status
3. **Reference** specific documentation files
4. **Follow** exact folder structure
5. **Validate** against requirements.md

### Quick Debugging
- **Console errors:** Check browser dev tools
- **API issues:** Check Network tab
- **Auth problems:** Check Supabase dashboard
- **Styling issues:** Check Tailwind classes
- **Mobile issues:** Test in mobile viewport

---

## 🎯 SUCCESS METRICS

### Development Goals
- ✅ **Day 1:** Authentication + Basic UI
- ✅ **Day 2:** Dashboard + Public Profiles  
- ✅ **Day 3:** Admin Panel + Polish

### Quality Standards
- 📱 **Mobile-first** design
- ⚡ **Fast** loading times
- 🔐 **Secure** implementation
- 🎨 **Consistent** UI/UX
- 📊 **Analytics** ready

---

**Remember: This is a 3-day sprint. Follow this guide exactly for maximum efficiency and consistency.**

**Next Step:** Read `docs/WAJIB_BACA_PERTAMA.md` for complete project context.