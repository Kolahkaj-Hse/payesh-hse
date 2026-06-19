# پایش پرسنل ایمنی منطقه ۹ 🛡️

اپلیکیشن وب پیشرو (PWA) برای مدیریت و پایش پرسنل ایمنی، برنامه اقماری، ثبت عملکرد، گزارش حوادث و مرخصی‌ها.

## نصب روی موبایل

پس از باز کردن لینک اپ در مرورگر:
- **اندروید (Chrome)**: گزینه «افزودن به صفحه اصلی» را در منو انتخاب کنید
- **iOS (Safari)**: دکمه Share → «Add to Home Screen» را انتخاب کنید

## استقرار در GitHub Pages

این ریپازیتوری با GitHub Pages به صورت خودکار منتشر می‌شود.  
لینک اپ پس از فعال‌سازی: `https://<username>.github.io/<repo-name>/`

## ساختار فایل‌ها

```
├── index.html              # اپ اصلی
├── manifest.webmanifest    # تنظیمات PWA
├── sw.js                   # Service Worker (آفلاین)
├── assets/
│   ├── icon.svg            # آیکون SVG
│   ├── icon-192.png        # آیکون ۱۹۲×۱۹۲
│   └── icon-512.png        # آیکون ۵۱۲×۵۱۲
└── .github/workflows/
    └── deploy.yml          # استقرار خودکار
```

## فناوری‌ها

- HTML/CSS/JS خالص — بدون framework
- فونت Vazirmatn (فارسی)
- تقویم جلالی کامل
- Service Worker برای کارکرد آفلاین
