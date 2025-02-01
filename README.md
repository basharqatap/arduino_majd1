
هنا جميع تفاصيل كل مايتعلق بالملفات اعلاه وبحسب اسم كل ملف:


example1 == HelloWokwi 

يهدف هذا المثال إلى اختبار القدرة على التحكم في تشغيل وإيقاف LED باستخدام كود برمجي على ميكروكنترولر مثل Arduino. الفكرة الرئيسية هي جعل LED يومض بمعدل مرتين في الثانية، أي أنه يضيء وينطفئ كل 500 مللي ثانية. يتم ذلك عبر تغيير حالة الدبوس المتصل بالـ LED بين التشغيل (HIGH) والإيقاف (LOW) مع استخدام تأخير زمني مناسب (delay).

Code:

void setup() {

pinMode(13, OUTPUT); }

void loop() {

digitalWrite(13, HIGH); delay(500);

digitalWrite(13, LOW); delay(500);

digitalWrite(13, HIGH); delay(500);

digitalWrite(13, LOW); delay(500);

}


الكود مكتوب بلغة Arduino، ويتكون من دالتين رئيسيتين: setup() و loop(). 

 أ) دالة setup():

cpp
void setup() {
  pinMode(13, OUTPUT);
}


- الشرح: 
  - void setup(): هذه الدالة يتم تنفيذها مرة واحدة عند بدء تشغيل الجهاز (الأردوينو). يتم استخدامها عادةً لتهيئة الإعدادات الأولية.
  - pinMode(13, OUTPUT)`: هنا يتم تحديد أن الطرف (Pin) رقم 13 على لوحة الأردوينو سيكون بمثابة مخرج (OUTPUT). هذا يعني أننا سنستخدم هذا الطرف لإرسال إشارة كهربائية لتشغيل أو إطفاء الـ LED.

 ب) دالة `loop():


void loop() {
  digitalWrite(13, HIGH);
  delay(500); 

  digitalWrite(13, LOW);
  delay(500); 

  digitalWrite(13, HIGH);
  delay(500); 

  digitalWrite(13, LOW);
  delay(500); 
}
```

- الشرح:
  - void loop(): هذه الدالة يتم تنفيذها بشكل متكرر بعد انتهاء دالة `setup()`. أي أن الكود الموجود بداخلها سيعمل بشكل مستمر طالما الجهاز يعمل.
  
  - digitalWrite(13, HIGH)`: هذا الأمر يرسل إشارة كهربائية عالية (HIGH) إلى الطرف رقم 13، مما يؤدي إلى إضاءة الـ LED المتصل بهذا الطرف.
  
  - delay(500): هذا الأمر يوقف تنفيذ الكود لمدة 500 مللي ثانية (نصف ثانية). خلال هذه الفترة، يبقى الـ LED مضاءً.
  
  - digitalWrite(13, LOW)`: هذا الأمر يرسل إشارة كهربائية منخفضة (LOW) إلى الطرف رقم 13، مما يؤدي إلى إطفاء الـ LED.
  
  - delay(500): مرة أخرى، يتم إيقاف التنفيذ لمدة 500 مللي ثانية، وخلال هذه الفترة يبقى الـ LED مطفأً.
  
  - يتم تكرار الأمرين digitalWrite(13, HIGH) و digitalWrite(13, LOW) مرة أخرى مع delay(500) بعد كل أمر، مما يؤدي إلى إضاءة الـ LED وإطفائه مرتين في الثانية الواحدة.

 
الكود يقوم بتشغيل وإطفاء الـ LED مرتين في الثانية عن طريق إرسال إشارة كهربائية عالية (HIGH) ومنخفضة (LOW) إلى الطرف رقم 13 على لوحة الأردوينو، مع تأخير 500 مللي ثانية بين كل إشارة.




===============================================================================================================
Example 2 :
فكرة المثال:
السؤال يطلب كتابة كود يجعل LED أحمر يلمع 4 مرات في 4 ثوانٍ، وLED أخضر يلمع 4 مرات في ثانيتين، مع شرط أن يعملا في نفس الوقت. أي أن الـ LED الأحمر يلمع كل ثانية (4 مرات في 4 ثوانٍ)، والـ LED الأخضر يلمع كل 0.5 ثانية (4 مرات في ثانيتين).

شرح الكود:

 تعريف المتغيرات:

-----
const int redLED = 13;   
const int greenLED = 12;  

unsigned long previousRedMillis = 0;  
unsigned long previousGreenMillis = 0; 

const long redInterval = 500;  
const long greenInterval = 250; 

bool redState = LOW;   
bool greenState = LOW; 
-----

  - redLED و greenLED`: يتم تعريف الطرفين (Pins) اللذين سيتم توصيل الـ LED الأحمر والأخضر بهما.
  - previousRedMillis و `previousGreenMillis: متغيرات لتخزين الوقت الأخير الذي تم فيه تغيير حالة الـ LED.
  - redInterval و `greenInterval`: الفترات الزمنية بين كل ومضة للـ LED الأحمر (500 مللي ثانية) والأخضر (250 مللي ثانية).
  - redState و `greenState`: متغيرات لتخزين الحالة الحالية للـ LED (HIGH أو LOW).

---

 دالة setup()`:

```cpp
void setup() {
  pinMode(redLED, OUTPUT);
  pinMode(greenLED, OUTPUT);
}
```

- الشرح:
  - `pinMode(redLED, OUTPUT)`: يتم تهيئة الطرف `redLED` كمخرج (OUTPUT) للتحكم في الـ LED الأحمر.
  - `pinMode(greenLED, OUTPUT)`: يتم تهيئة الطرف `greenLED` كمخرج (OUTPUT) للتحكم في الـ LED الأخضر.

---

 دالة loop():

--------------
void loop() {
  unsigned long currentMillis = millis();

  if (currentMillis - previousRedMillis >= redInterval) {
    previousRedMillis = currentMillis; 
    redState = !redState;             
    digitalWrite(redLED, redState);  
  }

  if (currentMillis - previousGreenMillis >= greenInterval) {
    previousGreenMillis = currentMillis; 
    greenState = !greenState;           
    digitalWrite(greenLED, greenState);  
  }
}


- الشرح:
  - currentMillis = millis(): يتم تخزين الوقت الحالي منذ بدء تشغيل الأردوينو.
  - الشرط الأول (if):
    - يتم التحقق إذا كان الوقت المنقضي منذ آخر تغيير لحالة الـ LED الأحمر يساوي أو يزيد عن redInterval (500 مللي ثانية).
    - إذا تحقق الشرط، يتم تحديث `previousRedMillis` بالوقت الحالي، وتغيير حالة الـ LED الأحمر (`redState`) من HIGH إلى LOW أو العكس.
    - يتم تطبيق الحالة الجديدة على الـ LED الأحمر باستخدام `digitalWrite`.
  - الشرط الثاني (if):
    - يتم التحقق إذا كان الوقت المنقضي منذ آخر تغيير لحالة الـ LED الأخضر يساوي أو يزيد عن `greenInterval` (250 مللي ثانية).
    - إذا تحقق الشرط، يتم تحديث `previousGreenMillis` بالوقت الحالي، وتغيير حالة الـ LED الأخضر (`greenState`) من HIGH إلى LOW أو العكس.
    - يتم تطبيق الحالة الجديدة على الـ LED الأخضر باستخدام `digitalWrite`.







===================================================================================================================
Example 3: 




