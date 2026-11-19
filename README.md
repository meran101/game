# لعبة التلوين (جماعية) - دليل الإعداد الكامل

الملفات: `index.html` (اللعبة) + `firebase-rules.json` (قواعد قاعدة البيانات) + هذا الملف.

## أولاً: إنشاء Firebase (مجاني، بدون بطاقة بنكية)
1. افتح https://console.firebase.google.com وسجّل الدخول بحساب Google.
2. اضغط **Create a project** (أو Add project) واكتب اسماً، مثل `coloring-game`، ثم Continue.
3. عطّل **Google Analytics** (غير مطلوب) ثم **Create project**، وانتظر ثم Continue.
4. من القائمة اليسرى: **Build ← Realtime Database** ثم **Create Database**.
5. اختر أي موقع للخادم (الأقرب لك أسرع)، ثم Next.
6. اختر **Start in test mode** ثم **Enable**.
7. ستظهر صفحة **Data**، وفي أعلاها رابط قاعدة البيانات، انسخه.
   شكله: `https://coloring-game-default-rtdb.firebaseio.com`
   أو: `https://coloring-game-default-rtdb.europe-west1.firebasedatabase.app`
   (كلاهما صحيح، انسخه كما يظهر لك).

## ثانياً: القواعد (مهم لتبقى اللعبة تعمل)
قواعد test mode تنتهي بعد 30 يوماً ثم تتوقف اللعبة، لذلك استبدلها الآن:
1. افتح تبويب **Rules** داخل Realtime Database.
2. احذف كل ما فيه والصق: `{"rules":{".read":true,".write":true}}`
3. اضغط **Publish**.

## ثالثاً: رفع اللعبة على GitHub
1. https://github.com ← **New repository** ← اسم مثل `coloring-game` ← Public ← Create.
2. **uploading an existing file** ← اسحب `index.html` ← **Commit changes**.
3. **Settings ← Pages ← Deploy from a branch ← main ← /(root) ← Save**.
4. بعد 1-2 دقيقة يظهر الرابط: `https://اسمك.github.io/coloring-game/`

## رابعاً: ربط اللعبة وبدء اللعب
1. افتح رابط اللعبة، والصق رابط Firebase في الخانة، ثم **حفظ**.
2. اضغط **نسخ رابط الدعوة** وأرسله لأصدقائك (يحمل الإعداد معه).
3. اتفقوا على رمز غرفة واحد، واكتبوه مع الاسم، ثم **ابدأ**.

## ملاحظات
- لا تنشر رابط Firebase علناً، لأن أي شخص يملكه يستطيع الكتابة في القاعدة.
- لحذف النقاط: Realtime Database ← Data ← مرّر المؤشر على `rooms` ← الحذف.
- الحد المجاني (1GB تخزين و100 اتصال متزامن) يكفي لعبتكم بكثير.
