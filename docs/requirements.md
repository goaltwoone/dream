# 📝 REQUIREMENTS LENGKAP
## Link-in-Bio Platform (Tumbuh Ide Indonesia)

**Project Type:** SaaS Web Application  
**Target Users:** Content Creator & Brand Indonesia  
**Primary Focus:** Surabaya, Gresik, Sidoarjo  
**Development Approach:** Mobile-First Web Application

---

## 🎯 STEP 1: CORE REQUIREMENTS (PRIORITAS UTAMA)

### 🎨 UI/UX FOUNDATION & MOBILE DESIGN

#### Design System
- **Color Scheme:** Purple (#8B5CF6) + Yellow (#EAB308) + White
- **Typography:** Inter/Poppins untuk headings, Inter untuk body
- **Theme Support:** Light mode (default) + Dark mode dengan toggle
- **Mobile-First:** Responsive design dengan pendekatan mobile-first
- **Native App Feel:** UI/UX yang terasa seperti aplikasi mobile native

#### Mobile Web Application Features
- **Bottom Navigation:** Tab navigation untuk mobile
- **Touch-Friendly:** Minimum 44px untuk touch targets
- **Swipe Gestures:** Horizontal swipe untuk navigasi
- **Pull-to-Refresh:** Refresh content dengan gesture
- **Native Animations:** Smooth transitions dan micro-interactions
- **PWA Ready:** Manifest dan service worker untuk installable app

#### Base UI Components
- Button (variants: primary, secondary, outline, ghost)
- Input (text, email, password, textarea, file upload)
- Card (profile card, link card, stats card)
- Modal (confirmation, form modal)
- Toast (success, error, warning, info notifications)
- Loading (spinner, skeleton, progress bar)
- Dropdown (select, search dropdown)
- Navigation (header, sidebar, bottom tabs, breadcrumb)

---

### 🔐 AUTHENTICATION SYSTEM

#### Registration Flow
**Route:** `/register`
**Form Fields:**
- Email (required, validation)
- Password (required, min 8 chars, strength indicator)
- Confirm Password (required, match validation)
- Terms Agreement (checkbox dengan text "Dengan mendaftar maka setuju dengan syarat dan ketentuan")

**Process:**
1. User submit form → validation
2. Create account di Supabase Auth
3. Kirim email verification (Supabase handle)
4. Redirect ke success page dengan countdown auto-redirect ke login (5 detik)
5. Success message: "Akun berhasil dibuat, mohon verifikasi email [email]"

#### Login Flow
**Route:** `/login`
**Form Fields:**
- Email (required)
- Password (required)
- "Lupa Password?" link

**Process:**
1. User submit form → Supabase auth
2. Check email verification status
3. If not verified: Show notification "Email belum dikonfirmasi" + resend button
4. If verified: Check profile completion status
5. If incomplete: Redirect to `/complete`
6. If complete: Redirect to `/dashboard`

#### Forgot Password Flow
**Route:** `/forgot-password`
**Form Fields:**
- Email (required)

**Process:**
1. User submit email
2. Supabase `resetPasswordForEmail()` (Supabase handle email sending)
3. Show success message: "Link reset password telah dikirim ke email Anda"
4. User click link in email → redirect to `/update-password`

**Route:** `/update-password`
**Form Fields:**
- New Password (required, min 8 chars)
- Confirm New Password (required, match validation)

#### Email Verification Resend
**Feature:** Tombol "Kirim Ulang Email Verifikasi"
**Process:** Supabase `resend()` function (Supabase handle)

#### Complete Profile Flow
**Route:** `/complete`
**Conditional Form Fields:**

**Base Fields (All Users):**
- Role Selection: Content Creator / Brand (radio buttons)
- Username (required, unique check, 3-20 chars, alphanumeric + underscore)
- Full Name (required)

**If Role = Content Creator:**
- Niche Selection (dropdown dengan search, minimum 1, maksimum 3)

**If Role = Brand:**
- Business Category (dropdown dengan search, maksimum 1)

**Process:**
1. User select role → form fields update dynamically
2. Username uniqueness check real-time
3. Submit → create profile record
4. Generate random avatar using DiceBear API
5. Redirect to `/dashboard`

---

### 🏠 DASHBOARD CORE FEATURES

#### Dashboard Layout
**Route:** `/dashboard`
**Components:**
- **Header:** Logo + app name, navigation menu (desktop), profile dropdown
- **Mobile Navigation:** Bottom tab navigation (Profile, Links, Analytics, Settings)
- **Desktop Navigation:** Sidebar dengan menu items
- **Footer:** Copyright info, app version

**Menu Items:**
- Profile Management
- Social Links
- Custom Links
- Analytics
- Settings

#### Profile Management
**Route:** `/dashboard/profile`

**Content Creator Form:**
- Profile Photo (upload, crop, max 5MB)
- Full Name (required)
- Tagline (optional, max 100 chars, "dalam 1 kalimat")
- Bio (optional, max 500 chars)
- Niche Selection (dapat diubah, 1-3 niche)
- Location (dropdown dengan search)
- Birth Date (date picker)
- Hide Age Toggle (untuk public page)

**Brand Form:**
- Profile Photo (upload, crop, max 5MB)
- Full Name (required)
- Bio (optional, max 500 chars)
- Business Category (dapat diubah, 1 kategori)
- Location (dropdown dengan search)

#### Social Links Management
**Route:** `/dashboard/social-links`

**Add Social Link Form:**
- Platform Selection (dropdown dengan logo: Instagram, TikTok, Facebook, Twitter, YouTube, Discord)
- Username Input (required)
- Auto-generate full URL di backend

**Social Links List:**
- Platform logo + full URL
- Edit button (modal form)
- Delete button (confirmation modal)
- Drag & drop reorder

**Backend URL Generation:**
\`\`\`
Instagram: https://instagram.com/[username]
TikTok: https://tiktok.com/@[username]
Facebook: https://facebook.com/[username]
Twitter: https://twitter.com/[username]
YouTube: https://youtube.com/@[username]
Discord: https://discord.gg/[username]
\`\`\`

#### Custom Links Management
**Route:** `/dashboard/custom-links`

**Add Custom Link Form:**
- Logo Upload (optional, max 2MB, square recommended)
- Full URL (required, validation)
- Title (required, max 100 chars)
- Description (optional, max 200 chars)

**Custom Links List:**
- Logo + title + URL preview
- Edit button (modal form)
- Delete button (confirmation modal)
- Drag & drop reorder
- Click count display

#### Basic Analytics
**Route:** `/dashboard/analytics`

**Analytics Dashboard:**
- Profile overview stats
- Total profile views (today, this week, this month)
- Total link clicks (today, this week, this month)
- Most clicked links (top 5)
- Recent activity feed
- Share profile button (copy URL)

**Profile Info Card:**
- Name, username, role
- Account created date
- Profile URL: `domain.com/[username]`
- Share button (copy link, QR code)

#### Settings
**Route:** `/dashboard/settings`

**Change Password:**
- New Password (required, min 8 chars)
- Confirm New Password (required, match validation)
- Submit button: "Ubah Password"
- Note: "Tidak perlu memasukkan password lama"

**Delete Account:**
- Delete button → confirmation modal
- Modal requires typing "KONFIRMASI" exactly
- Warning text about permanent deletion
- Final confirmation button

---

### 🌐 PUBLIC PROFILE PAGES

#### Dynamic Profile Route
**Route:** `/[username]`

**Layout Structure:**
- **Header:** App logo (kiri atas), "Buat Profile Gratis" button (kanan atas)
- **Profile Section:** Photo, name, username, role badge, bio/tagline, location, age (if not hidden), niche tags/category
- **Social Links Section:** Grid layout dengan platform logos, hover effects
- **Custom Links Section:** Card layout dengan logo, title, description
- **Footer:** "Powered by [App Name]" + link ke landing page

**Content Creator Public Page:**
- Profile photo (large, circle)
- Full name + @username
- "Content Creator" badge
- Tagline (prominent display)
- Bio (if filled)
- Location + age (if not hidden)
- Niche tags (colorful badges)
- Social links grid
- Custom links cards

**Brand Public Page:**
- Profile photo (large, circle)
- Full name + @username
- "Brand" badge
- Bio (prominent display)
- Location
- Business category badge
- Social links grid
- Custom links cards

#### SEO Optimization
- **Meta Title:** "[Full Name] - [Role] | [App Name]"
- **Meta Description:** Bio/tagline content (max 160 chars)
- **Open Graph Tags:** Profile photo, name, bio
- **Structured Data:** Person/Organization markup
- **Canonical URL:** Proper canonical tags

#### Analytics Tracking
- Page view tracking (IP, device, browser, referrer)
- Link click tracking (social + custom links)
- Real-time data untuk dashboard user
- Privacy-compliant (hash IP addresses)

#### Error Handling
- **404 Cases:** Username tidak ditemukan, user suspended/deleted
- **Custom 404 Page:** Dengan CTA untuk register
- **Rate Limiting:** Gentle limits untuk normal users, stricter untuk suspicious activity

---

### 📊 BASIC ANALYTICS SYSTEM

#### Data Collection
- **Profile Views:** IP, timestamp, device type, browser, referrer
- **Link Clicks:** Link ID, type (social/custom), IP, timestamp, device, browser
- **User Sessions:** Login/logout tracking
- **Performance Metrics:** Page load times, error rates

#### Analytics Dashboard
- **Real-time Counters:** Current online visitors
- **Time-based Stats:** Today, yesterday, this week, last week, this month, last month
- **Link Performance:** Click-through rates, most popular links
- **Visitor Insights:** Device breakdown (mobile/desktop), top referrers
- **Geographic Data:** Country/city breakdown (using free IP geolocation)

---

## 🚀 STEP 2: ADVANCED REQUIREMENTS (SETELAH STEP 1)

### 📊 Advanced Analytics
- UTM parameter tracking untuk campaign monitoring
- Geographic analytics dengan peta interaktif
- Device analytics detail (mobile vs desktop breakdown)
- Export analytics data (CSV, PDF)
- Analytics API untuk third-party integrations

### 🎨 UI/UX Enhancements
- Theme customization (user dapat ganti warna tema)
- Profile templates untuk berbagai niche
- Link preview cards dengan thumbnail dan meta description
- Advanced drag & drop dengan visual feedback
- Profile preview mode sebelum publish

### 📱 PWA Enhancements
- Service worker untuk offline functionality
- Push notifications untuk new followers dan link clicks
- App install prompts
- Background sync untuk analytics
- Offline indicators dan cached content

### 🔒 Security & Monitoring
- Login history tracking dengan device info
- Suspicious activity alerts
- Two-factor authentication untuk admin
- IP whitelist/blacklist functionality
- Security audit logs

### 👑 Admin Panel
- User management (view, suspend, delete users)
- Content moderation tools
- System analytics dan performance monitoring
- Master data management (niches, categories, locations, platforms)
- Bulk operations dan data export

### 🎯 Additional Features
- QR code generator untuk profile
- Social media integration untuk auto-import links
- Custom domain support (premium feature)
- White-label options
- API access untuk developers

---

## 🔧 TECHNICAL REQUIREMENTS

### Frontend Technology
- **Framework:** Next.js 14 dengan App Router
- **Styling:** Tailwind CSS dengan custom design system
- **State Management:** React Context + useState untuk client state
- **Server State:** Supabase real-time subscriptions
- **Forms:** React Hook Form dengan validation
- **Icons:** Lucide React atau Heroicons
- **Animations:** Framer Motion untuk smooth transitions

### Backend Technology
- **Database:** Supabase PostgreSQL dengan Row Level Security
- **Authentication:** Supabase Auth dengan email verification
- **Storage:** Supabase Storage untuk file uploads
- **API:** Next.js API routes dengan proper error handling
- **Validation:** Zod atau Yup untuk schema validation
- **Rate Limiting:** Custom middleware dengan Redis (optional)

### Mobile-First Requirements
- **Responsive Breakpoints:** 320px (mobile), 768px (tablet), 1024px+ (desktop)
- **Touch Targets:** Minimum 44px untuk semua interactive elements
- **Performance:** First Contentful Paint < 2s, Largest Contentful Paint < 4s
- **Accessibility:** WCAG 2.1 AA compliance
- **PWA Score:** Lighthouse PWA score > 90

### Security Requirements
- **Input Validation:** Client-side dan server-side validation
- **Sanitization:** HTML sanitization untuk user content
- **Rate Limiting:** API endpoints dan public pages
- **HTTPS:** SSL certificate untuk production
- **CORS:** Proper CORS configuration
- **CSP:** Content Security Policy headers

### Performance Requirements
- **Bundle Size:** JavaScript bundle < 500KB gzipped
- **Image Optimization:** WebP format dengan fallback
- **Caching:** Proper cache headers dan CDN integration
- **Database:** Optimized queries dengan proper indexing
- **Monitoring:** Error tracking dan performance monitoring

---

## 📱 MOBILE WEB APPLICATION SPECIFICATIONS

### Navigation Patterns
- **Mobile:** Bottom tab navigation dengan 4-5 main tabs
- **Tablet:** Sidebar navigation yang dapat di-collapse
- **Desktop:** Fixed sidebar dengan full menu

### Touch Interactions
- **Tap:** Standard button dan link interactions
- **Long Press:** Context menus untuk edit/delete actions
- **Swipe:** Horizontal swipe untuk navigation, vertical untuk refresh
- **Pinch:** Zoom untuk images (profile photos)
- **Pull-to-Refresh:** Refresh content pada list pages

### Mobile-Specific Features
- **Haptic Feedback:** Vibration untuk important actions (optional)
- **Native Sharing:** Web Share API untuk share profile
- **Camera Integration:** Direct camera access untuk profile photo
- **Geolocation:** Auto-detect location (dengan permission)
- **Offline Support:** Basic functionality saat offline

### Performance Optimizations
- **Lazy Loading:** Images dan components
- **Code Splitting:** Route-based code splitting
- **Prefetching:** Critical resources prefetching
- **Compression:** Gzip/Brotli compression
- **Caching:** Aggressive caching strategy

---

## 🎯 SUCCESS METRICS

### User Engagement
- **Registration Rate:** Target 70% completion rate dari landing ke registered
- **Profile Completion:** Target 90% completion rate dari registered ke active profile
- **Daily Active Users:** Target 60% DAU/MAU ratio
- **Link Clicks:** Average 10+ clicks per profile per month

### Technical Performance
- **Page Load Speed:** < 3 seconds pada 3G connection
- **Uptime:** 99.9% availability
- **Error Rate:** < 1% error rate pada production
- **Mobile Usage:** Target 80%+ mobile traffic

### Business Metrics
- **User Growth:** Target 100 new users per month (initial)
- **User Retention:** 70% retention setelah 7 hari, 40% setelah 30 hari
- **Geographic Distribution:** 60% dari Surabaya/Gresik/Sidoarjo area
- **Role Distribution:** Target 70% Content Creator, 30% Brand

---

**Note:** Semua requirements di Step 1 harus fully functional dan tested sebelum melanjutkan ke Step 2. Focus pada quality over quantity untuk membangun foundation yang solid.