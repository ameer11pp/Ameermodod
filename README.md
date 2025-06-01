<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فك تشفير ملفات PUBG Mobile - LIB Decryptor</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2ecc71;
            --secondary: #3498db;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --danger: #e74c3c;
            --warning: #f39c12;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #2c3e50, #4a235a);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: var(--light);
            line-height: 1.6;
            min-height: 100vh;
            padding-bottom: 40px;
        }
        
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        header {
            background: rgba(44, 62, 80, 0.9);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
        }
        
        .logo-container {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            color: var(--primary);
            text-shadow: 0 0 10px rgba(46, 204, 113, 0.5);
        }
        
        .logo i {
            font-size: 2.5rem;
            color: var(--primary);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
            margin-top: 15px;
        }
        
        nav a {
            color: var(--light);
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 30px;
            transition: all 0.3s ease;
            font-weight: 600;
        }
        
        nav a:hover, nav a.active {
            background: var(--primary);
            color: var(--dark);
        }
        
        .container {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
        }
        
        .hero {
            text-align: center;
            padding: 60px 20px;
            background: rgba(44, 62, 80, 0.7);
            border-radius: 15px;
            margin-bottom: 40px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        
        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
            color: var(--light);
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: var(--dark);
            padding: 12px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(46, 204, 113, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(46, 204, 113, 0.5);
        }
        
        .btn-secondary {
            background: var(--secondary);
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }
        
        .btn-secondary:hover {
            box-shadow: 0 6px 20px rgba(52, 152, 219, 0.5);
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }
        
        .feature-card {
            background: rgba(44, 62, 80, 0.8);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(44, 62, 80, 0.95);
        }
        
        .feature-card i {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .upload-section {
            background: rgba(44, 62, 80, 0.8);
            border-radius: 15px;
            padding: 40px;
            text-align: center;
            margin-bottom: 50px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        
        .upload-section h2 {
            font-size: 2rem;
            margin-bottom: 30px;
            color: var(--primary);
        }
        
        .upload-area {
            border: 3px dashed var(--secondary);
            border-radius: 15px;
            padding: 50px 20px;
            margin-bottom: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: rgba(52, 152, 219, 0.1);
        }
        
        .upload-area:hover {
            background: rgba(52, 152, 219, 0.2);
        }
        
        .upload-area i {
            font-size: 4rem;
            color: var(--secondary);
            margin-bottom: 20px;
        }
        
        .upload-area p {
            font-size: 1.2rem;
            margin-bottom: 15px;
        }
        
        .upload-area span {
            color: var(--warning);
            font-weight: bold;
        }
        
        .file-input {
            display: none;
        }
        
        .process-btn {
            margin: 20px auto;
            display: block;
            width: 250px;
        }
        
        .result-section {
            background: rgba(44, 62, 80, 0.8);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        
        .result-section h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--primary);
            text-align: center;
        }
        
        .result-content {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            padding: 20px;
            min-height: 200px;
            font-family: monospace;
            overflow-x: auto;
            white-space: pre-wrap;
        }
        
        .download-btn {
            margin: 20px auto 0;
            display: block;
            width: 250px;
        }
        
        .instructions {
            margin-top: 50px;
            background: rgba(44, 62, 80, 0.8);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        
        .instructions h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--primary);
            text-align: center;
        }
        
        .step {
            display: flex;
            align-items: flex-start;
            gap: 20px;
            margin-bottom: 30px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 10px;
        }
        
        .step-number {
            background: var(--primary);
            color: var(--dark);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
            flex-shrink: 0;
        }
        
        .step-content h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--secondary);
        }
        
        footer {
            text-align: center;
            padding: 30px 20px;
            margin-top: 50px;
            background: rgba(44, 62, 80, 0.9);
            border-radius: 15px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .social-links a {
            color: var(--light);
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            color: var(--primary);
            transform: translateY(-5px);
        }
        
        .progress-bar {
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            margin: 20px 0;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: var(--primary);
            width: 0%;
            border-radius: 5px;
            transition: width 0.5s ease;
        }
        
        .status {
            text-align: center;
            margin-top: 10px;
            font-weight: bold;
            color: var(--primary);
        }
        
        @media (max-width: 768px) {
            .logo-container {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero {
                padding: 40px 15px;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .upload-section {
                padding: 25px 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo-container">
            <div class="logo">
                <i class="fas fa-lock-open"></i>
                <h1>فك تشفير ملفات PUBG Mobile</h1>
            </div>
        </div>
        <nav>
            <ul>
                <li><a href="#" class="active">الرئيسية</a></li>
                <li><a href="#">المميزات</a></li>
                <li><a href="#">الدليل</a></li>
                <li><a href="#">الأسئلة الشائعة</a></li>
                <li><a href="#">اتصل بنا</a></li>
            </ul>
        </nav>
    </header>
    
    <div class="container">
        <section class="hero">
            <h2>فك تشفير ملفات LIB لـ PUBG Mobile بسهولة</h2>
            <p>أول وأقوى موقع لفك تشفير ملفات LIB مثل libvnurt و ovnjs و dadamaster. استخرج البيانات وفك تشفير الملفات في ثوانٍ معدودة دون الحاجة لبرامج معقدة!</p>
            <a href="#upload" class="btn">ابدأ الآن مجانًا</a>
        </section>
        
        <section class="features">
            <div class="feature-card">
                <i class="fas fa-bolt"></i>
                <h3>سرعة فائقة</h3>
                <p>فك تشفير الملفات في ثوانٍ معدودة باستخدام أحدث الخوارزميات والتقنيات المتقدمة</p>
            </div>
            
            <div class="feature-card">
                <i class="fas fa-shield-alt"></i>
                <h3>آمن وموثوق</h3>
                <p>جميع عمليات الفك تتم بشكل آمن دون الاحتفاظ بنسخ من ملفاتك أو مشاركتها مع أي جهة</p>
            </div>
            
            <div class="feature-card">
                <i class="fas fa-mobile-alt"></i>
                <h3>يدعم جميع الإصدارات</h3>
                <p>يدعم جميع إصدارات PUBG Mobile بما فيها الإصدارات العالمية والصينية والكراك</p>
            </div>
        </section>
        
        <section id="upload" class="upload-section">
            <h2>فك تشفير ملفاتك الآن</h2>
            
            <div class="upload-area" id="dropArea">
                <i class="fas fa-cloud-upload-alt"></i>
                <p>اسحب ملف LIB وأفلته هنا أو</p>
                <p><span>انقر لاختيار الملف</span></p>
                <p>الحد الأقصى لحجم الملف: 50MB</p>
                <p>(يدعم: libanort.ovnjs, libtersafe.so, libUE4.so, وغيرها)</p>
            </div>
            
            <input type="file" id="fileInput" class="file-input" accept=".so,.lib">
            
            <div class="progress-bar">
                <div class="progress" id="progressBar"></div>
            </div>
            <div class="status" id="statusText">في انتظار تحميل الملف...</div>
            
            <button class="btn process-btn" id="processBtn">بدء فك التشفير</button>
        </section>
        
        <section class="result-section">
            <h2>نتيجة فك التشفير</h2>
            <div class="result-content" id="resultContent">
                ستظهر هنا محتويات الملف بعد فك التشفير...
            </div>
            <button class="btn download-btn btn-secondary" id="downloadBtn" disabled>
                <i class="fas fa-download"></i> تحميل الملف المفكوك
            </button>
        </section>
        
        <section class="instructions">
            <h2>كيفية استخدام الموقع</h2>
            
            <div class="step">
                <div class="step-number">1</div>
                <div class="step-content">
                    <h3>تحديد موقع ملف LIB</h3>
                    <p>ابحث عن ملف LIB في جهازك. عادةً ما يكون موجودًا في المسار: <code>/Android/data/com.tencent.ig/files/UE4Game/ShadowTrackerExtra/ShadowTrackerExtra/Saved/Paks/</code></p>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">2</div>
                <div class="step-content">
                    <h3>تحميل الملف</h3>
                    <p>انقر على منطقة التحميل أو اسحب الملف وأفلته في المنطقة المخصصة. يمكنك تحميل أي ملف من نوع LIB مثل libanort.ovnjs أو libtersafe.so أو libUE4.so</p>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">3</div>
                <div class="step-content">
                    <h3>فك التشفير</h3>
                    <p>انقر على زر "بدء فك التشفير" وسيقوم الموقع بفك تشفير الملف باستخدام خوارزميات متقدمة خاصة بـ PUBG Mobile</p>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">4</div>
                <div class="step-content">
                    <h3>تحميل النتيجة</h3>
                    <p>بعد اكتمال عملية فك التشفير، يمكنك رؤية محتويات الملف مباشرة على الموقع أو تنزيل الملف المفكوك لاستخدامه</p>
                </div>
            </div>
        </section>
    </div>
    
    <footer>
        <div class="container">
            <h3>فك تشفير ملفات PUBG Mobile</h3>
            <p>الموقع الأول والأسرع لفك تشفير ملفات LIB الخاصة بلعبة ببجي موبايل</p>
            
            <div class="social-links">
                <a href="#"><i class="fab fa-telegram"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
                <a href="#"><i class="fab fa-discord"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
            </div>
            
            <p>© 2023 فك تشفير ملفات PUBG Mobile. جميع الحقوق محفوظة.</p>
            <p>هذا الموقع لأغراض تعليمية فقط. لا نتحمل مسؤولية أي استخدام غير قانوني.</p>
        </div>
    </footer>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const dropArea = document.getElementById('dropArea');
            const fileInput = document.getElementById('fileInput');
            const processBtn = document.getElementById('processBtn');
            const resultContent = document.getElementById('resultContent');
            const downloadBtn = document.getElementById('downloadBtn');
            const progressBar = document.getElementById('progressBar');
            const statusText = document.getElementById('statusText');
            
            // Handle drag and drop events
            ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
                dropArea.addEventListener(eventName, preventDefaults, false);
            });
            
            function preventDefaults(e) {
                e.preventDefault();
                e.stopPropagation();
            }
            
            ['dragenter', 'dragover'].forEach(eventName => {
                dropArea.addEventListener(eventName, highlight, false);
            });
            
            ['dragleave', 'drop'].forEach(eventName => {
                dropArea.addEventListener(eventName, unhighlight, false);
            });
            
            function highlight() {
                dropArea.style.borderColor = '#2ecc71';
                dropArea.style.backgroundColor = 'rgba(46, 204, 113, 0.2)';
            }
            
            function unhighlight() {
                dropArea.style.borderColor = '#3498db';
                dropArea.style.backgroundColor = 'rgba(52, 152, 219, 0.1)';
            }
            
            // Handle file drop
            dropArea.addEventListener('drop', handleDrop, false);
            
            function handleDrop(e) {
                const dt = e.dataTransfer;
                const files = dt.files;
                if (files.length) {
                    handleFiles(files[0]);
                }
            }
            
            // Handle file selection via click
            dropArea.addEventListener('click', () => {
                fileInput.click();
            });
            
            fileInput.addEventListener('change', function() {
                if (this.files.length) {
                    handleFiles(this.files[0]);
                }
            });
            
            function handleFiles(file) {
                // Check file type
                if (!file.name.endsWith('.so') && !file.name.endsWith('.lib')) {
                    statusText.textContent = 'نوع الملف غير مدعوم. الرجاء تحميل ملف LIB أو SO.';
                    statusText.style.color = '#e74c3c';
                    return;
                }
                
                // Check file size (50MB max)
                if (file.size > 50 * 1024 * 1024) {
                    statusText.textContent = 'حجم الملف كبير جدًا. الحد الأقصى 50MB.';
                    statusText.style.color = '#e74c3c';
                    return;
                }
                
                statusText.textContent = `تم تحميل الملف: ${file.name}`;
                statusText.style.color = '#2ecc71';
                
                // Simulate decryption process
                processBtn.addEventListener('click', function() {
                    // Simulate progress
                    let progress = 0;
                    const interval = setInterval(() => {
                        progress += Math.random() * 10;
                        if (progress >= 100) {
                            progress = 100;
                            clearInterval(interval);
                            
                            // Show result
                            statusText.textContent = 'تم فك التشفير بنجاح!';
                            statusText.style.color = '#2ecc71';
                            
                            // Enable download button
                            downloadBtn.disabled = false;
                            
                            // Show decrypted content
                            resultContent.textContent = generateDecryptedContent();
                        }
                        progressBar.style.width = `${progress}%`;
                    }, 200);
                });
            }
            
            // Generate sample decrypted content
            function generateDecryptedContent() {
                const functions = [
                    'DecryptData()', 'VerifyChecksum()', 'AntiCheatInit()', 'MemoryScan()', 
                    'HookDetection()', 'ProcessCheck()', 'DebuggerDetect()', 'EmulatorCheck()',
                    'RootDetection()', 'VirtualMachineCheck()', 'IntegrityCheck()', 'SignatureScan()',
                    'CodeObfuscation()', 'BehaviorAnalysis()', 'APIHookDetect()'
                ];
                
                let content = '// ملف LIB مفكوك التشفير\n\n';
                content += `// اسم الملف: libtersafe.so\n`;
                content += `// حجم الملف: 3.8MB\n`;
                content += `// إصدار PUBG: 2.5.0\n\n`;
                
                // Generate random functions
                for (let i = 0; i < 12; i++) {
                    const func = functions[Math.floor(Math.random() * functions.length)];
                    content += `void ${func} {\n`;
                    
                    // Add some assembly-like code
                    const instructions = ['MOV', 'PUSH', 'POP', 'CMP', 'JMP', 'CALL', 'RET', 'LEA', 'TEST', 'NOP'];
                    for (let j = 0; j < 5; j++) {
                        const instr = instructions[Math.floor(Math.random() * instructions.length)];
                        content += `    ${instr} ${getRandomRegister()}, ${getRandomOperand()}\n`;
                    }
                    
                    content += '}\n\n';
                }
                
                return content;
            }
            
            function getRandomRegister() {
                const registers = ['EAX', 'EBX', 'ECX', 'EDX', 'ESI', 'EDI', 'EBP', 'ESP'];
                return registers[Math.floor(Math.random() * registers.length)];
            }
            
            function getRandomOperand() {
                const operands = ['0x0', '0x1', '0x2', '0x4', '0x8', '0x10', '[EBX]', '[ECX+0x4]', 'DWORD PTR [EAX]', 'OFFSET 0x45AB12'];
                return operands[Math.floor(Math.random() * operands.length)];
            }
            
            // Download button functionality
            downloadBtn.addEventListener('click', function() {
                const content = resultContent.textContent;
                const blob = new Blob([content], { type: 'text/plain' });
                const url = URL.createObjectURL(blob);
                
                const a = document.createElement('a');
                a.href = url;
                a.download = 'decrypted_lib.txt';
                document.body.appendChild(a);
                a.click();
                
                // Clean up
                setTimeout(() => {
                    document.body.removeChild(a);
                    window.URL.revokeObjectURL(url);
                }, 100);
            });
        });
    </script>
</body>
</html>
