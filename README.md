<p>
<img src="https://img.shields.io/github/forks/artkulak/text2youtube.svg">
<img src="https://img.shields.io/github/stars/artkulak/text2youtube.svg">
<img src="https://img.shields.io/github/watchers/artkulak/text2youtube.svg">
<img src="https://img.shields.io/github/last-commit/artkulak/text2youtube.svg">
<img src="https://hits.sh/github.com/artkulak/text2youtube.svg">
</p>

# 🎬 text2youtube

## توضیحات

این فورک فقط ترجمه ریپازیتوری اصلی است.  
text2youtube از قدرت پیشرفته هوش مصنوعی برای اتوماسیون یوتیوب استفاده می‌کند و متن ساده را به محتوای ویدیویی جذاب تبدیل می‌کند. این پروژه با هدف اتوماسیون یوتیوب و تکنولوژی تبدیل متن به ویدیو طراحی شده است و فرآیند تولید محتوای ویدیویی را ساده‌تر می‌کند. این ابزار از هوش مصنوعی پیشرفته برای تولید سناریو، سنتز متن به صدا و ترکیب ویدیو استفاده می‌کند، که آن را به ابزاری نوآورانه در زمینه تبدیل متن به ویدیو و اتوماسیون یوتیوب تبدیل می‌کند.

## ویژگی‌ها

📜 تولید خودکار اسکریپت ویدیو از ورودی و اطلاعات مرجع (مانند اسکریپت ویدیوی دیگر). ما نه تنها اسکریپت را تولید می‌کنیم بلکه پرس‌وجوهایی برای یوتیوب/استوری‌بلوک‌ها انجام می‌دهیم تا بتوانیم ویدیوی خود را از مجموعه‌ای از کلیپ‌هایی که از این پرس‌وجوها دانلود می‌کنیم، بسازیم.

🎙 تولید صدا برای ویدیو با استفاده از Bark. Bark بهترین گزینه برای تولید صدای طبیعی در حال حاضر است و صدا یکی از مهم‌ترین بخش‌های یک ویدیوی یوتیوب است و ما در این زمینه آزمایش‌های زیادی انجام داده‌ایم. این مدل سریع روی Google Colab با GPU A100 اجرا می‌شود.

🎨 ما کدهای پایه‌ای برای ترکیب ویدیوها با استفاده از MoviePY داریم اما این کار به آرامی انجام می‌شود، بنابراین فعلاً کلیپ‌ها را از Storyblocks/Youtube و صدای ضبط شده صادر کرده و آن‌ها را در Adobe Premiere به سرعت ترکیب می‌کنیم.

## دموها

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1NpBJ4CFtGK4PWxQkb9D6pD5a2KNf8eKt?usp=sharing)

## شروع به کار

1. وابستگی‌های مورد نیاز را با اجرای دستور `pip install -r requirements.txt` نصب کنید.
2. برای نصب تبدیل متن به صدا، دستور `pip install git+https://github.com/suno-ai/bark.git` را اجرا کنید.
3. اطمینان حاصل کنید که فایل `cookies.json` با اعتبارنامه‌های لازم برای دسترسی به وب‌سایت **storyblocks.com** موجود باشد.
4. اطمینان حاصل کنید که فایل `env.yaml` شامل کلید API OpenAi و دایرکتوری‌های کاری است.
5. ورودی مورد نیاز OpenAI را در دایرکتوری prompts قرار دهید.
6. ورودی‌های محتوایی را در فایل‌های متنی در دایرکتوری SOURCE_DIR قرار دهید.
7. فایل اصلی برنامه `app.py` را اجرا کنید تا فرآیند تولید محتوا آغاز شود.
8. برنامه بقیه کارها را انجام خواهد داد و ویدیوهای جذاب با صداهای شنیدنی ایجاد می‌کند.

## ساختار پروژه

پروژه شامل چندین ماژول است:

- `src.audio`: شامل توابع مربوط به صدا برای سنتز متن به صدا.
- `src.config`: ذخیره تنظیمات پیکربندی برای برنامه.
- `src.logger`: پیاده‌سازی عملکرد لاگ‌گذاری برای برنامه.
- `src.openai_generation`: مدیریت تعاملات با OpenAI برای تولید سناریو.
- `src.video_processing`: مدیریت دانلود ویدیوها از یوتیوب یا videoblocks.com.
- `src.utils`: شامل توابع کمکی برای پردازش داده‌ها و مدیریت فایل‌ها.
- `src.video`: شامل توابع مربوط به ویدیو برای ترکیب و ویرایش.

## نتایج

در حین توسعه، تصمیم گرفتیم روی بخش مالی تمرکز کنیم و یک کانال یوتیوب با موضوع اقتصاد/کشورها بسازیم. [اینجا کانال را مشاهده کنید](https://www.youtube.com/channel/UC0JQ0xmoK_lcg5AchMGmI4Q)

ما روزانه یک ویدیو برای حدود ۲۰-۲۵ روز منتشر کردیم. در نهایت، حدود ۸,۰۰۰ بازدید، ۲۲۱ ساعت مشاهده و بیش از ۷۰ مشترک به دست آوردیم. میانگین زمان مشاهده ویدیوها حدود ۳۰٪ بود. نتایج این آزمایش نسبتاً دلگرم‌کننده بودند چون ویدیوها از کیفیت بالایی برخوردار نبودند و انتظار نتایج بدتری داشتم.

## مواردی که باید بهبود یابند

- در حال حاضر تغییر کیفیت صدای طبیعی تولید شده دشوار است اما فکر می‌کنم می‌توانیم پیشرفت زیادی در خود فرآیند تولید ویدیو داشته باشیم. به عنوان مثال، پیدا کردن راهی برای افزودن متون با کیفیت بالا به روی کلیپ‌های ویدیو می‌تواند یک مزیت بزرگ باشد. یا گرفتن تصاویر از گوگل و اعمال پارالاکس (اثر کن برنز) روی آن‌ها.
- بهبود سرعت تولید ویدیو با استفاده از MoviePY، به طوری که ویدیوها نیازی به صادرات به Adobe Premiere Pro نداشته باشند.
- امکان ایجاد محتوای یوتیوب شورت (محتوای کوتاه) را اضافه کنید، اگرچه پروژه‌های زیادی قبلاً این کار را انجام داده‌اند.

## وابستگی‌ها

- [OpenAI GPT-3 API](https://openai.com): برای تولید سناریو با استفاده از مدل‌های زبان.
- [کتابخانه Neural Network Text-to-Speech BARK](https://github.com/suno-ai/bark/): برای سنتز صدای طبیعی.
- [کتابخانه Python Requests](https://pypi.org/project/requests/): برای دسترسی به وب‌سایت‌ها و دانلود ویدیوها.
- [کتابخانه MoviePy](https://pypi.org/project/moviepy/): برای ترکیب و ویرایش ویدیو.

## مشارکت‌کنندگان

- [Art Kulakov](https://github.com/artkulak)
- [Movses M](https://github.com/mirmozavr)

## مجوز

این پروژه تحت [مجوز MIT](LICENSE) منتشر شده است. از آن به دلخواه خود استفاده و تغییر دهید.

[![Test and lint](https://github.com/artkulak/text2youtube/actions/workflows/check.yml/badge.svg)](https://github.com/artkulak/text2youtube/actions/workflows/check.yml)
