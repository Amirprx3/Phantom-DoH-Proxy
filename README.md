# Phantom DoH Proxy

**A High-Performance, Load-Balanced DNS-over-HTTPS Proxy on Cloudflare Workers.**

---

## 🇬🇧 English

### Overview

**Phantom DoH** is a robust middleware that acts as a smart gateway between your devices and global DNS providers. It ensures privacy, bypasses DNS hijacking, and optimizes speed by intelligently distributing requests.

### Features

* **Smart Load Balancing:** Uses a weighted algorithm to distribute queries across 7 premium providers:
* Cloudflare, Google, Quad9, AdGuard, NextDNS, Mullvad, and ControlD.


* **Fail-Safe Redundancy:** If a primary provider fails, the system automatically triggers `tryAllFallbacks()`, querying all providers simultaneously and returning the fastest healthy response.
* **Global Edge Performance:** Runs on Cloudflare's network, ensuring sub-millisecond latency from almost anywhere.
* **Modern Dashboard:** Includes a sleek, glassmorphic web interface to easily copy your endpoint.
* **Optimized Caching:** Implements a `300s` (5-minute) TTL to speed up repeated lookups.

### Installation

1. Sign in to your [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. Create a new **Worker**.
3. Paste the content of `workers.js` into the editor.
4. Click **Save and Deploy**.

---

## 🇮🇷 فارسی

### معرفی پروژه

**Phantom DoH** یک واسط هوشمند و قدرتمند برای پروتکل DNS-over-HTTPS است که بر پایه Cloudflare Workers توسعه یافته است. این پروژه با توزیع هوشمند درخواست‌ها بین چندین سرویس‌دهنده جهانی، پایداری و سرعت اینترنت شما را تضمین می‌کند.

### قابلیت‌های کلیدی

* **توزیع بار وزنی (Weighted LB):** برخلاف سیستم‌های راند-روبین ساده، این اسکریپت بر اساس اعتبار و سرعت (Weight) به سرویس‌دهنده‌ها اولویت می‌دهد.
* **سیستم جایگزینی خودکار (Fallback):** در صورت قطع شدن یکی از سرویس‌دهنده‌ها (مثلاً گوگل یا کلودفلر)، سیستم بلافاصله و بدون وقفه از سایر گزینه‌ها استفاده می‌کند تا اینترنت شما قطع نشود.
* **امنیت بالا:** تمامی درخواست‌ها با انکریپشن AES-256 (در لایه TLS) منتقل می‌شوند.
* **رابط کاربری مدرن:** دارای پنل تحت وب بسیار زیبا با تم Dark و قابلیت کپی آسان لینک اختصاصی.
* **سازگاری کامل:** قابل استفاده در اندروید (Private DNS)، ویندوز ۱۱، مرورگرها و تمامی کلاینت‌های DoH.

### نحوه راه‌اندازی

۱. وارد پنل کلودفلر شوید و یک **Worker** جدید بسازید.
۲. کدهای فایل `worker.js` را در ویرایشگر کپی کنید.
۳. دکمه **Save and Deploy** را بزنید.
۴. لینک اختصاصی شما آماده است! آن را در تنظیمات DNS مرورگر یا موبایل خود وارد کنید.

---

## 📊 Technical Stats | مشخصات فنی

| Feature | Description |
| --- | --- |
| **Runtime** | Cloudflare Workers (V8 Engine) |
| **Providers** | 7 Distributed Upstreams |
| **CORS** | Supported (Access-Control-Allow-Origin: *) |
| **Cache Strategy** | RFC 8484 Compliant (5 min TTL) |
| **Methods** | GET & POST Supported |

---

## 👨‍💻 Developer

**Created with ❤️ by Amirprx3**

> "Providing privacy and speed for everyone."