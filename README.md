# lightsaltdesign
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Light Salt Design - ワーム＆製作方法</title>
    <meta name="description" content="ワームと製作方法の紹介。最新のお知らせをチェック！">
    <meta name="keywords" content="ワーム, 釣り, ルアー, 製作方法, 釣具">
    <meta name="author" content="Light Salt Design">
    <link rel="canonical" href="https://your-website.com">

    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        /* ナビバー */
        .navbar {
            background-color: black;
            padding: 10px;
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        .navbar a {
            color: white;
            text-decoration: none;
            padding: 10px;
            display: block;
            text-align: center;
        }
        .navbar a:hover {
            background-color: gray;
        }

        /* 画像コンテナ */
        .image-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        .image-box {
            width: 100%;
            max-width: 100px;
            text-align: center;
            box-sizing: border-box;
        }
        .image-box a {
            display: block;
            border: 2px solid black;
            overflow: hidden;
        }
        .image-box img {
            width: 100%;
            height: auto;
            display: block;
        }
        .caption {
            margin-top: 5px;
            font-weight: bold;
        }

        /* お知らせ欄 */
        .notice-container {
            margin: 20px;
            width: 90%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
        }
        .notice-box {
            border: 1px solid black;
            padding: 10px;
            width: 100%;
        }

        /* スマホ対応 */
        @media (max-width: 600px) {
            .navbar {
                flex-direction: column;
                align-items: center;
            }
            .image-container {
                flex-direction: column;
                align-items: center;
            }
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
        <div class="image-box">
            <a href="worm.html">
                <img id="worm-image" src="worm1.jpg" alt="ワーム">
            </a>
            <div class="caption">ワーム</div>
        </div>
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
            <ul id="notice-list"></ul>
        </div>
    </div>

    <script>
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
        setInterval(changeImages, 5000);

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

        updateNotices();
    </script>

</body>
</html>

