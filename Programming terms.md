# 🧠 Programming Cheat Sheet (English → Arabic)

## 1️⃣ Core Programming Concepts

| English Term              | Arabic Translation   | Notes / Context                              |
| ------------------------- | -------------------- | -------------------------------------------- |
| Algorithm                 | خوارزمية             | Step-by-step procedure to solve a problem    |
| Data Structure            | هيكل البيانات        | Array, Object, Linked List, Stack, Queue     |
| Variable                  | متغير                | Holds a value                                |
| Constant                  | ثابت                 | Immutable value                              |
| Function / Method         | دالة / طريقة         | Block of reusable code                       |
| Class                     | فئة                  | Template for objects                         |
| Object                    | كائن                 | Instance of a class                          |
| Interface                 | واجهة                | Defines structure for objects/classes        |
| Module                    | وحدة / قسم           | Group of related code                        |
| Package / Library         | مكتبة / حزمة         | Prewritten code for reuse                    |
| Dependency                | اعتماد               | One module/class relies on another           |
| Dependency Injection (DI) | حقن الاعتماديات      | Automatic provisioning of dependencies       |
| Singleton                 | مفرد / وحيد          | Single instance of a class in app lifecycle  |
| Factory                   | مصنع / منشئ          | Returns new object instances                 |
| Observer / Event Emitter  | مراقب / مرسل أحداث   | Publish/subscribe pattern                    |
| Listener                  | مستمع للأحداث        | Reacts to events                             |
| Callback                  | دالة رد نداء         | Function passed as argument to execute later |
| Promise                   | وعد / نتيجة مستقبلية | Placeholder for async result                 |
| Async / Await             | غير متزامن / انتظار  | Simplifies async code                        |
| Exception / Error         | استثناء / خطأ        | Runtime error that needs handling            |
| Try / Catch               | حاول / التقط         | Error handling blocks                        |
| Thread / Process          | خيط / عملية          | Execution unit of a program                  |
| Stack / Heap              | المكدس / الكومة      | Memory management areas                      |
| Memory Leak               | تسرب الذاكرة         | Objects not freed, wasting memory            |
| Recursion                 | استدعاء ذاتي         | Function calls itself                        |
| Iteration                 | تكرار                | Loop over data                               |

## 2️⃣ Web & Networking Concepts

| English Term | Arabic Translation | Notes / Context |
|-------------|------------------|----------------|
| HTTP Request | طلب HTTP | Client asks for a resource |
| HTTP Response | استجابة HTTP | Server replies with data |
| URL / Endpoint | رابط / نقطة نهاية | API path or resource |
| Route | مسار | URL mapped to function |
| Header | رأس الطلب | Metadata sent with request |
| Body / Payload | جسم الطلب / البيانات | Main data sent in request |
| Status Code | كود الحالة | 200, 404, 500 etc. |
| Query Parameter | معامل الاستعلام | Data passed in URL |
| Session | جلسة | Server-side user state |
| Cookie | كوكي | Client-side stored state |
| Token | رمز / توكن | Authentication identifier |
| Authentication | التوثيق | Verify identity |
| Authorization | التفويض | Permission check |
| CORS (Cross-Origin) | سياسة مشاركة الموارد عبر الأصل | Browser security for API calls |
| REST API | واجهة برمجة تطبيقات REST | Resource-based API style |
| GraphQL | واجهة برمجة تطبيقات GraphQL | Query-based API style |

## 3️⃣ Database Concepts

| English Term | Arabic Translation | Notes / Context |
|-------------|------------------|----------------|
| Database | قاعدة بيانات | Structured data storage |
| Table / Collection | جدول / مجموعة | Stores records / documents |
| Column / Field | عمود / حقل | Attribute in record |
| Row / Record | صف / سجل | One data entry |
| Schema | مخطط / نموذج بيانات | Defines structure of database |
| Primary Key | المفتاح الأساسي | Unique identifier for a row |
| Foreign Key | المفتاح الأجنبي | Links to primary key of another table |
| Index | فهرس | Optimizes query lookup |
| Query | استعلام | Request for data |
| Join | دمج / ربط | Combine tables based on relation |
| Transaction | معاملة / عملية | Atomic group of operations |
| Rollback | التراجع | Undo operations in case of error |
| Migration | ترحيل / تحديث قاعدة البيانات | Schema evolution scripts |
| Seed | تهيئة بيانات / إدخال بيانات أولية | Preload initial data |
| ORM (Object-Relational Mapping) | خرائط الكائنات لعلاقات البيانات | Maps classes to tables |
| CRUD | إنشاء، قراءة، تحديث، حذف | Basic database operations |

## 4️⃣ Async / Event-Driven Concepts

| English Term | Arabic Translation | Notes / Context |
|-------------|------------------|----------------|
| Event Loop | حلقة الأحداث | Node.js mechanism for async tasks |
| Callback | دالة رد نداء | Function executed after another completes |
| Promise | وعد / نتيجة مستقبلية | Placeholder for future value |
| Async / Await | غير متزامن / انتظار | Syntactic sugar for promises |
| Observable / Stream | تدفق بيانات / مراقب | Continuous data flow |
| Subscription | اشتراك | Listening to observable events |
| Throttle | تنظيم | Limit function execution rate |
| Debounce | تأخير / تجنب التكرار | Delay execution until stable input |
| Queue | قائمة انتظار | Ordered tasks waiting execution |
| Pub/Sub | نشر/اشتراك | Publish/subscribe message pattern |

## 5️⃣ Design Patterns & Architecture

| English Term | Arabic Translation | Notes / Context |
|-------------|------------------|----------------|
| Singleton | مفرد / وحيد | Single instance |
| Factory | مصنع / منشئ | Object creation helper |
| Observer | مراقب / مستمع | Event-driven communication |
| Repository | مستودع | Abstract DB access layer |
| MVC (Model-View-Controller) | نموذج-عرض-تحكم | Separates presentation, logic, data |
| Layered Architecture | هيكل متعدد الطبقات | Presentation, business, data layers |
| Service | خدمة / طبقة خدمة | Handles business logic |
| Dependency Injection | حقن الاعتماديات | Decouples object creation |
| DTO (Data Transfer Object) | كائن نقل البيانات | Defines data for transport between layers |
| Adapter | محول / موائم | Converts interface to match another |
| Decorator | مُزيّن / تعديل | Wraps object/class with extra behavior |
| Middleware | وسيط / طبقة وسيطة | Pre/post-process requests |
| Interceptor | معترض / لاعتراض | Modify data in/out in framework |
| Guard | حارس | Authorization enforcement |
| Exception / Error Handling | معالجة الأخطاء / الاستثناءات | Global or scoped error handling |

## 6️⃣ Utilities / Common Programming Terms

| English Term                | Arabic Translation         | Notes / Context                                |
| --------------------------- | -------------------------- | ---------------------------------------------- |
| Logger / Console            | مسجل / وحدة تسجيل          | Logs messages/errors                           |
| Config / Environment Var    | إعدادات / متغير بيئة       | App configuration                              |
| Serialization               | تسلسل البيانات             | Convert objects to JSON or transferable format |
| Deserialization             | فك التسلسل                 | Convert back from JSON to objects              |
| Transformation              | تحويل                      | Change type/format of input/output             |
| Validation                  | التحقق من الصحة            | Check correctness of input                     |
| Regex / Regular Expression  | التعبيرات النمطية          | Pattern matching in strings                    |
| Cache                       | ذاكرة مؤقتة                | Temporary data storage                         |
| Retry                       | إعادة المحاولة             | Attempt operation again                        |
| Rate Limit                  | تحديد المعدل               | Limit number of requests in period             |
| Encryption / Decryption     | تشفير / فك تشفير           | Secure data                                    |
| Hash / Hashing              | هاش / تجزئة                | One-way data encoding                          |
| Compression / Decompression | ضغط / فك الضغط             | Reduce data size                               |
| Serialization / DTO mapping | تسلسل البيانات / تحويل DTO | Format data for transfer                       |