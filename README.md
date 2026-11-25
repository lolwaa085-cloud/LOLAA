# تطبيق لؤلؤة وبن 🌿

تطبيق أندرويد لتسويق وبيع المنتجات السودانية (بن، كركديه، صمغ عربي، سمسم، بهارات...). مكتوب بـ **Kotlin + Jetpack Compose** بواجهة عربية من اليمين لليسار.

## المزايا
- شاشة رئيسية بها بحث وتصفية حسب الفئة وشبكة منتجات
- شاشة تفاصيل المنتج مع اختيار الكمية
- سلة مشتريات (زيادة / إنقاص / حذف) مع الإجمالي
- إرسال الطلب إلى واتساب برسالة جاهزة تضم الاسم والعنوان والمنتجات والإجمالي

## التشغيل
1. ثبّت **Android Studio** (إصدار حديث).
2. افتح مجلد `LuluaWaBunn` من Android Studio وانتظر انتهاء مزامنة Gradle.
3. شغّل التطبيق على محاكي أو جوال حقيقي (Run ▶).
4. لإنتاج ملف APK: `Build > Build Bundle(s) / APK(s) > Build APK(s)`.

## قبل النشر — عدّل هذه الأشياء
| ماذا | أين |
|---|---|
| رقم واتساب لاستقبال الطلبات | `app/src/main/java/com/luluawabunn/app/data/Config.kt` (`WHATSAPP_NUMBER`) |
| العملة | نفس الملف (`CURRENCY`) |
| المنتجات والأسعار | `data/ProductRepository.kt` |
| اسم الحزمة `com.luluawabunn.app` | `app/build.gradle.kts` (`applicationId`) |

## إضافة صور حقيقية للمنتجات
حالياً يعرض التطبيق إيموجي بدل الصور. لاستخدام صور: أضفها في `res/drawable` وأضف الحقل `imageRes` إلى `Product`، ثم استبدل `ProductVisual` بـ `Image(painterResource(...))`.

## هيكل المشروع
```
app/src/main/java/com/luluawabunn/app/
├── MainActivity.kt
├── AppNav.kt            التنقل بين الشاشات
├── CartViewModel.kt     حالة السلة
├── data/                Config, Product, ProductRepository
└── ui/                  HomeScreen, ProductDetailScreen, CartScreen, Components, theme/
```
