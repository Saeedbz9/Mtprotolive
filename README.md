# MTProtoLive

پایگاه پروکسی‌های MTProto تلگرام — با بررسی زنده و مرتب‌سازی بر اساس پینگ.

🌐 **مشاهده سایت:** https://saeedbzdev.github.io/Mtprotolive/

## چی کار می‌کنه؟

- از ۲۰ کانال عمومی تلگرام (فایل `usernames.json`) پروکسی MTProto جمع می‌کنه
- هر پروکسی رو با یه اتصال TCP واقعی چک می‌کنه و پینگش رو اندازه می‌گیره
- آنلاین‌ها رو اول و بر اساس کمترین پینگ مرتب می‌کنه
- صفحه وب (`index.html`) رو با طراحی مدرن فارسی می‌سازه: فیلتر آنلاین/آفلاین،
  فیلتر نوع (TLS / Secure / معمولی)، جستجو در سرور، نمایش ۲۰ تایی با دکمه «۲۰ تای بعدی»،
  دکمه اتصال مستقیم در تلگرام و کپی لینک برای هر پروکسی

## به‌روزرسانی خودکار

GitHub Actions هر ۱۵ دقیقه اسکریپت `extract_proxies.php` رو اجرا می‌کنه و
`index.html` و `extracted_proxies.json` تازه رو به شاخه `gh-pages` می‌فرسته.
سایت روی GitHub Pages (از شاخه `gh-pages`) سرو می‌شه.

اجرای دستی: از تب Actions گزینه **Run workflow** یا با پارامتر `?scan` روی هاست PHP.

## فایل‌ها

| فایل | توضیح |
| --- | --- |
| `extract_proxies.php` | اسکنر: استخراج از کانال‌ها + چک TCP + ساخت `index.html` |
| `template.phtml` | قالب صفحه وب |
| `usernames.json` | کانال‌های تلگرام منبع |
| `.github/workflows/extract_proxies.yml` | اجرای خودکار هر ۱۵ دقیقه |
| `extracted_proxies.json` | خروجی JSON آخرین اسکن (خودکار ساخته می‌شه) |

## منبع

بر اساس [MTProtoNexus](https://github.com/itsyebekhe/MTProtoNexus) ساخته شده (MIT License)
و با طراحی و امکانات جدید بازنویسی شده.
