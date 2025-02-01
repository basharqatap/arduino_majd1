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


