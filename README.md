# 🔗 Tumbuh Ide Indonesia - Link-in-Bio Platform

**Modern, Mobile-First Link-in-Bio Platform built with Next.js 14 & Supabase**

[![Next.js](https://img.shields.io/badge/Next.js-14-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![Supabase](https://img.shields.io/badge/Supabase-Database-green?style=flat-square&logo=supabase)](https://supabase.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-blue?style=flat-square&logo=tailwindcss)](https://tailwindcss.com/)
[![Mobile First](https://img.shields.io/badge/Mobile-First-orange?style=flat-square)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)

---

## 🎯 PROJECT OVERVIEW

Platform link-in-bio yang memungkinkan users membuat halaman profil personal dengan kumpulan link sosial media dan custom links. Dibangun dengan pendekatan mobile-first untuk pengalaman optimal di semua device.

### ✨ **Key Features**
- 🔐 **Authentication System** - Register, login, email verification
- 👤 **Profile Management** - Custom bio, avatar, social links
- 🔗 **Link Management** - Social media & custom links dengan analytics
- 📊 **Analytics Dashboard** - Track clicks, visitors, dan performance
- 📱 **Mobile-First Design** - Optimized untuk mobile experience
- 🎨 **Customizable Themes** - Light/dark mode support
- 👑 **Admin Panel** - User management & content moderation

---

## 🚀 QUICK START FOR AI ASSISTANTS

### 📋 **MANDATORY FIRST STEPS**
1. **READ** `instructions.md` - Quick reference & core principles
2. **READ** `docs/WAJIB_BACA_PERTAMA.md` - Complete project context
3. **CHECK** `docs/dev_progress.md` - Current development status
4. **FOLLOW** `docs/project_structure.md` - Exact folder structure

### 🗂️ **DOCUMENTATION STRUCTURE**
\`\`\`
docs/
├── 📋 WAJIB_BACA_PERTAMA.md     # MUST READ - Project overview & context
├── 📝 requirements.md            # Complete technical requirements  
├── 🗄️ database_schema.md        # SQL schema & ready-to-use commands
├── 🎨 ui_components.md           # Design system & component specifications
├── 📊 dev_progress.md            # Development tracker & task breakdown
├── 📁 project_structure.md       # Exact folder structure to follow
└── 🚨 common_issues.md           # Troubleshooting & solutions guide
\`\`\`

---

## 🛠️ TECH STACK

### **Frontend**
- **Next.js 14** - React framework with App Router
- **React 18** - UI library with Server Components
- **Tailwind CSS** - Utility-first CSS framework
- **Lucide React** - Icon library

### **Backend**
- **Supabase** - Database, Authentication & Storage
- **Next.js API Routes** - Server-side logic
- **Server Actions** - Form handling & mutations

### **Development**
- **TypeScript** - Type safety (optional)
- **ESLint + Prettier** - Code formatting
- **Absolute Imports** - Clean import paths

---

## 📱 MOBILE-FIRST APPROACH

### **Design Principles**
- ✅ Touch targets ≥ 44px
- ✅ Bottom navigation for mobile
- ✅ Responsive breakpoints: Mobile → Tablet → Desktop
- ✅ Performance optimized for mobile networks
- ✅ Native-like interactions (swipe, pull-to-refresh)

### **Responsive Breakpoints**
\`\`\`css
Mobile:  320px - 767px   (Primary focus)
Tablet:  768px - 1023px  (Secondary)
Desktop: 1024px+         (Enhancement)
\`\`\`

---

## 🏗️ PROJECT STRUCTURE

\`\`\`
src/
├── app/                    # Next.js 14 App Router
│   ├── (auth)/            # Authentication pages group
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
│   └── common/           # Shared components
├── lib/                  # Utilities & configurations
├── hooks/                # Custom React hooks
├── contexts/             # React contexts
└── styles/               # CSS files
\`\`\`

---

## 🔧 ENVIRONMENT SETUP

### **Required Environment Variables**
\`\`\`bash
# Copy from .env.example and fill with your values
cp .env.example .env.local
\`\`\`

### **Install Dependencies**
\`\`\`bash
npm install
# or
yarn install
\`\`\`

### **Database Setup**
1. Create Supabase project
2. Run SQL commands from `docs/database_schema.md`
3. Configure RLS policies
4. Update environment variables

### **Start Development**
\`\`\`bash
npm run dev
# or
yarn dev
\`\`\`

---

## 🎯 DEVELOPMENT PHASES

### **📅 3-Day Development Sprint**

#### **PHASE 1: Foundation (Day 1)**
- ✅ Project setup & configuration
- ✅ Authentication system (register, login, verification)
- ✅ Base UI components library
- ✅ Database schema implementation
- ✅ Mobile-first layout foundation

#### **PHASE 2: Core Features (Day 2)**
- ✅ Dashboard functionality
- ✅ Profile management (bio, avatar, settings)
- ✅ Link management (social & custom links)
- ✅ Public profile pages
- ✅ File upload system

#### **PHASE 3: Advanced Features (Day 3)**
- ✅ Admin panel & user management
- ✅ Analytics dashboard & tracking
- ✅ Performance optimization
- ✅ Error handling & edge cases
- ✅ Production deployment

---

## 🤖 AI DEVELOPMENT WORKFLOW

### **Starting a New AI Session**

#### **Initial Prompt Template:**
\`\`\`
Saya sedang mengembangkan platform link-in-bio bernama "Tumbuh Ide Indonesia" menggunakan Next.js 14 dan Supabase. Semua dokumentasi project ada di folder /docs, dan ada file instructions.md di root directory.

Tolong baca instructions.md terlebih dahulu, lalu baca docs/WAJIB_BACA_PERTAMA.md untuk memahami project ini secara menyeluruh.

Saya ingin Anda membantu saya mengembangkan [SPECIFIC FEATURE] sesuai dengan dokumentasi yang ada. Pastikan mengikuti struktur folder yang sudah ditentukan di docs/project_structure.md dan menggunakan design system dari docs/ui_components.md.

Mohon konfirmasi bahwa Anda sudah membaca dan memahami dokumentasi project ini sebelum kita mulai.
\`\`\`

#### **Phase Handoff Process:**
1. **Pull latest code** from GitHub
2. **Read documentation** (instructions.md + WAJIB_BACA_PERTAMA.md)
3. **Check current progress** in dev_progress.md
4. **Continue development** from last checkpoint
5. **Update progress** and commit changes

---

## 📊 CURRENT STATUS

**Development Phase:** [Check `docs/dev_progress.md` for latest status]

**Last Updated:** [Date will be updated by AI during development]

**Next Milestone:** [Check dev_progress.md for current targets]

---

## 🔐 SECURITY FEATURES

- ✅ **Row Level Security (RLS)** - Database-level access control
- ✅ **Input Validation** - Client & server-side validation
- ✅ **Rate Limiting** - API endpoint protection
- ✅ **CSRF Protection** - Built-in Next.js protection
- ✅ **Secure File Upload** - Validated file types & sizes
- ✅ **Environment Variables** - Secure configuration management

---

## 📱 MOBILE FEATURES

- ✅ **Bottom Navigation** - Primary mobile navigation
- ✅ **Touch-Friendly UI** - 44px minimum touch targets
- ✅ **Swipe Gestures** - Native-like interactions
- ✅ **Pull-to-Refresh** - Mobile refresh pattern
- ✅ **Responsive Images** - Optimized for mobile networks
- ✅ **Progressive Web App** - App-like experience

---

## 🚀 DEPLOYMENT

### **Vercel Deployment (Recommended)**
1. Connect GitHub repository to Vercel
2. Configure environment variables in Vercel dashboard
3. Deploy automatically on push to main branch

### **Environment Variables for Production**
\`\`\`bash
NEXT_PUBLIC_SUPABASE_URL=your_production_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_production_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_production_service_role_key
\`\`\`

---

## 🐛 TROUBLESHOOTING

### **Common Issues**
- Check `docs/common_issues.md` for comprehensive troubleshooting guide
- Verify environment variables are correctly set
- Ensure Supabase project is active and accessible
- Check browser console for client-side errors
- Review Network tab for API call failures

### **Getting Help**
1. **Check documentation** in `/docs` folder first
2. **Search error messages** in common_issues.md
3. **Verify setup** against requirements.md
4. **Test on mobile** viewport for mobile-specific issues

---

## 📄 LICENSE

This project is developed for Tumbuh Ide Indonesia.

---

## 🤝 CONTRIBUTING

This project follows a structured AI-assisted development approach. All contributions should:

1. **Follow documentation** in `/docs` folder
2. **Maintain mobile-first** approach
3. **Use established** folder structure
4. **Update progress** in dev_progress.md
5. **Test on mobile** devices

---

## 📞 SUPPORT

For development support:
- Check `docs/common_issues.md` for troubleshooting
- Review `docs/WAJIB_BACA_PERTAMA.md` for project context
- Follow exact specifications in documentation files

---

**Built with ❤️ for Indonesian creators and entrepreneurs**

**Next Step for AI:** Read `instructions.md` then `docs/WAJIB_BACA_PERTAMA.md` to get started!