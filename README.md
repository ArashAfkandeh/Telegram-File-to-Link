# ربات ذخیره‌ساز فایل تلگرام 📁

این ربات تلگرام فایل‌های فوروارد شده را روی سرور شما ذخیره کرده و لینک دانلود یا استریم مستقیم آن‌ها را تحویل می‌دهد.

## امکانات 🚀

- ذخیره‌سازی امن فایل‌ها روی سرور شخصی با HTTPS
- محدود کردن دسترسی به کاربران مجاز
- حذف خودکار فایل‌های قدیمی
- پشتیبانی از پروکسی برای اتصال به تلگرام
- امنیت بالا با nginx و SSL

## پیش‌نیازها 📋

- سرور اوبونتو (20.04+)
- دامنه یا ساب‌دامنه
- اکانت تلگرام
- کلیدهای API تلگرام:
  - `API_ID` و `API_HASH` از [my.telegram.org/apps](https://my.telegram.org/apps)
  - `BOT_TOKEN` از [@BotFather](https://t.me/BotFather)

## نصب ربات 🔧

### روش ۱: نصب مستقیم با پارامترها

برای نصب مستقیم با پارامترها، از دستور زیر استفاده کنید:

```bash
curl -sSL https://raw.githubusercontent.com/ArashAfkandeh/Telegram-File-to-Link/blob/main/install.sh | sudo bash -s -- 'YOUR_DOMAIN' 'YOUR_EMAIL' 'API_ID' 'API_HASH' 'BOT_TOKEN'
```

**مثال:**

```bash
curl -sSL https://raw.githubusercontent.com/ArashAfkandeh/Telegram-File-to-Link/blob/main/install.sh | sudo bash -s -- 'bot.example.com' 'admin@example.com' '123456' 'abcdef1234567890abcdef1234567890' '5555555555:AAAAAAAAAAbbbbbbbbbbCCCCCCCCCC'
```

### روش ۲: نصب تعاملی (بدون پارامتر)

برای نصب تعاملی، می‌توانید مستقیماً از طریق curl اسکریپت را اجرا کنید:

```bash
curl -sSL https://raw.githubusercontent.com/ArashAfkandeh/Telegram-File-to-Link/blob/main/install.sh | sudo bash
```

یا اگر اسکریپت را دانلود کرده‌اید، بدون پارامتر اجرا کنید:

```bash
./install.sh
```

در هر دو حالت، اسکریپت به صورت تعاملی اطلاعات زیر را از شما درخواست می‌کند:
- دامنه یا ساب‌دامنه
- آدرس ایمیل
- شناسه API تلگرام
- کلید هش API تلگرام
- توکن ربات

### پارامترهای نصب

- `YOUR_DOMAIN`: دامنه یا ساب‌دامنه شما
- `YOUR_EMAIL`: ایمیل برای دریافت اخطارهای SSL
- `API_ID`: شناسه API تلگرام
- `API_HASH`: کلید هش API تلگرام
- `BOT_TOKEN`: توکن ربات دریافتی از BotFather

## مدیریت ربات

### مشاهده لاگ‌های ربات

```bash
sudo journalctl -u Telegram-File-to-Link -f
```

### حذف ربات

برای حذف کامل ربات و تمام تنظیمات آن، دستور زیر را اجرا کنید:

```bash
curl -sSL https://raw.githubusercontent.com/ArashAfkandeh/Telegram-File-to-Link/blob/main/install.sh | sudo bash -s -- --uninstall
```

یا اگر اسکریپت را قبلاً دانلود کرده‌اید:

```bash
./install.sh --uninstall
```

### ارتقاء 🔄

برای به‌روزرسانی به آخرین نسخه:

```bash
cd /opt/Telegram-File-to-Link
git pull
sudo systemctl restart Telegram-File-to-Link
```

## لایسنس 📝

این پروژه تحت لایسنس MIT منتشر شده است.
