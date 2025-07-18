# A09:2021 – فشل عملية تسجيل الاحداث والمراقبة 

## العوامل

| ربطها مع CWEs | الحد الأقصى للحدوث | متوسط معدل الحدوث | التغطية القصوى | متوسط معدل التغطية | متوسط استغلال الثغرات | متوسط التأثير | إجمالي التكرار | إجمالي نقاط الضعف CVEs |
|---------------|--------------------|-------------------|----------------|--------------------|-----------------------|---------------|----------------|------------------------|
| 4             | 19.23%             | 6.51%             | 53.67%         | 39.97%             | 6.87                  | 4.99          | 53,615         | 242                    |



## نظرة عامة

شهد " فشل في تسجيل السجلات الأمنية والمراقبة " ارتفاع بسيط من المرتبة العاشرة في أعلى عشرة مخاطر لعام 2017 إلى المرتبة التاسعة في الاستطلاع الذي تم إجراؤه في قطاع أمن التطبيقات. حيث يُشكّل " فشل في تسجيل السجلات الأمنية والمراقبة " تحدّيًا لإيجاد طريقة لاختباره، غالبًا ما يتطلّب ‏مقابلات أو استفسارات ما إذا كانت الهجمات تم اكتشافها أثناء عمليات اختبار الاختراق. ومع ذلك لا يوجد لهذا التصنيف الكثير من البيانات في قاعدة البيانات CVE/CVSS,، ولكن عمليات الاكتشاف والرصد والاستجابة لهذا التصنيف أمر في غاية الأهمية.    و يمكن أن يكون مؤثرًا على عدم فعاليّة المراقبة للأحداث وعلى الانتباه للإنذارات والتي قد تُسبّب الحوادث، أو عدم وجود أدلة كافية عند القيام بالتحاليل الجنائية وهذا التصنيف يرتبط بـ
 CWE-778 وكذلك CWE-117 و CWE-223 و CWE-532.



## الوصف 

عند العودة إلى أعلى عشرة مخاطر لعام 2021، نجد أن هذا التصنيف يقوم بالمساعدة على رصد واكتشاف واستجابة الثغرات النشِطة أو لعمليات الاختراق التي تحدث، ومن غير عملية تسجيل الأحداث ومراقبتها، لن تستطيع اكتشاف ورصد أو حتى الاستجابة للاختراقات، لذلك وجود عملية تسجيل الأحداث ومراقبتها يساعد على الاستجابة في الوقت المناسب:

-  الأحداث القابلة لإجراءات التدقيق والمتابعة، مثل عمليات تسجيل الدخول الفاشلة وكذلك عمليات النقل للملفات ذات الأحجام العالية التي لم يتم تسجيلها.

-   التنبيهات والإنذارات التي لم يتم تسجيلها أو يتم تسجيلها من دون وصف واضح.

-   لا يتم متابعة وتسجيل الأحداث ومراقبتها للتطبيقات أو واجهة برمجة التطبيقات API أي أنشطة ضارّة.

-   يتم تخزين سجلات الأحداث محلّيًا فقط 

-   وضع معايير مناسبة للتنبيهات الأمنية مثل (حد عمليات تسجيل الدخول) ، وكذلك إيجاد سياسة واضحة لعملية تصعيد التنبيهات الأمنية والعمل عليها بالشكل الصحيح.

-   عدم وجود أي إنذارات عند إجراء اختبارات الاختراق أو الفحص بواسطة أداة DAST مثل OWASP ZAP  

-   التطبيقات لا تستطيع اكتشاف أو  التنبيه عند وجود أنشطة ضارّة تحدث في الوقت الحالي.

أنت مُعرّض لتسريب البيانات والمعلومات في حال عدم ضبط عملية تسجيل الأحداث والتنبيهات بالشكل الصحيح والتي قد تسمح للمستخدم أو حتى المهاجم من مشاهدتها انظر إلى (A02- تخطّي صلاحيات الوصول.)


## كيفية الحماية منها 

يجب على المطوّرين تطبيق بعض أو كل عناصر التحكّم التالية والتي تعتمد على مدى استهداف وارتفاع المخاطر التي تستهدف التطبيق:

-   يجب التأكد من أن جميع عمليات الدخول، التحكم بالوصول والمدخلات التي تحدث على جانب الخادم مسجّلة بطريقة صحيحة وواضحة، وذلك لكشف العمليات الضارّة التي تساعدك فيما بعد في عملية التحليل الجنائي الرقمي

-   التأكد أن عمليات تسجيل الأحداث تتم بشكل منسّق وصحيح وذلك لكي يتم إدارتها بشكل صحيح.

-   التأكد من أن البيانات مشفّرة بالشكل الصحيح وذلك للحماية من عمليات الحقن أو الهجمات التي قد تحدث على أنظمة المراقبة

-   التأكد من أن عمليات نقل البيانات الحساسة تتم مراقبتها والتأكد من سلامتها، وذلك للتأكد من عدم تعرّضها لتخريب أو تلاعب أو أي حذف.

-   يجب أن يكون لدى فريق DevSecOps آلية فعّالة لعملية المراقبة والتي تقوم بعملية الاكتشاف والاستجابة للتنبيهات، مثل الأنشطة الضارّة. ومن أهم المرتكزات هي سرعة الاكتشاف والاستجابة لها.

-  قم بإيجاد خطة للاستجابة للحوادث السيبرانية وتستطيع الاعتماد على NIST 800-61r2 أو النسخ الأحدث إن توفّرت.

هناك تطبيقات وإطارات مفتوحة المصدر وتجارية مثل (OWASP ModSecurity Core Rule Set,، Open-Source Log) وهنا كذلك منصّات تقوم بعملية جمع وربط سجلات الأحداث مثل منصّة ELK Stack والتي تُتيح لك مميزات إضافية منها لوح للمراقبة وكذلك تنبيهات.


##  أمثلة على سيناريوهات الهجوم

**سيناريو #1:** ‎المشغّل لموقع تابع لشركة تؤمّن خطط التأمين الطبي للأطفال لم يتمكن من اكتشاف ثغرة امنية لعدم توفر أدوات تسجيل الاحداث الأمنية ومراقبتها. حيث قام أحد الأطراف الخارجية بإبلاغ شركة التأمين الطبي عن وجود هجمة سيبرانية تضمنت الدخول والتعديل على آلاف السجلات الصحية لأكثر من 3.5 مليون طفل. وفي التقرير المعدّ بعد الهجمة وُجِد أن مطوّري موقع الويب أهملوا نقاط ضعف امنية مهمّة. ولعدم وجود أدوات تسجيل الاحدث الأمنية ومراقبتها، قد يكون تسريب البيانات قد حدث من بداية عام 2013 وامتد الى أكثر من 7 سنوات.

**سيناريو #2:** ‎ واجهت شركة طيران هندية كبرى تسريب بيانات يضم بيانات جُمعت لأكثر من عشر سنوات لمعلومات مسافريها الشخصية مما يتضمن بيانات الجوازات والبطاقات البنكية. تسريب البيانات حدث في خدمة تخزين سحابية من موفّر خدمات سحابية والذي قام بدوره بتنبيه شركة الطيران بوجود التسريب بعد مدة.

**سيناريو #3:** ‎عانت شركة طيران أوروبية كبرى من تسريب ضمن لائحة النظام العام لحماية البيانات (GDPR). وقد عُلم أن التسريب حدث بسبب ثغرات في نظام الدفع تم استغلالها من قبل منفذي الهجوم والذين جمعوا سجلات الدفع لأكثر من 400,000 عميل. نتيجة لذلك، قام مشرّع الخصوصية بتغريم شركة الطيران 20  مليون باوند.

## المصادر

-   [OWASP Proactive Controls: Implement Logging and Monitoring](https://top10proactive.owasp.org/archive/2024/the-top-10/c9-security-logging-and-monitoring/)

-   [OWASP Application Security Verification Standard: V8 Logging and Monitoring](https://owasp.org/www-project-application-security-verification-standard)

-   [OWASP Testing Guide: Testing for Detailed Error Code](https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/08-Testing_for_Error_Handling/01-Testing_for_Error_Code)

-   [OWASP Cheat Sheet: Application Logging Vocabulary](https://cheatsheetseries.owasp.org/cheatsheets/Application_Logging_Vocabulary_Cheat_Sheet.html)

-   [OWASP Cheat Sheet: Logging](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html))   

-   [Data Integrity: Recovering from Ransomware and Other Destructive Events](https://csrc.nist.gov/publications/detail/sp/1800-11/final)

-   [Data Integrity: Identifying and Protecting Assets Against Ransomware and Other Destructive Events](https://csrc.nist.gov/publications/detail/sp/1800-25/final)

-   [Data Integrity: Detecting and Responding to Ransomware and Other Destructive Events](https://csrc.nist.gov/publications/detail/sp/1800-26/final)


## قائمة الربط مع إطار CWEs

[CWE-117 Improper Output Neutralization for Logs](https://cwe.mitre.org/data/definitions/117.html)

[CWE-223 Omission of Security-relevant Information](https://cwe.mitre.org/data/definitions/223.html)

[CWE-532 Insertion of Sensitive Information into Log File](https://cwe.mitre.org/data/definitions/532.html)

[CWE-778 Insufficient Logging](https://cwe.mitre.org/data/definitions/778.html)

