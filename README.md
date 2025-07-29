# 🚀 ROS 2 CLI Tools – Beginner Tutorial

فهم وتعلم الأدوات الأساسية في ROS 2 باستخدام **سطر الأوامر (CLI)** بدون الحاجة لكتابة كود. هذا الدليل مناسب لفهم المفاهيم الأساسية التالية:

- Nodes
- Topics
- Services
- Parameters
- Actions

---

> 🧰 تأكد أنك شغّلت بيئة ROS 2:
> ```bash
> source /opt/ros/humble/setup.bash
> ```

---

## 🧠 1. Nodes – العقد

العقد (Nodes) هي وحدات صغيرة تنفذ مهام محددة. كل عقدة تتواصل مع الآخرين عبر Topics أو Services.

🔎 **استعراض العقد المتاحة:**
```bash
ros2 node list
```

🔍 **عرض معلومات عن عقدة معيّنة:**
```bash
ros2 node info /node_name
```

---

## 📡 2. Topics – المواضيع

التوبيك (Topic) يُستخدم لإرسال واستقبال الرسائل بين العقد بطريقة غير متزامنة (Publisher/Subscriber).

🔎 **عرض جميع التوبيكات:**
```bash
ros2 topic list
```

📨 **مشاهدة الرسائل المرسلة في توبيك:**
```bash
ros2 topic echo /topic_name
```

🧾 **معرفة نوع الرسائل في توبيك:**
```bash
ros2 topic info /topic_name
```

✉️ **نشر رسالة إلى توبيك يدويًا:**
```bash
ros2 topic pub /topic_name std_msgs/msg/String "data: Hello World"
```

---

## 🧰 3. Services – الخدمات

الخدمة (Service) تنفّذ عملية عند الطلب وتُرجع نتيجة واحدة، مثل "احسب" أو "أوقف".

🔎 **عرض جميع الخدمات:**
```bash
ros2 service list
```

📄 **عرض نوع الخدمة:**
```bash
ros2 service type /service_name
```

📤 **إرسال طلب خدمة:**
```bash
ros2 service call /service_name service_type "{}"
```

مثال:
```bash
ros2 service call /add_two_ints example_interfaces/srv/AddTwoInts "{a: 2, b: 3}"
```

---

## ⚙️ 4. Parameters – المعلمات

المعلمات تُستخدم لتخزين إعدادات داخل العقدة ويمكن تغييرها بدون تعديل الكود.

🔎 **عرض جميع المعلمات:**
```bash
ros2 param list
```

🔍 **قراءة قيمة باراميتر:**
```bash
ros2 param get /node_name parameter_name
```

✏️ **تعديل قيمة باراميتر:**
```bash
ros2 param set /node_name parameter_name new_value
```

---

## 🎯 5. Actions – الإجراءات

الأكشن مشابه للسيرفِس، لكن يُستخدم للمهام التي تأخذ وقتًا أطول (مثل الحركة، الملاحة...).

🔎 **عرض جميع الأكشنات:**
```bash
ros2 action list
```

📘 **معرفة نوع الأكشن:**
```bash
ros2 action type /action_name
```

🚀 **إرسال هدف (Goal) إلى أكشن:**
```bash
ros2 action send_goal /action_name action_type "{}"
```

مثال:
```bash
ros2 action send_goal /fibonacci action_tutorials_interfaces/action/Fibonacci "{order: 5}"
```

---

## ✅ ملاحظات ختامية

- دائمًا استخدم `-h` للحصول على مساعدة:
  ```bash
  ros2 topic -h
  ```

- استخدم `tab` للإكمال التلقائي في الطرفية.

- هذه الأدوات راح  تساعدك على فهم عمل ROS 2 بدون كتابة أي كود.

---

📚 إذا حاب تعرف أكثر: [ROS 2 Documentation](https://docs.ros.org/en/humble/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim/Introducing-Turtlesim.html)
