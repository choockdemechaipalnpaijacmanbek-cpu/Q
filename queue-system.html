<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ระบบจองคิวและเรียกคิวอัจฉริยะ (A5 Print & Voice)</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Prompt', sans-serif; }
        @media print {
            body * { visibility: hidden; }
            #print-area, #print-area * { visibility: visible; }
            #print-area {
                position: absolute;
                left: 0;
                top: 0;
                width: 148mm;
                height: 210mm;
                padding: 15mm;
                background: white;
                font-size: 18px;
            }
        }
    </style>
</head>
<body class="bg-slate-100 min-h-screen text-slate-800">

    <!-- Header -->
    <header class="bg-indigo-600 text-white shadow-md p-4 flex justify-between items-center">
        <h1 class="text-xl font-bold">🎫 ระบบจัดการและจองคิวออนไลน์</h1>
        <div class="flex items-center gap-4">
            <button onclick="toggleAudio()" id="audio-btn" class="bg-emerald-500 hover:bg-emerald-600 px-3 py-1.5 rounded-lg text-sm font-medium transition flex items-center gap-1 shadow">
                🔊 เปิด/ปิด เสียงเรียกคิว
            </button>
            <span id="clock" class="text-sm bg-indigo-700 px-3 py-1 rounded-full"></span>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-4 md:p-6 grid grid-cols-1 lg:grid-cols-3 gap-6">
        
        <!-- ส่วนที่ 1: หน้าจอรับคิว / กดจองคิว (Customer Panel) -->
        <section class="bg-white rounded-2xl shadow-lg p-6 flex flex-col justify-between border border-slate-200">
            <div>
                <h2 class="text-xl font-bold text-indigo-700 mb-2 border-b pb-2">📌 รับบัตรคิวบริการ</h2>
                <p class="text-sm text-slate-500 mb-6">เลือกประเภทบริการที่ท่านต้องการเพื่อรับหมายเลขคิว</p>
                
                <div class="space-y-4">
                    <button onclick="createQueue('A')" class="w-full bg-gradient-to-r from-blue-500 to-indigo-600 hover:from-blue-600 hover:to-indigo-700 text-white p-4 rounded-xl shadow-md transition transform active:scale-95 flex justify-between items-center">
                        <div class="text-left">
                            <span class="block text-lg font-bold">หมวด A : บริการทั่วไป</span>
                            <span class="text-xs text-blue-100">ติดต่อสอบถาม / ธุรกรรมทั่วไป</span>
                        </div>
                        <span class="bg-white/25 px-3 py-1 rounded-lg text-xl font-bold">A</span>
                    </button>

                    <button onclick="createQueue('B')" class="w-full bg-gradient-to-r from-amber-500 to-orange-600 hover:from-amber-600 hover:to-orange-700 text-white p-4 rounded-xl shadow-md transition transform active:scale-95 flex justify-between items-center">
                        <div class="text-left">
                            <span class="block text-lg font-bold">หมวด B : บริการด่วนพิเศษ</span>
                            <span class="text-xs text-amber-100">ยื่นเอกสารด่วน / ชำระเงิน</span>
                        </div>
                        <span class="bg-white/25 px-3 py-1 rounded-lg text-xl font-bold">B</span>
                    </button>
                </div>
            </div>

            <!-- แสดงสถานะคิวล่าสุดของผู้รับบัตร -->
            <div id="latest-ticket-card" class="mt-8 bg-slate-50 rounded-xl p-4 border border-dashed border-slate-300 text-center hidden">
                <p class="text-xs text-slate-500">คิวล่าสุดของคุณ</p>
                <div id="my-queue-number" class="text-3xl font-extrabold text-indigo-600 my-1">-</div>
                <p class="text-xs text-slate-600" id="my-queue-time">-</p>
                <button onclick="printTicket()" class="mt-3 bg-slate-800 hover:bg-slate-900 text-white text-xs px-4 py-2 rounded-lg font-medium transition flex items-center justify-center gap-1 mx-auto">
                    🖨️ พิมพ์บัตรคิว (ขนาด A5)
                </button>
            </div>
        </section>

        <!-- ส่วนที่ 2: หน้าจอแสดงผลคิวปัจจุบัน (Queue Display Screen) -->
        <section class="bg-slate-900 text-white rounded-2xl shadow-lg p-6 flex flex-col justify-between border border-slate-800">
            <div class="text-center">
                <h2 class="text-sm font-semibold tracking-widest text-indigo-400 uppercase mb-1">กำลังเรียกคิว</h2>
                <div class="bg-slate-800 rounded-2xl p-6 border border-slate-700 shadow-inner my-3">
                    <div id="current-called-queue" class="text-6xl md:text-7xl font-black text-amber-400 tracking-wider">--</div>
                    <p id="current-counter" class="text-sm text-slate-400 mt-2">ช่องบริการที่: -</p>
                </div>
            </div>

            <div class="mt-6">
                <h3 class="text-sm font-semibold text-slate-400 mb-3 uppercase tracking-wider">คิวถัดไป (Next Queues)</h3>
                <div id="next-queue-list" class="space-y-2 max-h-48 overflow-y-auto pr-1">
                    <div class="text-slate-500 text-sm text-center py-4 bg-slate-800/50 rounded-xl">ไม่มีคิวรอ</div>
                </div>
            </div>

            <div class="mt-6 pt-4 border-t border-slate-800 text-center text-xs text-slate-500">
                ระบบเสียงอัตโนมัติพร้อมใช้งานผ่าน Wi-Fi / Browser
            </div>
        </section>

        <!-- ส่วนที่ 3: หน้าจอแอดมิน ควบคุมและจัดลำดับคิว (Admin Control Panel) -->
        <section class="bg-white rounded-2xl shadow-lg p-6 flex flex-col justify-between border border-slate-200">
            <div>
                <div class="flex justify-between items-center mb-4 border-b pb-2">
                    <h2 class="text-xl font-bold text-indigo-700">⚙️ ควบคุมและจัดลำดับคิว</h2>
                    <button onclick="resetAllQueues()" class="text-xs text-rose-500 hover:text-rose-700 font-medium">ล้างข้อมูลทั้งหมด</button>
                </div>

                <div class="mb-4">
                    <label class="block text-xs font-medium text-slate-600 mb-1">ระบุช่องบริการของคุณ:</label>
                    <input type="text" id="admin-counter-name" value="ช่องบริการที่ 1" class="w-full text-sm border border-slate-300 rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500">
                </div>

                <div class="space-y-2 max-h-80 overflow-y-auto pr-1" id="admin-queue-table">
                    <!-- รายการคิวทั้งหมดสำหรับจัดการ -->
                </div>
            </div>

            <div class="mt-4 pt-4 border-t border-slate-100 flex gap-2">
                <button onclick="callNextQueue()" class="flex-1 bg-emerald-600 hover:bg-emerald-700 text-white font-medium py-2.5 px-4 rounded-xl text-sm transition shadow">
                    📢 เรียกคิวถัดไป
                </button>
                <button onclick="repeatCallQueue()" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium py-2.5 px-4 rounded-xl text-sm transition">
                    🔄 เรียกซ้ำ
                </button>
            </div>
        </section>

    </main>

    <!-- Hidden Printable Area for A5 Ticket -->
    <div id="print-area" class="hidden">
        <div style="text-align: center; border-bottom: 2px dashed #333; padding-bottom: 20px; margin-bottom: 20px;">
            <h2 style="font-size: 24px; font-weight: bold; margin: 0;">บัตรคิวบริการ</h2>
            <p style="font-size: 14px; color: #666; margin: 5px 0;">กรุณารอเรียกหมายเลขที่หน้าจอแสดงผล</p>
        </div>
        <div style="text-align: center; margin: 40px 0;">
            <span style="font-size: 20px; color: #444; display: block;">หมายเลขคิวของคุณ</span>
            <h1 id="print-queue-num" style="font-size: 72px; font-weight: bold; color: #4f46e5; margin: 10px 0;">--</h1>
            <p id="print-queue-time" style="font-size: 14px; color: #666;">เวลา: --</p>
        </div>
        <div style="margin-top: 50px; font-size: 14px; color: #444; text-align: center;">
            <p>ขอบคุณที่ใช้บริการครับ/ค่ะ</p>
            <p style="font-size: 12px; color: #888; margin-top: 20px;">พิมพ์ผ่านระบบ Wi-Fi (ขนาด A5)</p>
        </div>
    </div>

    <!-- JavaScript Logic -->
    <script>
        // โหลดข้อมูลจาก LocalStorage หรือตั้งค่าเริ่มต้น
        let queues = JSON.parse(localStorage.getItem('queues')) || [];
        let currentCalled = JSON.parse(localStorage.getItem('currentCalled')) || null;
        let lastCreatedTicket = null;
        let audioEnabled = true;

        // นาฬิกาแสดงผลเรียลไทม์
        setInterval(() => {
            const now = new Date();
            document.getElementById('clock').innerText = now.toLocaleTimeString('th-TH');
        }, 1000);

        function saveState() {
            localStorage.setItem('queues', JSON.stringify(queues));
            localStorage.setItem('currentCalled', JSON.stringify(currentCalled));
            renderAll();
        }

        // 1. ฟังก์ชันสร้างคิวใหม่
        function createQueue(prefix) {
            const count = queues.filter(q => q.prefix === prefix).length + 1;
            const number = `${prefix}${String(count).padStart(3, '0')}`;
            const newQueue = {
                id: Date.now(),
                number: number,
                prefix: prefix,
                status: 'waiting', // waiting, called, completed, skipped
                time: new Date().toLocaleTimeString('th-TH', { hour: '2-digit', minute: '2-digit' })
            };

            queues.push(newQueue);
            lastCreatedTicket = newQueue;
            
            // แสดงการ์ดคิวล่าสุด
            document.getElementById('latest-ticket-card').classList.remove('hidden');
            document.getElementById('my-queue-number').innerText = newQueue.number;
            document.getElementById('my-queue-time').innerText = `เวลาจอง: ${newQueue.time}`;
            
            saveState();
        }

        // 2. สั่งพิมพ์สลิปขนาด A5 ผ่าน Wi-Fi / Browser Print
        function printTicket() {
            if (!lastCreatedTicket) return;
            document.getElementById('print-queue-num').innerText = lastCreatedTicket.number;
            document.getElementById('print-queue-time').innerText = `เวลา: ${lastCreatedTicket.time}`;
            window.print();
        }

        // 3. ระบบเสียงพูดภาษาไทย (Speech Synthesis)
        function speakQueue(text) {
            if (!audioEnabled || !('speechSynthesis' in window)) return;
            window.speechSynthesis.cancel(); // ยกเสียงค้างก่อนหน้า
            const utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = 'th-TH';
            utterance.rate = 0.9; // ความเร็วพอดีฟังชัด
            window.speechSynthesis.speak(utterance);
        }

        function toggleAudio() {
            audioEnabled = !audioEnabled;
            const btn = document.getElementById('audio-btn');
            if (audioEnabled) {
                btn.className = "bg-emerald-500 hover:bg-emerald-600 px-3 py-1.5 rounded-lg text-sm font-medium transition flex items-center gap-1 shadow";
                btn.innerHTML = "🔊 เปิด/ปิด เสียงเรียกคิว";
                speak("เปิดระบบเสียงแล้วครับ");
            } else {
                btn.className = "bg-slate-600 hover:bg-slate-700 px-3 py-1.5 rounded-lg text-sm font-medium transition flex items-center gap-1 shadow";
                btn.innerHTML = "🔇 ปิดเสียงอยู่";
            }
        }

        // 4. แอดมิน: เรียกคิวถัดไปอัตโนมัติ
        function callNextQueue() {
            const nextIndex = queues.findIndex(q => q.status === 'waiting');
            if (nextIndex === -1) {
                alert("ไม่มีคิวรอในขณะนี้ครับ");
                return;
            }

            // ถ้ามีคิวที่กำลังเรียกอยู่เดิม ให้เปลี่ยนสถานะเป็น completed
            queues.forEach(q => {
                if (q.status === 'called') q.status = 'completed';
            });

            const targetQueue = queues[nextIndex];
            targetQueue.status = 'called';
            currentCalled = targetQueue;

            const counterName = document.getElementById('admin-counter-name').value || "ช่องบริการ";
            
            // แปลงหมายเลขคิวให้อ่านออกเสียงง่าย เช่น A001 -> เอ ศูนย์ ศูนย์ หนึ่ง
            let spelledNumber = targetQueue.number.split('').map(char => {
                if(char === 'A') return 'เอ';
                if(char === 'B') return 'บี';
                return char;
            }).join(' ');

            const announcement = `ขอเชิญหมายเลข ${spelledNumber} ที่ ${counterName} ครับ`;
            speak(announcement);

            saveState();
        }

        function repeatCallQueue() {
            if (!currentCalled) {
                alert("ยังไม่มีคิวที่กำลังเรียกในขณะนี้");
                return;
            }
            const counterName = document.getElementById('admin-counter-name').value || "ช่องบริการ";
            let spelledNumber = currentCalled.number.split('').map(char => {
                if(char === 'A') return 'เอ';
                if(char === 'B') return 'บี';
                return char;
            }).join(' ');

            speak(`ขอเชิญหมายเลข ${spelledNumber} ที่ ${counterName} อีกครั้งครับ`);
        }

        // 5. แอดมิน: สลับลำดับคิวขึ้น / ลง (ลัดคิว)
        function moveQueue(index, direction) {
            const targetIndex = index + direction;
            if (targetIndex < 0 || targetIndex >= queues.length) return;
            
            // สลับตำแหน่งในอาเรย์
            const temp = queues[index];
            queues[index] = queues[targetIndex];
            queues[targetIndex] = temp;
            
            saveState();
        }

        function updateQueueStatus(id, newStatus) {
            const q = queues.find(item => item.id === id);
            if (q) {
                q.status = newStatus;
                if(newStatus === 'called') currentCalled = q;
                saveState();
            }
        }

        function deleteQueue(id) {
            queues = queues.filter(item => item.id !== id);
            saveState();
        }

        function resetAllQueues() {
            if(confirm("คุณต้องการล้างข้อมูลคิวทั้งหมดใช่หรือไม่?")) {
                queues = [];
                currentCalled = null;
                lastCreatedTicket = null;
                document.getElementById('latest-ticket-card').classList.add('hidden');
                localStorage.clear();
                saveState();
            }
        }

        // 6. เรนเดอร์ข้อมูลแสดงผลทั้งหมดบนหน้าจอ
        function renderAll() {
            // อัพเดตหน้าจอแสดงผลหลัก (Display Screen)
            const currentDisplay = document.getElementById('current-called-queue');
            const currentCounterText = document.getElementById('current-counter');
            const nextListContainer = document.getElementById('next-queue-list');
            const adminTable = document.getElementById('admin-queue-table');

            if (currentCalled) {
                currentDisplay.innerText = currentCalled.number;
                currentCounterText.innerText = `สถานะ: กำลังรับบริการ (${currentCalled.time})`;
            } else {
                currentDisplay.innerText = "--";
                currentCounterText.innerText = `ช่องบริการที่: -`;
            }

            // กรองคิวที่กำลังรอ
            const waitingQueues = queues.filter(q => q.status === 'waiting');
            if (waitingQueues.length > 0) {
                nextListContainer.innerHTML = waitingQueues.slice(0, 4).map((q, idx) => `
                    <div class="flex justify-between items-center bg-slate-800 px-4 py-2.5 rounded-xl border border-slate-700 text-sm">
                        <span class="font-bold text-amber-300 text-base">${q.number}</span>
                        <span class="text-xs text-slate-400">คิวที่ ${idx + 1} (${q.time})</span>
                    </div>
                `).join('');
            } else {
                nextListContainer.innerHTML = `<div class="text-slate-500 text-sm text-center py-4 bg-slate-800/50 rounded-xl">ไม่มีคิวรอ</div>`;
            }

            // เรนเดอร์ตารางจัดการแอดมิน
            if (queues.length > 0) {
                adminTable.innerHTML = queues.map((q, index) => `
                    <div class="flex items-center justify-between p-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm">
                        <div class="flex items-center gap-2">
                            <span class="font-bold text-indigo-600 w-12">${q.number}</span>
                            <span class="text-xs px-2 py-0.5 rounded-full ${
                                q.status === 'waiting' ? 'bg-amber-100 text-amber-700' :
                                q.status === 'called' ? 'bg-emerald-100 text-emerald-700' :
                                q.status === 'completed' ? 'bg-blue-100 text-blue-700' : 'bg-slate-200 text-slate-600'
                            }">${q.status}</span>
                        </div>
                        <div class="flex items-center gap-1">
                            ${q.status === 'waiting' ? `
                                <button onclick="moveQueue(${index}, -1)" title="เลื่อนขึ้น" class="p-1 hover:bg-slate-200 rounded text-xs text-slate-600">⬆️</button>
                                <button onclick="moveQueue(${index}, 1)" title="เลื่อนลง" class="p-1 hover:bg-slate-200 rounded text-xs text-slate-600">⬇️</button>
                            ` : ''}
                            <select onchange="updateQueueStatus(${q.id}, this.value)" class="text-xs border border-slate-300 rounded px-1.5 py-1 bg-white">
                                <option value="waiting" ${q.status === 'waiting' ? 'selected' : ''}>รอ</option>
                                <option value="called" ${q.status === 'called' ? 'selected' : ''}>กำลังเรียก</option>
                                <option value="completed" ${q.status === 'completed' ? 'selected' : ''}>เสร็จสิ้น</option>
                                <option value="skipped" ${q.status === 'skipped' ? 'selected' : ''}>ข้าม</option>
                            </select>
                            <button onclick="deleteQueue(${q.id})" class="text-rose-500 hover:text-rose-700 text-xs px-1">✕</button>
                        </div>
                    </div>
                `).join('');
            } else {
                adminTable.innerHTML = `<div class="text-slate-400 text-sm text-center py-6">ยังไม่มีรายการคิวในระบบ</div>`;
            }
        }

        // โหลดแสดงผลครั้งแรก
        renderAll();
    </script>
</body>
</html>
