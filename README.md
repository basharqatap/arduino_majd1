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

شرح الكود بالتفصيل :

دالة setup():
void setup() {
  pinMode(13, OUTPUT);
}
الوظيفة:
هذه الدالة تُنفَّذ مرة واحدة فقط عند بدء تشغيل لوحة الـ Arduino. يتم استخدامها لإعداد الإعدادات الأولية للمشروع.

المحتوى:

pinMode(13, OUTPUT);:
يتم هنا تعيين الـ pin 13 كمخرج (OUTPUT). هذا يعني أن الـ pin 13 سيستخدم لإرسال إشارة كهربائية (HIGH أو LOW) لتشغيل أو إيقاف الـ LED المتصل به.
2.دالة loop():

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
الوظيفة:
هذه الدالة تُنفَّذ بشكل متكرر بعد انتهاء دالة setup(). يتم استخدامها لتكرار العمليات الرئيسية في المشروع.

المحتوى:

digitalWrite(13, HIGH);:
يتم هنا إرسال إشارة كهربائية عالية (HIGH) إلى الـ pin 13، مما يؤدي إلى تشغيل الـ LED المتصل به.

delay(500);:
يتم هنا إيقاف التنفيذ لمدة 500 مللي ثانية (0.5 ثانية). هذا يعني أن الـ LED سيظل مضاءً لمدة نصف ثانية.

digitalWrite(13, LOW);:
يتم هنا إرسال إشارة كهربائية منخفضة (LOW) إلى الـ pin 13، مما يؤدي إلى إيقاف تشغيل الـ LED.

delay(500);:
يتم هنا إيقاف التنفيذ مرة أخرى لمدة 500 مللي ثانية. هذا يعني أن الـ LED سيظل مطفأً لمدة نصف ثانية.

يتم تكرار العملية مرة أخرى (digitalWrite(13, HIGH); وdelay(500); ثم digitalWrite(13, LOW); و delay(500);) لجعل الـ LED يومض مرتين في الثانية.


===========================================================================================================================================================================
example2 :





 1. وصف وشرح فكرة السؤال:
المطلوب هو برمجة دائرة إلكترونية تحتوي على LED أحمر وآخر أخضر بحيث:
- الـ LED الأحمر يومض 4 مرات خلال 4 ثوانٍ (أي مرة كل ثانية).
- الـ LED الأخضر يومض 4 مرات خلال 2 ثانية (أي مرة كل 0.5 ثانية).
- يجب أن يبدأ كلاهما في العمل في نفس الوقت وبدون استخدام دالة التاخير delay

 2. شرح الكود:
    the code:
const int redLED = 13;   
const int greenLED = 12;  


unsigned long previousRedMillis = 0;  
unsigned long previousGreenMillis = 0; 


const long redInterval = 500;  
const long greenInterval = 250; 


bool redState = LOW;   
bool greenState = LOW; 

void setup() {

  pinMode(redLED, OUTPUT);
  pinMode(greenLED, OUTPUT);
}

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

```cpp
 تعريف الأطراف (Pins) التي سيتم توصيل الـ LEDs بها
const int redLED = 2;    // LED الأحمر متصل بالطرف 2
const int greenLED = 3;  // LED الأخضر متصل بالطرف 3

void setup() {
   تهيئة الأطراف كمخرجات
  pinMode(redLED, OUTPUT);
  pinMode(greenLED, OUTPUT);
}

void loop() {
   تشغيل وإطفاء الـ LEDs وفقًا للفترات المطلوبة
  for (int i = 0; i < 4; i++) {
    digitalWrite(redLED, HIGH);   // تشغيل LED الأحمر
    digitalWrite(greenLED, HIGH); // تشغيل LED الأخضر
    delay(500);                   // انتظار 0.5 ثانية
    digitalWrite(greenLED, LOW);  // إطفاء LED الأخضر
    delay(500);                   // انتظار 0.5 ثانية
    digitalWrite(redLED, LOW);    // إطفاء LED الأحمر
  }
  delay(1000); // انتظار ثانية قبل تكرار العملية
}


شرح الدوال:
1. pinMode(pin, mode):
   - تُستخدم لتعريف الطرف (Pin) سواء كان إدخال (INPUT) أو إخراج (OUTPUT).
   - هنا، تم تعريف الطرفين 2 و 3 كمخرجات لتوصيل الـ LEDs.

2. digitalWrite(pin, value):
   - تُستخدم لتشغيل (HIGH) أو إطفاء (LOW) الطرف المحدد.
   - هنا، يتم تشغيل وإطفاء الـ LEDs وفقًا للتوقيت المطلوب.

3. delay(milliseconds):
   - تُستخدم لإيقاف البرنامج لفترة زمنية محددة (بالمللي ثانية).
   - هنا، يتم استخدامها للتحكم في فترات التشغيل والإطفاء.

4. loop():
   - تُكرر تنفيذ الأوامر بداخلها بشكل مستمر.
   - هنا، يتم تنفيذ عملية التشغيل والإطفاء للـ LEDs بشكل متكرر.

5. for (int i = 0; i < 4; i++):
   - حلقة تكرارية تُنفذ الأوامر بداخلها 4 مرات.
   - هنا، تُستخدم لضمان أن الـ LEDs يومضان 4 مرات وفقًا للفترات المحددة.
