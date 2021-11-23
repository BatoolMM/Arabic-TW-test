(بناء r-binderhuberhub)=
# بناء BinderHub الخاص بك

[mybinder.org](https://mybinder.org/) هو BinderHub المجاني العام الذي يستضيف ما يقرب من 100 ألف بايندر في الأسبوع. لماذا تريد بناء الخاص بك؟

Binder [{term}`def<Binder>`] هو مشروع مفتوح المصدر يديره المتطوعون وعليه فإنهم يطلبون أن يبقى المستخدمون في حدود حسابية معينة من أجل الحفاظ على تكاليف التشغيل منخفضة قدر الإمكان بينما لا يزالون يقدمون خدمة قابلة للاستعمال. باستضافة BinderHub، يمكنك تقديم المزيد من الموارد المرنة والمخصصة للمستخدمين.

ويمكن أن تشمل هذه التخصيصات ما يلي:

- المصادقة،
- موارد حسابية أكبر لكل مستخدم،
- مكتبات مكتبات مكتبية وحزم
- السماح بالوصول إلى المستودع الخاص،
- تخزين مستمر للمستخدمين،
- تقييد المشاركة داخل مؤسسة معينة أو فريق معين.

## المشاكل التي قد تواجهها عند نشر BinderHub

وأصبحت مراكز بيندرهوب تحظى بشعبية متزايدة بين الجامعات ومعاهد البحوث. ويرجع ذلك إلى أنها يمكن أن تيسر حالات متعددة من نفس المجموعة من الدفاتر لاستخدامها في إعداد دروس أو حلقات عمل.

إذا كنت تنشر BinderHub الذي تستضيفه سحابة نيابة عن مؤسستك، فقد تحتاج إلى أذونات محددة في اشتراك المنصة السحابية لمؤسستك. أي الأذونات التي تحتاج إليها سوف تختلف استناداً إلى منصة السحابة التي لديك حق الوصول إليها وسياسات خدمات تكنولوجيا المعلومات الخاصة بك. على أقل تقدير، ستحتاج إلى أن تكون قادراً على تعيين [التحكم في الوصول على أساس الأدوار (RBAC)](https://docs.microsoft.com/en-us/azure/role-based-access-control/overview) إلى مواردك حتى تتمكن من التصرف بشكل مستقل من أجل إدارة حركة مرور المستخدم.