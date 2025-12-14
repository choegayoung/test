<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Canvas Catalyst - 화가를 위한 후원 플랫폼</title>
    
    <style>
        /* 기본 설정 및 전체 레이아웃 (1920x1080 기준) */
        :root {
            --primary-color: #3f51b5; /* 인디고 */
            --secondary-color: #ff9800; /* 오렌지 */
            --text-color: #333;
            --bg-color: #f4f4f9;
            --max-width: 1600px;
        }

        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--bg-color);
            color: var(--text-color);
            min-height: 100vh;
            /* Flexbox를 사용하여 footer를 하단에 고정 */
            display: flex;
            flex-direction: column;
        }

        /* 🧱 헤더 스타일 */
        .main-header {
            background-color: #fff;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            padding: 20px 40px;
            /* Flexbox 컨테이너 설정 */
            display: flex;
            justify-content: space-between; /* 타이틀과 네비게이션 분리 */
            align-items: center; /* 수직 중앙 정렬 */
        }

        .site-title {
            margin: 0;
            color: var(--primary-color);
            font-size: 2.5em;
            font-weight: bold;
        }

        .main-nav a {
            text-decoration: none;
            color: var(--text-color);
            margin-left: 25px;
            font-weight: 500;
            transition: color 0.3s;
        }

        .main-nav a:hover {
            color: var(--secondary-color);
        }

        /* 🖼️ 메인 콘텐츠 스타일 */
        .main-content {
            width: 100%;
            max-width: var(--max-width);
            margin: 30px auto; /* 중앙 정렬 */
            padding: 0 20px;
            /* Flexbox를 사용하여 콘텐츠가 늘어나도록 설정 */
            flex-grow: 1;
        }

        .artist-showcase, .user-profile-section, .payment-section {
            padding: 40px;
            background-color: #fff;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
        }

        .artist-showcase h2 { display: flex;
            border-radius: 100px;
            color: var(--primary-color);
            margin-bottom: 40px;
            font-size: 2em;
        }

        /* 🧑‍🎨 아티스트 카드 스타일 (Flex 컨테이너) */
        .artist-card {
            display: flex; /* 내부 요소 (사진/설명)를 수평 배치 */
            margin-bottom: 30px;
            padding: 20px;
            border: 1px solid #eee;
            border-radius: 8px;
            align-items: flex-start; /* 상단 정렬 */
        }

        /* 📸 프로필 사진 컨테이너 (1:1 크기 유지) */
        .profile-container {
            flex-shrink: 0; /* 축소 방지 */
            width: 200px; /* 기본 크기 */
            height: 200px;
            margin-right: 30px;
        }

        .profile-photo {
            width: 100%;
            height: 100%;
            object-fit: cover; /* 이미지가 컨테이너를 채우도록 설정 */
            border-radius: 50%; /* 원형 프로필 사진 */
            border: 4px solid var(--secondary-color);
        }

        /* 📝 설명 영역 */
        .description-area {
            flex-grow: 1; /* 남은 공간을 채우도록 확장 */
        }

        .description-area h3 {
            margin-top: 0;
            color: var(--primary-color);
        }

        .description-area p {
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .support-button {
            display: inline-block;
            background-color: var(--secondary-color);
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: background-color 0.3s;
        }

        .support-button:hover {
            background-color: #e68900;
        }

        /* 👤 프로필 페이지 스타일 */
        .user-profile-section {
            display: flex; 
            flex-direction: column; 
            align-items: center; 
            text-align: center;
        }
        .profile-avatar {
            width: 150px; 
            height: 150px; 
            background-color: #ccc; 
            border-radius: 50%; 
            margin-bottom: 20px;
        }
        .dashboard {
            display: flex; 
            gap: 30px; 
            margin-top: 30px;
        }
        .info-box {
            padding: 20px; 
            border: 1px solid #ddd; 
            border-radius: 8px;
        }

        /* 💰 후원 페이지 스타일 */
        .payment-section {
            max-width: 600px; 
            margin: 0 auto;
        }
        .level-button {
            padding: 10px 15px;
            background-color: var(--bg-color);
            border: 1px solid var(--primary-color);
            color: var(--primary-color);
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s, color 0.3s;
        }
        .level-button:hover {
            background-color: var(--primary-color);
            color: white;
        }


        /* 🦶 푸터 스타일 */
        .main-footer {
            padding: 15px 0;
            text-align: center;
            background-color: #333;
            color: #fff;
            margin-top: auto; /* main-content가 늘어나도 하단에 고정 */
        }

        /* 📱 반응형 디자인: 작은 화면 */
        @media (max-width: 900px) {
            .main-header {
                flex-direction: column; 
                text-align: center;
            }

            .main-nav {
                margin-top: 15px;
            }

            .main-nav a {
                margin: 0 10px;
                display: inline-block;
            }

            .artist-card {
                flex-direction: column; 
                align-items: center;
                text-align: center;
            }

            .profile-container {
                margin: 0 auto 20px auto;
            }
            
            .description-area {
                text-align: left; 
            }
            
            .dashboard {
                flex-direction: column; /* 대시보드 박스 세로 정렬 */
                gap: 15px;
            }
        }
    </style>
</head>
<body>

    <header class="main-header">
        <h1 class="site-title">Canvas Catalyst</h1>
        <nav class="main-nav">
            <a href="#">홈 (메인)</a>
            <a href="#">둘러보기</a>
            <a href="#">시작하기</a>
            <a href="#">내 프로필</a>
            <a href="#">후원하기</a>
        </nav>
    </header>

    <main class="main-content">
        
        <section class="artist-showcase">
            <h2 style= "border-radius: 100px;">🔥 이달의 인기 아티스트</h2>
            
            <div class="artist-card">
                <div class="profile-container">

                    <img src="placeholder-artist1.jpg" alt="아티스트 A 프로필" class="profile-photo" style="border-radius: 100px;">
                </div>
                <div class="description-area">
                    <h3>아티스트 A: 빛과 그림자의 대가</h3>
                    <p>
                        아티스트 A는 전통 유화 기법을 현대적으로 재해석하는 작가입니다. 그의 작품은 깊이 있는 색채와 섬세한 명암 대비가 특징이며, 일상 속 찰나의 감정을 포착합니다.
                        그는 현재 새로운 대형 프로젝트 '도시의 기억'을 준비 중이며, 후원자님의 지지는 재료 구입과 전시 공간 확보에 큰 도움이 될 것입니다. 그의 창작 여정에 함께 해주세요! 
                        (총 15줄 이내의 간략한 설명이 여기에 들어갑니다. 이 텍스트는 설명을 위한 예시입니다.)
                        추가적인 설명...
                        추가적인 설명...
                        추가적인 설명...
                        추가적인 설명...
                    </p>
                    <a href="#" class="support-button">후원 페이지로 이동</a>
                </div>
            </div>

            <div class="artist-card">
                <div class="profile-container">
                    <img src="placeholder-artist2.jpg" alt="아티스트 B 프로필" class="profile-photo" style="border-radius: 120px;
                    ">
                </div>
                <div class="description-area">
                    <h3>아티스트 B: 디지털 드로잉의 혁신가</h3>
                    <p>
                        아티스트 B는 디지털 드로잉을 통해 초현실적인 세계를 구축하는 데 탁월합니다. 픽셀 하나하나에 생명을 불어넣어 독특한 상상력을 시각화합니다.
                        그의 목표는 인터랙티브한 디지털 아트 전시를 여는 것이며, 후원금은 고성능 장비 업그레이드 및 소프트웨어 라이선스 비용으로 사용될 것입니다.
                        (총 15줄 이내의 간략한 설명이 여기에 들어갑니다. 이 텍스트는 설명을 위한 예시입니다.)
                        추가적인 설명...
                        추가적인 설명...
                        추가적인 설명...
                        추가적인 설명...
                        추가적인 설명...
                    </p>
                    <a href="#" class="support-button">후원 페이지로 이동</a>
                </div>
            </div>
            
        </section>

        </main>

    <footer class="main-footer">
        <p>&copy; 2025 Canvas Catalyst. All rights reserved.</p>
    </footer>

</body>
</html>
