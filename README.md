# walidali
<?php

// إنشاء فئة للدرس الخاص
class PrivateLesson {
  // التعريفات الخاصة بالدرس
  private $subject;
  private $duration;
  private $price;
  private $password;

  // المتغيرات العامة
  public $liveStreamURL;

  // الدالة الخاصة بإنشاء الدرس
  public function __construct($subject, $duration, $price, $password) {
    $this->subject = $subject;
    $this->duration = $duration;
    $this->price = $price;
    $this->password = $password;
  }

  // الدالة الخاصة بعرض معلومات الدرس
  public function getInfo() {
    return "تعليم " . $this->subject . " لمدة " . $this->duration . " ساعة/ساعات و السعر هو " . $this->price . " دولار.";
  }

  // الدالة الخاصة بالتحقق من كلمة السر
  public function checkPassword($enteredPassword) {
    if ($enteredPassword == $this->password) {
      return true;
    } else {
      return false;
    }
  }
}

// إنشاء كائن من فئة الدرس الخاص
$mathLesson = new PrivateLesson("رياضيات", 2, 50, "math123");

// تعيين متغير البث المباشر للدرس
$mathLesson->liveStreamURL = "https://example.com/live/math";

// طباعة معلومات الدرس
echo $mathLesson->getInfo();

// التحقق من كلمة السر الصحيحة للدرس
if ($mathLesson->checkPassword("math123")) {
  echo "تم الدخول إلى الدرس بنجاح!";
} else {
  echo "كلمة السر غير صحيحة.";
}

