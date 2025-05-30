# =====================================
# APPLICATION CONFIGURATION
# =====================================

# App Basic Info
NEXT_PUBLIC_APP_NAME="Tumbuh Ide Indonesia"
NEXT_PUBLIC_APP_URL="https://yourdomain.com"
NEXT_PUBLIC_APP_DESCRIPTION="Create your professional link-in-bio page"
NEXT_PUBLIC_APP_KEYWORDS="link in bio, social media, profile, content creator, brand"

# App Assets
NEXT_PUBLIC_LOGO_URL="/logo.png"
NEXT_PUBLIC_FAVICON_URL="/favicon.ico"
NEXT_PUBLIC_OG_IMAGE_URL="/og-image.png"

# Contact Info
NEXT_PUBLIC_CONTACT_EMAIL="hello@yourdomain.com"
NEXT_PUBLIC_SUPPORT_EMAIL="support@yourdomain.com"
NEXT_PUBLIC_SUPPORT_PHONE="+62-XXX-XXXX-XXXX"

# =====================================
# SUPABASE CONFIGURATION
# =====================================

# Supabase Project Settings
NEXT_PUBLIC_SUPABASE_URL="https://your-project-id.supabase.co"
NEXT_PUBLIC_SUPABASE_ANON_KEY="your-supabase-anon-key"
SUPABASE_SERVICE_ROLE_KEY="your-supabase-service-role-key"

# Supabase Storage
NEXT_PUBLIC_SUPABASE_STORAGE_BUCKET="profile-images"
SUPABASE_STORAGE_URL="https://your-project-id.supabase.co/storage/v1"

# =====================================
# THEME & DESIGN CONFIGURATION
# =====================================

# Primary Theme Colors
NEXT_PUBLIC_PRIMARY_COLOR="#8B5CF6"        # Purple
NEXT_PUBLIC_PRIMARY_HOVER="#7C3AED"        # Purple Dark
NEXT_PUBLIC_SECONDARY_COLOR="#EAB308"      # Yellow
NEXT_PUBLIC_SECONDARY_HOVER="#D97706"      # Yellow Dark

# Background Colors
NEXT_PUBLIC_BACKGROUND_LIGHT="#FFFFFF"     # White
NEXT_PUBLIC_BACKGROUND_DARK="#0F172A"      # Dark Slate

# Text Colors
NEXT_PUBLIC_TEXT_PRIMARY="#1E293B"         # Slate 800
NEXT_PUBLIC_TEXT_SECONDARY="#64748B"       # Slate 500
NEXT_PUBLIC_TEXT_MUTED="#94A3B8"           # Slate 400

# =====================================
# FILE UPLOAD CONFIGURATION
# =====================================

# File Size Limits (in bytes)
NEXT_PUBLIC_MAX_PROFILE_IMAGE_SIZE="5242880"    # 5MB
NEXT_PUBLIC_MAX_CUSTOM_LOGO_SIZE="2097152"      # 2MB
NEXT_PUBLIC_MAX_GENERAL_FILE_SIZE="10485760"    # 10MB

# Allowed File Types
NEXT_PUBLIC_ALLOWED_IMAGE_TYPES="image/jpeg,image/png,image/webp,image/svg+xml"
NEXT_PUBLIC_ALLOWED_LOGO_TYPES="image/jpeg,image/png,image/webp,image/svg+xml"

# Image Processing
NEXT_PUBLIC_IMAGE_QUALITY="80"
NEXT_PUBLIC_THUMBNAIL_SIZE="150"
NEXT_PUBLIC_MAX_IMAGE_WIDTH="1200"
NEXT_PUBLIC_MAX_IMAGE_HEIGHT="1200"

# =====================================
# RATE LIMITING CONFIGURATION
# =====================================

# API Rate Limits (requests per window)
RATE_LIMIT_API_REQUESTS="100"
RATE_LIMIT_API_WINDOW="900000"              # 15 minutes in milliseconds

# Auth Rate Limits
RATE_LIMIT_LOGIN_REQUESTS="5"
RATE_LIMIT_LOGIN_WINDOW="900000"            # 15 minutes
RATE_LIMIT_REGISTER_REQUESTS="3"
RATE_LIMIT_REGISTER_WINDOW="3600000"        # 1 hour

# Public Page Rate Limits
RATE_LIMIT_PUBLIC_REQUESTS="50"
RATE_LIMIT_PUBLIC_WINDOW="900000"           # 15 minutes

# Upload Rate Limits
RATE_LIMIT_UPLOAD_REQUESTS="10"
RATE_LIMIT_UPLOAD_WINDOW="3600000"          # 1 hour

# =====================================
# SEO CONFIGURATION
# =====================================

# Default Meta Tags
NEXT_PUBLIC_DEFAULT_TITLE="Tumbuh Ide Indonesia - Professional Link in Bio"
NEXT_PUBLIC_DEFAULT_DESCRIPTION="Create your professional link-in-bio page for free. Perfect for content creators and brands."
NEXT_PUBLIC_DEFAULT_KEYWORDS="link in bio, biolink, social media, profile, content creator"

# Social Media Meta
NEXT_PUBLIC_TWITTER_SITE="@yourtwitterhandle"
NEXT_PUBLIC_TWITTER_CREATOR="@yourtwitterhandle"
NEXT_PUBLIC_FB_APP_ID="your-facebook-app-id"

# Structured Data
NEXT_PUBLIC_ORGANIZATION_NAME="Tumbuh Ide Indonesia"
NEXT_PUBLIC_ORGANIZATION_URL="https://yourdomain.com"
NEXT_PUBLIC_ORGANIZATION_LOGO="https://yourdomain.com/logo.png"

# =====================================
# EMAIL CONFIGURATION
# =====================================

# SMTP Settings for Notifications
SMTP_HOST="smtp.gmail.com"
SMTP_PORT="587"
SMTP_SECURE="false"
SMTP_USER="your-email@gmail.com"
SMTP_PASS="your-app-specific-password"

# Email Templates
EMAIL_FROM_NAME="Tumbuh Ide Indonesia"
EMAIL_FROM_ADDRESS="noreply@yourdomain.com"
EMAIL_REPLY_TO="support@yourdomain.com"

# Email Features
ENABLE_EMAIL_NOTIFICATIONS="true"
ENABLE_WELCOME_EMAIL="true"
ENABLE_PASSWORD_RESET_EMAIL="true"

# =====================================
# SECURITY CONFIGURATION
# =====================================

# JWT & Encryption
JWT_SECRET="your-super-secure-jwt-secret-key-minimum-32-characters"
ENCRYPTION_KEY="your-32-character-encryption-key"
HASH_SALT_ROUNDS="12"

# Session Management
SESSION_TIMEOUT="86400000"                  # 24 hours in milliseconds
REMEMBER_ME_DURATION="2592000000"           # 30 days in milliseconds

# Content Security Policy
CSP_REPORT_URI="https://yourdomain.com/api/csp-report"
ENABLE_CSP="true"

# =====================================
# EXTERNAL SERVICES
# =====================================

# Avatar Generation Service
DICEBEAR_API_URL="https://api.dicebear.com/7.x"
DICEBEAR_STYLE="avataaars"                  # avataaars, identicon, initials
ENABLE_RANDOM_AVATARS="true"

# Analytics Services
GOOGLE_ANALYTICS_ID="G-XXXXXXXXXX"
ENABLE_ANALYTICS="true"

# Social Media Platform URLs (for link building)
PLATFORM_INSTAGRAM_URL="https://instagram.com/"
PLATFORM_TIKTOK_URL="https://tiktok.com/@"
PLATFORM_FACEBOOK_URL="https://facebook.com/"
PLATFORM_TWITTER_URL="https://twitter.com/"
PLATFORM_YOUTUBE_URL="https://youtube.com/@"
PLATFORM_DISCORD_URL="https://discord.gg/"
PLATFORM_LINKEDIN_URL="https://linkedin.com/in/"
PLATFORM_GITHUB_URL="https://github.com/"
PLATFORM_TWITCH_URL="https://twitch.tv/"
PLATFORM_SNAPCHAT_URL="https://snapchat.com/add/"

# =====================================
# DEVELOPMENT CONFIGURATION
# =====================================

# Environment
NODE_ENV="development"                      # development, production, test
NEXT_PUBLIC_DEBUG="true"
NEXT_PUBLIC_API_BASE_URL="http://localhost:3000"

# Development Tools
ENABLE_REACT_DEVTOOLS="true"
ENABLE_REDUX_DEVTOOLS="true"
SHOW_DEVELOPMENT_WARNINGS="true"

# Database
DATABASE_URL="postgresql://user:password@localhost:5432/dbname"  # if using local DB
ENABLE_DATABASE_LOGGING="true"

# Testing
TEST_DATABASE_URL="postgresql://user:password@localhost:5432/test_dbname"
ENABLE_TEST_MODE="false"

# =====================================
# PERFORMANCE CONFIGURATION
# =====================================

# Caching
ENABLE_REDIS_CACHE="false"                  # Set to true if using Redis
REDIS_URL="redis://localhost:6379"
CACHE_DURATION="3600"                       # 1 hour in seconds

# CDN Configuration
NEXT_PUBLIC_CDN_URL=""                      # Your CDN URL if using one
ENABLE_IMAGE_OPTIMIZATION="true"

# Database Performance
CONNECTION_POOL_SIZE="20"
CONNECTION_TIMEOUT="30000"                  # 30 seconds

# =====================================
# MONITORING & LOGGING
# =====================================

# Error Tracking
SENTRY_DSN=""                              # Your Sentry DSN if using Sentry
ENABLE_ERROR_TRACKING="false"

# Logging
LOG_LEVEL="info"                           # error, warn, info, debug
ENABLE_ACCESS_LOGS="true"
ENABLE_ERROR_LOGS="true"

# Health Checks
ENABLE_HEALTH_CHECK="true"
HEALTH_CHECK_PATH="/api/health"

# =====================================
# BACKUP & MAINTENANCE
# =====================================

# Backup Configuration
ENABLE_AUTO_BACKUP="false"
BACKUP_SCHEDULE="0 2 * * *"                # Daily at 2 AM (cron format)
BACKUP_RETENTION_DAYS="30"

# Maintenance Mode
ENABLE_MAINTENANCE_MODE="false"
MAINTENANCE_MESSAGE="We're currently performing scheduled maintenance. Please check back soon."

# =====================================
# FEATURE FLAGS
# =====================================

# Core Features
ENABLE_USER_REGISTRATION="true"
ENABLE_EMAIL_VERIFICATION="true"
ENABLE_PROFILE_COMPLETION="true"
ENABLE_FILE_UPLOADS="true"

# Social Features
ENABLE_SOCIAL_LINKS="true"
ENABLE_CUSTOM_LINKS="true"
ENABLE_LINK_ANALYTICS="true"

# Advanced Features
ENABLE_ANALYTICS_DASHBOARD="true"
ENABLE_ADMIN_PANEL="true"
ENABLE_USER_MANAGEMENT="true"
ENABLE_CONTENT_MODERATION="true"

# UI Features
ENABLE_DARK_MODE="true"
ENABLE_THEME_CUSTOMIZATION="false"
ENABLE_CUSTOM_DOMAINS="false"

# =====================================
# LOCALIZATION
# =====================================

# Language Settings
DEFAULT_LOCALE="id"                        # Indonesian
SUPPORTED_LOCALES="id,en"                  # Indonesian, English
ENABLE_RTL="false"

# Timezone
DEFAULT_TIMEZONE="Asia/Jakarta"
ENABLE_TIMEZONE_DETECTION="true"

# =====================================
# WEBHOOK CONFIGURATION
# =====================================

# Webhook URLs (if needed)
WEBHOOK_USER_CREATED=""
WEBHOOK_PROFILE_UPDATED=""
WEBHOOK_LINK_CLICKED=""

# Webhook Security
WEBHOOK_SECRET_KEY="your-webhook-secret-key"
ENABLE_WEBHOOK_VERIFICATION="true"

# =====================================
# THIRD PARTY INTEGRATIONS
# =====================================

# Payment Processing (if implementing premium features)
STRIPE_PUBLISHABLE_KEY=""
STRIPE_SECRET_KEY=""
STRIPE_WEBHOOK_SECRET=""

# Social Login (if implementing)
GOOGLE_CLIENT_ID=""
GOOGLE_CLIENT_SECRET=""
FACEBOOK_APP_ID=""
FACEBOOK_APP_SECRET=""

# =====================================
# MOBILE APP CONFIGURATION
# =====================================

# Deep Links
NEXT_PUBLIC_APP_SCHEME="tumbuhide"
NEXT_PUBLIC_ANDROID_PACKAGE=""
NEXT_PUBLIC_IOS_BUNDLE_ID=""

# App Store Links
NEXT_PUBLIC_ANDROID_APP_URL=""
NEXT_PUBLIC_IOS_APP_URL=""

# =====================================
# ADDITIONAL NOTES
# =====================================

# IMPORTANT: 
# 1. Never commit this file with real values to version control
# 2. Copy this file to .env.local and fill in your actual values
# 3. Ensure all production values are properly secured
# 4. Regularly rotate sensitive keys and secrets
# 5. Use different values for development, staging, and production environments

# REQUIRED MINIMUM SETUP:
# - NEXT_PUBLIC_SUPABASE_URL
# - NEXT_PUBLIC_SUPABASE_ANON_KEY
# - SUPABASE_SERVICE_ROLE_KEY
# - JWT_SECRET
# - ENCRYPTION_KEY

# OPTIONAL BUT RECOMMENDED:
# - Email SMTP settings for notifications
# - Analytics tracking IDs
# - Error tracking service
# - File upload configurations