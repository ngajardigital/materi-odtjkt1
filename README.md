# materi-odtjkt1
Materi Orientasi Dasar TJKT Fase E kelas X Kurikulum Merdeka
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presentasi Komponen Komputer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #333;
        }

        .presentation-container {
            width: 95%;
            max-width: 1200px;
            height: 90vh;
            background: white;
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            position: relative;
        }

        .slide {
            display: none;
            padding: 60px;
            height: 100%;
            overflow-y: auto;
            animation: slideIn 0.5s ease-in-out;
        }

        .slide.active {
            display: block;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateX(30px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .slide-header {
            text-align: center;
            margin-bottom: 40px;
            padding-bottom: 20px;
            border-bottom: 3px solid #3498db;
        }

        .slide-title {
            font-size: 2.5rem;
            color: #2c3e50;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #3498db, #9b59b6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .slide-subtitle {
            font-size: 1.2rem;
            color: #7f8c8d;
        }

        .content-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .content-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .content-visual {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 400px;
        }

        .definition-box {
            background: linear-gradient(135deg, #e8f5e8, #d4edda);
            border-left: 5px solid #28a745;
            padding: 25px;
            border-radius: 10px;
            margin-bottom: 25px;
        }

        .definition-box h3 {
            color: #155724;
            font-size: 1.4rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .function-list {
            list-style: none;
            padding: 0;
        }

        .function-item {
            background: linear-gradient(135deg, #fff, #f8f9fa);
            margin-bottom: 15px;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #3498db;
            transition: transform 0.3s ease;
        }

        .function-item:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .function-item h4 {
            color: #2c3e50;
            font-size: 1.2rem;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .specs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 25px;
        }

        .spec-card {
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border: 2px solid #e9ecef;
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .spec-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border-color: #3498db;
        }

        .spec-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            display: block;
        }

        /* Motherboard Visual */
        .motherboard-visual {
            width: 400px;
            height: 300px;
            background: #0a4d3a;
            border-radius: 10px;
            position: relative;
            border: 2px solid #1a7a5e;
            overflow: hidden;
        }

        .circuit-pattern {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                linear-gradient(90deg, rgba(26, 122, 94, 0.3) 1px, transparent 1px),
                linear-gradient(rgba(26, 122, 94, 0.3) 1px, transparent 1px);
            background-size: 15px 15px;
        }

        .mb-component {
            position: absolute;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        .cpu-socket {
            top: 80px;
            left: 100px;
            width: 60px;
            height: 60px;
            background: #2a2a2a;
            border: 2px solid #ff4757;
            animation: pulse-red 2s infinite;
        }

        .ram-slots {
            top: 40px;
            right: 60px;
            width: 80px;
            height: 60px;
            background: #333;
            border: 2px solid #ffa502;
            animation: pulse-orange 2s infinite;
        }

        .pcie-slots {
            bottom: 80px;
            left: 50px;
            width: 120px;
            height: 40px;
            background: #2a2a2a;
            border: 2px solid #2ed573;
            animation: pulse-green 2s infinite;
        }

        .power-connector {
            top: 20px;
            right: 20px;
            width: 40px;
            height: 20px;
            background: #1a1a1a;
            border: 2px solid #3742fa;
        }

        @keyframes pulse-red {
            0%, 100% { box-shadow: 0 0 0 0 rgba(255, 71, 87, 0.7); }
            50% { box-shadow: 0 0 0 8px rgba(255, 71, 87, 0); }
        }

        @keyframes pulse-orange {
            0%, 100% { box-shadow: 0 0 0 0 rgba(255, 165, 2, 0.7); }
            50% { box-shadow: 0 0 0 8px rgba(255, 165, 2, 0); }
        }

        @keyframes pulse-green {
            0%, 100% { box-shadow: 0 0 0 0 rgba(46, 213, 115, 0.7); }
            50% { box-shadow: 0 0 0 8px rgba(46, 213, 115, 0); }
        }

        .mb-labels {
            position: absolute;
            font-size: 10px;
            font-weight: bold;
            color: white;
            background: rgba(0, 0, 0, 0.7);
            padding: 2px 6px;
            border-radius: 3px;
        }

        .label-cpu { top: 60px; left: 80px; color: #ff4757; }
        .label-ram { top: 20px; right: 40px; color: #ffa502; }
        .label-pcie { bottom: 60px; left: 30px; color: #2ed573; }

        /* CPU Visual */
        .cpu-visual {
            width: 200px;
            height: 200px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 15px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        .cpu-chip {
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            border-radius: 8px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            animation: cpuPulse 2s infinite;
        }

        .cpu-chip::before {
            content: '🧠';
            font-size: 3rem;
            animation: rotate 4s linear infinite;
        }

        .cpu-pins {
            position: absolute;
            bottom: -10px;
            left: 10px;
            right: 10px;
            height: 20px;
            background: linear-gradient(90deg, #bdc3c7 0%, #95a5a6 50%, #bdc3c7 100%);
            border-radius: 0 0 8px 8px;
        }

        .cpu-pins::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 100%;
            background-image: repeating-linear-gradient(90deg, #7f8c8d 0px, #7f8c8d 2px, transparent 2px, transparent 4px);
        }

        @keyframes cpuPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* RAM Visual */
        .ram-visual {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .ram-stick {
            width: 40px;
            height: 200px;
            background: linear-gradient(135deg, #27ae60, #2ecc71);
            border-radius: 8px;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            animation: ramGlow 3s infinite alternate;
        }

        .ram-stick::before {
            content: '';
            position: absolute;
            top: 10px;
            left: 5px;
            right: 5px;
            bottom: 10px;
            background: #1e8449;
            border-radius: 4px;
        }

        .ram-stick::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 20px;
            height: 2px;
            background: #f39c12;
            box-shadow: 0 -20px 0 #f39c12, 0 -10px 0 #f39c12, 0 10px 0 #f39c12, 0 20px 0 #f39c12;
        }

        @keyframes ramGlow {
            0% { box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2); }
            100% { box-shadow: 0 5px 25px rgba(46, 204, 113, 0.4); }
        }

        .data-flow {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .data-particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #3498db;
            border-radius: 50%;
            animation: dataFlow 2s linear infinite;
        }

        @keyframes dataFlow {
            0% { transform: translateY(0) scale(0); opacity: 0; }
            10% { opacity: 1; transform: scale(1); }
            90% { opacity: 1; }
            100% { transform: translateY(-200px) scale(0); opacity: 0; }
        }

        /* GPU Visual Styles */
        .gpu-visual {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .gpu-card {
            width: 300px;
            height: 120px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 10px;
            position: relative;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .gpu-chip {
            position: absolute;
            top: 20px;
            left: 50px;
            width: 80px;
            height: 40px;
            background: linear-gradient(135deg, #e74c3c, #c0392b);
            border-radius: 5px;
            animation: gpuPulse 2s infinite;
        }

        .gpu-fans {
            position: absolute;
            top: 15px;
            right: 30px;
            display: flex;
            gap: 10px;
        }

        .gpu-fan {
            width: 30px;
            height: 30px;
            border: 3px solid #95a5a6;
            border-radius: 50%;
            border-top-color: #3498db;
            animation: spin 1s linear infinite;
        }

        .gpu-ports {
            position: absolute;
            bottom: 10px;
            right: 20px;
            width: 60px;
            height: 15px;
            background: #7f8c8d;
            border-radius: 3px;
        }

        .visual-effects {
            display: flex;
            gap: 10px;
        }

        .pixel-stream {
            width: 4px;
            height: 60px;
            background: linear-gradient(to top, transparent, #3498db, transparent);
            animation: pixelFlow 1.5s infinite;
        }

        .pixel-stream:nth-child(2) { animation-delay: 0.3s; }
        .pixel-stream:nth-child(3) { animation-delay: 0.6s; }

        @keyframes gpuPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes pixelFlow {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Storage Visual Styles */
        .storage-visual {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 30px;
        }

        .storage-device {
            width: 120px;
            height: 80px;
            border-radius: 8px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .hdd-device {
            background: linear-gradient(135deg, #34495e, #2c3e50);
        }

        .ssd-device {
            background: linear-gradient(135deg, #27ae60, #2ecc71);
        }

        .device-label {
            position: absolute;
            top: -25px;
            font-weight: bold;
            font-size: 1.1rem;
            color: #2c3e50;
        }

        .spinning-disk {
            width: 50px;
            height: 50px;
            border: 3px solid #95a5a6;
            border-radius: 50%;
            border-top-color: #3498db;
            animation: spin 2s linear infinite;
        }

        .flash-chips {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5px;
        }

        .chip {
            width: 20px;
            height: 15px;
            background: #1e8449;
            border-radius: 2px;
            animation: chipBlink 2s infinite alternate;
        }

        .chip:nth-child(2) { animation-delay: 0.5s; }
        .chip:nth-child(3) { animation-delay: 1s; }
        .chip:nth-child(4) { animation-delay: 1.5s; }

        @keyframes chipBlink {
            0% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        .vs-divider {
            font-size: 1.5rem;
            font-weight: bold;
            color: #e74c3c;
            background: white;
            padding: 10px 15px;
            border-radius: 50%;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .storage-comparison {
            display: grid;
            gap: 20px;
        }

        .storage-type {
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border-radius: 10px;
            padding: 20px;
            border-left: 4px solid;
        }

        .hdd-type { border-left-color: #3498db; }
        .ssd-type { border-left-color: #27ae60; }

        .pros-cons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 15px;
        }

        .pros ul, .cons ul {
            list-style: none;
            padding-left: 0;
            margin-top: 8px;
        }

        .pros li, .cons li {
            padding: 3px 0;
            font-size: 0.9rem;
        }

        /* PSU Visual Styles */
        .psu-visual {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .psu-unit {
            width: 200px;
            height: 120px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 8px;
            position: relative;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .psu-fan {
            position: absolute;
            top: 20px;
            left: 20px;
            width: 40px;
            height: 40px;
            border: 3px solid #95a5a6;
            border-radius: 50%;
            border-top-color: #f39c12;
            animation: spin 1.5s linear infinite;
        }

        .psu-cables {
            position: absolute;
            right: -30px;
            top: 10px;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .cable {
            width: 40px;
            height: 6px;
            border-radius: 3px;
        }

        .cable-24pin { background: #e74c3c; }
        .cable-8pin { background: #f39c12; }
        .cable-pcie { background: #27ae60; }
        .cable-sata { background: #3498db; }

        .power-flow {
            display: flex;
            gap: 15px;
        }

        .electricity-bolt {
            font-size: 2rem;
            color: #f1c40f;
            animation: electricFlow 1s infinite alternate;
        }

        .electricity-bolt::before {
            content: '⚡';
        }

        .electricity-bolt:nth-child(2) { animation-delay: 0.3s; }
        .electricity-bolt:nth-child(3) { animation-delay: 0.6s; }

        @keyframes electricFlow {
            0% { opacity: 0.5; transform: scale(0.8); }
            100% { opacity: 1; transform: scale(1.2); }
        }

        /* Input Devices Visual Styles */
        .input-visual {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .input-showcase {
            display: flex;
            flex-direction: column;
            gap: 30px;
            align-items: center;
        }

        .showcase-item {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .mouse-device {
            width: 60px;
            height: 40px;
            background: linear-gradient(135deg, #34495e, #2c3e50);
            border-radius: 15px 15px 8px 8px;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .mouse-device::before {
            content: '';
            position: absolute;
            top: 8px;
            left: 50%;
            transform: translateX(-50%);
            width: 2px;
            height: 15px;
            background: #95a5a6;
            border-radius: 1px;
        }

        .cursor-trail {
            width: 0;
            height: 0;
            border-left: 8px solid #3498db;
            border-top: 6px solid transparent;
            border-bottom: 6px solid transparent;
            animation: cursorBlink 1s infinite;
        }

        .keyboard-device {
            display: flex;
            gap: 3px;
            background: #34495e;
            padding: 8px;
            border-radius: 5px;
        }

        .key {
            width: 15px;
            height: 15px;
            background: #95a5a6;
            border-radius: 2px;
            transition: all 0.3s ease;
        }

        .key.active {
            background: #3498db;
            transform: translateY(2px);
        }

        .mic-device {
            width: 20px;
            height: 40px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 10px 10px 5px 5px;
            position: relative;
        }

        .mic-device::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 30px;
            height: 8px;
            background: #95a5a6;
            border-radius: 4px;
        }

        .sound-waves {
            display: flex;
            gap: 3px;
            align-items: center;
        }

        .wave {
            width: 3px;
            background: #3498db;
            border-radius: 2px;
            animation: waveAnimation 1s infinite ease-in-out;
        }

        .wave:nth-child(1) { height: 15px; animation-delay: 0s; }
        .wave:nth-child(2) { height: 25px; animation-delay: 0.2s; }
        .wave:nth-child(3) { height: 20px; animation-delay: 0.4s; }

        @keyframes cursorBlink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0.3; }
        }

        @keyframes waveAnimation {
            0%, 100% { transform: scaleY(0.5); }
            50% { transform: scaleY(1); }
        }

        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .input-devices-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .input-device {
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .input-device:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border-color: #3498db;
        }

        .device-icon {
            font-size: 2rem;
            display: block;
            margin-bottom: 10px;
        }

        .input-device h4 {
            color: #2c3e50;
            font-size: 1.1rem;
            margin-bottom: 8px;
        }

        .input-device p {
            color: #6c757d;
            font-size: 0.9rem;
        }

        /* Output Devices Visual Styles */
        .output-visual {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .output-showcase {
            display: flex;
            flex-direction: column;
            gap: 30px;
            align-items: center;
        }

        .monitor-device {
            width: 80px;
            height: 60px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 8px 8px 0 0;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .screen {
            position: absolute;
            top: 5px;
            left: 5px;
            right: 5px;
            bottom: 5px;
            background: #1a1a1a;
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .pixel-display {
            display: flex;
            flex-direction: column;
            gap: 2px;
        }

        .pixel-row {
            display: flex;
            gap: 2px;
        }

        .pixel {
            width: 6px;
            height: 6px;
            border-radius: 1px;
            animation: pixelGlow 2s infinite alternate;
        }

        .pixel.red { background: #e74c3c; }
        .pixel.green { background: #27ae60; }
        .pixel.blue { background: #3498db; }
        .pixel.yellow { background: #f1c40f; }
        .pixel.purple { background: #9b59b6; }
        .pixel.cyan { background: #1abc9c; }

        .monitor-stand {
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 30px;
            height: 15px;
            background: #95a5a6;
            border-radius: 0 0 5px 5px;
        }

        .printer-device {
            width: 70px;
            height: 40px;
            position: relative;
        }

        .printer-body {
            width: 100%;
            height: 30px;
            background: linear-gradient(135deg, #95a5a6, #7f8c8d);
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
        }

        .paper-output {
            position: absolute;
            bottom: -10px;
            left: 10px;
            right: 10px;
        }

        .paper {
            width: 100%;
            height: 15px;
            background: white;
            border: 1px solid #bdc3c7;
            border-radius: 2px;
            animation: paperSlide 3s infinite;
        }

        .speaker-device {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #2c3e50, #34495e);
            border-radius: 50%;
            position: relative;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .speaker-cone {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 30px;
            height: 30px;
            background: #34495e;
            border-radius: 50%;
            border: 3px solid #95a5a6;
        }

        .sound-waves-output {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .sound-ring {
            border: 2px solid #3498db;
            border-radius: 50%;
            animation: soundRipple 2s infinite;
        }

        .ring1 { width: 20px; height: 20px; animation-delay: 0s; }
        .ring2 { width: 30px; height: 30px; animation-delay: 0.5s; }
        .ring3 { width: 40px; height: 40px; animation-delay: 1s; }

        @keyframes pixelGlow {
            0% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        @keyframes paperSlide {
            0%, 70% { transform: translateY(0); }
            100% { transform: translateY(-5px); }
        }

        @keyframes soundRipple {
            0% { transform: scale(0.8); opacity: 1; }
            100% { transform: scale(1.5); opacity: 0; }
        }

        /* Component Interaction Visual Styles */
        .interaction-visual {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
        }

        .component-flow {
            display: flex;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .flow-component {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            padding: 15px;
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border: 2px solid #e9ecef;
            border-radius: 12px;
            transition: all 0.3s ease;
            animation: componentPulse 3s infinite;
        }

        .flow-component:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border-color: #3498db;
        }

        .comp-icon {
            font-size: 1.5rem;
        }

        .comp-label {
            font-size: 0.9rem;
            font-weight: bold;
            color: #2c3e50;
        }

        .flow-arrow {
            font-size: 1.5rem;
            color: #3498db;
            font-weight: bold;
            animation: arrowPulse 2s infinite;
        }

        .motherboard-connection {
            position: relative;
            width: 100%;
            text-align: center;
        }

        .connection-line {
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #3498db, #2ecc71, #f39c12, #e74c3c);
            border-radius: 2px;
            animation: dataTransfer 2s infinite;
        }

        .mb-label {
            margin-top: 10px;
            font-size: 0.9rem;
            color: #2c3e50;
            font-weight: bold;
        }

        @keyframes componentPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes arrowPulse {
            0%, 100% { opacity: 0.6; }
            50% { opacity: 1; }
        }

        @keyframes dataTransfer {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        /* Workflow Steps Styles */
        .workflow-steps {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .workflow-step {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border-radius: 10px;
            border-left: 4px solid #3498db;
            transition: all 0.3s ease;
        }

        .workflow-step:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .step-number {
            width: 30px;
            height: 30px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .step-content h4 {
            color: #2c3e50;
            margin-bottom: 5px;
            font-size: 1.1rem;
        }

        .step-content p {
            color: #6c757d;
            font-size: 0.95rem;
            margin: 0;
        }

        /* Conclusion Visual Styles */
        .conclusion-visual {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
        }

        .computer-puzzle {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            padding: 20px;
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .puzzle-piece {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border: 2px solid #3498db;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 5px;
            transition: all 0.3s ease;
            animation: puzzleFloat 3s infinite ease-in-out;
        }

        .puzzle-piece:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 25px rgba(52, 152, 219, 0.3);
        }

        .puzzle-piece span {
            font-size: 1.5rem;
        }

        .puzzle-piece small {
            font-size: 0.7rem;
            font-weight: bold;
            color: #2c3e50;
        }

        .piece-mb { animation-delay: 0s; }
        .piece-cpu { animation-delay: 0.5s; }
        .piece-ram { animation-delay: 1s; }
        .piece-gpu { animation-delay: 1.5s; }
        .piece-storage { animation-delay: 2s; }
        .piece-psu { animation-delay: 2.5s; }

        .completion-message {
            text-align: center;
        }

        .message-bubble {
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            padding: 20px 30px;
            border-radius: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: 0 10px 30px rgba(52, 152, 219, 0.3);
            animation: bubbleBounce 2s infinite ease-in-out;
        }

        .bubble-icon {
            font-size: 1.5rem;
        }

        .message-bubble p {
            margin: 0;
            font-size: 1.1rem;
            font-weight: 500;
        }

        @keyframes puzzleFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes bubbleBounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Summary and QA Styles */
        .conclusion-summary {
            margin-bottom: 30px;
        }

        .summary-point {
            display: flex;
            align-items: flex-start;
            gap: 15px;
            margin-bottom: 20px;
            padding: 15px;
            background: linear-gradient(135deg, #fff, #f8f9fa);
            border-radius: 10px;
            border-left: 4px solid #3498db;
            transition: all 0.3s ease;
        }

        .summary-point:hover {
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .summary-icon {
            font-size: 1.5rem;
            margin-top: 2px;
        }

        .summary-point p {
            margin: 0;
            color: #2c3e50;
            line-height: 1.6;
        }

        .qa-section {
            display: grid;
            gap: 20px;
        }

        .qa-box, .thank-you-box {
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .qa-box {
            background: linear-gradient(135deg, #e8f5e8, #d4edda);
            border: 2px solid #28a745;
        }

        .thank-you-box {
            background: linear-gradient(135deg, #fff3cd, #ffeaa7);
            border: 2px solid #ffc107;
        }

        .qa-box:hover, .thank-you-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .qa-box h3 {
            color: #155724;
            margin-bottom: 10px;
        }

        .thank-you-box h3 {
            color: #856404;
            margin-bottom: 10px;
        }

        .qa-box p {
            color: #155724;
            margin: 0;
            font-style: italic;
        }

        .thank-you-box p {
            color: #856404;
            margin: 0;
            font-weight: 500;
        }

        /* Navigation */
        .nav-container {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 15px;
            align-items: center;
            background: rgba(255, 255, 255, 0.9);
            padding: 15px 25px;
            border-radius: 50px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }

        .nav-btn {
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        .nav-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(52, 152, 219, 0.4);
        }

        .nav-btn:disabled {
            background: #bdc3c7;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .slide-counter {
            background: #2c3e50;
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: bold;
        }

        @media (max-width: 768px) {
            .slide {
                padding: 30px 20px;
            }
            
            .content-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .slide-title {
                font-size: 1.8rem;
            }
            
            .motherboard-visual {
                width: 300px;
                height: 200px;
            }
            
            .cpu-visual {
                width: 150px;
                height: 150px;
            }
            
            .nav-container {
                flex-direction: column;
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="presentation-container">
        <!-- Slide 3: Motherboard -->
        <div class="slide active">
            <div class="slide-header">
                <h1 class="slide-title">🔧 Papan Induk (Motherboard)</h1>
                <p class="slide-subtitle">Jantung & Tulang Punggung Komputer</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu Motherboard?</h3>
                        <p>Papan sirkuit utama tempat semua komponen penting komputer terpasang dan saling terhubung. Bayangkan seperti <strong>"jalan raya utama"</strong> di kota komputer Anda.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin-bottom: 20px; font-size: 1.4rem;">⚙️ Fungsi Utama:</h3>
                    
                    <ul class="function-list">
                        <li class="function-item">
                            <h4>🔗 Penghubung</h4>
                            <p>Menghubungkan CPU, RAM, kartu grafis, penyimpanan, dan komponen lainnya agar bisa "berkomunikasi" satu sama lain.</p>
                        </li>
                        
                        <li class="function-item">
                            <h4>⚡ Penyedia Daya</h4>
                            <p>Mendistribusikan listrik ke berbagai komponen dengan tegangan yang tepat.</p>
                        </li>
                        
                        <li class="function-item">
                            <h4>🏠 Rumah</h4>
                            <p>Menjadi tempat tinggal bagi 'otak' dan 'memori' komputer serta komponen penting lainnya.</p>
                        </li>
                    </ul>
                </div>
                
                <div class="content-visual">
                    <div class="motherboard-visual">
                        <div class="circuit-pattern"></div>
                        
                        <div class="mb-component cpu-socket"></div>
                        <div class="mb-component ram-slots"></div>
                        <div class="mb-component pcie-slots"></div>
                        <div class="mb-component power-connector"></div>
                        
                        <div class="mb-labels label-cpu">CPU Socket</div>
                        <div class="mb-labels label-ram">RAM Slots</div>
                        <div class="mb-labels label-pcie">PCIe Slots</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 4: CPU -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🧠 CPU (Central Processing Unit)</h1>
                <p class="slide-subtitle">Otak Komputer Kita</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu CPU?</h3>
                        <p>Komponen utama yang berfungsi sebagai <strong>"otak"</strong> komputer. Dia melakukan semua perhitungan, memproses instruksi, dan menjalankan semua program.</p>
                    </div>
                    
                    <div class="function-item">
                        <h4>⚙️ Fungsi Utama</h4>
                        <p>Mengeksekusi instruksi dari program, mengelola aliran data, dan melakukan operasi matematika serta logika. Tanpa CPU, komputer hanyalah benda mati.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Spesifikasi Penting:</h3>
                    
                    <div class="specs-grid">
                        <div class="spec-card">
                            <span class="spec-icon">🔄</span>
                            <h4>Core (Inti)</h4>
                            <p>Ibarat jumlah "otak kecil" di dalam CPU. Makin banyak core, makin banyak tugas yang bisa dikerjakan bersamaan.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">⚡</span>
                            <h4>GHz (Kecepatan)</h4>
                            <p>Mengukur kecepatan CPU dalam memproses instruksi. Angka lebih tinggi biasanya berarti lebih cepat.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">🏭</span>
                            <h4>Merek Populer</h4>
                            <p><strong>Intel</strong> dan <strong>AMD</strong> adalah dua produsen CPU terbesar di dunia.</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="cpu-visual">
                        <div class="cpu-chip"></div>
                        <div class="cpu-pins"></div>
                        
                        <div class="data-flow">
                            <div class="data-particle" style="left: 20%; animation-delay: 0s;"></div>
                            <div class="data-particle" style="left: 40%; animation-delay: 0.5s;"></div>
                            <div class="data-particle" style="left: 60%; animation-delay: 1s;"></div>
                            <div class="data-particle" style="left: 80%; animation-delay: 1.5s;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 5: RAM -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">💾 RAM (Random Access Memory)</h1>
                <p class="slide-subtitle">Memori Jangka Pendek yang Super Cepat</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu RAM?</h3>
                        <p>Memori tempat komputer menyimpan data yang sedang aktif atau program yang sedang berjalan untuk sementara waktu. Bayangkan seperti <strong>"meja kerja"</strong> CPU yang sangat luas.</p>
                    </div>
                    
                    <div class="function-item">
                        <h4>⚡ Fungsi Utama</h4>
                        <p>Mempercepat akses data dan program. Ketika Anda membuka banyak aplikasi atau tab browser, RAM berperan penting agar semuanya berjalan lancar.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Peran Penting:</h3>
                    
                    <div class="specs-grid">
                        <div class="spec-card">
                            <span class="spec-icon">🔄</span>
                            <h4>Multitasking</h4>
                            <p>Semakin besar RAM, semakin banyak aplikasi yang bisa Anda jalankan bersamaan tanpa melambat.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">⚡</span>
                            <h4>Kecepatan Data</h4>
                            <p>RAM jauh lebih cepat dari penyimpanan jangka panjang (HDD/SSD), sehingga data yang sering diakses disimpan di sini.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">📊</span>
                            <h4>Kapasitas & Jenis</h4>
                            <p>Umumnya diukur dalam GB (8GB, 16GB, 32GB). Jenis terbaru seperti DDR4 dan DDR5 menawarkan kecepatan tinggi.</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="ram-visual">
                        <div class="ram-stick" style="animation-delay: 0s;"></div>
                        <div class="ram-stick" style="animation-delay: 0.5s;"></div>
                        <div class="ram-stick" style="animation-delay: 1s;"></div>
                        <div class="ram-stick" style="animation-delay: 1.5s;"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 6: GPU -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🎮 GPU (Graphics Processing Unit)</h1>
                <p class="slide-subtitle">Otak Visual Komputer</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu GPU?</h3>
                        <p>Komponen khusus yang bertugas memproses semua yang berhubungan dengan tampilan visual di layar Anda.</p>
                    </div>
                    
                    <div class="function-item">
                        <h4>🎨 Fungsi Utama</h4>
                        <p>Menggambar gambar, video, animasi, dan grafis 3D dengan sangat cepat.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Pentingnya untuk:</h3>
                    
                    <div class="specs-grid">
                        <div class="spec-card">
                            <span class="spec-icon">🎮</span>
                            <h4>Gaming</h4>
                            <p>Menampilkan grafis game yang realistis dan detail dengan frame rate tinggi.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">🎬</span>
                            <h4>Desain & Video</h4>
                            <p>Mempercepat proses rendering gambar dan video resolusi tinggi.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">🥽</span>
                            <h4>Virtual Reality</h4>
                            <p>Menghadirkan pengalaman visual VR yang mulus dan realistis.</p>
                        </div>
                    </div>
                    
                    <div style="margin-top: 25px; padding: 20px; background: linear-gradient(135deg, #fff3cd, #ffeaa7); border-radius: 10px; border-left: 4px solid #ffc107;">
                        <h4 style="color: #856404; margin-bottom: 10px;">📋 Jenis GPU:</h4>
                        <p style="color: #856404; margin-bottom: 8px;"><strong>Terintegrasi:</strong> Intel Iris Xe, AMD Radeon Graphics</p>
                        <p style="color: #856404;"><strong>Dedicated:</strong> NVIDIA GeForce, AMD Radeon</p>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="gpu-visual">
                        <div class="gpu-card">
                            <div class="gpu-chip"></div>
                            <div class="gpu-fans">
                                <div class="gpu-fan"></div>
                                <div class="gpu-fan"></div>
                            </div>
                            <div class="gpu-ports"></div>
                        </div>
                        <div class="visual-effects">
                            <div class="pixel-stream"></div>
                            <div class="pixel-stream"></div>
                            <div class="pixel-stream"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 7: Storage -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">💽 Penyimpanan Data (HDD/SSD)</h1>
                <p class="slide-subtitle">Gudang Ingatan Komputer</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu Penyimpanan Data?</h3>
                        <p>Tempat komputer menyimpan semua file, program, dan sistem operasi secara permanen, bahkan saat komputer dimatikan. Bayangkan seperti <strong>"perpustakaan"</strong> tempat semua buku komputer Anda tersimpan.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">💾 Dua Jenis Utama:</h3>
                    
                    <div class="storage-comparison">
                        <div class="storage-type hdd-type">
                            <h4>🔵 HDD (Hard Disk Drive)</h4>
                            <p><strong>Teknologi:</strong> Piringan magnetik berputar</p>
                            <div class="pros-cons">
                                <div class="pros">
                                    <strong>✅ Kelebihan:</strong>
                                    <ul>
                                        <li>Kapasitas besar</li>
                                        <li>Harga lebih murah</li>
                                    </ul>
                                </div>
                                <div class="cons">
                                    <strong>❌ Kekurangan:</strong>
                                    <ul>
                                        <li>Lambat</li>
                                        <li>Rentan guncangan</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                        
                        <div class="storage-type ssd-type">
                            <h4>🟢 SSD (Solid State Drive)</h4>
                            <p><strong>Teknologi:</strong> Chip memori flash</p>
                            <div class="pros-cons">
                                <div class="pros">
                                    <strong>✅ Kelebihan:</strong>
                                    <ul>
                                        <li>Super cepat</li>
                                        <li>Lebih awet & hemat energi</li>
                                    </ul>
                                </div>
                                <div class="cons">
                                    <strong>❌ Kekurangan:</strong>
                                    <ul>
                                        <li>Kapasitas lebih kecil</li>
                                        <li>Harga lebih mahal</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="storage-visual">
                        <div class="storage-device hdd-device">
                            <div class="device-label">HDD</div>
                            <div class="spinning-disk"></div>
                        </div>
                        <div class="vs-divider">VS</div>
                        <div class="storage-device ssd-device">
                            <div class="device-label">SSD</div>
                            <div class="flash-chips">
                                <div class="chip"></div>
                                <div class="chip"></div>
                                <div class="chip"></div>
                                <div class="chip"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 8: PSU -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">⚡ PSU (Power Supply Unit)</h1>
                <p class="slide-subtitle">Sumber Energi Vital</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu PSU?</h3>
                        <p>Komponen yang berfungsi mengubah listrik dari stop kontak menjadi daya yang bisa digunakan oleh semua komponen komputer.</p>
                    </div>
                    
                    <div class="function-item">
                        <h4>🔌 Fungsi Utama</h4>
                        <p>Menyediakan "makanan" berupa listrik dengan voltase yang tepat ke setiap bagian komputer (Motherboard, CPU, GPU, dll.).</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Pentingnya Pemilihan PSU yang Tepat:</h3>
                    
                    <div class="specs-grid">
                        <div class="spec-card">
                            <span class="spec-icon">🛡️</span>
                            <h4>Kestabilan</h4>
                            <p>PSU yang bagus memastikan listrik stabil, mencegah kerusakan komponen.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">⚡</span>
                            <h4>Kecukupan Daya</h4>
                            <p>Harus cukup kuat untuk menyuplai daya ke semua komponen, terutama GPU yang haus daya.</p>
                        </div>
                        
                        <div class="spec-card">
                            <span class="spec-icon">🌱</span>
                            <h4>Efisiensi</h4>
                            <p>PSU yang efisien lebih hemat listrik dan menghasilkan sedikit panas.</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="psu-visual">
                        <div class="psu-unit">
                            <div class="psu-fan"></div>
                            <div class="psu-cables">
                                <div class="cable cable-24pin"></div>
                                <div class="cable cable-8pin"></div>
                                <div class="cable cable-pcie"></div>
                                <div class="cable cable-sata"></div>
                            </div>
                        </div>
                        <div class="power-flow">
                            <div class="electricity-bolt"></div>
                            <div class="electricity-bolt"></div>
                            <div class="electricity-bolt"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 9: Input Devices -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🖱️ Perangkat Input</h1>
                <p class="slide-subtitle">Cara Kita Berbicara dengan Komputer</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu Perangkat Input?</h3>
                        <p>Alat yang kita gunakan untuk memasukkan data atau perintah ke dalam komputer. Ini seperti <strong>"indera"</strong> komputer yang menerima informasi dari kita.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Contoh & Fungsi:</h3>
                    
                    <div class="input-devices-grid">
                        <div class="input-device">
                            <span class="device-icon">🖱️</span>
                            <h4>Mouse</h4>
                            <p>Untuk menggerakkan kursor, memilih, dan mengklik objek di layar.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">⌨️</span>
                            <h4>Keyboard</h4>
                            <p>Untuk mengetik teks, angka, dan memberikan perintah.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">🎤</span>
                            <h4>Mikrofon</h4>
                            <p>Untuk memasukkan suara (rekaman, panggilan video).</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">📷</span>
                            <h4>Webcam</h4>
                            <p>Untuk memasukkan gambar bergerak atau video.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">🖨️</span>
                            <h4>Scanner</h4>
                            <p>Untuk mengubah dokumen fisik menjadi digital.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">📱</span>
                            <h4>Touchscreen</h4>
                            <p>Layar yang bisa langsung menerima sentuhan sebagai input.</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="input-visual">
                        <div class="input-showcase">
                            <div class="showcase-item mouse-showcase">
                                <div class="mouse-device"></div>
                                <div class="cursor-trail"></div>
                            </div>
                            <div class="showcase-item keyboard-showcase">
                                <div class="keyboard-device">
                                    <div class="key"></div>
                                    <div class="key"></div>
                                    <div class="key"></div>
                                    <div class="key active"></div>
                                    <div class="key"></div>
                                </div>
                            </div>
                            <div class="showcase-item mic-showcase">
                                <div class="mic-device"></div>
                                <div class="sound-waves">
                                    <div class="wave"></div>
                                    <div class="wave"></div>
                                    <div class="wave"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 10: Output Devices -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🖥️ Perangkat Output</h1>
                <p class="slide-subtitle">Cara Komputer Berbicara dengan Kita</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Apa Itu Perangkat Output?</h3>
                        <p>Alat yang digunakan komputer untuk menampilkan atau menghasilkan data yang sudah diproses agar bisa kita lihat, dengar, atau sentuh. Ini seperti <strong>"suara"</strong> atau <strong>"mata"</strong> komputer yang menyampaikan informasi kepada kita.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 20px 0; font-size: 1.4rem;">🔧 Contoh & Fungsi:</h3>
                    
                    <div class="input-devices-grid">
                        <div class="input-device">
                            <span class="device-icon">🖥️</span>
                            <h4>Monitor</h4>
                            <p>Menampilkan gambar dan teks visual dari komputer.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">🖨️</span>
                            <h4>Printer</h4>
                            <p>Mencetak dokumen digital ke kertas fisik.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">🔊</span>
                            <h4>Speaker</h4>
                            <p>Menghasilkan suara dari data audio komputer.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">🎧</span>
                            <h4>Headphone</h4>
                            <p>Menghasilkan suara pribadi langsung ke telinga.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">📽️</span>
                            <h4>Projector</h4>
                            <p>Memproyeksikan tampilan komputer ke layar besar.</p>
                        </div>
                        
                        <div class="input-device">
                            <span class="device-icon">📳</span>
                            <h4>Vibrator</h4>
                            <p>Memberikan feedback sentuhan (gamepad/HP).</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="output-visual">
                        <div class="output-showcase">
                            <div class="showcase-item monitor-showcase">
                                <div class="monitor-device">
                                    <div class="screen">
                                        <div class="pixel-display">
                                            <div class="pixel-row">
                                                <div class="pixel red"></div>
                                                <div class="pixel green"></div>
                                                <div class="pixel blue"></div>
                                            </div>
                                            <div class="pixel-row">
                                                <div class="pixel yellow"></div>
                                                <div class="pixel purple"></div>
                                                <div class="pixel cyan"></div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="monitor-stand"></div>
                                </div>
                            </div>
                            <div class="showcase-item printer-showcase">
                                <div class="printer-device">
                                    <div class="printer-body"></div>
                                    <div class="paper-output">
                                        <div class="paper"></div>
                                    </div>
                                </div>
                            </div>
                            <div class="showcase-item speaker-showcase">
                                <div class="speaker-device">
                                    <div class="speaker-cone"></div>
                                </div>
                                <div class="sound-waves-output">
                                    <div class="sound-ring ring1"></div>
                                    <div class="sound-ring ring2"></div>
                                    <div class="sound-ring ring3"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 11: Component Interaction -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🎼 Orkestra Komponen</h1>
                <p class="slide-subtitle">Bagaimana Semua Bekerja Sama?</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="definition-box">
                        <h3>🎯 Saling Terhubung</h3>
                        <p>Semua komponen yang kita bahas tadi tidak bekerja sendiri-sendiri, tapi saling terhubung dan berinteraksi melalui <strong>Motherboard</strong>.</p>
                    </div>
                    
                    <h3 style="color: #2c3e50; margin: 25px 0 15px 0; font-size: 1.4rem;">🔄 Contoh Alur Kerja:</h3>
                    
                    <div class="workflow-steps">
                        <div class="workflow-step">
                            <div class="step-number">1</div>
                            <div class="step-content">
                                <h4>🖱️ Input</h4>
                                <p>Anda mengklik mouse untuk membuka aplikasi.</p>
                            </div>
                        </div>
                        
                        <div class="workflow-step">
                            <div class="step-number">2</div>
                            <div class="step-content">
                                <h4>🧠 Processing</h4>
                                <p>Perintah diterima oleh CPU (Otak).</p>
                            </div>
                        </div>
                        
                        <div class="workflow-step">
                            <div class="step-number">3</div>
                            <div class="step-content">
                                <h4>💾 Loading</h4>
                                <p>CPU memuat aplikasi dari Storage ke RAM.</p>
                            </div>
                        </div>
                        
                        <div class="workflow-step">
                            <div class="step-number">4</div>
                            <div class="step-content">
                                <h4>🎮 Rendering</h4>
                                <p>CPU dan GPU bekerja sama memproses grafis.</p>
                            </div>
                        </div>
                        
                        <div class="workflow-step">
                            <div class="step-number">5</div>
                            <div class="step-content">
                                <h4>🖥️ Output</h4>
                                <p>Hasil ditampilkan di Monitor dan Speaker.</p>
                            </div>
                        </div>
                    </div>
                    
                    <div style="margin-top: 25px; padding: 20px; background: linear-gradient(135deg, #e8f5e8, #d4edda); border-radius: 10px; border-left: 4px solid #28a745;">
                        <h4 style="color: #155724; margin-bottom: 10px;">⚖️ Pentingnya Keselarasan:</h4>
                        <p style="color: #155724;">Komponen yang seimbang (misal: CPU kuat dengan RAM cukup) akan menghasilkan kinerja komputer yang optimal.</p>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="interaction-visual">
                        <div class="component-flow">
                            <div class="flow-component input-comp">
                                <div class="comp-icon">🖱️</div>
                                <div class="comp-label">Input</div>
                            </div>
                            
                            <div class="flow-arrow">→</div>
                            
                            <div class="flow-component cpu-comp">
                                <div class="comp-icon">🧠</div>
                                <div class="comp-label">CPU</div>
                            </div>
                            
                            <div class="flow-arrow">↕</div>
                            
                            <div class="flow-component ram-comp">
                                <div class="comp-icon">💾</div>
                                <div class="comp-label">RAM</div>
                            </div>
                            
                            <div class="flow-arrow">↕</div>
                            
                            <div class="flow-component storage-comp">
                                <div class="comp-icon">💽</div>
                                <div class="comp-label">Storage</div>
                            </div>
                            
                            <div class="flow-arrow">→</div>
                            
                            <div class="flow-component gpu-comp">
                                <div class="comp-icon">🎮</div>
                                <div class="comp-label">GPU</div>
                            </div>
                            
                            <div class="flow-arrow">→</div>
                            
                            <div class="flow-component output-comp">
                                <div class="comp-icon">🖥️</div>
                                <div class="comp-label">Output</div>
                            </div>
                        </div>
                        
                        <div class="motherboard-connection">
                            <div class="connection-line"></div>
                            <div class="mb-label">🔧 Motherboard - Penghubung Semua Komponen</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Slide 12: Conclusion -->
        <div class="slide">
            <div class="slide-header">
                <h1 class="slide-title">🎯 Kesimpulan</h1>
                <p class="slide-subtitle">Mari Berlayar di Dunia Komputer!</p>
            </div>
            
            <div class="content-grid">
                <div class="content-text">
                    <div class="conclusion-summary">
                        <h3 style="color: #2c3e50; margin-bottom: 20px; font-size: 1.4rem;">📚 Yang Telah Kita Pelajari:</h3>
                        
                        <div class="summary-point">
                            <span class="summary-icon">🤝</span>
                            <p>Komputer adalah kumpulan komponen yang bekerja sama secara harmonis.</p>
                        </div>
                        
                        <div class="summary-point">
                            <span class="summary-icon">⚙️</span>
                            <p>Setiap bagian memiliki peran krusial, mulai dari <strong>Motherboard</strong> sebagai tulang punggung, <strong>CPU</strong> sebagai otak, <strong>RAM</strong> sebagai memori kerja cepat.</p>
                        </div>
                        
                        <div class="summary-point">
                            <span class="summary-icon">🎨</span>
                            <p><strong>GPU</strong> untuk visual, <strong>HDD/SSD</strong> sebagai gudang data, hingga <strong>PSU</strong> sebagai sumber energi.</p>
                        </div>
                        
                        <div class="summary-point">
                            <span class="summary-icon">🌐</span>
                            <p>Pemahaman ini adalah fondasi penting untuk kalian yang ingin mendalami dunia <strong>jaringan komputer dan telekomunikasi</strong>.</p>
                        </div>
                    </div>
                    
                    <div class="qa-section">
                        <div class="qa-box">
                            <h3>💬 Ajakan Bertanya</h3>
                            <p>"Ada pertanyaan atau hal yang ingin kalian diskusikan lebih lanjut?"</p>
                        </div>
                        
                        <div class="thank-you-box">
                            <h3>🙏 Terima Kasih</h3>
                            <p>"Terima kasih atas perhatiannya!"</p>
                        </div>
                    </div>
                </div>
                
                <div class="content-visual">
                    <div class="conclusion-visual">
                        <div class="computer-puzzle">
                            <div class="puzzle-piece piece-mb">
                                <span>🔧</span>
                                <small>MB</small>
                            </div>
                            <div class="puzzle-piece piece-cpu">
                                <span>🧠</span>
                                <small>CPU</small>
                            </div>
                            <div class="puzzle-piece piece-ram">
                                <span>💾</span>
                                <small>RAM</small>
                            </div>
                            <div class="puzzle-piece piece-gpu">
                                <span>🎮</span>
                                <small>GPU</small>
                            </div>
                            <div class="puzzle-piece piece-storage">
                                <span>💽</span>
                                <small>SSD</small>
                            </div>
                            <div class="puzzle-piece piece-psu">
                                <span>⚡</span>
                                <small>PSU</small>
                            </div>
                        </div>
                        
                        <div class="completion-message">
                            <div class="message-bubble">
                                <span class="bubble-icon">💡</span>
                                <p>Sekarang kalian sudah memahami dasar-dasar komputer!</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Navigation -->
        <div class="nav-container">
            <button class="nav-btn" onclick="previousSlide()" id="prevBtn">← Sebelumnya</button>
            <div class="slide-counter">
                <span id="currentSlide">1</span> / <span id="totalSlides">10</span>
            </div>
            <button class="nav-btn" onclick="nextSlide()" id="nextBtn">Selanjutnya →</button>
        </div>
    </div>

    <script>
        let currentSlideIndex = 0;
        const slides = document.querySelectorAll('.slide');
        const totalSlides = slides.length;

        document.getElementById('totalSlides').textContent = totalSlides;

        function showSlide(index) {
            slides.forEach(slide => slide.classList.remove('active'));
            slides[index].classList.add('active');
            
            document.getElementById('currentSlide').textContent = index + 1;
            
            // Update navigation buttons
            document.getElementById('prevBtn').disabled = index === 0;
            document.getElementById('nextBtn').disabled = index === totalSlides - 1;
        }

        function nextSlide() {
            if (currentSlideIndex < totalSlides - 1) {
                currentSlideIndex++;
                showSlide(currentSlideIndex);
            }
        }

        function previousSlide() {
            if (currentSlideIndex > 0) {
                currentSlideIndex--;
                showSlide(currentSlideIndex);
            }
        }

        // Keyboard navigation
        document.addEventListener('keydown', function(event) {
            if (event.key === 'ArrowRight') {
                nextSlide();
            } else if (event.key === 'ArrowLeft') {
                previousSlide();
            }
        });

        // Initialize
        showSlide(0);

        // Add some interactive effects
        document.querySelectorAll('.spec-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(-5px) scale(1)';
            });
        });

        // Add click effects to motherboard components
        document.querySelectorAll('.mb-component').forEach(component => {
            component.addEventListener('click', function() {
                this.style.animation = 'none';
                setTimeout(() => {
                    this.style.animation = '';
                }, 100);
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'967336732659df9b',t:'MTc1Mzg2MTI3Ny4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
