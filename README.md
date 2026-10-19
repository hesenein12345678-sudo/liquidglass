# Liquid Glass 🫧

تطبيق أندرويد (Jetpack Compose) يعرض تصميم **Liquid Glass** بالكامل باستخدام مكتبة
[**Backdrop**](https://github.com/Kyant0/AndroidLiquidGlass) من Kyant0.

An Android app built with Jetpack Compose that showcases the **Liquid Glass** look using the Backdrop library.

## المميزات / Features

- **شريط سفلي زجاجي (Bottom Tabs)** مثل الموجود في Backdrop Catalog: كبسولة زجاجية + مؤشر زجاجي قابل للسحب ويتمدد عند اللمس.
- **Home**: عرض لعناصر زجاجية (أزرار، Switch، Slider، كروت) فوق خلفية متحركة.
- **About**: شرح عن التطبيق + زر تيليجرام (`@xezn9`) وزر تيك توك (`@xezn99`).
- **Profile** بأسلوب تيك توك:
  - صورة ملف شخصي وبانر يتلاشى تدريجياً من الأسفل فقط
  - الاسم واسم المستخدم
  - قصة (نص + صورة) تختفي تلقائياً بعد 24 ساعة
  - كل شيء قابل للتخصيص (صورة، بانر، اسم، مستخدم، قصة)
- كل زر وعنصر قابل للضغط له حركة Spring ناعمة بأسلوب Apple، وانزلاق بين الصفحات.

## هيكل المشروع / Structure

```
LiquidGlass/
├── settings.gradle.kts
├── build.gradle.kts
├── gradle.properties
└── app/
    ├── build.gradle.kts
    └── src/main/
        ├── AndroidManifest.xml
        ├── res/...
        └── java/com/xezn/liquidglass/
            ├── MainActivity.kt
            ├── Data.kt              ← بيانات البروفايل والتخزين
            └── ui/
                ├── App.kt           ← الجذر + التنقل
                ├── Tabs.kt          ← الشريط السفلي Liquid Glass
                ├── Components.kt    ← الأزرار والكروت (glass / bouncyClick)
                ├── Screens.kt       ← Home / About / Profile
                └── Overlays.kt      ← نوافذ التعديل وعارض القصة
```

## البناء على GitHub (بدون جهازك) / Build on GitHub

1. أنشئ Repository جديد على GitHub.
2. ارفع هذه الملفات في **جذر** الـ Repository:
   - ملف المشروع `LiquidGlass.zip` (كما هو، لا تفك ضغطه)
   - `README.md`
   - `build.yml` داخل المجلد `.github/workflows/` (أي المسار الكامل `.github/workflows/build.yml`)
3. بعد الرفع يبدأ البناء تلقائياً (أو من تبويب **Actions** ← **Build Android APK** ← **Run workflow**).
4. الـ Workflow يفك ضغط الـ zip داخل GitHub، يجهز JDK 17 و Android SDK و Gradle، ثم يبني `assembleDebug`.
5. بعد النجاح افتح التشغيل واضغط على **LiquidGlass-debug-apk** في قسم Artifacts لتحميل الـ APK وتثبيته.

## البناء محلياً / Build locally

افتح مجلد المشروع في Android Studio (Narwhal أو أحدث) واضغط Run. أو:

```bash
gradle assembleDebug
```

## ملاحظات / Notes

- تأثير العدسة (Lens/Refraction) يحتاج **Android 13+** (API 33)؛ في الإصدارات الأقدم يظهر التمويه فقط.
- إصدار المكتبة محدد في `app/build.gradle.kts`:
  `io.github.kyant0:backdrop:2.0.0` — يمكنك تغييره لأحدث إصدار من Maven Central.
- بيانات الملف الشخصي تُحفظ محلياً على الجهاز فقط.

## الحسابات / Contact

- Telegram: https://t.me/xezn9
- TikTok: https://www.tiktok.com/@xezn99
