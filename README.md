# arduino_majd1
Assignment 1 - Eng. Majed Al-Suraihi , IOT Subject


يهدف هذا المثال إلى اختبار القدرة على التحكم في تشغيل وإيقاف LED باستخدام كود برمجي على ميكروكنترولر مثل Arduino. الفكرة الرئيسية هي جعل LED يومض بمعدل مرتين في الثانية، أي أنه يضيء وينطفئ كل 500 مللي ثانية. يتم ذلك عبر تغيير حالة الدبوس المتصل بالـ LED بين التشغيل (HIGH) والإيقاف (LOW) مع استخدام تأخير زمني مناسب (delay).

Code: 

void setup() {
 
  pinMode(13, OUTPUT);
}

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

شرح الكود بالتفصيل :

1. دالة setup():
```cpp
void setup() {
  pinMode(13, OUTPUT);
}
```

- الوظيفة:  
  هذه الدالة تُنفَّذ مرة واحدة فقط عند بدء تشغيل لوحة الـ Arduino. يتم استخدامها لإعداد الإعدادات الأولية للمشروع.

- المحتوى:
  - `pinMode(13, OUTPUT);`:  
    يتم هنا تعيين الـ pin 13 كمخرج (OUTPUT). هذا يعني أن الـ pin 13 سيستخدم لإرسال إشارة كهربائية (HIGH أو LOW) لتشغيل أو إيقاف الـ LED المتصل به.

---

 2.دالة loop():
```cpp
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

- الوظيفة:  
  هذه الدالة تُنفَّذ بشكل متكرر بعد انتهاء دالة setup(). يتم استخدامها لتكرار العمليات الرئيسية في المشروع.

- المحتوى:
  - `digitalWrite(13, HIGH);`:  
    يتم هنا إرسال إشارة كهربائية عالية (HIGH) إلى الـ pin 13، مما يؤدي إلى تشغيل الـ LED المتصل به.

  - `delay(500);`:  
    يتم هنا إيقاف التنفيذ لمدة 500 مللي ثانية (0.5 ثانية). هذا يعني أن الـ LED سيظل مضاءً لمدة نصف ثانية.

  - `digitalWrite(13, LOW);`:  
    يتم هنا إرسال إشارة كهربائية منخفضة (LOW) إلى الـ pin 13، مما يؤدي إلى إيقاف تشغيل الـ LED.

  - `delay(500);`:  
    يتم هنا إيقاف التنفيذ مرة أخرى لمدة 500 مللي ثانية. هذا يعني أن الـ LED سيظل مطفأً لمدة نصف ثانية.

  - يتم تكرار العملية مرة أخرى (digitalWrite(13, HIGH); وdelay(500); ثم digitalWrite(13, LOW); و delay(500);) لجعل الـ LED يومض مرتين في الثانية.



