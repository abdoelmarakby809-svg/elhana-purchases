# نظام إدارة المشتريات – الهنا اليكتريك

موقع ثابت على GitHub Pages، وقاعدة البيانات على Firebase Firestore (مجاني). الدخول بإيميل وكلمة مرور.

## 1) إنشاء قاعدة البيانات (Firebase)
1. ادخل https://console.firebase.google.com واعمل Add project (بدون Analytics).
2. من Project settings > Your apps اضغط أيقونة الويب `</>` وسجّل التطبيق، وانسخ قيم `firebaseConfig` والصقها في ملف `firebase-config.js`.
3. Build > Authentication > Get started > Sign-in method > فعّل Email/Password.
4. Authentication > Users > Add user: أضف إيميل وكلمة مرور لكل موظف.
5. Authentication > Settings > User actions: ألغِ تفعيل Enable create (sign-up) حتى لا يستطيع غريب إنشاء حساب.
6. Build > Firestore Database > Create database (اختر Production mode)، ثم تبويب Rules والصق محتوى `firestore.rules` واضغط Publish.

## 2) الرفع على GitHub
1. اعمل repository جديد على GitHub، وارفع كل ملفات المجلد (index.html و logo.png و firebase-config.js و firestore.rules و README.md).
2. Settings > Pages > Source: Deploy from a branch > main / root > Save.
3. بعد دقيقة هيظهر الرابط: `https://USERNAME.github.io/REPO/`.
4. في Firebase: Authentication > Settings > Authorized domains > Add domain وأضف `USERNAME.github.io`.

## ملاحظات
- مفاتيح firebaseConfig ليست سرية، الحماية من تسجيل الدخول وقواعد Firestore. لا ترفع على GitHub أي ملفات بيانات.
- الخطة المجانية (Spark) تكفي استخدام شركة صغيرة ومتوسطة.
- لعمل نسخة احتياطية: Firestore > Export (أو سجّل بياناتك دوريًا).
