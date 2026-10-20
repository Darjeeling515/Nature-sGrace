<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Health & Wellness - サプリメント公式通販</title>
    <style>
        :root {
            --primary-color: #2e7d32;
            --bg-color: #f5f5f5;
            --text-color: #333;
            --card-bg: #fff;
            --border-color: #e0e0e0;
            --accent-color: #e65100;
        }

        /* 暗転後のダークモード変数 */
        body.dark-mode {
            --primary-color: #8b0000;
            --bg-color: #0a0a0a;
            --text-color: #e0e0e0;
            --card-bg: #1a1a1a;
            --border-color: #333;
            --accent-color: #ff1744;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Helvetica Neue', Arial, 'Hiragino Kaku Gothic ProN', 'Hiragino Sans', Meiryo, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            transition: background-color 1.5s ease, color 1.5s ease;
        }

        header {
            background-color: var(--primary-color);
            color: #fff;
            padding: 2rem 1rem;
            text-align: center;
            transition: background-color 1.5s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1rem;
        }

        /* VIPコード入力エリア（目立たせる） */
        .vip-banner {
            background: linear-gradient(135deg, #fff3e0, #ffe0b2);
            border: 2px dashed var(--accent-color);
            border-radius: 8px;
            padding: 2rem;
            text-align: center;
            margin-bottom: 3rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            transition: opacity 1s ease;
        }
        
        body.dark-mode .vip-banner {
            display: none; /* ダークモード時は隠す */
        }

        .vip-banner h2 {
            color: var(--accent-color);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .vip-input-group {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 1rem;
        }

        .vip-input-group input {
            padding: 12px 20px;
            font-size: 1.2rem;
            border: 2px solid #ccc;
            border-radius: 4px;
            width: 300px;
            text-align: center;
            letter-spacing: 2px;
        }

        .vip-input-group button {
            padding: 12px 30px;
            font-size: 1.1rem;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s;
        }

        .vip-input-group button:hover {
            background-color: #bf360c;
        }

        #error-msg {
            color: red;
            margin-top: 10px;
            font-weight: bold;
            display: none;
        }

        /* 商品グリッド */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s, background-color 1.5s, border-color 1.5s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0,0,0,0.1);
        }
        
        body.dark-mode .card:hover {
            box-shadow: 0 8px 20px rgba(255, 0, 0, 0.2);
        }

        .item-code {
            font-family: monospace;
            color: #888;
            font-size: 0.9rem;
            margin-bottom: 10px;
            display: inline-block;
            background: rgba(0,0,0,0.05);
            padding: 3px 8px;
            border-radius: 4px;
        }
        
        body.dark-mode .item-code {
            color: #ff5252;
            background: rgba(255,0,0,0.1);
        }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            height: 3rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card p {
            font-size: 0.95rem;
            line-height: 1.5;
            margin-bottom: 20px;
            height: 4rem;
            overflow: hidden;
        }

        .price {
            font-size: 1.4rem;
            font-weight: bold;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .add-to-cart {
            width: 100%;
            padding: 10px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            transition: opacity 0.3s;
        }

        .add-to-cart:hover {
            opacity: 0.8;
        }

        /* 警告モーダル（ダークウェブ侵入時） */
        #warning-modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 9999;
            color: red;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        #warning-modal h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 0 0 10px red;
        }

        #warning-modal p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            line-height: 1.6;
            max-width: 600px;
        }

        #warning-modal button {
            background: transparent;
            color: red;
            border: 2px solid red;
            padding: 15px 40px;
            font-size: 1.2rem;
            cursor: pointer;
