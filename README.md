# Sokōn Proxy for Render & Google Apps Script

هذا المستودع يحتوي على إعدادات خادم Nginx خفيف (Docker) ليعمل كوسيط آمن (Reverse Proxy) على منصة Render.

## الهدف
- تحويل رابط HTTP غير المشفر (`http://62.193.79.186:8090/`) إلى رابط HTTPS مشفر مجاناً.
- فك قيود الـ Iframe (`X-Frame-Options`) ليعمل الموقع داخل **Google Apps Script** أو أي صفحة خارجية بسلاسة.
- حل مشكلة كوكيز الجلسة (`SameSite=None; Secure`) لضمان تسجيل الدخول داخل الـ Iframe.
- حل مشكلة حظر الـ Host من قِبل نظام Django (`400 Bad Request`).

## خطوات النشر على Render
1. قم برفع هذا المجلد على مستودع جديد في **GitHub**.
2. ادخل إلى [Render.com](https://dashboard.render.com/) واضغط على **New +** ثم **Web Service**.
3. اختر مستودع الـ GitHub الخاص بك.
4. Render سيتعرف تلقائياً على `Dockerfile` (Environment: Docker).
5. اضغط **Create Web Service**.
6. بعد اكتمال البناء (Live باللون الأخضر)، انسخ الرابط الآمن الناتج وضعه في كود الـ Iframe داخل Google Apps Script.
