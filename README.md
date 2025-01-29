# lightsaltdesign
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Light Salt Design - ワーム＆製作方法</title>

    <!-- SEO対策 -->
    <meta name="description" content="ワームと製作方法の紹介。最新のお知らせをチェック！">
    <meta name="keywords" content="ワーム, 釣り, ルアー, 製作方法, 釣具">
    <meta name="author" content="Light Salt Design">
    <link rel="canonical" href="https://your-website.com">
    
    <!-- 構造化データ (SEO強化) -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "Website",
        "name": "Light Salt Design",
        "url": "https://your-website.com",
        "description": "ワームの紹介と製作方法。最新情報も随時更新！"
    }
    </script>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        /* ナビバー */
        .navbar {
            background-color: black;
            padding: 10px;
            display: flex;
            justify-content: space-around;
        }
        .navbar a {
            color: white;
            text-decoration: none;
            padding: 10px;
        }
        .navbar a:hover {
            background-color: gray;
        }
        /* 画像コンテナ */
        .image-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        .image-container a {
            display: block;
            width: 500px;
            height: 500px;
            border: 2px solid black;
            overflow: hidden;
        }
        .image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        /* お知らせ欄 */
        .notice-container {
            margin: 20px;
        }
        .notice-box {
            border: 1px solid black;
            padding: 10px;
            width: 300px;
            margin: 0 auto;
        }
    </style>
</head>
<body>

    <!-- ナビバー -->
    <div class="navbar">
        <a href="worm.html">ワーム</a>
        <a href="seisaku.html">製作方法</a>
        <a href="https://www.instagram.com/light.salt.design/" target="_blank">Instagram</a>
        <a href="https://twitter.com" target="_blank">X</a>
        <a href="#notices">お知らせ</a>
    </div>

    <h1>Light Salt Design</h1>

    
         <!-- 画像エリア -->
    <div class="image-container">
        <!-- ワーム画像（スライドショー） -->
     <div class="image-box">
        <a href="worm.html">
            <img id="worm-image" src="worm1.jpg" alt="ワーム">
        </a>
        <div class="caption">ワーム</div>
     </div>
        <!-- 製作方法画像（スライドショー） -->
     <div class="image-box">
        <a href="seisaku.html">
            <img id="seisaku-image" src="seisaku1.jpg" alt="製作方法">
        </a>
        <div class="caption">製作方法</div>
     </div>
    </div>

    

    <!-- お知らせ欄 -->
    <div class="notice-container">
        <h2>お知らせ</h2>
        <div class="notice-box" id="notices">
            <ul id="notice-list">
                <!-- 最新のお知らせ4件がここに表示される -->
            </ul>
        </div>
    </div>

    <script>
        // 画像スライドショー（5秒ごとに切り替え）
        let wormImages = ["worm1.jpg", "worm2.jpg", "worm3.jpg"];
        let seisakuImages = ["seisaku1.jpg", "seisaku2.jpg", "seisaku3.jpg"];
        let wormIndex = 0;
        let seisakuIndex = 0;

        function changeImages() {
            wormIndex = (wormIndex + 1) % wormImages.length;
            seisakuIndex = (seisakuIndex + 1) % seisakuImages.length;
            document.getElementById("worm-image").src = wormImages[wormIndex];
            document.getElementById("seisaku-image").src = seisakuImages[seisakuIndex];
        }
        setInterval(changeImages, 5000); // 5秒ごとに画像を変更
	</script>

        <script>
        let notices = [
            { text: "お知らせ 1", link: "notice1.html" },
            { text: "お知らせ 2", link: "notice2.html" },
            { text: "お知らせ 3", link: "notice3.html" },
            { text: "お知らせ 4", link: "notice4.html" }
        ];

        function updateNotices() {
            let noticeList = document.getElementById("notice-list");
            noticeList.innerHTML = "";
            notices.forEach(notice => {
                let li = document.createElement("li");
                let a = document.createElement("a");
                a.href = notice.link;
                a.textContent = notice.text;
                li.appendChild(a);
                noticeList.appendChild(li);
            });
        }

        function addNotice(newNotice) {
            notices.unshift(newNotice);
            if (notices.length > 4) {
                notices.pop();
            }
            updateNotices();
        }

        updateNotices();

        // 管理者のみが新しいお知らせを追加できるようにする
        function adminAddNotice(text, link) {
            let newNotice = { text: text, link: link };
            addNotice(newNotice);
        }            </script>

</body>
</html>
