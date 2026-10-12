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
        
        /* ตั้งค่าสำหรับการพิมพ์ออกกระดาษ A5 แผ่นเดียวเป๊ะๆ */
        @media print {
            body * {
                visibility: hidden;
            }
            #print-area, #print-area * {
                visibility: visible;
            }
            #print-area {
                position: absolute;
                left: 0;
                top: 0;
                width: 148mm;
                height: 210mm;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                background: white;
                margin: 0;
                padding: 0;
            }
            @page {
                size: A5 portrait;
                margin: 0;
            }
        }
    </style>
</head>
<body class="bg-slate-100 min-h-screen text-slate-800" onclick="initAudioUserGesture()">

    <!-- Header -->
    <header class="bg-indigo-600 text-white shadow-md p-4 flex justify-between items-center">
        <h1 class="text-xl font-bold">🎫 ระบบจัดการและจองคิวออนไลน์</h1>
        <div class="flex items-center gap-4">
            <button onclick="toggleAudio(event)" id="audio-btn" class="bg-emerald-500 hover:bg-emerald-600 px-3 py-1.5 rounded-lg text-sm font-medium transition flex items-center gap-1 shadow cursor-pointer">
                🔊 เปิด/ปิด เสียงเรียกคิว
            </button>
            <span id="clock" class="text-sm bg-indigo-700 px-3 py-1 rounded-full"></span>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-4 md:p-6 grid grid-cols-1 lg:grid-cols-3 gap-6">
        
        <!-- ส่วนที่ 1: หน้าจอรับคิว / กดจองคิว (Customer Panel) -->
        <section class="bg-white rounded-2xl shadow-lg p-6 flex flex-col justify-between border border-slate-200
