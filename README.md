<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Para Mi Amor 💖</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #87CEEB 0%, #B0E0E6 50%, #E0F6FF 100%);
            min-height: 100vh;
            padding: 10px;
            position: relative;
            overflow-x: hidden;
        }

        /* Decorative elements */
        .decoration {
            position: fixed;
            pointer-events: none;
            z-index: 1;
            animation: float 8s ease-in-out infinite;
        }

        .flower {
            font-size: 25px;
            animation: rotate 12s linear infinite;
        }

        .cat {
            font-size: 30px;
            animation: bounce 3s ease-in-out infinite;
        }

        .butterfly {
            font-size: 20px;
            animation: flutter 6s ease-in-out infinite;
        }

        .star {
            font-size: 18px;
            animation: twinkle 4s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px); }
            25% { transform: translateY(-20px) translateX(10px); }
            50% { transform: translateY(-40px) translateX(-5px); }
            75% { transform: translateY(-20px) translateX(-10px); }
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
        }

        @keyframes flutter {
            0%, 100% { transform: translateX(0px) rotate(0deg); }
            25% { transform: translateX(15px) rotate(5deg); }
            50% { transform: translateX(-10px) rotate(-3deg); }
            75% { transform: translateX(5px) rotate(2deg); }
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        .container {
            max-width: 400px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.85);
            border-radius: 25px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
            overflow: hidden;
            backdrop-filter: blur(15px);
            border: 2px solid rgba(255, 255, 255, 0.3);
            position: relative;
            z-index: 2;
            animation: slideIn 1s ease-out;
        }

        @keyframes slideIn {
            0% { 
                opacity: 0; 
                transform: translateY(50px) scale(0.9); 
            }
            100% { 
                opacity: 1; 
                transform: translateY(0px) scale(1); 
            }
        }

        .header {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1, #FFC0CB);
            color: white;
            padding: 25px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .music-player {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 20px;
            margin: 20px 0;
            backdrop-filter: blur(10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }

        .music-player::before {
            content: '🎵';
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 25px;
            opacity: 0.3;
            animation: float 4s ease-in-out infinite;
        }

        .music-controls {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }

        .play-btn {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            color: white;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 105, 180, 0.3);
        }

        .play-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 25px rgba(255, 105, 180, 0.4);
        }

        .volume-control {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .volume-slider {
            width: 80px;
            height: 5px;
            border-radius: 5px;
            background: #ddd;
            outline: none;
            -webkit-appearance: none;
        }

        .volume-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: #FF69B4;
            cursor: pointer;
        }

        .music-upload {
            margin-top: 15px;
            text-align: center;
        }

        .music-upload input[type="file"] {
            display: none;
        }

        .upload-label {
            display: inline-block;
            background: linear-gradient(135deg, #87CEEB, #B0E0E6);
            color: white;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 14px;
            box-shadow: 0 5px 15px rgba(135, 206, 235, 0.3);
        }

        .upload-label:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(135, 206, 235, 0.4);
        }

        .song-info {
            text-align: center;
            color: #666;
            font-size: 14px;
            font-style: italic;
            margin-bottom: 10px;
        }

        .progress-bar {
            width: 100%;
            height: 6px;
            background: #ddd;
            border-radius: 3px;
            overflow: hidden;
            margin: 10px 0;
        }

        .progress {
            height: 100%;
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            width: 0%;
            transition: width 0.1s ease;
        }

        .music-note {
            position: absolute;
            font-size: 20px;
            opacity: 0;
            pointer-events: none;
            animation: musicFloat 3s ease-out;
        }

        @keyframes musicFloat {
            0% {
                opacity: 1;
                transform: translateY(0px) rotate(0deg);
            }
            100% {
                opacity: 0;
                transform: translateY(-100px) rotate(360deg);
            }
        }

        .equalizer {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 3px;
            margin-left: 15px;
        }

        .eq-bar {
            width: 3px;
            background: #FF69B4;
            border-radius: 2px;
            animation: equalizer 1s ease-in-out infinite;
        }

        .eq-bar:nth-child(1) { height: 10px; animation-delay: 0s; }
        .eq-bar:nth-child(2) { height: 15px; animation-delay: 0.2s; }
        .eq-bar:nth-child(3) { height: 20px; animation-delay: 0.4s; }
        .eq-bar:nth-child(4) { height: 15px; animation-delay: 0.6s; }
        .eq-bar:nth-child(5) { height: 12px; animation-delay: 0.8s; }

        @keyframes equalizer {
            0%, 100% { transform: scaleY(1); }
            50% { transform: scaleY(0.3); }
        }

        .header::before {
            content: '💕';
            position: absolute;
            font-size: 120px;
            opacity: 0.1;
            top: -30px;
            right: -30px;
            animation: float 8s ease-in-out infinite;
        }

        .header::after {
            content: '🌸';
            position: absolute;
            font-size: 40px;
            opacity: 0.2;
            top: 10px;
            left: 10px;
            animation: rotate 15s linear infinite;
        }

        .header h1 {
            font-size: 26px;
            margin-bottom: 8px;
            text-shadow: 2px 2px 6px rgba(0,0,0,0.3);
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .header p {
            font-size: 14px;
            opacity: 0.95;
        }

        .content {
            padding: 25px 20px;
        }

        .section {
            margin-bottom: 25px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            border-left: 5px solid #FF69B4;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.5s;
        }

        .section:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 15px 35px rgba(255, 105, 180, 0.2);
            border-left-color: #FFB6C1;
        }

        .section:hover::before {
            left: 100%;
        }

        .section h3 {
            color: #333;
            font-size: 18px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section h3 span {
            font-size: 22px;
            animation: bounce 2s ease-in-out infinite;
        }

        .section p {
            color: #666;
            line-height: 1.7;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .section-image {
            width: 100%;
            max-height: 200px;
            object-fit: cover;
            border-radius: 15px;
            margin-top: 10px;
            transition: transform 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .section-image:hover {
            transform: scale(1.05);
        }

        .edit-mode {
            display: none;
        }

        .edit-mode textarea {
            width: 100%;
            padding: 15px;
            border: 2px solid #FF69B4;
            border-radius: 15px;
            font-size: 14px;
            font-family: inherit;
            resize: vertical;
            min-height: 100px;
            background: rgba(255, 255, 255, 0.95);
            transition: all 0.3s ease;
        }

        .edit-mode textarea:focus {
            outline: none;
            border-color: #FFB6C1;
            box-shadow: 0 0 15px rgba(255, 105, 180, 0.3);
            transform: scale(1.02);
        }

        .edit-mode input[type="file"] {
            width: 100%;
            padding: 10px;
            border: 2px dashed #FF69B4;
            border-radius: 10px;
            margin-top: 10px;
            background: rgba(255, 182, 193, 0.1);
        }

        .btn {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            color: white;
            border: none;
            padding: 14px 22px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 14px;
            font-weight: bold;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 6px 20px rgba(255, 105, 180, 0.3);
            margin: 5px;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.4s ease, height 0.4s ease;
        }

        .btn:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(255, 105, 180, 0.4);
        }

        .btn:hover::before {
            width: 100%;
            height: 100%;
        }

        .btn:active {
            transform: translateY(-1px) scale(1.02);
        }

        .btn-secondary {
            background: linear-gradient(135deg, #87CEEB, #B0E0E6);
            box-shadow: 0 6px 20px rgba(135, 206, 235, 0.3);
        }

        .btn-secondary:hover {
            box-shadow: 0 8px 25px rgba(135, 206, 235, 0.4);
        }

        .controls {
            text-align: center;
            margin: 25px 0;
            padding: 20px;
            background: rgba(255, 255, 255, 0.4);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            animation: fadeInUp 1.5s ease-out;
        }

        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .add-section {
            margin-top: 25px;
            padding: 25px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 20px;
            border: 3px dashed #FF69B4;
            animation: borderGlow 3s ease-in-out infinite;
        }

        @keyframes borderGlow {
            0%, 100% { border-color: #FF69B4; }
            50% { border-color: #FFB6C1; }
        }

        .add-section input, .add-section textarea {
            width: 100%;
            padding: 12px 15px;
            margin: 10px 0;
            border: 2px solid #FF69B4;
            border-radius: 15px;
            font-size: 14px;
            background: rgba(255, 255, 255, 0.95);
            transition: all 0.3s ease;
        }

        .add-section input:focus, .add-section textarea:focus {
            outline: none;
            border-color: #FFB6C1;
            box-shadow: 0 0 15px rgba(255, 105, 180, 0.3);
            transform: scale(1.02);
        }

        /* Photo Carousel Styles */
        .photo-carousel-container {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 25px;
            padding: 30px;
            margin: 25px 0;
            backdrop-filter: blur(15px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
            position: relative;
            overflow: hidden;
        }

        .carousel-header {
            text-align: center;
            margin-bottom: 25px;
        }

        .carousel-header h3 {
            color: #FF69B4;
            font-size: 24px;
            margin-bottom: 8px;
            text-shadow: 2px 2px 6px rgba(0,0,0,0.1);
        }

        .carousel-wrapper {
            position: relative;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 20px;
            padding: 20px;
            margin: 20px 0;
            min-height: 300px;
            overflow: hidden;
        }

        .carousel-container {
            position: relative;
            width: 100%;
            height: 280px;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .carousel-slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: all 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            transform: translateX(100%);
        }

        .carousel-slide.active {
            opacity: 1;
            transform: translateX(0);
        }

        .carousel-slide.prev {
            transform: translateX(-100%);
        }

        .carousel-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 15px;
        }

        .slide-content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.7));
            color: white;
            padding: 30px 20px 20px;
            border-radius: 0 0 15px 15px;
        }

        .slide-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 8px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .slide-description {
            font-size: 14px;
            opacity: 0.9;
            line-height: 1.4;
        }

        .default-slide {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100%;
            background: linear-gradient(135deg, #E0F6FF 0%, #FFB6C1 100%);
            border-radius: 15px;
            border: 3px dashed #FF69B4;
        }

        .default-content {
            text-align: center;
            color: #666;
        }

        .default-content span {
            font-size: 60px;
            display: block;
            margin-bottom: 15px;
            opacity: 0.6;
        }

        .default-content p {
            font-size: 16px;
            font-style: italic;
        }

        .carousel-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(255, 255, 255, 0.9);
            color: #FF69B4;
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            transition: all 0.3s ease;
            z-index: 10;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .carousel-nav:hover {
            background: #FF69B4;
            color: white;
            transform: translateY(-50%) scale(1.1);
            box-shadow: 0 8px 25px rgba(255, 105, 180, 0.4);
        }

        .prev-btn {
            left: 15px;
        }

        .next-btn {
            right: 15px;
        }

        .carousel-indicators {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 20px;
        }

        .indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 105, 180, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .indicator.active {
            background: #FF69B4;
            transform: scale(1.3);
            box-shadow: 0 0 15px rgba(255, 105, 180, 0.5);
        }

        .carousel-controls {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .photo-upload-form {
            background: rgba(255, 182, 193, 0.1);
            border-radius: 20px;
            padding: 25px;
            margin-top: 20px;
            border: 2px dashed #FF69B4;
        }

        .photo-upload-form h4 {
            color: #FF69B4;
            text-align: center;
            margin-bottom: 20px;
            font-size: 18px;
        }

        .photo-upload-form input, .photo-upload-form textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 2px solid #FFB6C1;
            border-radius: 10px;
            font-size: 14px;
            background: rgba(255, 255, 255, 0.9);
        }

        .photo-preview {
            margin: 15px 0;
            text-align: center;
        }

        .photo-preview img {
            max-width: 200px;
            max-height: 150px;
            object-fit: cover;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .calendar-container {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 25px;
            margin: 25px 0;
            backdrop-filter: blur(10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .calendar-header h3 {
            color: #FF69B4;
            font-size: 20px;
            margin-bottom: 10px;
            text-align: center;
        }

        .calendar-nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .nav-btn {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            color: white;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
        }

        .nav-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(255, 105, 180, 0.3);
        }

        .month-year {
            font-size: 18px;
            font-weight: bold;
            color: #333;
        }

        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 5px;
            margin-bottom: 20px;
        }

        .calendar-day {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            color: #666;
            font-weight: bold;
        }

        .calendar-date {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 14px;
            color: #333;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
        }

        .calendar-date:hover {
            background: rgba(255, 105, 180, 0.1);
            transform: scale(1.1);
        }

        .special-date {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            color: white;
            animation: pulse 2s ease-in-out infinite;
        }

        .today {
            background: rgba(135, 206, 235, 0.3);
            border: 2px solid #87CEEB;
        }

        .add-date-form {
            background: rgba(255, 182, 193, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-top: 15px;
            border: 2px dashed #FF69B4;
        }

        .add-date-form input, .add-date-form textarea {
            width: 100%;
            padding: 12px;
            margin: 8px 0;
            border: 2px solid #FFB6C1;
            border-radius: 10px;
            font-size: 14px;
            background: rgba(255, 255, 255, 0.9);
        }

        .special-dates-list {
            margin-top: 15px;
            max-height: 200px;
            overflow-y: auto;
        }

        .special-date-item {
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            padding: 12px;
            margin: 8px 0;
            border-left: 4px solid #FF69B4;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s ease;
        }

        .date-info {
            flex-grow: 1;
        }

        .date-title {
            font-weight: bold;
            color: #333;
            font-size: 14px;
        }

        .date-description {
            color: #666;
            font-size: 12px;
            margin-top: 3px;
        }

        .date-day {
            font-size: 12px;
            color: #FF69B4;
            font-weight: bold;
        }

        .delete-date-btn {
            background: #FF6B6B;
            color: white;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 12px;
            margin-left: 10px;
        }

        .date-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background: linear-gradient(135deg, #FFB6C1 0%, #FFFFFF 50%, #E0F6FF 100%);
            border-radius: 25px;
            padding: 0;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }

        .modal-header {
            background: linear-gradient(135deg, #FF69B4, #FFB6C1);
            color: white;
            padding: 20px 25px;
            border-radius: 25px 25px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-header h3 {
            margin: 0;
            font-size: 20px;
        }

        .close-modal {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
        }

        .modal-body {
            padding: 30px 25px;
            text-align: center;
        }

        .modal-date {
            background: rgba(255, 105, 180, 0.1);
            color: #FF69B4;
            padding: 15px 20px;
            border-radius: 20px;
            font-size: 16px;
            font-weight: bold;
            margin-bottom: 20px;
            border: 2px solid rgba(255, 105, 180, 0.3);
        }

        .modal-description {
            color: #333;
            font-size: 15px;
            line-height: 1.6;
            margin-bottom: 25px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 15px;
            border-left: 4px solid #FF69B4;
        }

        .modal-actions {
            padding: 20px 25px;
            border-top: 1px solid rgba(255, 105, 180, 0.2);
            display: flex;
            justify-content: center;
            gap: 15px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 0 0 25px 25px;
        }

        .decorative-garden {
            text-align: center;
            margin: 30px 0;
            padding: 25px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 25px;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
            min-height: 120px;
        }

        .lily-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 15px;
        }

        .lily {
            font-size: 35px;
            animation: lilyBloom 4s ease-in-out infinite;
        }

        .lily-1 { animation-delay: 0s; }
        .lily-2 { animation-delay: 1s; }
        .lily-3 { animation-delay: 2s; }

        @keyframes lilyBloom {
            0%, 100% {
                transform: scale(1) rotate(0deg);
                opacity: 0.8;
            }
            25% {
                transform: scale(1.2) rotate(5deg);
                opacity: 1;
            }
            50% {
                transform: scale(1.1) rotate(-3deg);
                opacity: 0.9;
            }
            75% {
                transform: scale(1.15) rotate(2deg);
                opacity: 1;
            }
        }

        .cats-container {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 15px;
        }

        .cute-cat {
            font-size: 32px;
            animation: catPlay 3s ease-in-out infinite;
        }

        .cat-1 { animation-delay: 0.5s; }
        .cat-2 { animation-delay: 1.5s; }

        @keyframes catPlay {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            20% { transform: translateY(-8px) rotate(-5deg); }
            40% { transform: translateY(-15px) rotate(5deg); }
            60% { transform: translateY(-8px) rotate(-2deg); }
            80% { transform: translateY(-3px) rotate(2deg); }
        }

        .garden-elements {
            display: flex;
            justify-content: center;
            gap: 25px;
        }

        .element {
            font-size: 28px;
            animation: gentleSway 5s ease-in-out infinite;
        }

        .element-1 { animation-delay: 0s; }
        .element-2 { animation-delay: 1.5s; }
        .element-3 { animation-delay: 3s; }

        @keyframes gentleSway {
            0%, 100% {
                transform: translateX(0px) rotate(0deg);
                opacity: 0.7;
            }
            25% {
                transform: translateX(5px) rotate(3deg);
                opacity: 1;
            }
            50% {
                transform: translateX(-3px) rotate(-2deg);
                opacity: 0.8;
            }
            75% {
                transform: translateX(3px) rotate(1deg);
                opacity: 0.9;
            }
        }

        .footer {
            text-align: center;
            padding: 25px;
            color: #666;
            font-style: italic;
            background: rgba(255, 255, 255, 0.4);
            position: relative;
            overflow: hidden;
        }

        .delete-btn {
            background: linear-gradient(135deg, #FF6B6B, #FF4757);
            font-size: 12px;
            padding: 10px 16px;
            margin-left: 10px;
        }

        .image-preview {
            position: relative;
            display: inline-block;
        }

        .remove-image {
            position: absolute;
            top: -10px;
            right: -10px;
            background: #FF6B6B;
            color: white;
            border: none;
            border-radius: 50%;
            width: 25px;
            height: 25px;
            font-size: 12px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 2px 8px rgba(0,0,0,0.3);
        }

        .decorations-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes fadeOut {
            0% { opacity: 1; transform: translateY(0); }
            100% { opacity: 0; transform: translateY(-20px); }
        }

        @keyframes modalFadeOut {
            0% { opacity: 1; }
            100% { opacity: 0; }
        }

        @media (max-width: 480px) {
            .container {
                margin: 5px;
                border-radius: 20px;
            }
            
            .header h1 {
                font-size: 22px;
            }
            
            .section h3 {
                font-size: 16px;
            }

            .decoration {
                font-size: 20px;
            }
            
            .carousel-nav {
                width: 40px;
                height: 40px;
                font-size: 16px;
            }
            
            .prev-btn {
                left: 10px;
            }
            
            .next-btn {
                right: 10px;
            }
            
            .modal-content {
                width: 95%;
                margin: 10px;
            }
            
            .carousel-controls {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Decorative elements -->
    <div class="decorations-container" id="decorations"></div>

    <div class="container">
        <div class="header">
            <h1>💖 Para Mi Amor 💖</h1>
            <p>Un lugar especial lleno de amor y ternura</p>
        </div>

        <div class="content">
            <div class="music-player">
                <div class="song-info" id="song-info">
                    🎵 Selecciona una canción para crear un ambiente romántico
                </div>
                <div class="progress-bar">
                    <div class="progress" id="progress"></div>
                </div>
                <div class="music-controls">
                    <button class="play-btn" id="play-btn" onclick="toggleMusic()">▶️</button>
                    <div class="volume-control">
                        <span>🔊</span>
                        <input type="range" class="volume-slider" id="volume-slider" min="0" max="100" value="70" onchange="changeVolume()">
                    </div>
                    <div class="equalizer" id="equalizer" style="display: none;">
                        <div class="eq-bar"></div>
                        <div class="eq-bar"></div>
                        <div class="eq-bar"></div>
                        <div class="eq-bar"></div>
                        <div class="eq-bar"></div>
                    </div>
                </div>
                <div class="music-upload">
                    <label for="music-file" class="upload-label">
                        🎶 Subir Canción
                    </label>
                    <input type="file" id="music-file" accept="audio/*" onchange="loadMusic(this)">
                </div>
                <audio id="audio-player" loop></audio>
            </div>

            <div class="controls">
                <button class="btn" onclick="toggleEditMode()">✏️ Modo Edición</button>
                <button class="btn btn-secondary" onclick="toggleAddSection()">➕ Agregar Sección</button>
            </div>

            <div id="sections-container">
                <div class="section" data-id="1">
                    <div class="view-mode">
                        <h3><span>💗</span> Por qué te amo</h3>
                        <p>Eres la luz de mi vida, tu sonrisa ilumina mis días más oscuros. Cada momento contigo es un regalo que atesoro en mi corazón. Tu bondad, tu humor y tu amor me hacen una mejor persona cada día.</p>
                    </div>
                    <div class="edit-mode">
                        <h3><span>💗</span> Por qué te amo</h3>
                        <textarea>Eres la luz de mi vida, tu sonrisa ilumina mis días más oscuros. Cada momento contigo es un regalo que atesoro en mi corazón. Tu bondad, tu humor y tu amor me hacen una mejor persona cada día.</textarea>
                        <input type="file" accept="image/*" onchange="handleImageUpload(this, 1)" class="image-upload">
                        <button class="btn" onclick="saveSection(1)">💾 Guardar</button>
                        <button class="btn delete-btn" onclick="deleteSection(1)">🗑️ Eliminar</button>
                    </div>
                </div>

                <div class="section" data-id="2">
                    <div class="view-mode">
                        <h3><span>🌟</span> Nuestros recuerdos favoritos</h3>
                        <p>Recuerdo nuestra primera cita como si fuera ayer. El nerviosismo, las risas, esa conexión instantánea. Cada aventura juntos se convierte en un tesoro invaluable. Desde paseos bajo la lluvia hasta noches viendo películas abrazados.</p>
                    </div>
                    <div class="edit-mode">
                        <h3><span>🌟</span> Nuestros recuerdos favoritos</h3>
                        <textarea>Recuerdo nuestra primera cita como si fuera ayer. El nerviosismo, las risas, esa conexión instantánea. Cada aventura juntos se convierte en un tesoro invaluable. Desde paseos bajo la lluvia hasta noches viendo películas abrazados.</textarea>
                        <input type="file" accept="image/*" onchange="handleImageUpload(this, 2)" class="image-upload">
                        <button class="btn" onclick="saveSection(2)">💾 Guardar</button>
                        <button class="btn delete-btn" onclick="deleteSection(2)">🗑️ Eliminar</button>
                    </div>
                </div>

                <div class="section" data-id="3">
                    <div class="view-mode">
                        <h3><span>🎯</span> Nuestros sueños juntos</h3>
                        <p>Sueño con todos los lugares que visitaremos, las aventuras que viviremos y los momentos hermosos que crearemos. Quiero construir un hogar lleno de amor, risas y felicidad contigo. Nuestro futuro brilla tanto como tu hermosa sonrisa.</p>
                    </div>
                    <div class="edit-mode">
                        <h3><span>🎯</span> Nuestros sueños juntos</h3>
                        <textarea>Sueño con todos los lugares que visitaremos, las aventuras que viviremos y los momentos hermosos que crearemos. Quiero construir un hogar lleno de amor, risas y felicidad contigo. Nuestro futuro brilla tanto como tu hermosa sonrisa.</textarea>
                        <input type="file" accept="image/*" onchange="handleImageUpload(this, 3)" class="image-upload">
                        <button class="btn" onclick="saveSection(3)">💾 Guardar</button>
                        <button class="btn delete-btn" onclick="deleteSection(3)">🗑️ Eliminar</button>
                    </div>
                </div>
            </div>

            <div class="add-section" id="add-section" style="display: none;">
                <h3>➕ Agregar nueva sección</h3>
                <input type="text" id="new-title" placeholder="Título de la sección (ej: Nuestras canciones favoritas)">
                <input type="text" id="new-emoji" placeholder="Emoji para el título (ej: 🎵)">
                <textarea id="new-content" placeholder="Escribe aquí el contenido de la nueva sección..." rows="4"></textarea>
                <input type="file" accept="image/*" id="new-image">
                <button class="btn" onclick="addSection()">✨ Crear Sección</button>
                <button class="btn btn-secondary" onclick="toggleAddSection()">❌ Cancelar</button>
            </div>

            <div class="photo-carousel-container">
                <div class="carousel-header">
                    <h3>📸 Nuestros Momentos Especiales 📸</h3>
                    <p>Los recuerdos más hermosos juntos</p>
                </div>
                
                <div class="carousel-wrapper">
                    <div class="carousel-container" id="carousel-container">
                        <div class="carousel-slide active" data-id="1">
                            <div class="default-slide">
                                <div class="default-content">
                                    <span>📷</span>
                                    <p>Agrega tu primera foto especial</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <button class="carousel-nav prev-btn" onclick="prevSlide()">◀</button>
                    <button class="carousel-nav next-btn" onclick="nextSlide()">▶</button>
                    
                    <div class="carousel-indicators" id="carousel-indicators">
                        <div class="indicator active" onclick="goToSlide(0)"></div>
                    </div>
                </div>

                <div class="carousel-controls">
                    <button class="btn btn-secondary" onclick="togglePhotoUpload()">
                        📸 Agregar Foto
                    </button>
                    <button class="btn" onclick="toggleAutoplay()" id="autoplay-btn">
                        ⏸️ Pausar Carrusel
                    </button>
                </div>

                <div class="photo-upload-form" id="photo-upload-form" style="display: none;">
                    <h4>📸 Agregar Nueva Foto</h4>
                    <input type="file" accept="image/*" id="photo-file" onchange="previewPhoto()">
                    <div class="photo-preview" id="photo-preview"></div>
                    <input type="text" id="photo-title" placeholder="Título de la foto (ej: Nuestra primera cita)">
                    <textarea id="photo-description" placeholder="Descripción del momento especial..." rows="3"></textarea>
                    <button class="btn" onclick="addPhoto()">💕 Agregar Foto</button>
                    <button class="btn btn-secondary" onclick="togglePhotoUpload()">❌ Cancelar</button>
                </div>
            </div>

            <div class="calendar-container">
                <div class="calendar-header">
                    <h3>💖 Nuestras Fechas Especiales 💖</h3>
                </div>
                <div class="calendar-nav">
                    <button class="nav-btn" onclick="changeMonth(-1)">◀</button>
                    <div class="month-year" id="month-year"></div>
                    <button class="nav-btn" onclick="changeMonth(1)">▶</button>
                </div>
                <div class="calendar-grid" id="calendar-grid"></div>
                
                <div class="add-date-form" id="add-date-form" style="display: none;">
                    <h4>➕ Agregar Fecha Especial</h4>
                    <input type="date" id="special-date" placeholder="Fecha">
                    <input type="text" id="date-title" placeholder="Título (ej: Nuestro Aniversario)">
                    <textarea id="date-description" placeholder="Descripción de por qué es especial..." rows="3"></textarea>
                    <button class="btn" onclick="addSpecialDate()">💕 Guardar Fecha</button>
                    <button class="btn btn-secondary" onclick="toggleDateForm()">❌ Cancelar</button>
                </div>

                <button class="btn btn-secondary" onclick="toggleDateForm()" style="width: 100%; margin-top: 15px;">
                    📅 Agregar Fecha Especial
                </button>

                <div class="special-dates-list" id="special-dates-list"></div>
            </div>

            <!-- Modal para fechas especiales -->
            <div class="date-modal" id="date-modal" style="display: none;">
                <div class="modal-content">
                    <div class="modal-header">
                        <h3 id="modal-date-title"></h3>
                        <button class="close-modal" onclick="closeDateModal()">✖️</button>
                    </div>
                    <div class="modal-body">
                        <div class="modal-date" id="modal-date"></div>
                        <div class="modal-description" id="modal-description"></div>
                    </div>
                    <div class="modal-actions">
                        <button class="btn btn-secondary" onclick="editSpecialDate()" id="edit-date-btn">✏️ Editar</button>
                        <button class="btn delete-btn" onclick="deleteFromModal()" id="delete-date-btn">🗑️ Eliminar</button>
                    </div>
                </div>
            </div>

            <div class="decorative-garden">
                <div class="lily-container">
                    <div class="lily lily-1">🏵️</div>
                    <div class="lily lily-2">🌺</div>
                    <div class="lily lily-3">🌸</div>
                </div>
                <div class="cats-container">
                    <div class="cute-cat cat-1">😸</div>
                    <div class="cute-cat cat-2">😺</div>
                </div>
                <div class="garden-elements">
                    <div class="element element-1">🌿</div>
                    <div class="element element-2">🍀</div>
                    <div class="element element-3">🌱</div>
                </div>
            </div>
        </div>

        <div class="footer">
            <p>Con todo mi amor, siempre 💕</p>
        </div>
    </div>

    <script>
        let editMode = false;
        let sectionCounter = 3;
        let audioPlayer = null;
        let isPlaying = false;
        let currentDate = new Date();
        let specialDates = [];
        let photos = [];
        let currentSlide = 0;
        let autoplayInterval = null;
        let isAutoplaying = true;
        let currentModalDate = null;

        // Initialize everything when page loads
        document.addEventListener('DOMContentLoaded', function() {
            createDecorations();
            updateCalendar();
            loadData();
            initCarousel();
            
            // Create floating hearts occasionally
            setInterval(() => {
                if (Math.random() > 0.92) {
                    createFloatingHeart();
                }
            }, 1000);

            // Create butterflies occasionally
            setInterval(() => {
                if (Math.random() > 0.97) {
                    createButterfly();
                }
            }, 2000);

            // Close modal when clicking outside
            document.getElementById('date-modal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeDateModal();
                }
            });
        });

        // Photo Carousel Functions
        function initCarousel() {
            if (photos.length === 0) {
                currentSlide = 0;
                updateIndicators();
                return;
            }
            
            startAutoplay();
            updateCarousel();
        }

        function addPhoto() {
            const fileInput = document.getElementById('photo-file');
            const title = document.getElementById('photo-title').value.trim();
            const description = document.getElementById('photo-description').value.trim();
            const file = fileInput.files[0];

            if (!file) {
                alert('Por favor selecciona una foto 📸');
                return;
            }

            if (!title) {
                alert('Por favor agrega un título para la foto 💕');
                return;
            }

            const reader = new FileReader();
            reader.onload = function(e) {
                const newPhoto = {
                    id: Date.now(),
                    src: e.target.result,
                    title: title,
                    description: description || 'Un momento especial juntos 💖'
                };

                photos.push(newPhoto);
                renderCarousel();
                togglePhotoUpload();
                
                // Clear form
                fileInput.value = '';
                document.getElementById('photo-title').value = '';
                document.getElementById('photo-description').value = '';
                document.getElementById('photo-preview').innerHTML = '';
                
                // Animation for new photo
                createSparkles(document.querySelector('.photo-carousel-container'));
                
                saveData();
            };
            reader.readAsDataURL(file);
        }

        function renderCarousel() {
            const container = document.getElementById('carousel-container');
            const indicators = document.getElementById('carousel-indicators');
            
            container.innerHTML = '';
            indicators.innerHTML = '';

            if (photos.length === 0) {
                // Show default slide
                container.innerHTML = `
                    <div class="carousel-slide active" data-id="default">
                        <div class="default-slide">
                            <div class="default-content">
                                <span>📷</span>
                                <p>Agrega tu primera foto especial</p>
                            </div>
                        </div>
                    </div>
                `;
                indicators.innerHTML = '<div class="indicator active"></div>';
                currentSlide = 0;
                return;
            }

            // Render photo slides
            photos.forEach((photo, index) => {
                const slide = document.createElement('div');
                slide.className = `carousel-slide ${index === currentSlide ? 'active' : ''}`;
                slide.setAttribute('data-id', photo.id);
                
                slide.innerHTML = `
                    <img src="${photo.src}" alt="${photo.title}">
                    <div class="slide-content">
                        <div class="slide-title">${photo.title}</div>
                        <div class="slide-description">${photo.description}</div>
                    </div>
                `;
                
                container.appendChild(slide);

                // Add indicator
                const indicator = document.createElement('div');
                indicator.className = `indicator ${index === currentSlide ? 'active' : ''}`;
                indicator.onclick = () => goToSlide(index);
                indicators.appendChild(indicator);
            });
        }

        function nextSlide() {
            if (photos.length === 0) return;
            
            currentSlide = (currentSlide + 1) % photos.length;
            updateCarousel();
        }

        function prevSlide() {
            if (photos.length === 0) return;
            
            currentSlide = currentSlide === 0 ? photos.length - 1 : currentSlide - 1;
            updateCarousel();
        }

        function goToSlide(index) {
            if (photos.length === 0) return;
            
            currentSlide = index;
            updateCarousel();
        }

        function updateCarousel() {
            const slides = document.querySelectorAll('.carousel-slide');
            const indicators = document.querySelectorAll('.indicator');
            
            slides.forEach((slide, index) => {
                slide.classList.remove('active', 'prev');
                if (index === currentSlide) {
                    slide.classList.add('active');
                } else if (index < currentSlide) {
                    slide.classList.add('prev');
                }
            });
            
            indicators.forEach((indicator, index) => {
                indicator.classList.toggle('active', index === currentSlide);
            });
        }

        function updateIndicators() {
            const indicators = document.getElementById('carousel-indicators');
            indicators.innerHTML = '';
            
            const count = photos.length || 1;
            for (let i = 0; i < count; i++) {
                const indicator = document.createElement('div');
                indicator.className = `indicator ${i === currentSlide ? 'active' : ''}`;
                indicator.onclick = () => goToSlide(i);
                indicators.appendChild(indicator);
            }
        }

        function togglePhotoUpload() {
            const form = document.getElementById('photo-upload-form');
            const isVisible = form.style.display !== 'none';
            
            if (isVisible) {
                form.style.display = 'none';
                document.getElementById('photo-preview').innerHTML = '';
            } else {
                form.style.display = 'block';
                form.scrollIntoView({ behavior: 'smooth' });
            }
        }

        function previewPhoto() {
            const fileInput = document.getElementById('photo-file');
            const preview = document.getElementById('photo-preview');
            const file = fileInput.files[0];

            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    preview.innerHTML = `<img src="${e.target.result}" alt="Vista previa">`;
                };
                reader.readAsDataURL(file);
            } else {
                preview.innerHTML = '';
            }
        }

        function startAutoplay() {
            if (photos.length <= 1) return;
            
            autoplayInterval = setInterval(() => {
                if (isAutoplaying) {
                    nextSlide();
                }
            }, 4000);
        }

        function stopAutoplay() {
            if (autoplayInterval) {
                clearInterval(autoplayInterval);
                autoplayInterval = null;
            }
        }

        function toggleAutoplay() {
            const btn = document.getElementById('autoplay-btn');
            
            if (isAutoplaying) {
                isAutoplaying = false;
                stopAutoplay();
                btn.textContent = '▶️ Reanudar Carrusel';
                btn.classList.add('btn-secondary');
            } else {
                isAutoplaying = true;
                startAutoplay();
                btn.textContent = '⏸️ Pausar Carrusel';
                btn.classList.remove('btn-secondary');
            }
        }

        // Enhanced Date Modal Functions
        function showDateInfo(dateStr) {
            const specialDate = specialDates.find(sd => sd.date === dateStr);
            if (!specialDate) return;
            
            currentModalDate = specialDate;
            
            document.getElementById('modal-date-title').textContent = specialDate.title;
            document.getElementById('modal-date').textContent = formatDateString(dateStr);
            document.getElementById('modal-description').textContent = specialDate.description;
            document.getElementById('edit-date-btn').setAttribute('data-id', specialDate.id);
            document.getElementById('delete-date-btn').setAttribute('data-id', specialDate.id);
            
            const modal = document.getElementById('date-modal');
            modal.style.display = 'flex';
            
            // Add floating hearts effect
            createFloatingModalHearts();
        }

        function closeDateModal() {
            const modal = document.getElementById('date-modal');
            modal.style.display = 'none';
            currentModalDate = null;
        }

        function deleteFromModal() {
            if (currentModalDate && confirm('¿Estás segura de que quieres eliminar esta fecha especial?')) {
                deleteSpecialDate(currentModalDate.id);
                closeDateModal();
            }
        }

        function editSpecialDate() {
            if (!currentModalDate) return;
            
            closeDateModal();
            
            // Pre-fill the form with current data
            document.getElementById('special-date').value = currentModalDate.date;
            document.getElementById('date-title').value = currentModalDate.title;
            document.getElementById('date-description').value = currentModalDate.description;
            
            // Remove the current date from array temporarily
            specialDates = specialDates.filter(date => date.id !== currentModalDate.id);
            
            toggleDateForm();
        }

        function formatDateString(dateStr) {
            const date = new Date(dateStr + 'T00:00:00');
            return date.toLocaleDateString('es-ES', {
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            });
        }

        function createFloatingModalHearts() {
            const modal = document.querySelector('.modal-content');
            const hearts = ['💕', '💖', '💗', '💓', '💘'];
            
            for (let i = 0; i < 5; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                    heart.style.position = 'absolute';
                    heart.style.left = Math.random() * 80 + 10 + '%';
                    heart.style.top = '100%';
                    heart.style.fontSize = Math.random() * 10 + 15 + 'px';
                    heart.style.pointerEvents = 'none';
                    heart.style.zIndex = '1001';
                    heart.style.transition = 'all 3s ease-out';
                    heart.style.opacity = '0.8';
                    
                    modal.appendChild(heart);
                    
                    setTimeout(() => {
                        heart.style.transform = 'translateY(-300px) rotate(360deg)';
                        heart.style.opacity = '0';
                    }, 50);
                    
                    setTimeout(() => {
                        if (heart.parentNode) {
                            heart.remove();
                        }
                    }, 3000);
                }, i * 200);
            }
        }

        // Data persistence functions
        function saveData() {
            const data = {
                sections: [],
                specialDates: specialDates,
                photos: photos,
                musicInfo: audioPlayer ? {
                    hasMusic: !!audioPlayer.src,
                    volume: audioPlayer.volume
                } : null
            };

            // Save section data
            document.querySelectorAll('.section').forEach(section => {
                const id = section.getAttribute('data-id');
                const title = section.querySelector('h3').textContent;
                const content = section.querySelector('.view-mode p').textContent;
                const image = section.querySelector('.section-image');
                
                data.sections.push({
                    id: id,
                    title: title,
                    content: content,
                    image: image ? image.src : null
                });
            });

            // Store data in memory (since localStorage is not supported)
            window.appData = data;
        }

        function loadData() {
            if (window.appData) {
                const data = window.appData;
                
                // Load special dates
                if (data.specialDates) {
                    specialDates = data.specialDates;
                    updateCalendar();
                    updateSpecialDatesList();
                }

                // Load photos
                if (data.photos) {
                    photos = data.photos;
                    renderCarousel();
                    initCarousel();
                }

                // Load music settings
                if (data.musicInfo && audioPlayer) {
                    audioPlayer.volume = data.musicInfo.volume || 0.7;
                    document.getElementById('volume-slider').value = (audioPlayer.volume * 100);
                }
            }
        }

        // Calendar functions
        function updateCalendar() {
            const year = currentDate.getFullYear();
            const month = currentDate.getMonth();
            
            document.getElementById('month-year').textContent = 
                `${getMonthName(month)} ${year}`;
            
            const grid = document.getElementById('calendar-grid');
            grid.innerHTML = '';
            
            // Add day headers
            const days = ['Dom', 'Lun', 'Mar', 'Mié', 'Jue', 'Vie', 'Sáb'];
            days.forEach(day => {
                const dayEl = document.createElement('div');
                dayEl.className = 'calendar-day';
                dayEl.textContent = day;
                grid.appendChild(dayEl);
            });
            
            // Get first day of month and number of days
            const firstDay = new Date(year, month, 1).getDay();
            const daysInMonth = new Date(year, month + 1, 0).getDate();
            const today = new Date();
            
            // Add empty cells for days before first day of month
            for (let i = 0; i < firstDay; i++) {
                const emptyEl = document.createElement('div');
                emptyEl.className = 'calendar-date';
                grid.appendChild(emptyEl);
            }
            
            // Add days of month
            for (let day = 1; day <= daysInMonth; day++) {
                const dateEl = document.createElement('div');
                dateEl.className = 'calendar-date';
                dateEl.textContent = day;
                
                const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
                
                // Check if it's today
                if (today.getFullYear() === year && 
                    today.getMonth() === month && 
                    today.getDate() === day) {
                    dateEl.classList.add('today');
                }
                
                // Check if it's a special date
                if (specialDates.some(sd => sd.date === dateStr)) {
                    dateEl.classList.add('special-date');
                }
                
                dateEl.onclick = () => showDateInfo(dateStr);
                grid.appendChild(dateEl);
            }
        }

        function getMonthName(month) {
            const months = [
                'Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio',
                'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'
            ];
            return months[month];
        }

        function changeMonth(direction) {
            currentDate.setMonth(currentDate.getMonth() + direction);
            updateCalendar();
        }

        function toggleDateForm() {
            const form = document.getElementById('add-date-form');
            const isVisible = form.style.display !== 'none';
            
            if (isVisible) {
                form.style.display = 'none';
                // Clear form
                document.getElementById('special-date').value = '';
                document.getElementById('date-title').value = '';
                document.getElementById('date-description').value = '';
            } else {
                form.style.display = 'block';
                form.scrollIntoView({ behavior: 'smooth' });
            }
        }

        function addSpecialDate() {
            const date = document.getElementById('special-date').value;
            const title = document.getElementById('date-title').value.trim();
            const description = document.getElementById('date-description').value.trim();

            if (!date || !title) {
                alert('Por favor completa la fecha y el título 💕');
                return;
            }

            const newDate = {
                date: date,
                title: title,
                description: description,
                id: Date.now()
            };

            specialDates.push(newDate);
            updateCalendar();
            updateSpecialDatesList();
            toggleDateForm();
            saveData();

            // Create celebration effect
            createSparkles(document.querySelector('.calendar-container'));
        }

        function deleteSpecialDate(id) {
            if (confirm('¿Estás segura de que quieres eliminar esta fecha especial? 💔')) {
                specialDates = specialDates.filter(date => date.id !== id);
                updateCalendar();
                updateSpecialDatesList();
                saveData();
            }
        }

        function updateSpecialDatesList() {
            const list = document.getElementById('special-dates-list');
            list.innerHTML = '';

            if (specialDates.length === 0) {
                list.innerHTML = '<p style="text-align: center; color: #666; font-style: italic;">No hay fechas especiales aún 💕</p>';
                return;
            }

            specialDates.sort((a, b) => new Date(a.date) - new Date(b.date));

            specialDates.forEach(dateObj => {
                const dateEl = document.createElement('div');
                dateEl.className = 'special-date-item';
                
                const dateStr = new Date(dateObj.date + 'T00:00:00').toLocaleDateString('es-ES', {
                    weekday: 'long',
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric'
                });

                dateEl.innerHTML = `
                    <div class="date-info">
                        <div class="date-title">💕 ${dateObj.title}</div>
                        <div class="date-description">${dateObj.description}</div>
                        <div class="date-day">${dateStr}</div>
                    </div>
                    <button class="delete-date-btn" onclick="deleteSpecialDate(${dateObj.id})">×</button>
                `;

                list.appendChild(dateEl);
            });
        }

        // Music player functions
        function loadMusic(input) {
            const file = input.files[0];
            if (file) {
                audioPlayer = document.getElementById('audio-player');
                const url = URL.createObjectURL(file);
                audioPlayer.src = url;
                
                document.getElementById('song-info').textContent = `🎵 ${file.name}`;
                document.getElementById('play-btn').textContent = '▶️';
                isPlaying = false;
                
                // Set up progress tracking
                audioPlayer.addEventListener('timeupdate', updateProgress);
                audioPlayer.addEventListener('ended', () => {
                    document.getElementById('play-btn').textContent = '▶️';
                    isPlaying = false;
                    document.getElementById('equalizer').style.display = 'none';
                });
                
                // Set initial volume
                audioPlayer.volume = 0.7;
                
                // Create musical notes effect
                createMusicalNotes();
            }
        }

        function toggleMusic() {
            if (!audioPlayer || !audioPlayer.src) {
                alert('¡Primero sube una canción romántica! 💕');
                return;
            }

            if (isPlaying) {
                audioPlayer.pause();
                document.getElementById('play-btn').textContent = '▶️';
                document.getElementById('equalizer').style.display = 'none';
                isPlaying = false;
            } else {
                audioPlayer.play();
                document.getElementById('play-btn').textContent = '⏸️';
                document.getElementById('equalizer').style.display = 'flex';
                isPlaying = true;
                createMusicalNotes();
            }
        }

        function changeVolume() {
            const volume = document.getElementById('volume-slider').value / 100;
            if (audioPlayer) {
                audioPlayer.volume = volume;
            }
        }

        function updateProgress() {
            if (audioPlayer) {
                const progress = (audioPlayer.currentTime / audioPlayer.duration) * 100;
                document.getElementById('progress').style.width = progress + '%';
            }
        }

        function createMusicalNotes() {
            if (!isPlaying) return;
            
            const notes = ['🎵', '🎶', '♪', '♫', '🎼'];
            const musicPlayer = document.querySelector('.music-player');
            
            for (let i = 0; i < 3; i++) {
                setTimeout(() => {
                    if (!isPlaying) return;
                    
                    const note = document.createElement('div');
                    note.className = 'music-note';
                    note.textContent = notes[Math.floor(Math.random() * notes.length)];
                    note.style.left = Math.random() * (musicPlayer.offsetWidth - 30) + 'px';
                    note.style.top = '20px';
                    
                    musicPlayer.appendChild(note);
                    
                    setTimeout(() => {
                        if (note.parentNode) {
                            note.remove();
                        }
                    }, 3000);
                }, i * 500);
            }
            
            // Continue creating notes while playing
            if (isPlaying) {
                setTimeout(createMusicalNotes, 2000);
            }
        }

        // Create floating decorations
        function createDecorations() {
            const decorationsContainer = document.getElementById('decorations');
            const decorativeEmojis = ['🏵️', '🌺', '🌸', '🌷', '🌻', '😸', '😺', '🱍', '🦋', '✨', '⭐', '💫', '🌿', '🍀'];
            
            for (let i = 0; i < 15; i++) {
                setTimeout(() => {
                    const decoration = document.createElement('div');
                    decoration.className = 'decoration';
                    decoration.style.left = Math.random() * 100 + '%';
                    decoration.style.top = Math.random() * 100 + '%';
                    decoration.style.animationDelay = Math.random() * 8 + 's';
                    
                    const emoji = decorativeEmojis[Math.floor(Math.random() * decorativeEmojis.length)];
                    decoration.textContent = emoji;
                    
                    // Add specific classes for different animations
                    if (['🏵️', '🌺', '🌸', '🌷', '🌻'].includes(emoji)) {
                        decoration.classList.add('flower');
                    } else if (['😸', '😺', '🱍'].includes(emoji)) {
                        decoration.classList.add('cat');
                    } else if (emoji === '🦋') {
                        decoration.classList.add('butterfly');
                    } else {
                        decoration.classList.add('star');
                    }
                    
                    decorationsContainer.appendChild(decoration);
                }, i * 300);
            }
        }

        function toggleEditMode() {
            editMode = !editMode;
            const viewModes = document.querySelectorAll('.view-mode');
            const editModes = document.querySelectorAll('.edit-mode');
            const btn = document.querySelector('.controls .btn');

            if (editMode) {
                viewModes.forEach(vm => {
                    vm.style.display = 'none';
                });
                editModes.forEach(em => {
                    em.style.display = 'block';
                });
                btn.textContent = '👁️ Modo Vista';
                btn.style.background = 'linear-gradient(135deg, #87CEEB, #B0E0E6)';
            } else {
                viewModes.forEach(vm => {
                    vm.style.display = 'block';
                });
                editModes.forEach(em => em.style.display = 'none');
                btn.textContent = '✏️ Modo Edición';
                btn.style.background = 'linear-gradient(135deg, #FF69B4, #FFB6C1)';
            }
        }

        function handleImageUpload(input, sectionId) {
            const file = input.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const section = document.querySelector(`[data-id="${sectionId}"]`);
                    let imageContainer = section.querySelector('.image-preview');
                    
                    if (!imageContainer) {
                        imageContainer = document.createElement('div');
                        imageContainer.className = 'image-preview';
                        section.querySelector('.view-mode').appendChild(imageContainer);
                    }
                    
                    imageContainer.innerHTML = `
                        <img src="${e.target.result}" alt="Imagen de la sección" class="section-image">
                        <button class="remove-image" onclick="removeImage(${sectionId})" title="Eliminar imagen">×</button>
                    `;
                    
                    // Animate image appearance
                    const img = imageContainer.querySelector('.section-image');
                    img.style.opacity = '0';
                    img.style.transform = 'scale(0.8)';
                    setTimeout(() => {
                        img.style.transition = 'all 0.5s ease';
                        img.style.opacity = '1';
                        img.style.transform = 'scale(1)';
                    }, 50);
                };
                reader.readAsDataURL(file);
            }
        }

        function removeImage(sectionId) {
            const section = document.querySelector(`[data-id="${sectionId}"]`);
            const imageContainer = section.querySelector('.image-preview');
            if (imageContainer) {
                const img = imageContainer.querySelector('.section-image');
                img.style.transition = 'all 0.3s ease';
                img.style.opacity = '0';
                img.style.transform = 'scale(0.8)';
                setTimeout(() => {
                    imageContainer.remove();
                }, 300);
            }
        }

        function saveSection(id) {
            const section = document.querySelector(`[data-id="${id}"]`);
            const textarea = section.querySelector('textarea');
            const viewP = section.querySelector('.view-mode p');
            
            viewP.textContent = textarea.value;
            
            // Save data
            saveData();
            
            // Animate save with sparkles
            const saveBtn = section.querySelector('.btn');
            const originalText = saveBtn.textContent;
            saveBtn.textContent = '✨ Guardado ✨';
            
            // Create sparkle effect
            createSparkles(saveBtn);
            
            setTimeout(() => {
                saveBtn.textContent = originalText;
            }, 2000);
        }

        function createSparkles(element) {
            for (let i = 0; i < 6; i++) {
                setTimeout(() => {
                    const sparkle = document.createElement('div');
                    sparkle.textContent = '✨';
                    sparkle.style.position = 'absolute';
                    sparkle.style.left = (element.offsetLeft + Math.random() * 100 - 50) + 'px';
                    sparkle.style.top = (element.offsetTop + Math.random() * 100 - 50) + 'px';
                    sparkle.style.fontSize = '16px';
                    sparkle.style.pointerEvents = 'none';
                    sparkle.style.zIndex = '1000';
                    sparkle.style.animation = 'twinkle 1.5s ease-out';
                    
                    element.parentNode.appendChild(sparkle);
                    
                    setTimeout(() => sparkle.remove(), 1500);
                }, i * 100);
            }
        }

        function deleteSection(id) {
            if (confirm('¿Estás seguro de que quieres eliminar esta sección? 🥺')) {
                const section = document.querySelector(`[data-id="${id}"]`);
                section.style.transition = 'all 0.5s ease';
                section.style.transform = 'translateX(-100%) rotate(-10deg)';
                section.style.opacity = '0';
                setTimeout(() => {
                    section.remove();
                }, 500);
            }
        }

        function toggleAddSection() {
            const addSection = document.getElementById('add-section');
            const isVisible = addSection.style.display !== 'none';
            
            if (isVisible) {
                addSection.style.display = 'none';
                // Clear form
                document.getElementById('new-title').value = '';
                document.getElementById('new-emoji').value = '';
                document.getElementById('new-content').value = '';
                document.getElementById('new-image').value = '';
            } else {
                addSection.style.display = 'block';
                addSection.scrollIntoView({ behavior: 'smooth' });
            }
        }

        function addSection() {
            const title = document.getElementById('new-title').value.trim();
            const emoji = document.getElementById('new-emoji').value.trim() || '💖';
            const content = document.getElementById('new-content').value.trim();
            const imageFile = document.getElementById('new-image').files[0];

            if (!title || !content) {
                alert('Por favor completa el título y el contenido 😊');
                return;
            }

            sectionCounter++;
            const container = document.getElementById('sections-container');
            
            const newSection = document.createElement('div');
            newSection.className = 'section';
            newSection.setAttribute('data-id', sectionCounter);
            newSection.style.opacity = '0';
            newSection.style.transform = 'translateY(30px) scale(0.9)';
            
            newSection.innerHTML = `
                <div class="view-mode">
                    <h3><span>${emoji}</span> ${title}</h3>
                    <p>${content}</p>
                </div>
                <div class="edit-mode" ${editMode ? 'style="display: block;"' : ''}>
                    <h3><span>${emoji}</span> ${title}</h3>
                    <textarea>${content}</textarea>
                    <input type="file" accept="image/*" onchange="handleImageUpload(this, ${sectionCounter})" class="image-upload">
                    <button class="btn" onclick="saveSection(${sectionCounter})">💾 Guardar</button>
                    <button class="btn delete-btn" onclick="deleteSection(${sectionCounter})">🗑️ Eliminar</button>
                </div>
            `;

            if (editMode) {
                newSection.querySelector('.view-mode').style.display = 'none';
            } else {
                newSection.querySelector('.edit-mode').style.display = 'none';
            }

            container.appendChild(newSection);

            // Handle image if provided
            if (imageFile) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const imageContainer = document.createElement('div');
                    imageContainer.className = 'image-preview';
                    imageContainer.innerHTML = `
                        <img src="${e.target.result}" alt="Imagen de la sección" class="section-image">
                        <button class="remove-image" onclick="removeImage(${sectionCounter})" title="Eliminar imagen">×</button>
                    `;
                    newSection.querySelector('.view-mode').appendChild(imageContainer);
                };
                reader.readAsDataURL(imageFile);
            }

            // Animate in
            setTimeout(() => {
                newSection.style.transition = 'all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
                newSection.style.opacity = '1';
                newSection.style.transform = 'translateY(0) scale(1)';
            }, 50);

            // Clear form and hide
            toggleAddSection();

            // Scroll to new section with celebration
            setTimeout(() => {
                newSection.scrollIntoView({ behavior: 'smooth' });
                createSparkles(newSection);
            }, 400);
        }

        // Create floating hearts occasionally
        function createFloatingHeart() {
            const hearts = ['💕', '💖', '💗', '💓', '💘'];
            const heart = document.createElement('div');
            heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
            heart.style.position = 'fixed';
            heart.style.left = Math.random() * (window.innerWidth - 50) + 'px';
            heart.style.top = window.innerHeight + 'px';
            heart.style.fontSize = Math.random() * 10 + 20 + 'px';
            heart.style.pointerEvents = 'none';
            heart.style.zIndex = '999';
            heart.style.transition = 'all 4s ease-out';

            document.body.appendChild(heart);

            setTimeout(() => {
                heart.style.transform = 'translateY(-' + (window.innerHeight + 100) + 'px) rotate(360deg)';
                heart.style.opacity = '0';
            }, 100);

            setTimeout(() => {
                heart.remove();
            }, 4000);
        }

        // Butterfly creation function
        function createButterfly() {
            const butterfly = document.createElement('div');
            butterfly.innerHTML = '🦋';
            butterfly.style.position = 'fixed';
            butterfly.style.fontSize = '25px';
            butterfly.style.pointerEvents = 'none';
            butterfly.style.zIndex = '998';
            butterfly.style.left = '-50px';
            butterfly.style.top = Math.random() * (window.innerHeight - 100) + 'px';
            butterfly.style.transition = 'all 8s linear';
            document.body.appendChild(butterfly);

            setTimeout(() => {
                butterfly.style.transform = 'translateX(' + (window.innerWidth + 100) + 'px)';
            }, 100);

            setTimeout(() => {
                butterfly.remove();
            }, 8000);
        }
    </script>
</body>
</html>
