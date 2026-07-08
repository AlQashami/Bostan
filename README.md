# 🌳 بستان

تطبيق ويب شخصي لمتابعة القراءة والمعرفة — يشمل فهرس المكتبة، سجل القراءة، قاعدة المعرفة، الاقتباسات، المفردات، المشاريع، والهوية الشخصية.

## التقنيات
- HTML/CSS/JS (بدون أي إطار عمل خارجي)
- Firebase Authentication (تسجيل دخول بالبريد الإلكتروني)
- Firebase Firestore (تخزين البيانات سحابيًا)

## النشر
هذا المستودع منشور مباشرة عبر GitHub Pages من الفرع `main`.

## قواعد أمان Firestore المطلوبة
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /bustan_users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```
