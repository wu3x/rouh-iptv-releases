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

<a href="https://github.com/wu3x/rouh-iptv-releases/releases/download/windows-latest/ROUH-IPTV-Windows-Setup.exe">
  <img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS_EXE-2563EB?style=for-the-badge&logo=windows&logoColor=white" alt="تحميل نسخة الويندوز" height="44">
</a>

<br>

<sub>تحميل نسخة الويندوز (تجريبية)</sub>

<br>

<sub>قد يظهر تحذير Windows SmartScreen لأن النسخة تجريبية وغير موقعة لويندوز.<br>إذا تأكدت من مصدر الملف، اضغط «مزيد من المعلومات» ثم «التشغيل على أي حال» وأكمل التثبيت.</sub>

<br><br>

![Android](https://img.shields.io/badge/ANDROID-APK-16803D?style=flat-square&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-IPA-7C3AED?style=flat-square&logo=apple&logoColor=white)
![Releases](https://img.shields.io/badge/RELEASES-GitHub-30363D?style=flat-square&logo=github&logoColor=white)
<a href="https://www.instagram.com/wu3x/"><img src="https://img.shields.io/badge/Instagram-wu3x-E4405F?style=flat-square&logo=instagram&logoColor=white" alt="Instagram @wu3x"></a>

</div>

---

## البنية التقنية | System Architecture

<sub>APPLICATION CORE · WEB RUNTIME · REMOTE CONFIGURATION · RELEASE DISTRIBUTION</sub>

```mermaid
flowchart TB
    U["ROUH IPTV"]
    subgraph APP["Application Layer"]
        UI["User Interface"]
        IPTV["IPTV Playback"]
        WEB["Embedded Browser"]
        UPD["Update Manager"]
        UI --> IPTV
        UI --> WEB
        UI --> UPD
    end
    subgraph NET["Android Web Runtime"]
        NAV["Navigation & Session"]
        FILTER["Request Filtering"]
        DPI["ByeDPI · JNI"]
        NAV --> FILTER
        NAV --> DPI
    end
    subgraph REMOTE["Remote Services"]
        JSON["Platform Catalog · JSON"]
        REL["GitHub Releases"]
        EXT["External Content Sources"]
    end
    U --> UI
    WEB --> NAV
    WEB --> JSON
    FILTER --> EXT
    DPI --> EXT
    IPTV --> EXT
    UPD --> REL
    classDef core fill:#26354a,stroke:#7895bd,color:#ffffff
    classDef network fill:#24443d,stroke:#69b69d,color:#ffffff
    classDef remote fill:#423454,stroke:#a58ac9,color:#ffffff
    class U,UI,IPTV,WEB,UPD core
    class NAV,FILTER,DPI network
    class JSON,REL,EXT remote
```

### Architecture Layers

| Layer | Responsibility |
|:--|:--|
| Presentation | واجهة المستخدم والتصنيفات والمفضلة |
| Playback | تشغيل مصادر IPTV المتوافقة |
| Web Runtime | إدارة التنقل وجلسات التصفح |
| Network | فلترة الطلبات ومحرك ByeDPI في أندرويد |
| Remote Configuration | إدارة قائمة المنصات والنطاقات من مصدر مركزي |
| Distribution | إدارة ملفات الإصدارات والتحديثات المستقلة |

### Remote Configuration Flow

```mermaid
sequenceDiagram
    participant A as Android App
    participant C as Local Catalog Cache
    participant R as Remote JSON
    participant W as WebView
    A->>C: Read cached catalog
    A->>R: Fetch current catalog
    alt Fetch successful
        R-->>A: Platforms and allowed domains
        A->>C: Update local cache
    else Network error
        A->>C: Use available cached data
    end
    A->>W: Open selected platform
    W->>W: Apply navigation and request rules
```

<sub>المخططات تمثل البنية المنطقية للمشروع، مع تفاصيل محرك الشبكة وإدارة القائمة الخاصة بنسخة Android.</sub>

---

## نظرة عامة | Overview

**ROUH IPTV** تطبيق مستقل لتشغيل اشتراكات IPTV وتصفح المنصات عبر واجهة موحدة، مع إصدارات لأجهزة Android وiOS وWindows (نسخة الويندوز لتصفح المواقع فقط).

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

| Windows | EXE | نسخة تجريبية | [Windows Release](https://github.com/wu3x/rouh-iptv-releases/releases/tag/windows-latest) |

روابط التحميل ثابتة، ويتم تحديث ملفات الإصدارات عند اكتمال عملية النشر. يمكن متابعة تفاصيل الإصدارات من [صفحة Releases](https://github.com/wu3x/rouh-iptv-releases/releases).

## التثبيت والتحديث | Installation

- **Android:** حمّل ملف APK وافتحه، ثم وافق على التثبيت. يمكن التحديث فوق النسخة الحالية عند تطابق اسم الحزمة والتوقيع.
- **iOS:** حمّل ملف IPA ووقّعه باستخدام طريقة تثبيت متوافقة مع جهازك.
- **التحديثات:** يتم نشر تحديثات كل نظام بصورة مستقلة.

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

Android · iOS · Windows

[Releases](https://github.com/wu3x/rouh-iptv-releases/releases) · [Instagram](https://www.instagram.com/wu3x/)

<sub>© ROUH IPTV</sub>

</div>
