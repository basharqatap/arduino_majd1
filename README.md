
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




===================================================================================================================
Example 3: 




