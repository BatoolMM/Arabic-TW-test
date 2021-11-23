(rr-vcs-git)=
# البدء مع Git

للبدء، يرجى التأكد من تثبيت Git على جهاز الكمبيوتر الخاص بك. التعليمات لتثبيت Git على لينكس و ويندوز و ماك آلات متوفرة [هنا](https://Git-scm.com/book/en/v2/Getting-Started-Installing-Git). بمجرد اكتمال التثبيت، انتقل إلى دليل المشروع الخاص بك عبر واجهة المحطة الطرفية أو سطر الأوامر (على سبيل المثال، `cd my-project-folder`). يحتوي مجلد المشروع الخاص بك على جميع ملفاتك، بما في ذلك الدلائل الفرعية.

عند العمل على مشروع ، ستجري العديد من التغييرات على ملفاتك أثناء تقدمك. قد تحتاج أحيانا إلى التراجع عن التغييرات، أو إلقاء نظرة أخرى على الإصدارات السابقة، أو مقارنة الإصدارات السابقة. حفظ كل نسخة منفردة (مثل `version_1.py` و `الإصدار_2.py`هو أمر فوضوي ويصبح بسرعة غير عملي.

وتعمل الالتزامات كنقاط تفتيش حيث يمكن العودة بأمان إلى ملفات فردية أو إلى مشروع كامل عند الضرورة. من خلال الدخول في التزامات، يمكنك حفظ إصدارات التعليمات البرمجية الخاصة بك والتبديل بينهم/مقارنتهم بسهولة دون الاستحواذ على الدليل الخاص بك.

للبدء مع مستودع Git الخاص بك، قم بتشغيل أمر Git التالي في المحطة الطرفية لإنشاء / تهيئة مستودع Git الخاص بك:

```
git init
```

ولا يلزم القيام بذلك إلا مرة واحدة لكل مشروع.

فكر في المستودع كمكان يتم فيه تخزين التاريخ. عندما تقوم بتهيئة مستودع باستخدام `git init`، لن تتم إضافة جميع الملفات في مشروعك إلى مستودع Git حيث أنها غير متبوعة بواسطة Git بشكل افتراضي. لذلك، الخطوة التالية هي إضافة ملفاتك إلى مستودع Git والسماح Git بتعقبها.

قم بتشغيل الأمر التالي لإضافة جميع الملفات في المجلد الحالي:
```
git يضاف
```
أو قم بتشغيل الأمر التالي لإضافة الملفات فقط ('your_file_name' في هذا المثال:
```
git أضف ملف_اسمك
```

هذا الأمر يضع ملفاتك المضافة حديثا أو أي تغييرات أخرى في ما يسمى حالة "التجهيز".

```{figure} ../../figures/change-stage-repo.png
---
name: change-stage-repo
البديل : مثال توضيحي لـ `git add` و git يلتزمان بالأمرين.
---
كيف 'git إضافة' و 'git commit' يعملان
```

إذا كنت غير متأكد من الملفات التي تمت إضافتها، فما هي الملفات التي تم تغييرها، أو ما هي الملفات التي لم يتم تعقبها، يمكنك تشغيل ما يلي لمعرفة ذلك:

```
git status
```

الخطوة التالية هي "التزام" بأي تغييرات مخزنة في منطقة التجهيز الخاصة بك بحيث يتم تسجيلها في المستودع الخاص بك.

```
التزام git
```
تهانينا، لقد انتهت من إعداد المستودع الخاص بك!

سوف تتعلم المزيد عن `git الالتزام` في الفصل التالي.