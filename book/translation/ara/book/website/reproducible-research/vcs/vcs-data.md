(rr-vcs-data)=
# التحكم في الإصدار للبيانات

وناقشنا أن النسخة التي تتحكم في مكونات المشاريع المتطورة يمكن أن تساعد على جعل العمل أكثر تنظيما، وكفاءة، وتعاضدية، وقابلة للتكرار. غير أن العديد من المشاريع العلمية لا تحتوي فقط على رموز أو مخطوطات أو ملفات أخرى صغيرة الحجم. ويحتوي العديد من المشاريع على ملفات أكبر مثل البيانات (المدخلات) أو نتائج التحليل. التي يمكن أن تتغير أو يتم تحديثها في مشروع تماما مثل المكونات الأخرى مثل الكود والمخطوطات. ويمكن لجانب قابلية التكرار في مشروع علمي أن يتحسن كثيرا إذا استطعنا تتبع المجموعة الفرعية أو النسخة الفرعية من البيانات التي يستند إليها تحليل أو نتيجة معينة.

(r-vcs-data-aluance)=
## أهمية بيانات التحكم في الإصدار

وينبغي ألا نعتبر أن البيانات المستخدمة في التحليل هي بيانات جامدة؛ وحالما يتم الحصول عليها، فإنها لا تتغير وتشكل مدخلا لتحليل معين ولعماد نتائجنا العلمية. والحقيقة هي أن البيانات نادرا ما تكون ثابتة. فعلى سبيل المثال، يمكن خلال أي مشروع علمي توسيع نطاق مجموعات البيانات بإضافة بيانات جديدة تكييفها مع مخططات التسمية الجديدة، تمت إعادة تنظيمه في تسلسل هرمي مختلف للملفات، تم تحديثه بنقاط بيانات جديدة أو تم تعديله لإصلاح أي أخطاء.

وهذه العمليات الدينامية ممتازة ومفيدة للعلم لأنها تكفل أن تكون البيانات قابلة للاستخدام ومستكملة. لكنها قد تكون مربكة إذا لم تكن موثقة توثيقاً كافياً . إذا تغيرت مجموعة بيانات تشكل أساس حساب نتيجة علمية دون التحكم في الإصدار، يمكن تهديد إمكانية التكرار: النتائج قد تصبح غير صالحة، أو البرامج النصية التي تستند إلى أسماء الملفات التي يمكن أن تتغير بين الإصدارات أن تنقطع. ولا سيما إذا استعيض عن البيانات الأصلية ببيانات جديدة دون وجود أي تحكم في الإصدار، فقد لا تستنسخ النتائج الأصلية للتحليل. ولذلك، إصدار التحكم في البيانات والملفات الكبيرة الأخرى بطريقة مشابهة لنسخة التحكم في التعليمات البرمجية أو المخطوطات يمكن أن تساعد على ضمان قابلية المشروع للاستنساخ والتقاط مصدر النتائج؛ القبعة هي "المجموعة الفرعية الدقيقة وإصدار البيانات مجموعة نتيجة منشأ من". وإلى جانب جميع العناصر الأخرى لمشروع البحوث، تشكل البيانات المحددة في نسخ دقيقة جزءا من نتائج البحوث.

```{figure} ../../figures/provenance.jpg
---
الطول: 500px
الاسم: المصدر
بديل: Provenance أي البيانات التي تحتوي على الإصدار الذي يعتبر الحساب حاسما بالنسبة للقابلية للتكاثر.
---
بروانس أي بيانات كان الإصدار الأساس للحساب الذي هو أمر حاسم لإمكانية التكرار.
_توضيح مشروع طريق التورين_ من سكريبيريا. يستخدم بموجب ترخيص CC-BY 4.0. DOI: [10.5281/zenodo.3332807] (https://doi.org/10.5281/zenodo.3332807).
```

(rr-vcs-data-challenges)=
## التحديات في التحكم في الإصدار

وتبعا لحجم البيانات والتعديلات التي تدخل عليها، قد لا تكون أدوات التحكم في الإصدارات مثل Git مناسبة للبيانات. ما دامت الملفات للتحكم في الإصدار صغيرة الحجم ويمكن تخزينها في بعض الملفات `csv` أو الملفات المنفصلة بين الأحرف، الأدوات مثل [Git](https://git-scm.com/) مناسبة.

عندما تعمل وتشارك وتتعاون على ملفات كبيرة محتملة [ثنائية](https://en.wikipedia.org/wiki/Binary_file) (مثل العديد من صيغ البيانات العلمية)، تحتاج إلى التفكير في طرق التحكم في هذه البيانات باستخدام أدوات متخصصة. ويرجع ذلك إلى أن معظم أدوات التحكم في الإصدارات - مثل Git - ليست ملائمة تماماً للتعامل مع البيانات الثنائية الكبيرة. كمستودع Git يخزن كل نسخة من كل ملف أضيف إليه، الملفات الكبيرة التي تخضع لتعديلات منتظمة يمكن أن تضخّم حجم المشروع بشكل كبير. إذا حاول الآخرون استنساخ مستودعك أو إحضار / سحب لتحديثه محلياً، سيستغرق القيام بذلك وقتا أطول إذا كان يحتوي على ملفات أكبر تم إصدارها وتعديلها.

ما هو غير مريح بشكل خاص هو أن خدمات استضافة المستودعات مثل GitHub تفرض الحد الأقصى لحجم الملفات على المستخدمين (على الأقل في إصداراتهم المجانية). على سبيل المثال، إذا تجاوز ملف واحد في مستودعك 100 ميغابايت، فلن تتمكن من دفع هذا الملف إلى مستودع GitHub . وعلاوة على ذلك، إذا أضيف ملف كبير عن طريق الخطأ إلى المستودع، إزالة الملف من المستودع يمكن أن تكون مملة، لأن هذا الملف يحتاج إلى [تطهير](https://help.github.com/en/github/authenticating-to-github/removing-sensitive-data-from-a-repository). يمكن أن تجعل أوجه القصور هذه الإصدار التحكم في الملفات مملة وبطيئة، وتعوق التعاون على المستودعات ذات البيانات الكبيرة. ومنع البيانات أو المشاريع ذات البيانات من المشاركة على منصات مثل GitHub.

(rr-vcs-data-tools) =
## أدوات بيانات التحكم في الإصدار

العديد من الأدوات متاحة للتعامل مع التحكم في الإصدار ومشاركة الملفات الكبيرة. معظمها يندمج بشكل جيد جدا مع Git ويوسع نطاق قدرات المستودع للتحكم في الملفات الكبيرة. مع هذه الأدوات، يمكن إضافة بيانات كبيرة إلى المستودع، يتم التحكم في الإصدار، ثم الرجوع إلى الحالات السابقة، أو تم تحديثها وتعديلها بشكل تعاوني، وحتى مشاركتها عبر GitHub كملفات صغيرة الحجم. وتشمل بعض هذه الأدوات ما يلي:

(rr-vcs-data--tools-lfs)=
### Git LFS

[Git LFS](https://git-lfs.github.com/) يأتي مع امتداد سطر الأوامر إلى Git ويسمح لك بمعالجة الملفات من أي حجم على حد سواء، باستخدام أوامر Git القياسية. غير أن أحد العيوب الرئيسية هو أن Git LFS هو حل _مركزي_ الملفات الكبيرة لا يتم توزيعها ولكن يتم تخزينها على خادم بعيد. ويتطلب هذا عادة إعداد الخادم الخاص بك أو دفع ثمن خدمة - مما قد يجعلها غير قابلة للوصول إلى هذه الخدمة.

(rr-vcs-data-tools-gitannex)=
### `git-annex`

أداة [`git-annex`](https://git-annex.branchable.com/) هي نظام موزع يمكنه إدارة ومشاركة ملفات كبيرة مستقلة عن خدمة مركزية أو خادم. `git-annex` manages all file _content_ in a separate directory in the repository (`.git/annex/objects`, the so-called _annex_) and only places file _names_ with some metadata into version control by Git. عندما يتم دفع مستودع Git مع مرفق إلى خدمة استضافة ويب مثل GitHub، لا يتم تحميل المحتويات المخزنة في المرفق. وبدلا من ذلك، يمكن دفعهم إلى نظام تخزين (مثل خادوم شبكة الويب)، ولكن أيضا خدمات الطرف الثالث مثل Dropbox, Google Drive, Amazon S3, box. أم، و [أكثر من ذلك بكثير](https://git-annex.branchable.com/special_remotes/)). إذا تم استنساخ مستودع مع مرفق، لن يحتوي الاستنساخ على _محتويات_ من جميع الملفات المرفقة بشكل افتراضي، ولكن عرض أسماء الملفات فقط. وهذا يجعل المستودع صغيرا، حتى لو تعقب مئات الجيغابايت من البيانات، والاستنساخ بسرعة. أثناء تخزين محتويات الملفات في واحد أو أكثر من حلول تخزين خارجية مجانية أو تجارية. بناء على الطلب، يمكن الحصول على أي محتوى للملف باستخدام `git-annex الحصول على` أمر من وحدة تخزين الملفات الخارجية.

(rr-vcs-data-tools-datalad)=
### البيانات

[البيانات](https://www.datalad.org/)، يبني على Git و git-annex . مثل `git-annex`، فهو يسمح لك بالتحكم في البيانات ومشاركتها عبر موفري أطراف ثالثة ولكن يبسط هذه الوظيفة ويوسع نطاقها. بالإضافة إلى تبادل الملفات الكبيرة ومراقبتها؛ وهو يسمح بتسجيل وتبادل واستخدام بيئات البرمجيات، وتسجيل الأوامر أو تحليلات البيانات وإعادة تنفيذها، والعمل بسلاسة عبر تسلسل هرمي للمستودعات.