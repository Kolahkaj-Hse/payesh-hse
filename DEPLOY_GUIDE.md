# راهنمای گام‌به‌گام آپلود در GitHub Pages

## پیش‌نیاز
یک حساب رایگان در [github.com](https://github.com) داشته باشید.

---

## روش اول: آپلود مستقیم (بدون Git — آسان‌ترین)

### گام ۱ — ساخت ریپازیتوری جدید
1. وارد github.com شوید
2. روی دکمه **«+»** بالا سمت راست کلیک → **New repository**
3. تنظیمات:
   - **Repository name**: `payesh-hse` (یا هر نامی دلخواه)
   - **Visibility**: Public ✅ (برای GitHub Pages رایگان باید Public باشد)
   - **Add a README file**: ❌ تیک نزنید
4. روی **Create repository** کلیک کنید

---

### گام ۲ — آپلود فایل‌ها
1. در صفحه ریپازیتوری جدید روی **uploading an existing file** کلیک کنید
2. همه فایل‌های زیر را drag & drop کنید:
   ```
   index.html
   manifest.webmanifest
   sw.js
   README.md
   .nojekyll
   ```
3. پوشه `assets` را هم آپلود کنید:
   - روی **choose your files** کلیک کنید
   - فایل‌های `assets/icon-192.png`، `assets/icon-512.png`، `assets/icon.svg` را انتخاب کنید
   - ⚠️ **مهم**: قبل از commit، در باکس نام فایل، مسیر `assets/` را اضافه کنید

   > ترفند ساده‌تر: ابتدا پوشه assets را در GitHub ایجاد کنید:
   > کلیک روی **Create new file** → تایپ `assets/placeholder.txt` → Commit

4. پیام commit مثل `"Initial upload"` بنویسید
5. **Commit changes** را بزنید

---

### گام ۳ — فعال‌سازی GitHub Pages
1. در ریپازیتوری روی **Settings** کلیک کنید
2. از منوی سمت چپ، **Pages** را انتخاب کنید
3. در بخش **Source** گزینه **GitHub Actions** را انتخاب کنید
4. فایل `.github/workflows/deploy.yml` را هم آپلود کنید (همان مسیر را بسازید)

---

### گام ۴ — آپلود پوشه .github/workflows
1. روی **Create new file** کلیک کنید
2. در باکس نام، تایپ کنید: `.github/workflows/deploy.yml`
3. محتوای فایل `deploy.yml` را کپی‌پیست کنید
4. **Commit changes** کنید

---

### گام ۵ — مشاهده استقرار
1. به تب **Actions** بروید
2. منتظر بمانید تا workflow با ✅ سبز کامل شود (۱-۲ دقیقه)
3. به **Settings → Pages** برگردید
4. لینک اپ نمایش داده می‌شود:
   ```
   https://<username>.github.io/payesh-hse/
   ```

---

## روش دوم: با Git (برای توسعه‌دهنده)

```bash
# کلون ریپازیتوری
git clone https://github.com/<username>/payesh-hse.git
cd payesh-hse

# کپی فایل‌ها
cp /path/to/files/* .

# آپلود
git add .
git commit -m "Initial PWA setup"
git push origin main
```

---

## تست نصب PWA روی موبایل

پس از آنلاین شدن اپ:

### اندروید (Chrome)
1. لینک را در Chrome باز کنید
2. منوی ⋮ → **Install app** یا **Add to Home Screen**
3. اپ مثل اپ نصبی روی صفحه اصلی ظاهر می‌شود ✅

### iOS (Safari)
1. لینک را در Safari باز کنید  
2. دکمه Share (مربع با فلش بالا) →
3. **Add to Home Screen** → **Add**
4. اپ با آیکون سپر سبز نصب می‌شود ✅

---

## نکات مهم

| موضوع | توضیح |
|-------|-------|
| **HTTPS** | GitHub Pages به صورت خودکار SSL دارد — برای PWA الزامی است |
| **به‌روزرسانی** | هر بار که `index.html` را ویرایش کنید، GitHub Actions خودکار deploy می‌کند |
| **حافظه آفلاین** | Service Worker فایل‌ها را کش می‌کند؛ پس از اولین بارگذاری آفلاین کار می‌کند |
| **ریپازیتوری Private** | برای GitHub Pages رایگان باید Public باشد یا از GitHub Pro استفاده کنید |

