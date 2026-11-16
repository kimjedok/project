<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>대한민국 해군 소개 | ROK NAVY</title>
    <style>
        :root {
            --bg-white: #FFFFFF;
            --navy-blue: #0E4A84;
            --navy-dark: #09325A;
            --point-gray: #898C8E;
            --light-gray-bg: #F8F9FA;
            --border-color: #E2E5E8;
            --text-dark: #1E2328;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, 'Malgun Gothic', sans-serif;
            background-color: var(--bg-white);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* 상단 내비게이션 */
        nav {
            position: sticky;
            top: 0;
            z-index: 100;
            background-color: var(--bg-white);
            border-bottom: 1px solid var(--border-color);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.25rem;
            font-weight: 800;
            color: var(--navy-blue);
            letter-spacing: -0.5px;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logo span {
            color: var(--point-gray);
            font-weight: 500;
            font-size: 0.9rem;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 600;
            font-size: 0.95rem;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: var(--navy-blue);
        }

        /* 히어로 배너 */
        header {
            background-color: var(--navy-blue);
            color: var(--bg-white);
            padding: 5rem 1.5rem;
            text-align: center;
            border-bottom: 4px solid var(--point-gray);
        }

        header .sub-badge {
            display: inline-block;
            border: 1px solid var(--point-gray);
            color: var(--bg-white);
            padding: 0.25rem 0.85rem;
            font-size: 0.8rem;
            letter-spacing: 2px;
            margin-bottom: 1rem;
            border-radius: 2px;
        }

        header h1 {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            letter-spacing: -1px;
        }

        header p {
            max-width: 650px;
            margin: 0 auto;
            font-size: 1.05rem;
            color: rgba(255, 255, 255, 0.88);
        }

        /* 공통 섹션 레이아웃 */
        main {
            max-width: 1100px;
            margin: 0 auto;
            padding: 3rem 1.5rem;
        }

        section {
            margin-bottom: 5rem;
            scroll-margin-top: 80px;
        }

        .section-header {
            border-left: 4px solid var(--navy-blue);
            padding-left: 1rem;
            margin-bottom: 2rem;
        }

        .section-header .eng-title {
            color: var(--point-gray);
            font-size: 0.85rem;
            font-weight: 700;
            letter-spacing: 1.5px;
            text-transform: uppercase;
        }

        .section-header h2 {
            color: var(--navy-blue);
            font-size: 1.75rem;
            font-weight: 800;
        }

        /* 1. 편제 (주력부대) 그리드 */
        .unit-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 1.25rem;
        }

        .unit-card {
            background-color: var(--bg-white);
            border: 1px solid var(--border-color);
            border-top: 3px solid var(--navy-blue);
            padding: 1.5rem;
            border-radius: 4px;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .unit-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 20px rgba(14, 74, 132, 0.08);
        }

        .unit-tag {
            display: inline-block;
            font-size: 0.75rem;
            color: var(--point-gray);
            font-weight: 700;
            margin-bottom: 0.4rem;
        }

        .unit-card h3 {
            color: var(--navy-blue);
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }

        .unit-card p {
            font-size: 0.92rem;
            color: #4A5056;
        }

        /* 2. 전력 (함정 체계) 탭 및 카드 */
        .fleet-tabs {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tab-btn {
            background-color: var(--bg-white);
            border: 1px solid var(--point-gray);
            color: var(--text-dark);
            padding: 0.5rem 1.1rem;
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            border-radius: 3px;
            transition: all 0.2s;
        }

        .tab-btn.active, .tab-btn:hover {
            background-color: var(--navy-blue);
            border-color: var(--navy-blue);
            color: var(--bg-white);
        }

        .fleet-table-wrap {
            overflow-x: auto;
            border: 1px solid var(--border-color);
            border-radius: 4px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
            font-size: 0.95rem;
        }

        th {
            background-color: var(--navy-blue);
            color: var(--bg-white);
            padding: 0.9rem 1.2rem;
            font-weight: 600;
            white-space: nowrap;
        }

        td {
            padding: 0.9rem 1.2rem;
            border-bottom: 1px solid var(--border-color);
        }

        tr:last-child td {
            border-bottom: none;
        }

        tr:nth-child(even) {
            background-color: var(--light-gray-bg);
        }

        .ship-badge {
            display: inline-block;
            background-color: var(--bg-white);
            border: 1px solid var(--point-gray);
            color: var(--navy-blue);
            font-size: 0.8rem;
            font-weight: 700;
            padding: 0.15rem 0.5rem;
            border-radius: 3px;
            margin-right: 0.4rem;
        }

        .ref-link-box {
            margin-top: 1rem;
            text-align: right;
            font-size: 0.88rem;
        }

        .ref-link-box a {
            color: var(--navy-blue);
            text-decoration: none;
            font-weight: 600;
        }

        .ref-link-box a:hover {
            text-decoration: underline;
        }

        /* 3. 해군 관련 뉴스 */
        .news-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.25rem;
            margin-bottom: 1.5rem;
        }

        .news-card {
            border: 1px solid var(--border-color);
            padding: 1.5rem;
            border-radius: 4px;
            background-color: var(--bg-white);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .news-meta {
            font-size: 0.8rem;
            color: var(--point-gray);
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .news-card h3 {
            font-size: 1.08rem;
            color: var(--text-dark);
            margin-bottom: 0.75rem;
            line-height: 1.4;
        }

        .news-card p {
            font-size: 0.9rem;
            color: #555;
            margin-bottom: 1rem;
        }

        .news-banner {
            background-color: var(--light-gray-bg);
            border: 1px solid var(--border-color);
            border-left: 4px solid var(--point-gray);
            padding: 1.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 1rem;
            border-radius: 4px;
        }

        .news-banner-text h4 {
            color: var(--navy-blue);
            font-size: 1.1rem;
            margin-bottom: 0.25rem;
        }

        .news-banner-text p {
            color: #555;
            font-size: 0.9rem;
        }

        .btn-primary {
            display: inline-block;
            background-color: var(--navy-blue);
            color: var(--bg-white);
            padding: 0.75rem 1.5rem;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95rem;
            border-radius: 4px;
            transition: background-color 0.2s;
        }

        .btn-primary:hover {
            background-color: var(--navy-dark);
        }

        /* 푸터 */
        footer {
            background-color: var(--bg-white);
            border-top: 1px solid var(--border-color);
            padding: 2.5rem 1.5rem;
            text-align: center;
            color: var(--point-gray);
            font-size: 0.9rem;
        }

        footer strong {
            color: var(--navy-blue);
        }

        @media (max-width: 640px) {
            header h1 {
                font-size: 1.9rem;
            }
            .nav-links {
                gap: 1rem;
                font-size: 0.85rem;
            }
        }
    </style>
</head>
<body>

    <!-- 상단 내비게이션 -->
    <nav>
        <a href="#" class="logo">ROK NAVY <span>| 대한민국 해군 소개</span></a>
        <ul class="nav-links">
            <li><a href="#organization">편제</a></li>
            <li><a href="#forces">전력</a></li>
            <li><a href="#news">해군 뉴스</a></li>
        </ul>
    </nav>

    <!-- 메인 히어로 영역 -->
    <header>
        <div class="sub-badge">REPUBLIC OF KOREA NAVY</div>
        <h1>필승해군 · 정예해군</h1>
        <p>조국의 바다를 수호하고 세계 평화에 기여하는 대한민국 해군의 주요 편제와 핵심 해상 전력을 소개합니다.</p>
    </header>

    <main>
        <!-- 1. 편제 (주력부대) -->
        <section id="organization">
            <div class="section-header">
                <div class="eng-title">01. Organization</div>
                <h2>편제 (주력부대)</h2>
            </div>
            <div class="unit-grid">
                <div class="unit-card">
                    <span class="unit-tag">동해 수호</span>
                    <h3>제1함대사령부</h3>
                    <p>강원도 동해시에 위치하며, 동해 해역의 영해 수호와 해상 방위 작전을 전담하는 주력 함대입니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">서해 수호</span>
                    <h3>제2함대사령부</h3>
                    <p>경기도 평택시에 위치하며, 서해 NLL(북방한계선) 사수 및 수도권 서측 해역 방어를 책임집니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">남해 수호</span>
                    <h3>제3함대사령부</h3>
                    <p>전라남도 영암군에 위치하며, 남해 및 제주 해역의 해상 교통로 보호와 연안 방어를 수행합니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">수중 전략전력</span>
                    <h3>잠수함사령부</h3>
                    <p>경상남도 창원시 진해에 본부를 두고, 은밀한 수중 작전과 국가 전략 억제 임무를 수행합니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">입체 항공작전</span>
                    <h3>해군항공사령부</h3>
                    <p>해상초계기 및 해상작전헬기를 운용하며 대잠수함 작전, 해상 감시·정찰 및 구조 임무를 담당합니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">특수작전 전력</span>
                    <h3>해군특수전전단 (UDT/SEAL)</h3>
                    <p>전천후 특수타격, 폭발물 처리(EOD), 해난구조(SSU) 등 고난도 특수작전을 수행하는 최정예 부대입니다.</p>
                </div>
                <div class="unit-card">
                    <span class="unit-tag">국가전략기동부대</span>
                    <h3>해병대사령부</h3>
                    <p>상륙작전을 주임무로 하며, 서북도서 방어 및 신속기동부대로서 국가 위기 대응의 선봉에 섭니다.</p>
                </div>
            </div>
        </section>

        <!-- 2. 전력 (함정 체계) -->
        <section id="forces">
            <div class="section-header">
                <div class="eng-title">02. Naval Forces</div>
                <h2>전력 (주요 운용 함선)</h2>
            </div>

            <div class="fleet-tabs">
                <button class="tab-btn active" onclick="filterFleet('all', this)">전체 보기</button>
                <button class="tab-btn" onclick="filterFleet('destroyer', this)">구축함</button>
                <button class="tab-btn" onclick="filterFleet('frigate', this)">호위함·초계함</button>
                <button class="tab-btn" onclick="filterFleet('submarine', this)">잠수함</button>
                <button class="tab-btn" onclick="filterFleet('amphibious', this)">상륙·기뢰·지원함</button>
                <button class="tab-btn" onclick="filterFleet('patrol', this)">고속함·고속정</button>
            </div>

            <div class="fleet-table-wrap">
                <table id="fleetTable">
                    <thead>
                        <tr>
                            <th>함종 구분</th>
                            <th>함급 / 분류 기호</th>
                            <th>주요 특징 및 대표 함정</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr data-category="destroyer">
                            <td><strong>구축함</strong></td>
                            <td><span class="ship-badge">DDG</span> 정조대왕급 · 세종대왕급</td>
                            <td>이지스(Aegis) 전투체계를 탑재한 대한민국 해군의 핵심 기동함대 주력 전력 (KDDX 차세대 구축함 추진)</td>
                        </tr>
                        <tr data-category="destroyer">
                            <td><strong>구축함</strong></td>
                            <td><span class="ship-badge">DDH</span> 충무공이순신급 · 광개토대왕급</td>
                            <td>대공·대함·대잠 입체 작전 능력을 갖춘 한국형 다목적 구축함</td>
                        </tr>
                        <tr data-category="frigate">
                            <td><strong>호위함</strong></td>
                            <td><span class="ship-badge">FFG</span> 충남급 · 대구급 · 인천급</td>
                            <td>해역함대의 주력 전투함으로 대잠 능력과 대함·대공 방어력을 대폭 강화한 차기 호위함</td>
                        </tr>
                        <tr data-category="frigate">
                            <td><strong>초계함</strong></td>
                            <td><span class="ship-badge">PCC</span> 포항급</td>
                            <td>연안 경비 및 대잠 초계 임무를 수행해 온 핵심 연안 방어 전력</td>
                        </tr>
                        <tr data-category="submarine">
                            <td><strong>잠수함</strong></td>
                            <td><span class="ship-badge">SS</span> 도산안창호급 · 손원일급 · 장보고급</td>
                            <td>3,000톤급 중형 잠수함(도산안창호급)부터 1,800톤·1,200톤급까지 운용하는 핵심 수중 전력</td>
                        </tr>
                        <tr data-category="amphibious">
                            <td><strong>상륙함</strong></td>
                            <td><span class="ship-badge">LPH</span> 독도급 / <span class="ship-badge">LST</span> 천왕봉급·고준봉급</td>
                            <td>대형수송함(독도함·마라도함)을 중심으로 상륙작전 지휘 및 병력·장비 수송 수행</td>
                        </tr>
                        <tr data-category="amphibious">
                            <td><strong>기뢰전·지원함</strong></td>
                            <td><span class="ship-badge">MLS/MSH</span> 원산·남포·양양급 / <span class="ship-badge">AOE</span> 소양·천지급</td>
                            <td>기뢰 부설·소해함, 군수지원함, 수상함·잠수함 구조함(통영함·강화도함), 훈련함(한산도함)</td>
                        </tr>
                        <tr data-category="patrol">
                            <td><strong>고속함·고속정</strong></td>
                            <td><span class="ship-badge">PKG</span> 윤영하급 / <span class="ship-badge">PKMR</span> 참수리급(신형)</td>
                            <td>연안 및 NLL 수호를 담당하는 고기동 유도탄고속함 및 신형 고속정 전력</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="ref-link-box">
                <a href="https://namu.wiki/w/%ED%8B%80:%ED%98%84%EB%8C%80%EC%A0%84/%ED%95%9C%EA%B5%AD%20%ED%95%A8%EC%84%A0" target="_blank" rel="noopener noreferrer">
                    ↗ 상세 한국 함선 분류 체계 전체보기 (나무위키 참고 자료)
                </a>
            </div>
        </section>

        <!-- 3. 해군 관련 뉴스 -->
        <section id="news">
            <div class="section-header">
                <div class="eng-title">03. Navy News</div>
                <h2>해군 관련 뉴스</h2>
            </div>

            <div class="news-container">
                <div class="news-card">
                    <div>
                        <div class="news-meta">해상 안보 · 국제 동향</div>
                        <h3>호르무즈 해협 등 주요 해상 교통로 및 글로벌 해군 작전 동향</h3>
                        <p>국제 해상 물류 핵심 요충지의 기뢰·선박 안전 이슈 및 각국 해군의 해상 작전 현황 관련 주요 보도입니다.</p>
                    </div>
                </div>
                <div class="news-card">
                    <div>
                        <div class="news-meta">전력 증강 · 방위산업</div>
                        <h3>차세대 이지스 구축함 및 한국형 함정 건조·인도 소식</h3>
                        <p>정조대왕급 구축함, 충남급 호위함, 도산안창호급 잠수함 등 해군 첨단 전력화 추진 현황을 확인하세요.</p>
                    </div>
                </div>
            </div>

            <div class="news-banner">
                <div class="news-banner-text">
                    <h4>실시간 해군 최신 뉴스 모아보기</h4>
                    <p>네이버 뉴스 검색 결과에서 '해군' 관련 최신 기사를 실시간으로 확인하실 수 있습니다.</p>
                </div>
                <a href="https://m.search.naver.com/search.naver?ssc=tab.m_news.all&query=%ED%95%B4%EA%B5%B0&sm=mtb_clk.jou&sort=1&photo=0&field=0&pd=0&ds=2026.11.13&de=2026.11.13&docid=&qdt=0&related=0&mynews=1&office_type=1&office_section_code=1&news_office_checked=1052&nso=so%3Add%2Cp%3Aall&is_sug_officeid=0&office_category=0&service_area=0" target="_blank" rel="noopener noreferrer" class="btn-primary">
                    네이버 해군 뉴스 바로가기 →
                </a>
            </div>
        </section>
    </main>

    <footer>
        <p><strong>REPUBLIC OF KOREA NAVY</strong> | 본 페이지는 대한민국 해군 소개를 위해 제작된 정보 안내 웹사이트입니다.</p>
    </footer>

    <script>
        function filterFleet(category, btn) {
            // 버튼 활성화 상태 변경
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');

            // 테이블 행 필터링
            const rows = document.querySelectorAll('#fleetTable tbody tr');
            rows.forEach(row => {
                if (category === 'all' || row.getAttribute('data-category') === category) {
                    row.style.display = '';
                } else {
                    row.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>
