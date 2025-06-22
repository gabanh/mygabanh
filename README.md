<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>امتحان فهم المقروء - الصف السادس - مدرسة الأمل</title>
    <style>
        :root {
            --primary: #3498db;
            --secondary: #2ecc71;
            --accent: #e74c3c;
            --light: #f8f9fa;
            --dark: #343a40;
            --border: #dee2e6;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* ترويسة الصفحة */
        .exam-header {
            background: linear-gradient(135deg, #1a5276, #2e86c1);
            color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            margin-bottom: 25px;
            text-align: center;
        }
        
        .exam-header h1 {
            font-size: 1.8rem;
            margin-bottom: 10px;
        }
        
        .exam-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 15px;
        }
        
        .info-item {
            background-color: rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
        }
        
        /* منطقة المحتوى الرئيسي */
        .main-content {
            display: flex;
            gap: 25px;
            margin-bottom: 30px;
        }
        
        /* شريط الأسئلة الجانبي */
        .questions-sidebar {
            flex: 0 0 250px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            padding: 20px;
            height: fit-content;
        }
        
        .sidebar-title {
            font-size: 1.2rem;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary);
            color: var(--dark);
        }
        
        .question-nav {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 10px;
        }
        
        .nav-item {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background-color: var(--light);
            border: 1px solid var(--border);
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .nav-item:hover {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }
        
        .nav-item.active {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }
        
        .nav-item.answered {
            background-color: var(--secondary);
            color: white;
            border-color: var(--secondary);
        }
        
        .section-nav {
            margin-top: 25px;
        }
        
        .section-btn {
            display: block;
            width: 100%;
            padding: 10px 15px;
            margin-bottom: 10px;
            background-color: #e9ecef;
            border: none;
            border-radius: 8px;
            text-align: right;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .section-btn:hover {
            background-color: var(--primary);
            color: white;
        }
        
        .section-btn.active {
            background-color: var(--primary);
            color: white;
        }
        
        /* منطقة النص والأسئلة */
        .exam-content {
            flex: 1;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            padding: 30px;
            position: relative;
        }
        
        .timer-container {
            position: absolute;
            top: 20px;
            left: 20px;
            background: linear-gradient(135deg, #e74c3c, #c0392b);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .text-title {
            font-size: 1.5rem;
            color: #1a5276;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--border);
        }
        
        .reading-text {
            background-color: #f8f9fa;
            border-left: 4px solid var(--primary);
            padding: 20px;
            border-radius: 0 8px 8px 0;
            margin-bottom: 30px;
            line-height: 1.8;
            max-height: 250px;
            overflow-y: auto;
        }
        
        .highlight {
            background-color: #fff3cd;
            padding: 2px 4px;
            border-radius: 3px;
        }
        
        .question-container {
            margin-bottom: 30px;
        }
        
        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border);
        }
        
        .question-number {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary);
        }
        
        .question-points {
            background-color: var(--secondary);
            color: white;
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 0.9rem;
        }
        
        .question-text {
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.7;
        }
        
        /* أنواع الأسئلة */
        .open-answer {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 1rem;
            resize: vertical;
            min-height: 100px;
            transition: border-color 0.3s;
        }
        
        .open-answer:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
        }
        
        .mcq-options {
            display: grid;
            gap: 12px;
        }
        
        .mcq-option {
            display: flex;
            align-items: flex-start;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .mcq-option:hover {
            background-color: #f1f8ff;
            border-color: var(--primary);
        }
        
        .mcq-option.selected {
            background-color: #e1f0fa;
            border-color: var(--primary);
        }
        
        .option-input {
            margin-left: 10px;
            margin-top: 3px;
        }
        
        .option-text {
            flex: 1;
        }
        
        .grid-answers {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .grid-answer {
            padding: 10px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 1rem;
        }
        
        .grid-answer:focus {
            outline: none;
            border-color: var(--primary);
        }
        
        /* أزرار التنقل */
        .navigation-btns {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }
        
        .nav-btn {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .prev-btn {
            background-color: #e9ecef;
            color: var(--dark);
        }
        
        .prev-btn:hover {
            background-color: #d6d8db;
        }
        
        .next-btn {
            background-color: var(--primary);
            color: white;
        }
        
        .next-btn:hover {
            background-color: #2980b9;
        }
        
        .submit-btn {
            background-color: var(--secondary);
            color: white;
        }
        
        .submit-btn:hover {
            background-color: #27ae60;
        }
        
        /* تذييل الصفحة */
        .exam-footer {
            text-align: center;
            padding: 20px;
            color: #6c757d;
            font-size: 0.9rem;
            border-top: 1px solid var(--border);
            margin-top: 20px;
        }
        
        /* رسائل التنبيه */
        .alert {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            z-index: 1000;
            opacity: 0;
            transform: translateY(-20px);
            transition: all 0.4s ease;
        }
        
        .alert.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .alert-success {
            background-color: var(--secondary);
            color: white;
        }
        
        .alert-warning {
            background-color: #f39c12;
            color: white;
        }
        
        /* تصميم متجاوب */
        @media (max-width: 992px) {
            .main-content {
                flex-direction: column;
            }
            
            .questions-sidebar {
                flex: 0 0 auto;
            }
            
            .question-nav {
                grid-template-columns: repeat(8, 1fr);
            }
        }
        
        @media (max-width: 576px) {
            .question-nav {
                grid-template-columns: repeat(5, 1fr);
            }
            
            .grid-answers {
                grid-template-columns: 1fr;
            }
            
            .nav-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- ترويسة الامتحان -->
        <header class="exam-header">
            <h1>امتحان في فهم المقروء للصف السادس</h1>
            <p>مدرسة الأمل - يونيو 2020</p>
            <div class="exam-info">
                <div class="info-item">الاسم: __________</div>
                <div class="info-item">الصف: __________</div>
                <div class="info-item">الرقم: __________</div>
            </div>
        </header>
        
        <div class="main-content">
            <!-- شريط الأسئلة الجانبي -->
            <aside class="questions-sidebar">
                <div class="sidebar-section">
                    <h3 class="sidebar-title">أسئلة الامتحان</h3>
                    <div class="question-nav">
                        <div class="nav-item active">1</div>
                        <div class="nav-item">2</div>
                        <div class="nav-item">3</div>
                        <div class="nav-item">4</div>
                        <div class="nav-item">5</div>
                        <div class="nav-item">6</div>
                        <div class="nav-item">7</div>
                        <div class="nav-item">8</div>
                        <div class="nav-item">9</div>
                        <div class="nav-item answered">10</div>
                        <div class="nav-item">11</div>
                        <div class="nav-item">12</div>
                        <div class="nav-item">13</div>
                        <div class="nav-item">14</div>
                        <div class="nav-item">15</div>
                        <div class="nav-item">16</div>
                        <div class="nav-item">17</div>
                        <div class="nav-item">18</div>
                        <div class="nav-item">19</div>
                        <div class="nav-item">20</div>
                    </div>
                </div>
                
                <div class="sidebar-section section-nav">
                    <h3 class="sidebar-title">أجزاء الامتحان</h3>
                    <button class="section-btn active">النص الأول: الكفيف</button>
                    <button class="section-btn">النص الثاني: الرجل والحصان</button>
                    <button class="section-btn">النص الثالث: النوم</button>
                    <button class="section-btn">النص الرابع: إطالة عمر الزهور</button>
                </div>
            </aside>
            
            <!-- محتوى الامتحان -->
            <main class="exam-content">
                <div class="timer-container">الوقت المتبقي: <span id="timer">01:29:45</span></div>
                
                <h2 class="text-title">النص الأول: الكفيف</h2>
                
                <div class="reading-text">
                    <p>كان الرجل الكفيف يمرّ يومياً في أنحارتنا، يحمل عصاه الخشبية البيضاء ويتمايل في مشيته. وكنا نحن الأولاد نلاحظ مروره بفضول كبير. في البداية، كنا نتعجب من طريقة مشيته المائلة، وكنا أحياناً نضحك ونقلّده. لكن أبي لاحظ تصرفنا ذات يوم، فجلس معنا وأخبرنا قصة هذا الرجل.</p>
                    
                    <p>قال أبي: "هذا الرجل فقد بصره وهو في ريعان الشباب بسبب حادث مؤسف، لكنه لم يستسلم. تعلم كيف يعتمد على نفسه، وأصبح يذهب إلى عمله يومياً بمفرده. إنه مثال للصبر والإرادة". <span class="highlight">منذ ذلك اليوم، تغيرت نظرتنا إليه. لم نعد نضحك على مشيته، بل كنا نساعده إذا احتاج إلى عبور الشارع، أو نرشده إذا ضل طريقه.</span></p>
                    
                    <p>ذات مرة، رأيته يحاول عبور الشارع وكانت السيارات تسير بسرعة. أسرعت إليه وأمسكت بذراعه. ابتسم وقال: "شكراً يا بني". سألته: "هل تريد مساعدتي في حمل حقيبتك؟" أجاب: "لا، أنا معتاد على حملها، لكن دليلي إلى البقالة سيكون مفيداً". فأخذته إلى البقالة وهو يضع يده على كتفي. شعرت بسعادة غامرة وأنا أساعده.</p>
                </div>
                
                <div class="question-container">
                    <div class="question-header">
                        <div class="question-number">السؤال 1</div>
                        <div class="question-points">(2 نقطة)</div>
                    </div>
                    
                    <div class="question-text">
                        كيف كان الأولاد يتصرفون عند مرور الرجل الكفيف في أنحارتهم، بحسب الأسطر (5-1)؟
                    </div>
                    
                    <textarea class="open-answer" placeholder="اكتب إجابتك هنا..."></textarea>
                </div>
                
                <div class="question-container">
                    <div class="question-header">
                        <div class="question-number">السؤال 2</div>
                        <div class="question-points">(1 نقطة)</div>
                    </div>
                    
                    <div class="question-text">
                        ما هي العادة التي يتحدّث عنها الشطر 12 من النّص؟
                    </div>
                    
                    <div class="mcq-options">
                        <div class="mcq-option">
                            <div class="option-input">☐</div>
                            <div class="option-text">مرور الكفيف في الشارع</div>
                        </div>
                        <div class="mcq-option selected">
                            <div class="option-input">☑</div>
                            <div class="option-text">لعب الأولاد معًا</div>
                        </div>
                        <div class="mcq-option">
                            <div class="option-input">☐</div>
                            <div class="option-text">مرافقة الولد لأبيه</div>
                        </div>
                        <div class="mcq-option">
                            <div class="option-input">☐</div>
                            <div class="option-text">تمایل ومشي الكفيف</div>
                        </div>
                    </div>
                </div>
                
                <div class="navigation-btns">
                    <button class="nav-btn prev-btn">السابق</button>
                    <button class="nav-btn next-btn">التالي</button>
                </div>
            </main>
        </div>
        
        <footer class="exam-footer">
            <p>© 2023 مدرسة الأمل - جميع الحقوق محفوظة | تم تطوير هذا النظام لتسهيل عملية الامتحانات الإلكترونية</p>
        </footer>
    </div>
    
    <!-- رسائل التنبيه -->
    <div class="alert alert-success">تم حفظ الإجابة بنجاح!</div>
    <div class="alert alert-warning">يجب الإجابة على هذا السؤال قبل الانتقال</div>

    <script>
        // متغيرات النظام
        let currentQuestion = 1;
        const totalQuestions = 20;
        let examDuration = 90 * 60; // 90 دقيقة بالثواني
        
        // عناصر DOM
        const timerElement = document.getElementById('timer');
        const navItems = document.querySelectorAll('.nav-item');
        const sectionBtns = document.querySelectorAll('.section-btn');
        const prevBtn = document.querySelector('.prev-btn');
        const nextBtn = document.querySelector('.next-btn');
        const mcqOptions = document.querySelectorAll('.mcq-option');
        const successAlert = document.querySelector('.alert-success');
        const warningAlert = document.querySelector('.alert-warning');
        
        // تهيئة العداد
        function updateTimer() {
            const minutes = Math.floor(examDuration / 60);
            const seconds = examDuration % 60;
            
            timerElement.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
            
            if (examDuration <= 0) {
                clearInterval(timerInterval);
                timerElement.textContent = "انتهى الوقت!";
                submitExam();
            } else {
                examDuration--;
            }
        }
        
        let timerInterval = setInterval(updateTimer, 1000);
        
        // تحديث السؤال الحالي
        function setActiveQuestion(questionNum) {
            currentQuestion = questionNum;
            
            // تحديث شريط التنقل
            navItems.forEach((item, index) => {
                item.classList.remove('active');
                if (index + 1 === questionNum) {
                    item.classList.add('active');
                }
            });
            
            // تحديث واجهة السؤال (في تطبيق حقيقي سيتم جلب بيانات السؤال)
            document.querySelector('.question-number').textContent = `السؤال ${questionNum}`;
        }
        
        // التنقل بين الأسئلة
        navItems.forEach((item, index) => {
            item.addEventListener('click', () => {
                setActiveQuestion(index + 1);
            });
        });
        
        // التنقل بين أقسام الامتحان
        sectionBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                sectionBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                // في تطبيق حقيقي سيتم تحميل النص والأسئلة الخاصة بهذا القسم
            });
        });
        
        // أزرار السابق والتالي
        prevBtn.addEventListener('click', () => {
            if (currentQuestion > 1) {
                setActiveQuestion(currentQuestion - 1);
            }
        });
        
        nextBtn.addEventListener('click', () => {
            if (currentQuestion < totalQuestions) {
                setActiveQuestion(currentQuestion + 1);
            } else {
                showAlert(successAlert);
                setTimeout(() => {
                    submitExam();
                }, 1500);
            }
        });
        
        // اختيار إجابة متعددة
        mcqOptions.forEach(option => {
            option.addEventListener('click', () => {
                // إزالة التحديد من جميع الخيارات
                mcqOptions.forEach(opt => opt.classList.remove('selected'));
                
                // تحديد الخيار الحالي
                option.classList.add('selected');
                
                // تحديد أيقونة التحديد
                option.querySelector('.option-input').textContent = '☑';
                
                // إظهار تنبيه الحفظ
                showAlert(successAlert);
            });
        });
        
        // إظهار رسائل التنبيه
        function showAlert(alertElement) {
            alertElement.classList.add('show');
            setTimeout(() => {
                alertElement.classList.remove('show');
            }, 3000);
        }
        
        // إرسال الامتحان
        function submitExam() {
            clearInterval(timerInterval);
            alert('تم إرسال إجاباتك بنجاح! شكرًا لك.');
            // في تطبيق حقيقي سيتم هنا إرسال الإجابات إلى الخادم
        }
        
        // تهيئة أولية
        document.addEventListener('DOMContentLoaded', () => {
            // في تطبيق حقيقي سيتم جلب بيانات الامتحان من خادم
            setActiveQuestion(1);
        });
    </script>
</body>
</html>
