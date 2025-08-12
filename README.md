<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI 會議掃描器與日曆助理 - README</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif, 'Noto Sans TC', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-100">
    <div class="container mx-auto p-4 sm:p-6 md:p-8 max-w-4xl">
        <div class="bg-white rounded-lg shadow-lg p-6 sm:p-8 md:p-10">
            <header class="border-b pb-4 mb-6">
                <h1 class="text-3xl sm:text-4xl font-bold text-gray-900">AI 會議掃描器與日曆助理</h1>
            </header>

            <main class="space-y-8">
                <section>
                    <p class="text-gray-700 leading-relaxed">
                        這是一個單頁式網頁應用程式，它使用 AI 掃描圖片和 PDF 中的活動資訊，並將其新增至您的 Google 日曆。它的設計宗旨在於快速將傳單、海報或任何文件上的活動細節數位化，為您節省手動輸入的時間。
                    </p>
                </section>

                <section>
                    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">✨ 功能特色</h2>
                    <ul class="list-disc list-inside space-y-2 text-gray-700">
                        <li><strong>AI 資訊擷取：</strong> 使用 Gemini AI 模型來辨識並擷取活動的標題、日期、時間、主持人、地點和備註等細節。</li>
                        <li><strong>Google 日曆整合：</strong> 只需點擊一下，即可將擷取的活動資訊直接新增至您的主要 Google 日曆。</li>
                        <li>
                            <strong>多種輸入方式：</strong>
                            <ul class="list-circle list-inside pl-5 mt-2 space-y-1">
                                <li><strong>檔案上傳：</strong> 從您的裝置中選擇圖片或 PDF 檔案。</li>
                                <li><strong>拖放功能：</strong> 將檔案直接拖曳至上傳區域。</li>
                                <li><strong>相機拍攝：</strong> 使用您裝置的相機直接拍攝文件照片。</li>
                            </ul>
                        </li>
                        <li><strong>可編輯欄位：</strong> 在將資訊新增至日曆前，可以預覽並編輯擷取的內容。</li>
                        <li><strong>在地化 AI 回應：</strong> AI 被設定為優先以繁體中文 (zh-tw) 提供擷取的資訊。</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">🚀 如何使用</h2>
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mt-4 mb-2">1. 初始設定 (僅需一次)</h3>
                        <p class="text-gray-700 mb-4">要使用 Google 日曆和 AI 掃描功能，您需要將此應用程式連結至您自己的 Google Cloud 專案。</p>
                        <ol class="list-decimal list-inside space-y-3 text-gray-700">
                            <li>
                                <strong>建立 Google Cloud 憑證：</strong>
                                <ul class="list-circle list-inside pl-5 mt-2 space-y-1">
                                    <li>前往 <a href="https://console.cloud.google.com/" target="_blank" class="text-blue-600 hover:underline">Google Cloud Console</a>。</li>
                                    <li>如果您還沒有專案，請建立一個新專案。</li>
                                    <li>啟用 <strong>Google Calendar API</strong> 和 <strong>Generative Language API</strong>。</li>
                                    <li>前往 <strong>「憑證」</strong> 頁面並建立一組 <strong>API 金鑰</strong>。</li>
                                    <li>為「網頁應用程式」建立一個 <strong>OAuth 2.0 用戶端 ID</strong>。</li>
                                </ul>
                            </li>
                            <li>
                                <strong>部署應用程式：</strong>
                                <ul class="list-circle list-inside pl-5 mt-2 space-y-1">
                                    <li>儲存此專案中的 <code class="bg-gray-200 text-sm p-1 rounded">index.html</code> 檔案。</li>
                                    <li>將其部署到像 <a href="https://zeabur.com/" target="_blank" class="text-blue-600 hover:underline">Zeabur</a>、Vercel 或 Netlify 這樣的託管服務上，以獲得一個永久的 URL。本指南假設您在 Zeabur 上進行部署。</li>
                                </ul>
                            </li>
                            <li>
                                <strong>設定憑證：</strong>
                                <ul class="list-circle list-inside pl-5 mt-2 space-y-1">
                                    <li>在您的 OAuth 2.0 用戶端 ID 設定中，將您的應用程式 URL (例如 <code class="bg-gray-200 text-sm p-1 rounded">https://your-app.zeabur.app</code>) 新增至 <strong>「已授權的 JavaScript 來源」</strong> 和 <strong>「已授權的重新導向 URI」</strong> 這兩個欄位。</li>
                                    <li>在您的 API 金鑰設定中，請確保沒有任何 API 限制，或者已明確允許使用「Generative Language API」。</li>
                                </ul>
                            </li>
                            <li>
                                <strong>發布應用程式：</strong>
                                <ul class="list-circle list-inside pl-5 mt-2 space-y-1">
                                    <li>在 Google Cloud Console 的 <strong>「OAuth 同意畫面」</strong> 部分，將發布狀態從「測試」變更為 <strong>「正式版」</strong>，以避免授權錯誤。</li>
                                </ul>
                            </li>
                        </ol>
                    </div>
                    <div>
                        <h3 class="text-xl font-semibold text-gray-800 mt-6 mb-2">2. 使用應用程式</h3>
                        <ol class="list-decimal list-inside space-y-2 text-gray-700">
                            <li><strong>輸入憑證：</strong> 開啟應用程式，展開「Google Calendar Settings」部分，然後貼上您的 <strong>API 金鑰</strong>和<strong>用戶端 ID</strong>。點擊「Save & Initialize」。</li>
                            <li><strong>上傳檔案：</strong> 使用檔案選擇器、拖放功能或相機來上傳您的活動圖片或 PDF。</li>
                            <li><strong>AI 掃描：</strong> 預覽畫面將會出現。點擊「Scan File with AI」。</li>
                            <li><strong>預覽與編輯：</strong> AI 將會填入「Extracted Information」中的欄位。您可以點擊任何欄位來編輯文字。</li>
                            <li><strong>新增至日曆：</strong> 點擊「Add to Google Calendar」。首次使用時，系統可能會要求您登入 Google 帳戶並授予權限。</li>
                        </ol>
                    </div>
                </section>

                <section>
                    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">🛠️ 使用技術</h2>
                    <ul class="list-disc list-inside space-y-2 text-gray-700">
                        <li><strong>HTML, CSS, JavaScript:</strong> 網頁應用程式的核心。</li>
                        <li><strong>Tailwind CSS:</strong> 用於設計使用者介面。</li>
                        <li><strong>Google Generative AI (Gemini):</strong> 用於 AI 驅動的文字擷取。</li>
                        <li><strong>Google Calendar API:</strong> 用於建立日曆活動。</li>
                        <li><strong>Google Identity Services:</strong> 用於 OAuth 2.0 身份驗證。</li>
                        <li><strong>PDF.js:</strong> 用於在瀏覽器中呈現 PDF 預覽。</li>
                    </ul>
                </section>

                <section>
                    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">🤝 貢獻</h2>
                    <p class="text-gray-700 mb-4">
                        歡迎各種貢獻！如果您對新功能或改進有任何想法，請隨時 fork 此儲存庫並提交 pull request。
                    </p>
                    <ol class="list-decimal list-inside space-y-2 text-gray-700">
                        <li>Fork 本專案</li>
                        <li>建立您的功能分支 (<code class="bg-gray-200 text-sm p-1 rounded">git checkout -b feature/AmazingFeature</code>)</li>
                        <li>提交您的變更 (<code class="bg-gray-200 text-sm p-1 rounded">git commit -m 'Add some AmazingFeature'</code>)</li>
                        <li>推送至分支 (<code class="bg-gray-200 text-sm p-1 rounded">git push origin feature/AmazingFeature</code>)</li>
                        <li>開啟一個 Pull Request</li>
                    </ol>
                </section>

                <section>
                    <h2 class="text-2xl font-semibold text-gray-800 border-b pb-2 mb-4">📄 授權</h2>
                    <p class="text-gray-700">
                        本專案採用 MIT 授權。詳情請參閱 <code class="bg-gray-200 text-sm p-1 rounded">LICENSE</code> 檔案。
                    </p>
                </section>
            </main>
        </div>
    </div>
</body>
</html>
