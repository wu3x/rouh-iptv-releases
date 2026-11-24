<div align="center">

# ROUH IPTV

**مشغل IPTV**

**ومشغل لجميع مواقع الافلام والمسلسلات بدون اعلانات**

<br>

<a href="https://github.com/wu3x/rouh-iptv-releases/releases/download/android-latest/ROUH-IPTV-Android.apk">
  <img src="https://img.shields.io/badge/DOWNLOAD-ANDROID_APK-16803D?style=for-the-badge&logo=android&logoColor=white" alt="تحميل نسخة الأندرويد" height="44">
</a>

<br>

<sub>تحميل نسخة الأندرويد</sub>

<br><br>

<a href="https://github.com/wu3x/rouh-iptv-releases/releases/download/ios-latest/ROUH-IPTV-iOS-unsigned.ipa">
  <img src="https://img.shields.io/badge/DOWNLOAD-iOS_IPA-6D28D9?style=for-the-badge&logo=apple&logoColor=white" alt="تحميل نسخة الآيفون" height="44">
</a>

<br>

<sub>تحميل نسخة الآيفون (يحتاج لتوقيع)</sub>

<br><br>

![Android](https://img.shields.io/badge/ANDROID-APK-16803D?style=flat-square&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-IPA-7C3AED?style=flat-square&logo=apple&logoColor=white)
![Releases](https://img.shields.io/badge/RELEASES-GitHub-30363D?style=flat-square&logo=github&logoColor=white)
<a href="https://www.instagram.com/wu3x/"><img src="https://img.shields.io/badge/Instagram-wu3x-E4405F?style=flat-square&logo=instagram&logoColor=white" alt="Instagram @wu3x"></a>

</div>

---

## نظرة عامة | Overview

**ROUH IPTV** تطبيق مستقل لتشغيل اشتراكات IPTV وتصفح المنصات عبر واجهة موحدة، مع إصدارات مخصصة لأجهزة Android وiOS.

### المزايا | Features

| الميزة | التفاصيل |
|:--|:--|
| IPTV | تشغيل المحتوى من الاشتراكات المتوافقة |
| المنصات والمواقع | تصنيفات للأفلام والمسلسلات والأنمي والمباريات |
| تجربة التصفح | متصفح مدمج مع تقليل الإعلانات والمفضلة |
| الاتصال | خيار فك الحجب باستخدام ByeDPI في نسخة Android |
| التحديثات | إدارة مستقلة لإصدارات Android وiOS |

## الإصدارات | Releases

| النظام | صيغة الملف | حالة التثبيت | الإصدار |
|:--|:--|:--|:--|
| Android | APK | موقّع وجاهز للتثبيت | [Android Release](https://github.com/wu3x/rouh-iptv-releases/releases/tag/android-latest) |
| iOS | IPA | يتطلب توقيعًا صالحًا | [iOS Release](https://github.com/wu3x/rouh-iptv-releases/releases/tag/ios-latest) |

روابط التحميل ثابتة، ويتم تحديث ملفات الإصدارات عند اكتمال عملية النشر. يمكن متابعة تفاصيل الإصدارات من [صفحة Releases](https://github.com/wu3x/rouh-iptv-releases/releases).

## التثبيت والتحديث | Installation

- **Android:** حمّل ملف APK وافتحه، ثم وافق على التثبيت. يمكن التحديث فوق النسخة الحالية عند تطابق اسم الحزمة والتوقيع.
- **iOS:** حمّل ملف IPA ووقّعه باستخدام طريقة تثبيت متوافقة مع جهازك.
- **التحديثات:** يتم نشر تحديثات كل نظام بصورة مستقلة.

## البنية التقنية | System Architecture

```mermaid
flowchart TD
    A[ROUH IPTV] --> B[IPTV Playback]
    A --> C[Embedded Browser]
    C --> D[Platform Catalog]
    C --> E[Request Filtering]
    D --> F[Remote JSON]
    A --> G[Update Manager]
    G --> H[GitHub Releases]
    C --> I[Android ByeDPI Engine]
```

### Architecture Layers

| Layer | Responsibility |
|:--|:--|
| Presentation | واجهة المستخدم والتصنيفات والمفضلة |
| Playback | تشغيل مصادر IPTV المتوافقة |
| Web Runtime | إدارة جلسات التصفح والتنقل بين الصفحات |
| Network | معالجة الاتصال وفلترة الطلبات في المتصفح |
| Remote Configuration | جلب قائمة المنصات والنطاقات المسموح بها |
| Distribution | إدارة ملفات الإصدارات والتحديثات |

## دورة بناء أندرويد | Android CI/CD

```mermaid
flowchart LR
    A[Source] --> B[GitHub Actions]
    B --> C[Gradle Build]
    C --> D[APK Signing]
    D --> E[Package and Signature Validation]
    E --> F[Release Asset]
    F --> G[In-app Update]
```

- **Build environment:** Windows self-hosted runner · Android SDK 35 · Gradle.
- **Native integration:** JNI libraries for ARM64, ARMv7, x86 and x86_64.
- **Release integrity:** التحقق من هوية الحزمة والتوقيع ورقم الإصدار قبل النشر.
- **Version management:** زيادة رقم بناء أندرويد تلقائيًا بالاعتماد على الإصدار المنشور.
- **Distribution channels:** مسارات نشر مستقلة لأندرويد وiOS.

### Android Technology Stack

<div align="center">

![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![Android](https://img.shields.io/badge/Android_SDK-35-3DDC84?style=flat-square&logo=android&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

</div>

<details>
<summary><b>Release contract · تفاصيل واجهة التوزيع</b></summary>

| Property | Android | iOS |
|:--|:--|:--|
| Release tag | `android-latest` | `ios-latest` |
| Artifact | `ROUH-IPTV-Android.apk` | `ROUH-IPTV-iOS-unsigned.ipa` |
| Distribution | GitHub Releases | GitHub Releases |
| Signing | Android release signature | External signing required |

</details>

## ملاحظات تقنية | Technical Notes

تُدار قائمة المنصات مركزيًا، مما يسمح بتحديث الروابط دون الحاجة إلى إصدار جديد لبعض التغييرات. قد يختلف توفر المواقع تبعًا لحالة الخدمات الخارجية والشبكة.

التطبيق لا يستضيف المحتوى المعروض، ويتحمل المستخدم مسؤولية استخدام المصادر والاشتراكات التي يملك حق الوصول إليها.

### Open Source Acknowledgements

تستخدم نسخة Android مكونات من مشروع [ByeDPIAndroid](https://github.com/dovecoteescapee/ByeDPIAndroid) المرخص بموجب GPL-3.0. يخضع توزيع المكونات والكود المصدري المقابل لشروط تراخيصها.

---

<div align="center">

**ROUH IPTV**

Android · iOS

[Releases](https://github.com/wu3x/rouh-iptv-releases/releases) · [Instagram](https://www.instagram.com/wu3x/)

<sub>© ROUH IPTV</sub>

</div>
