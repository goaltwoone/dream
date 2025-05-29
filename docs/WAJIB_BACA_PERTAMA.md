# 🚀 WAJIB BACA PERTAMA
## Link-in-Bio Platform (Tumbuh Ide Indonesia)

**Project Status:** 🔄 In Development  
**Last Updated:** [Tanggal Update]  
**Tech Stack:** Next.js 14 + Supabase + Tailwind CSS

---

## 📋 OVERVIEW PROJECT

### Tujuan Project
Platform Link-in-Bio profesional untuk content creator dan brand di Indonesia, dengan fokus awal di Surabaya, Gresik, dan Sidoarjo. Platform ini memungkinkan pengguna membuat halaman profil dengan link sosial media dan custom link yang dapat diakses melalui URL `domain.com/[username]`.

### User Roles
1. **Content Creator (CC)**: Fokus personal branding, multiple niches (1-3), opsi tampilkan umur
2. **Brand**: Fokus bisnis, single business category
3. **Admin**: Akses penuh sistem, manajemen user & konten

### Core Features (Step 1)
- User registration/authentication dengan email verification
- Role-based profiles (Content Creator, Brand, Admin)
- Social media links management
- Custom links dengan analytics
- Public profile pages (domain.com/[username])
- Basic analytics dashboard
- Mobile-first web application yang terasa seperti native app

---

## 🏗️ STRATEGI DEVELOPMENT

### Step 1: Foundation (PRIORITAS UTAMA)
Fokus pada membangun foundation yang solid dan fully functional dengan core features:

1. **UI/UX Foundation & Mobile Design**
   - Setup Next.js + Tailwind
   - Design system (colors, typography, spacing)
   - Komponen UI dasar dengan mobile-first approach
   - Layout components (Header, Footer, Navigation)

2. **Authentication System**
   - Register flow dengan email verification
   - Login flow dengan redirect logic
   - Forgot password flow
   - Complete profile flow (role, username, niche/category)
   - Auth middleware & route protection

3. **Dashboard Core Features**
   - Profile management (edit profile, upload photo)
   - Social links CRUD (add, edit, delete, list)
   - Custom links CRUD (add, edit, delete, list, reorder)
   - Settings (change password, delete account)
   - Basic analytics (view count, click count)

4. **Public Profile Pages**
   - Dynamic route [username]
   - Public profile display (responsive)
   - Social links grid dengan click tracking
   - Custom links list dengan click tracking
   - SEO meta tags

5. **Testing & Polish**
   - Cross-browser testing
   - Mobile responsive testing
   - Performance optimization
   - Security hardening

### Step 2: Enhancement (SETELAH STEP 1 SELESAI)
Setelah Step 1 solid dan fully functional, baru lanjut ke advanced features:

- Advanced analytics (UTM, device breakdown, geographic)
- Theme customization & profile templates
- PWA support
- Enhanced security (login history)
- Admin panel
- Profile preview & QR code
- Push notifications

---

## 📱 MOBILE-FIRST WEB APPLICATION

Project ini mengutamakan pendekatan **mobile-first** dengan UI/UX yang terasa seperti native app:

- Bottom navigation untuk mobile
- Touch-friendly buttons & inputs
- Swipe gestures
- Pull-to-refresh
- Native-like animations
- PWA ready (installable as mobile app)

Semua fitur harus dioptimalkan untuk pengalaman mobile yang mulus, namun tetap responsif di tablet dan desktop.

---

## 📂 STRUKTUR PROJECT

### Backend Structure
\`\`\`
src/lib/
├── auth/           # Authentication utilities
├── database/       # Database operations
├── validation/     # Input validation
├── analytics/      # Analytics tracking
└── upload/         # File upload handling
\`\`\`

### Frontend Structure
\`\`\`
src/components/
├── ui/             # Base UI components
├── forms/          # Form components
├── dashboard/      # Dashboard-specific components
├── mobile/         # Mobile-specific components
└── public/         # Public page components
\`\`\`

### Routes Structure
\`\`\`
src/app/
├── (auth)/         # Auth routes (login, register, forgot, complete)
├── (dashboard)/    # Dashboard routes
├── (admin)/        # Admin routes
├── (public)/       # Public static pages (about, contact, terms)
├── [username]/     # Dynamic public profile routes
└── api/            # API endpoints
\`\`\`

---

## 🗄️ DATABASE STRUCTURE

Project menggunakan Supabase untuk authentication dan database dengan struktur utama:

- **profiles**: Data utama user (extends auth.users)
- **profile_niches**: Many-to-many (CC dapat memiliki 1-3 niche)
- **profile_categories**: Many-to-many (Brand memiliki 1 kategori)
- **social_links**: One-to-many (unlimited social media links)
- **custom_links**: One-to-many (unlimited custom links)
- **analytics**: Tracking untuk page views dan link clicks

Detail lengkap schema dan SQL commands tersedia di `database_schema.md`.

---

## 🔒 SECURITY REQUIREMENTS

- Input validation & sanitization untuk semua form
- Row Level Security (RLS) di Supabase
- Route protection dengan middleware
- Rate limiting untuk API dan public pages
- File upload validation dan sanitization
- XSS prevention
- CSRF protection

---

## 📚 DOKUMENTASI PENTING

Untuk memahami project secara menyeluruh, baca file-file berikut secara berurutan:

1. **WAJIB_BACA_PERTAMA.md** (file ini) - Overview dan strategi development
2. **dev_progress.md** - Status development saat ini
3. **instruction.md** - Panduan teknis detail
4. **requirements.md** - Spesifikasi fitur lengkap
5. **database_schema.md** - Schema database dan SQL commands
6. **ui_components.md** - Library komponen UI dan design system
7. **common_issues.md** - Troubleshooting dan solusi umum

---

## ⚠️ CRITICAL REMINDERS

### Untuk AI Assistant
1. **FOKUS PADA STEP 1 DULU** - Jangan loncat ke advanced features sebelum foundation solid
2. **MOBILE-FIRST APPROACH** - Semua UI/UX harus optimal di mobile
3. **PEMISAHAN BACKEND/FRONTEND** - Jaga pemisahan yang jelas sesuai struktur
4. **SECURITY FIRST** - Validasi semua input, gunakan RLS, sanitize data
5. **KONSISTENSI KODE** - Ikuti patterns yang sudah ada

### Untuk Developer
1. **ENVIRONMENT VARIABLES** - Gunakan .env untuk semua konfigurasi, hindari hardcoding
2. **SUPABASE SETUP** - Pastikan RLS policies diimplementasikan dengan benar
3. **RESPONSIVE TESTING** - Test di berbagai ukuran layar dan device
4. **PERFORMANCE** - Optimasi loading time dan bundle size
5. **ACCESSIBILITY** - Pastikan aplikasi accessible

---

## 🎯 NEXT STEPS

1. Cek `dev_progress.md` untuk melihat status development saat ini
2. Pahami requirements lengkap di `requirements.md`
3. Review database schema di `database_schema.md`
4. Pelajari komponen UI di `ui_components.md`
5. Mulai development sesuai fase di `dev_progress.md`

---

**Remember:** Fokus pada membangun foundation yang solid (Step 1) dengan pendekatan mobile-first sebelum menambahkan fitur-fitur advanced.