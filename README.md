<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>دوره رایگان ساخت ربات بله با پایتون</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #f8fafc 0%, #eef2f5 100%);
            font-family: system-ui, 'Segoe UI', 'Tahoma', 'Vazirmatn', 'Vazir', 'IranSans', 'Roboto', sans-serif;
            line-height: 1.65;
            color: #1e293b;
            padding: 2rem 1rem;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.96);
            backdrop-filter: blur(0px);
            border-radius: 2rem;
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.25), 0 2px 6px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            padding: 2rem 2rem 3rem;
            transition: all 0.2s ease;
        }

        @media (max-width: 768px) {
            body {
                padding: 1rem 0.75rem;
            }

            .container {
                padding: 1.5rem 1rem;
                border-radius: 1.5rem;
            }
        }

        /* typography */
        h1 {
            font-size: 1.95rem;
            font-weight: 800;
            background: linear-gradient(135deg, #0f2b3d, #1e6f5c);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            margin-bottom: 0.5rem;
            text-align: center;
            letter-spacing: -0.3px;
        }

        h2 {
            font-size: 1.65rem;
            font-weight: 700;
            border-right: 5px solid #2c7a64;
            padding-right: 1rem;
            margin: 2rem 0 1rem 0;
            color: #0f3b2c;
        }

        h3 {
            font-weight: 700;
            font-size: 1.35rem;
            margin: 1.5rem 0 0.75rem;
            color: #1e4a3b;
        }

        .badge-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.75rem;
            margin: 1.5rem 0 1rem;
        }

        .badge {
            display: inline-flex;
            align-items: center;
            background: #fff;
            padding: 0.4rem 1rem;
            border-radius: 48px;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
            transition: transform 0.15s ease, box-shadow 0.2s;
            font-size: 0.85rem;
            font-weight: 500;
            border: 1px solid #e2e8f0;
            gap: 0.4rem;
        }

        .badge:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 18px rgba(0, 0, 0, 0.1);
            border-color: #cbd5e1;
        }

        .badge img, .badge svg {
            width: 18px;
            height: 18px;
        }

        a {
            text-decoration: none;
            color: #1f7b66;
            font-weight: 500;
            transition: color 0.2s;
        }

        a:hover {
            color: #0b4e3f;
            text-decoration: underline;
        }

        .card-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1.25rem;
            margin: 1.5rem 0;
        }

        .card {
            background: #ffffffdd;
            backdrop-filter: blur(4px);
            background: #ffffff;
            border-radius: 1.5rem;
            padding: 1.2rem 1rem;
            flex: 1 1 220px;
            border: 1px solid #e9edf2;
            transition: all 0.2s;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.02);
        }

        .card strong {
            display: block;
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: #0c4e3f;
        }

        .responsive-table {
            width: 100%;
            overflow-x: auto;
            margin: 1.5rem 0;
            border-radius: 1rem;
            border: 1px solid #e2edf2;
            background: white;
        }

        table {
            width: 100%;
            min-width: 500px;
            border-collapse: collapse;
            font-size: 0.9rem;
        }

        th, td {
            padding: 1rem 1rem;
            text-align: right;
            border-bottom: 1px solid #eef2f6;
        }

        th {
            background-color: #f1f9f5;
            font-weight: 700;
            color: #155e48;
        }

        tr:hover td {
            background-color: #f9fefb;
        }

        code, pre {
            font-family: 'JetBrains Mono', 'Fira Code', monospace;
            background: #1e2a36;
            color: #e4f5e9;
            border-radius: 14px;
            padding: 0.2rem 0.4rem;
            font-size: 0.85rem;
        }

        pre {
            padding: 1rem;
            overflow-x: auto;
            white-space: pre-wrap;
            word-break: break-word;
            background: #0f1a1f;
            margin: 1rem 0;
            border-radius: 1rem;
            direction: ltr;
            text-align: left;
        }

        .btn-outline {
            display: inline-block;
            background: transparent;
            border: 1.5px solid #2c7a64;
            color: #2c7a64;
            padding: 0.4rem 1rem;
            border-radius: 60px;
            font-weight: 600;
            transition: 0.2s;
        }

        .btn-outline:hover {
            background: #2c7a64;
            color: white;
            text-decoration: none;
        }

        .footnote {
            background: #eef7f3;
            border-radius: 1rem;
            padding: 1rem 1.5rem;
            margin: 1.8rem 0;
            border-right: 5px solid #2c7a64;
        }

        hr {
            margin: 2rem 0;
            border: none;
            height: 2px;
            background: linear-gradient(to left, #cbdde6, transparent);
        }

        .star-call {
            text-align: center;
            background: linear-gradient(125deg, #fef9e6, #fff6e8);
            border-radius: 2rem;
            padding: 1.2rem;
            margin-top: 2rem;
        }

        @media (max-width: 580px) {
            h1 { font-size: 1.6rem; }
            h2 { font-size: 1.4rem; }
            .container { padding: 1.2rem; }
            .badge { font-size: 0.7rem; padding: 0.25rem 0.8rem; }
        }
    </style>
</head>
<body>
<div class="container">
    
    <!-- header & title -->
    <div style="text-align: center;">
        <h1>🤖 دوره رایگان ساخت ربات بله با پایتون</h1>
        <p style="font-size: 1.1rem; color: #2c5a4a; margin-top: 0.25rem;">✨ از صفر تا صد به همراه کد و ویدیو ✨</p>
    </div>

    <!-- responsive badges (flex wrap) -->
    <div class="badge-container">
        <a class="badge" href="https://python.org" target="_blank"><span>🐍 Python 3.8+</span></a>
        <a class="badge" href="https://github.com/theesmaeil1/bale-bot-course" target="_blank"><span>⭐ ستاره GitHub</span></a>
        <a class="badge" href="./LICENSE" target="_blank"><span>📜 مجوز ViraiGame</span></a>
        <a class="badge" href="https://www.aparat.com/playlist/25173730" target="_blank"><span>🎬 پلی‌لیست آپارات</span></a>
        <a class="badge" href="https://viraigame.ir" target="_blank"><span>🌐 وبسایت دوره</span></a>
        <a class="badge" href="https://github.com/theesmaeil1/bale-bot-course/releases" target="_blank"><span>📦 Releases</span></a>
    </div>

    <!-- Introduction -->
    <section>
        <h2>📌 درباره دوره</h2>
        <p>این مخزن حاوی <strong>کدهای کامل و ویدیوهای آموزشی یک دوره جامع و کاملاً رایگان</strong> برای ساخت ربات در پیام‌رسان بله با استفاده از زبان برنامه‌نویسی پایتون است.  
        هدف این دوره ارائه دانشی عملی از سطح مقدماتی تا پیشرفته به شکلی پروژه‌محور می‌باشد.</p>
        
        <div class="card-grid">
            <div class="card"><strong>✅ کاملاً رایگان</strong> بدون نیاز به ثبت‌نام خاص</div>
            <div class="card"><strong>🧠 پروژه‌محور</strong> کدهای هر جلسه در دسترس</div>
            <div class="card"><strong>📈 گام‌به‌گام</strong> از نصب تا قابلیت‌های پیچیده</div>
        </div>

        <p><strong>📺 منابع آموزشی:</strong> ویدیوها در <a href="https://www.aparat.com/playlist/25173730" target="_blank">پلی‌لیست اختصاصی آپارات</a> و <a href="https://viraigame.ir" target="_blank">وبسایت ViraiGame</a> — کد منبع در همین مخزن — همچنین بسته کامل هر قسمت در بخش <a href="https://github.com/theesmaeil1/bale-bot-course/releases" target="_blank">Releases</a> منتشر می‌شود.</p>
    </section>

    <!-- پیش‌نیازها و نصب سریع -->
    <h2>🧩 پیش‌نیازها و نصب سریع</h2>
    <div class="responsive-table">
        <table>
            <thead>
                <tr><th>پیش‌نیاز</th><th>توضیح</th></tr>
            </thead>
            <tbody>
                <tr><td>🐍 <strong>Python 3.8+</strong></td><td><a href="https://python.org" target="_blank">دانلود از python.org</a></td></tr>
                <tr><td>🤖 <strong>کتابخانه رسمی بله</strong></td><td>نصب با <code>pip</code> (توضیح کامل در قسمت اول)</td></tr>
                <tr><td>📱 <strong>حساب بله</strong></td><td>برای دریافت توکن و تست ربات</td></tr>
            </tbody>
        </table>
    </div>

    <h3>⚡ راه‌اندازی در چند خط</h3>
    <pre><code># 1. کلون کردن مخزن
git clone https://github.com/theesmaeil1/bale-bot-course.git

# 2. ورود به پوشه پروژه
cd bale-bot-course

# 3. (اختیاری) ایجاد محیط مجازی — پیشنهاد می‌شود
python -m venv venv
source venv/bin/activate   # در ویندوز: venv\Scripts\activate

# 4. نصب کتابخانه رسمی بله
pip install balebot</code></pre>
    <div class="footnote">
        📌 <strong>نکته مهم:</strong> دریافت توکن ربات و تنظیمات اولیه به تفصیل در قسمت ۲ آموزش داده می‌شود. برای آشنایی کامل حتماً ویدیو جلسه دوم را دنبال کنید.
    </div>

    <!-- فهرست قسمت‌ها با جدول ریسپانسیو -->
    <h2>🎬 فهرست قسمت‌ها و لینک ویدیوها</h2>
    <div class="responsive-table">
        <table>
            <thead>
                <tr><th>شماره</th><th>عنوان جلسه</th><th>فایل(های) کد</th><th>لینک ویدیو</th></tr>
            </thead>
            <tbody>
                <tr><td>۱</td><td>معرفی دوره و توضیحات اختصاصی</td><td><a href="https://github.com/theesmaeil1/bale-bot-course/releases">📁 دریافت</a></td><td><a href="https://www.aparat.com/playlist/25173730" target="_blank">🎥 تماشا</a></td></tr>
                <tr><td>۲</td><td>دریافت توکن، ساخت اولین ربات ساده</td><td>در حال آماده‌سازی</td><td>به زودی</td></tr>
                <tr><td>۳</td><td>مدیریت پیام‌ها و کیبورد شیشه‌ای</td><td>در حال آماده‌سازی</td><td>به زودی</td></tr>
                <tr><td>۴</td><td>ربات دانلودر و فایل‌ها</td><td>در حال آماده‌سازی</td><td>به زودی</td></tr>
                <tr><td>۵+</td><td>قابلیت‌های پیشرفته دیتابیس، منوهای داینامیک، API و ...</td><td>به زودی</td><td>به زودی</td></tr>
            </tbody>
        </table>
    </div>
    <p style="margin-top: -0.5rem;">🔗 <strong>لینک مستقیم پلی‌لیست آپارات:</strong> <a href="https://www.aparat.com/playlist/25173730" target="_blank">aparat.com/playlist/25173730</a></p>

    <!-- دانلود ریسورس‌ها -->
    <h2>📦 دانلود ریسورس‌های هر قسمت</h2>
    <p>تمامی کدها، فایل‌های پروژه، تصاویر و فایل‌های مورد نیاز برای تمرین و اجرای ربات، پس از انتشار هر ویدیو در بخش <strong>Releases گیت‌هاب</strong> قرار داده می‌شود.</p>
    <div style="background: #eef2fa; border-radius: 1rem; padding: 0.8rem 1.2rem; margin: 1rem 0;">
        👉 <strong><a href="https://github.com/theesmaeil1/bale-bot-course/releases" target="_blank">مشاهده و دانلود از صفحه Releases</a></strong><br>
        • فایل <code>Source code (zip)</code> حاوی کدهای دقیق همان جلسه است.<br>
        • هر Release با برچسب شماره قسمت (مثلاً <code>v1.0-ep01</code>) منتشر می‌شود.
    </div>

    <!-- لینک‌های مفید -->
    <h2>🌐 لینک‌های مفید</h2>
    <div class="card-grid" style="margin-bottom: 0.5rem;">
        <div class="card"><a href="https://viraigame.ir" target="_blank">📢 وبسایت رسمی دوره</a></div>
        <div class="card"><a href="https://www.aparat.com/theesmaeil1" target="_blank">📺 کانال آپارات مدرس</a></div>
        <div class="card"><a href="https://github.com/theesmaeil1/bale-bot-course" target="_blank">💾 مخزن گیت‌هاب</a></div>
        <div class="card"><a href="https://github.com/theesmaeil1/bale-bot-course/issues" target="_blank">💬 گزارش مشکل یا ایده</a></div>
    </div>

    <!-- مشارکت -->
    <h2>🤝 مشارکت و بهبود</h2>
    <p>نظرات و پیشنهادات شما مایه پیشرفت دوره است:</p>
    <ul style="margin-right: 1.5rem; line-height: 1.7;">
        <li>🍴 پروژه را <strong>Fork</strong> کنید.</li>
        <li>🌿 یک Branch جدید بسازید و تغییرات خود را اعمال کنید.</li>
        <li>🚀 <strong>Pull Request</strong> ارسال کنید.</li>
        <li>برای گزارش مشکل یا ایده‌های جدید از <strong>Issues</strong> استفاده کنید.</li>
    </ul>

    <!-- مجوز و حمایت -->
    <h2>📜 مجوز</h2>
    <p>این دوره تحت مجوز اختصاصی <strong>ViraiGame</strong> منتشر شده است. برای جزئیات به فایل <code>LICENSE</code> مراجعه کنید.</p>
    <div style="display: flex; align-items: center; gap: 10px; flex-wrap: wrap; margin: 0.5rem 0 1rem;">
        <span class="badge" style="background:#ede9fe;">📜 مجوز ViraiGame Custom</span>
    </div>

    <div class="star-call">
        ⭐ <strong>حمایت از دوره</strong> ⭐<br>
        اگر این مطالب برایتان مفید بود:<br>
        ➕ روی دکمه <strong>⭐ Star</strong> در گیت‌هاب کلیک کنید<br>
        📢 دوره را به دیگران معرفی کنید<br>
        <span style="font-size: 0.85rem;">✨ هر ستاره و بازخورد کوچک، انرژی ادامه کار رایگان ماست ✨</span>
    </div>

    <hr>
    <p style="text-align: center; font-weight: 500; margin-bottom: 0;">با آرزوی موفقیت – <strong>اسماعیل</strong></p>
    <p style="text-align: center; font-size: 0.8rem; opacity: 0.7;">ViraiGame Academy | آموزش رایگان ربات‌سازی پیام‌رسان بله</p>
</div>
</body>
</html>
