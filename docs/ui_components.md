# 🎨 UI COMPONENTS & DESIGN SYSTEM
## Link-in-Bio Platform (Tumbuh Ide Indonesia)

**Design Approach:** Mobile-First Web Application  
**Theme:** Purple + Yellow + White dengan Dark Mode Support  
**Framework:** Tailwind CSS dengan Custom Design System

---

## 🎯 DESIGN PRINCIPLES

### Mobile-First Philosophy
- **Touch-Friendly:** Minimum 44px untuk semua interactive elements
- **Readable:** Minimum 16px font size untuk body text
- **Accessible:** High contrast ratios, clear visual hierarchy
- **Fast:** Optimized untuk mobile networks dan devices
- **Native Feel:** Animations dan interactions yang terasa natural

### Visual Hierarchy
- **Clear Information Architecture:** Prioritas konten yang jelas
- **Consistent Spacing:** 8px grid system untuk consistency
- **Meaningful Colors:** Warna yang memiliki semantic meaning
- **Progressive Disclosure:** Informasi complex dipecah menjadi steps

---

## 🎨 COLOR SYSTEM

### Primary Colors
\`\`\`css
/* Light Mode */
--primary-50: #faf5ff;
--primary-100: #f3e8ff;
--primary-500: #8b5cf6;    /* Main Purple */
--primary-600: #7c3aed;    /* Hover Purple */
--primary-700: #6d28d9;    /* Active Purple */
--primary-900: #4c1d95;    /* Dark Purple */

/* Secondary Colors */
--secondary-50: #fefce8;
--secondary-100: #fef9c3;
--secondary-500: #eab308;   /* Main Yellow */
--secondary-600: #d97706;   /* Hover Yellow */
--secondary-700: #b45309;   /* Active Yellow */

/* Neutral Colors */
--white: #ffffff;
--gray-50: #f9fafb;
--gray-100: #f3f4f6;
--gray-200: #e5e7eb;
--gray-300: #d1d5db;
--gray-400: #9ca3af;
--gray-500: #6b7280;
--gray-600: #4b5563;
--gray-700: #374151;
--gray-800: #1f2937;
--gray-900: #111827;

/* Semantic Colors */
--success: #10b981;
--warning: #f59e0b;
--error: #ef4444;
--info: #3b82f6;
\`\`\`

### Dark Mode Colors
\`\`\`css
/* Dark Mode Overrides */
--bg-primary: #0f172a;      /* Slate 900 */
--bg-secondary: #1e293b;    /* Slate 800 */
--bg-tertiary: #334155;     /* Slate 700 */
--text-primary: #f8fafc;    /* Slate 50 */
--text-secondary: #cbd5e1;  /* Slate 300 */
--text-muted: #94a3b8;      /* Slate 400 */
--border: #475569;          /* Slate 600 */
\`\`\`

---

## 📝 TYPOGRAPHY SYSTEM

### Font Families
\`\`\`css
/* Primary Font */
--font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;

/* Display Font (untuk headings) */
--font-display: 'Poppins', 'Inter', sans-serif;

/* Monospace (untuk code/usernames) */
--font-mono: 'JetBrains Mono', 'Fira Code', monospace;
\`\`\`

### Typography Scale
\`\`\`css
/* Font Sizes */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.875rem;    /* 14px */
--text-base: 1rem;      /* 16px */
--text-lg: 1.125rem;    /* 18px */
--text-xl: 1.25rem;     /* 20px */
--text-2xl: 1.5rem;     /* 24px */
--text-3xl: 1.875rem;   /* 30px */
--text-4xl: 2.25rem;    /* 36px */

/* Line Heights */
--leading-tight: 1.25;
--leading-normal: 1.5;
--leading-relaxed: 1.625;

/* Font Weights */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;
\`\`\`

---

## 📏 SPACING SYSTEM

### 8px Grid System
\`\`\`css
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-5: 1.25rem;   /* 20px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-10: 2.5rem;   /* 40px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
--space-20: 5rem;     /* 80px */
\`\`\`

### Container Sizes
\`\`\`css
--container-sm: 640px;
--container-md: 768px;
--container-lg: 1024px;
--container-xl: 1280px;
\`\`\`

---

## 🧱 BASE UI COMPONENTS

### 1. Button Component
\`\`\`jsx
// Button.jsx
const Button = ({ 
  children, 
  variant = 'primary', 
  size = 'md', 
  loading = false,
  disabled = false,
  fullWidth = false,
  icon,
  ...props 
}) => {
  const baseClasses = `
    inline-flex items-center justify-center font-medium rounded-lg 
    transition-all duration-200 focus:outline-none focus:ring-2 
    focus:ring-offset-2 disabled:opacity-50 disabled:cursor-not-allowed
    active:scale-95
  `;

  const variants = {
    primary: `
      bg-purple-600 hover:bg-purple-700 text-white 
      focus:ring-purple-500 shadow-sm hover:shadow-md
    `,
    secondary: `
      bg-yellow-500 hover:bg-yellow-600 text-white 
      focus:ring-yellow-500 shadow-sm hover:shadow-md
    `,
    outline: `
      border-2 border-purple-600 text-purple-600 hover:bg-purple-50 
      focus:ring-purple-500 dark:border-purple-400 dark:text-purple-400 
      dark:hover:bg-purple-900/20
    `,
    ghost: `
      text-gray-700 hover:bg-gray-100 focus:ring-gray-500 
      dark:text-gray-300 dark:hover:bg-gray-800
    `,
    danger: `
      bg-red-600 hover:bg-red-700 text-white 
      focus:ring-red-500 shadow-sm hover:shadow-md
    `
  };

  const sizes = {
    sm: 'px-3 py-2 text-sm min-h-[36px]',
    md: 'px-4 py-3 text-base min-h-[44px]',
    lg: 'px-6 py-4 text-lg min-h-[52px]'
  };

  const classes = `
    ${baseClasses} 
    ${variants[variant]} 
    ${sizes[size]} 
    ${fullWidth ? 'w-full' : ''}
  `;

  return (
    <button 
      className={classes} 
      disabled={disabled || loading}
      {...props}
    >
      {loading && (
        <svg className="animate-spin -ml-1 mr-2 h-4 w-4" fill="none" viewBox="0 0 24 24">
          <circle className="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" strokeWidth="4" />
          <path className="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z" />
        </svg>
      )}
      {icon && !loading && <span className="mr-2">{icon}</span>}
      {children}
    </button>
  );
};
\`\`\`

### 2. Input Component
\`\`\`jsx
// Input.jsx
const Input = ({ 
  label, 
  error, 
  helper, 
  icon, 
  required = false,
  className = '',
  ...props 
}) => {
  const inputClasses = `
    w-full px-4 py-3 text-base rounded-lg border transition-colors
    focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent
    disabled:bg-gray-100 disabled:cursor-not-allowed
    dark:bg-gray-800 dark:border-gray-600 dark:text-white
    ${error 
      ? 'border-red-500 focus:ring-red-500' 
      : 'border-gray-300 dark:border-gray-600'
    }
    ${icon ? 'pl-12' : 'pl-4'}
    ${className}
  `;

  return (
    <div className="space-y-1">
      {label && (
        <label className="block text-sm font-medium text-gray-700 dark:text-gray-300">
          {label}
          {required && <span className="text-red-500 ml-1">*</span>}
        </label>
      )}
      
      <div className="relative">
        {icon && (
          <div className="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
            <span className="text-gray-400">{icon}</span>
          </div>
        )}
        
        <input className={inputClasses} {...props} />
      </div>
      
      {error && (
        <p className="text-sm text-red-600 dark:text-red-400">{error}</p>
      )}
      
      {helper && !error && (
        <p className="text-sm text-gray-500 dark:text-gray-400">{helper}</p>
      )}
    </div>
  );
};
\`\`\`

### 3. Card Component
\`\`\`jsx
// Card.jsx
const Card = ({ 
  children, 
  variant = 'default',
  padding = 'md',
  hover = false,
  className = '',
  ...props 
}) => {
  const baseClasses = `
    bg-white dark:bg-gray-800 rounded-lg border border-gray-200 
    dark:border-gray-700 transition-all duration-200
  `;

  const variants = {
    default: '',
    elevated: 'shadow-md hover:shadow-lg',
    outlined: 'border-2',
    gradient: 'bg-gradient-to-br from-purple-50 to-yellow-50 dark:from-purple-900/20 dark:to-yellow-900/20'
  };

  const paddings = {
    none: '',
    sm: 'p-4',
    md: 'p-6',
    lg: 'p-8'
  };

  const hoverClasses = hover ? 'hover:shadow-md hover:scale-105 cursor-pointer' : '';

  const classes = `
    ${baseClasses} 
    ${variants[variant]} 
    ${paddings[padding]} 
    ${hoverClasses} 
    ${className}
  `;

  return (
    <div className={classes} {...props}>
      {children}
    </div>
  );
};
\`\`\`

### 4. Modal Component
\`\`\`jsx
// Modal.jsx
const Modal = ({ 
  isOpen, 
  onClose, 
  title, 
  children, 
  size = 'md',
  showCloseButton = true 
}) => {
  const sizes = {
    sm: 'max-w-md',
    md: 'max-w-lg',
    lg: 'max-w-2xl',
    xl: 'max-w-4xl',
    full: 'max-w-full mx-4'
  };

  if (!isOpen) return null;

  return (
    <div className="fixed inset-0 z-50 overflow-y-auto">
      {/* Backdrop */}
      <div 
        className="fixed inset-0 bg-black bg-opacity-50 transition-opacity"
        onClick={onClose}
      />
      
      {/* Modal */}
      <div className="flex min-h-full items-center justify-center p-4">
        <div className={`
          relative w-full ${sizes[size]} bg-white dark:bg-gray-800 
          rounded-lg shadow-xl transform transition-all
        `}>
          {/* Header */}
          {(title || showCloseButton) && (
            <div className="flex items-center justify-between p-6 pb-4">
              {title && (
                <h3 className="text-lg font-semibold text-gray-900 dark:text-white">
                  {title}
                </h3>
              )}
              {showCloseButton && (
                <button
                  onClick={onClose}
                  className="text-gray-400 hover:text-gray-600 dark:hover:text-gray-300"
                >
                  <svg className="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M6 18L18 6M6 6l12 12" />
                  </svg>
                </button>
              )}
            </div>
          )}
          
          {/* Content */}
          <div className="px-6 pb-6">
            {children}
          </div>
        </div>
      </div>
    </div>
  );
};
\`\`\`

### 5. Toast Component
\`\`\`jsx
// Toast.jsx
const Toast = ({ 
  message, 
  type = 'info', 
  isVisible, 
  onClose,
  duration = 5000 
}) => {
  const [isShowing, setIsShowing] = useState(false);

  useEffect(() => {
    if (isVisible) {
      setIsShowing(true);
      const timer = setTimeout(() => {
        setIsShowing(false);
        setTimeout(onClose, 300); // Wait for animation
      }, duration);
      return () => clearTimeout(timer);
    }
  }, [isVisible, duration, onClose]);

  const types = {
    success: {
      bg: 'bg-green-500',
      icon: '✓',
      text: 'text-white'
    },
    error: {
      bg: 'bg-red-500',
      icon: '✕',
      text: 'text-white'
    },
    warning: {
      bg: 'bg-yellow-500',
      icon: '⚠',
      text: 'text-white'
    },
    info: {
      bg: 'bg-blue-500',
      icon: 'ℹ',
      text: 'text-white'
    }
  };

  const config = types[type];

  if (!isVisible) return null;

  return (
    <div className={`
      fixed top-4 right-4 z-50 flex items-center space-x-3 px-4 py-3 rounded-lg 
      shadow-lg transform transition-all duration-300 min-w-[300px]
      ${config.bg} ${config.text}
      ${isShowing ? 'translate-x-0 opacity-100' : 'translate-x-full opacity-0'}
    `}>
      <span className="text-lg">{config.icon}</span>
      <p className="flex-1 text-sm font-medium">{message}</p>
      <button 
        onClick={() => {
          setIsShowing(false);
          setTimeout(onClose, 300);
        }}
        className="text-white hover:text-gray-200"
      >
        <svg className="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>
  );
};
\`\`\`

### 6. Loading Components
\`\`\`jsx
// Loading.jsx
export const LoadingSpinner = ({ size = 'md', color = 'purple' }) => {
  const sizes = {
    sm: 'w-4 h-4',
    md: 'w-8 h-8',
    lg: 'w-12 h-12',
    xl: 'w-16 h-16'
  };

  const colors = {
    purple: 'text-purple-600',
    yellow: 'text-yellow-500',
    gray: 'text-gray-500'
  };

  return (
    <svg 
      className={`animate-spin ${sizes[size]} ${colors[color]}`} 
      fill="none" 
      viewBox="0 0 24 24"
    >
      <circle 
        className="opacity-25" 
        cx="12" 
        cy="12" 
        r="10" 
        stroke="currentColor" 
        strokeWidth="4" 
      />
      <path 
        className="opacity-75" 
        fill="currentColor" 
        d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z" 
      />
    </svg>
  );
};

export const LoadingSkeleton = ({ className = '', lines = 1 }) => {
  return (
    <div className={`animate-pulse ${className}`}>
      {Array.from({ length: lines }).map((_, i) => (
        <div 
          key={i} 
          className="h-4 bg-gray-200 dark:bg-gray-700 rounded mb-2 last:mb-0"
          style={{ width: `${Math.random() * 40 + 60}%` }}
        />
      ))}
    </div>
  );
};

export const LoadingPage = () => {
  return (
    <div className="flex items-center justify-center min-h-[400px]">
      <div className="text-center space-y-4">
        <LoadingSpinner size="xl" />
        <p className="text-gray-500 dark:text-gray-400">Memuat...</p>
      </div>
    </div>
  );
};
\`\`\`

### 7. Dropdown Component
\`\`\`jsx
// Dropdown.jsx
const Dropdown = ({ 
  label, 
  options = [], 
  value, 
  onChange, 
  placeholder = 'Pilih opsi...',
  searchable = false,
  error,
  required = false 
}) => {
  const [isOpen, setIsOpen] = useState(false);
  const [searchTerm, setSearchTerm] = useState('');
  const dropdownRef = useRef(null);

  const filteredOptions = searchable 
    ? options.filter(option => 
        option.label.toLowerCase().includes(searchTerm.toLowerCase())
      )
    : options;

  const selectedOption = options.find(option => option.value === value);

  useEffect(() => {
    const handleClickOutside = (event) => {
      if (dropdownRef.current && !dropdownRef.current.contains(event.target)) {
        setIsOpen(false);
      }
    };
    document.addEventListener('mousedown', handleClickOutside);
    return () => document.removeEventListener('mousedown', handleClickOutside);
  }, []);

  return (
    <div className="space-y-1" ref={dropdownRef}>
      {label && (
        <label className="block text-sm font-medium text-gray-700 dark:text-gray-300">
          {label}
          {required && <span className="text-red-500 ml-1">*</span>}
        </label>
      )}
      
      <div className="relative">
        <button
          type="button"
          onClick={() => setIsOpen(!isOpen)}
          className={`
            w-full px-4 py-3 text-left bg-white dark:bg-gray-800 border rounded-lg
            focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent
            ${error ? 'border-red-500' : 'border-gray-300 dark:border-gray-600'}
            ${isOpen ? 'ring-2 ring-purple-500' : ''}
          `}
        >
          <span className={selectedOption ? 'text-gray-900 dark:text-white' : 'text-gray-500'}>
            {selectedOption ? selectedOption.label : placeholder}
          </span>
          <svg 
            className={`absolute right-3 top-1/2 transform -translate-y-1/2 w-5 h-5 transition-transform ${isOpen ? 'rotate-180' : ''}`}
            fill="none" 
            stroke="currentColor" 
            viewBox="0 0 24 24"
          >
            <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M19 9l-7 7-7-7" />
          </svg>
        </button>

        {isOpen && (
          <div className="absolute z-10 w-full mt-1 bg-white dark:bg-gray-800 border border-gray-300 dark:border-gray-600 rounded-lg shadow-lg max-h-60 overflow-auto">
            {searchable && (
              <div className="p-2 border-b border-gray-200 dark:border-gray-700">
                <input
                  type="text"
                  placeholder="Cari..."
                  value={searchTerm}
                  onChange={(e) => setSearchTerm(e.target.value)}
                  className="w-full px-3 py-2 border border-gray-300 dark:border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-purple-500 dark:bg-gray-700"
                />
              </div>
            )}
            
            <div className="py-1">
              {filteredOptions.length > 0 ? (
                filteredOptions.map((option) => (
                  <button
                    key={option.value}
                    type="button"
                    onClick={() => {
                      onChange(option.value);
                      setIsOpen(false);
                      setSearchTerm('');
                    }}
                    className={`
                      w-full px-4 py-2 text-left hover:bg-gray-100 dark:hover:bg-gray-700
                      ${option.value === value ? 'bg-purple-50 dark:bg-purple-900/20 text-purple-700 dark:text-purple-300' : 'text-gray-900 dark:text-white'}
                    `}
                  >
                    {option.label}
                  </button>
                ))
              ) : (
                <p className="px-4 py-2 text-gray-500 dark:text-gray-400">Tidak ada opsi ditemukan</p>
              )}
            </div>
          </div>
        )}
      </div>
      
      {error && (
        <p className="text-sm text-red-600 dark:text-red-400">{error}</p>
      )}
    </div>
  );
};
\`\`\`

---

## 📱 MOBILE-SPECIFIC COMPONENTS

### 1. Bottom Navigation
\`\`\`jsx
// BottomNavigation.jsx
const BottomNavigation = () => {
  const pathname = usePathname();
  
  const navItems = [
    {
      href: '/dashboard',
      icon: <HomeIcon className="w-6 h-6" />,
      label: 'Home',
      isActive: pathname === '/dashboard'
    },
    {
      href: '/dashboard/links',
      icon: <LinkIcon className="w-6 h-6" />,
      label: 'Links',
      isActive: pathname.includes('/dashboard/links')
    },
    {
      href: '/dashboard/analytics',
      icon: <BarChartIcon className="w-6 h-6" />,
      label: 'Analytics',
      isActive: pathname.includes('/dashboard/analytics')
    },
    {
      href: '/dashboard/settings',
      icon: <SettingsIcon className="w-6 h-6" />,
      label: 'Settings',
      isActive: pathname.includes('/dashboard/settings')
    }
  ];

  return (
    <nav className="fixed bottom-0 left-0 right-0 z-40 bg-white dark:bg-gray-900 border-t border-gray-200 dark:border-gray-800 md:hidden">
      <div className="flex justify-around items-center h-16 px-4">
        {navItems.map((item) => (
          <Link
            key={item.href}
            href={item.href}
            className={`
              flex flex-col items-center justify-center space-y-1 px-3 py-2 rounded-lg
              transition-colors duration-200 min-w-[64px]
              ${item.isActive 
                ? 'text-purple-600 dark:text-purple-400 bg-purple-50 dark:bg-purple-900/20' 
                : 'text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-300'
              }
            `}
          >
            {item.icon}
            <span className="text-xs font-medium">{item.label}</span>
          </Link>
        ))}
      </div>
    </nav>
  );
};
\`\`\`

### 2. Pull to Refresh
\`\`\`jsx
// PullToRefresh.jsx
const PullToRefresh = ({ onRefresh, children }) => {
  const [isPulling, setIsPulling] = useState(false);
  const [pullDistance, setPullDistance] = useState(0);
  const [isRefreshing, setIsRefreshing] = useState(false);
  
  const threshold = 60;
  let startY = 0;
  let currentY = 0;

  const handleTouchStart = (e) => {
    if (window.scrollY === 0) {
      startY = e.touches[0].clientY;
    }
  };

  const handleTouchMove = (e) => {
    if (window.scrollY === 0 && startY > 0) {
      currentY = e.touches[0].clientY;
      const distance = Math.max(0, (currentY - startY) * 0.5);
      
      if (distance > 0) {
        setIsPulling(true);
        setPullDistance(Math.min(distance, threshold * 1.5));
      }
    }
  };

  const handleTouchEnd = async () => {
    if (isPulling && pullDistance >= threshold && !isRefreshing) {
      setIsRefreshing(true);
      try {
        await onRefresh();
      } finally {
        setIsRefreshing(false);
      }
    }
    
    setIsPulling(false);
    setPullDistance(0);
    startY = 0;
  };

  return (
    <div 
      className="relative"
      onTouchStart={handleTouchStart}
      onTouchMove={handleTouchMove}
      onTouchEnd={handleTouchEnd}
    >
      {/* Pull indicator */}
      <div 
        className={`
          absolute top-0 left-0 right-0 flex items-center justify-center
          transition-all duration-200 bg-gray-50 dark:bg-gray-800
          ${isPulling || isRefreshing ? 'visible' : 'invisible'}
        `}
        style={{ 
          height: isPulling ? `${pullDistance}px` : isRefreshing ? '60px' : '0px',
          transform: `translateY(-${isPulling ? 0 : 60}px)`
        }}
      >
        <div className="flex items-center space-x-2 text-gray-600 dark:text-gray-400">
          {isRefreshing ? (
            <>
              <LoadingSpinner size="sm" />
              <span className="text-sm">Memuat ulang...</span>
            </>
          ) : (
            <>
              <svg 
                className={`w-5 h-5 transition-transform ${pullDistance >= threshold ? 'rotate-180' : ''}`}
                fill="none" 
                stroke="currentColor" 
                viewBox="0 0 24 24"
              >
                <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M19 14l-7-7-7 7" />
              </svg>
              <span className="text-sm">
                {pullDistance >= threshold ? 'Lepaskan untuk memuat ulang' : 'Tarik untuk memuat ulang'}
              </span>
            </>
          )}
        </div>
      </div>
      
      {/* Content */}
      <div style={{ paddingTop: isRefreshing ? '60px' : '0px' }}>
        {children}
      </div>
    </div>
  );
};
\`\`\`

### 3. Swipe Actions
\`\`\`jsx
// SwipeActions.jsx
const SwipeActions = ({ 
  children, 
  leftAction, 
  rightAction, 
  onLeftSwipe, 
  onRightSwipe 
}) => {
  const [swipeDistance, setSwipeDistance] = useState(0);
  const [isSwipeActive, setIsSwipeActive] = useState(false);
  
  let startX = 0;
  let currentX = 0;
  const threshold = 100;

  const handleTouchStart = (e) => {
    startX = e.touches[0].clientX;
    setIsSwipeActive(true);
  };

  const handleTouchMove = (e) => {
    if (!isSwipeActive) return;
    
    currentX = e.touches[0].clientX;
    const distance = currentX - startX;
    setSwipeDistance(Math.max(-150, Math.min(150, distance)));
  };

  const handleTouchEnd = () => {
    if (Math.abs(swipeDistance) >= threshold) {
      if (swipeDistance > 0 && onLeftSwipe) {
        onLeftSwipe();
      } else if (swipeDistance < 0 && onRightSwipe) {
        onRightSwipe();
      }
    }
    
    setSwipeDistance(0);
    setIsSwipeActive(false);
  };

  return (
    <div className="relative overflow-hidden">
      {/* Background actions */}
      <div className="absolute inset-0 flex">
        {/* Left action */}
        {leftAction && (
          <div 
            className="flex items-center justify-center bg-green-500 text-white px-4"
            style={{ width: Math.max(0, swipeDistance) }}
          >
            {swipeDistance > threshold && leftAction}
          </div>
        )}
        
        {/* Right action */}
        {rightAction && (
          <div 
            className="flex items-center justify-center bg-red-500 text-white px-4 ml-auto"
            style={{ width: Math.max(0, -swipeDistance) }}
          >
            {-swipeDistance > threshold && rightAction}
          </div>
        )}
      </div>
      
      {/* Content */}
      <div 
        className="relative z-10 bg-white dark:bg-gray-800 transition-transform duration-200"
        style={{ transform: `translateX(${swipeDistance}px)` }}
        onTouchStart={handleTouchStart}
        onTouchMove={handleTouchMove}
        onTouchEnd={handleTouchEnd}
      >
        {children}
      </div>
    </div>
  );
};
\`\`\`

---

## 🎨 THEME SYSTEM

### Theme Provider
\`\`\`jsx
// ThemeProvider.jsx
const ThemeContext = createContext();

export const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState('light');

  useEffect(() => {
    const savedTheme = localStorage.getItem('theme') || 'light';
    setTheme(savedTheme);
    
    if (savedTheme === 'dark') {
      document.documentElement.classList.add('dark');
    }
  }, []);

  const toggleTheme = () => {
    const newTheme = theme === 'light' ? 'dark' : 'light';
    setTheme(newTheme);
    localStorage.setItem('theme', newTheme);
    
    if (newTheme === 'dark') {
      document.documentElement.classList.add('dark');
    } else {
      document.documentElement.classList.remove('dark');
    }
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

export const useTheme = () => {
  const context = useContext(ThemeContext);
  if (!context) {
    throw new Error('useTheme must be used within ThemeProvider');
  }
  return context;
};
\`\`\`

### Theme Toggle Button
\`\`\`jsx
// ThemeToggle.jsx
const ThemeToggle = () => {
  const { theme, toggleTheme } = useTheme();

  return (
    <button
      onClick={toggleTheme}
      className="p-2 rounded-lg bg-gray-100 dark:bg-gray-800 text-gray-600 dark:text-gray-400 hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors"
      aria-label="Toggle theme"
    >
      {theme === 'light' ? (
        <svg className="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z" />
        </svg>
      ) : (
        <svg className="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z" />
        </svg>
      )}
    </button>
  );
};
\`\`\`

---

## 📏 RESPONSIVE BREAKPOINTS

### Tailwind CSS Configuration
\`\`\`js
// tailwind.config.js
module.exports = {
  content: ['./src/**/*.{js,jsx,ts,tsx}'],
  darkMode: 'class',
  theme: {
    extend: {
      screens: {
        'xs': '375px',
        'sm': '640px',
        'md': '768px',
        'lg': '1024px',
        'xl': '1280px',
        '2xl': '1536px',
      },
      colors: {
        primary: {
          50: '#faf5ff',
          100: '#f3e8ff',
          500: '#8b5cf6',
          600: '#7c3aed',
          700: '#6d28d9',
          900: '#4c1d95',
        },
        secondary: {
          50: '#fefce8',
          100: '#fef9c3',
          500: '#eab308',
          600: '#d97706',
          700: '#b45309',
        }
      },
      fontFamily: {
        primary: ['Inter', 'sans-serif'],
        display: ['Poppins', 'Inter', 'sans-serif'],
        mono: ['JetBrains Mono', 'monospace'],
      },
      spacing: {
        '18': '4.5rem',
        '88': '22rem',
      },
      minHeight: {
        'touch': '44px',
      },
      animation: {
        'fade-in': 'fadeIn 0.2s ease-in-out',
        'slide-up': 'slideUp 0.3s ease-out',
        'scale-in': 'scaleIn 0.2s ease-out',
      },
      keyframes: {
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        },
        slideUp: {
          '0%': { transform: 'translateY(10px)', opacity: '0' },
          '100%': { transform: 'translateY(0)', opacity: '1' },
        },
        scaleIn: {
          '0%': { transform: 'scale(0.95)', opacity: '0' },
          '100%': { transform: 'scale(1)', opacity: '1' },
        },
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
};
\`\`\`

---

## 📋 COMPONENT USAGE GUIDELINES

### Do's
- ✅ Gunakan semantic HTML elements
- ✅ Implementasikan proper ARIA labels
- ✅ Minimum 44px untuk touch targets
- ✅ Consistent spacing menggunakan 8px grid
- ✅ Loading states untuk semua async operations
- ✅ Error handling dan validation feedback
- ✅ Mobile-first responsive design

### Don'ts
- ❌ Hardcode colors, gunakan design tokens
- ❌ Inline styles, gunakan Tailwind classes
- ❌ Ignore accessibility requirements
- ❌ Fixed pixel values untuk responsive design
- ❌ Missing loading/error states
- ❌ Inconsistent spacing dan typography

---

**Note:** Semua komponen sudah dioptimalkan untuk mobile-first approach dan siap untuk implementasi PWA. Pastikan untuk test di berbagai device dan browser sebelum production.
\`\`\`
