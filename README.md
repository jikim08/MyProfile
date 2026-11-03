# Kim JiHoo — Personal Portfolio

김지후의 관심 분야, 연구 경험, 개발 프로젝트와 활동을 소개하는 개인 포트폴리오입니다. Hugo의 Gokarna 테마를 바탕으로 콘텐츠와 화면 구성을 수정하고, GitHub Pages로 배포했습니다.

- **작성자:** 김지후
- **배포 사이트:** https://jikim08.github.io/MyProfile/
- **저장소:** https://github.com/jikim08/MyProfile

## 페이지 구성

| 페이지 | 주요 내용 |
| --- | --- |
| Home | 자기소개, 약력, 관심 분야, 주요 경험, 수상 경력, 앞으로의 목표 |
| Posts | 글 게시를 위한 안내와 Tistory 연결 |
| Projects | 프로젝트 목록과 개별 프로젝트의 소개·담당 역할·결과·회고 |

Projects에는 LPPLS 모델의 C++ 전환, JAVICE 홈페이지 제작, Java Swing 피아노 리듬게임, 생체신호·IMU 기반 감정인식 연구, 운전자 긴급 대응 안전 시스템을 정리했습니다. 감정인식 연구 페이지에서는 논문 PDF도 열어볼 수 있습니다.

## 사용 기술

| 구분 | 기술 및 용도 |
| --- | --- |
| 정적 사이트 생성 | Hugo Extended |
| 기본 테마 | Gokarna |
| 콘텐츠·설정 | Markdown, YAML front matter, TOML |
| 화면 구성 | Hugo 템플릿, HTML, CSS, JavaScript |
| 글꼴·아이콘 | SUIT Variable, 테마에 포함된 Feather 및 SVG 아이콘 |
| 빌드 보조 | Python 3 |
| 버전 관리·자동 배포 | Git, GitHub Actions, GitHub Pages |

GitHub Actions는 **Hugo Extended 0.167.0**을 사용합니다. 로컬에서는 **Hugo Extended 0.169.0**으로 빌드를 확인했습니다. 배포 환경과 동일한 버전으로 재현하려면 0.167.0을 사용하면 됩니다.

## 직접 수정한 부분

- 홈 상단을 프로필 사진, 이름, 소개 문구, SNS 링크가 있는 검은 배경의 영역으로 구성했습니다. CSS로 대각선 질감과 반사광 애니메이션을 적용했습니다.
- About Me 아래에 약력, 관심 분야, 주요 경험, 수상 경력과 목표를 배치했습니다. 관심 분야는 카드 형태로, 약력은 표 형태로 정리하고 구분선과 여백을 조정했습니다.
- Projects 목록과 상세 페이지에 같은 배너를 적용했습니다. 상세 페이지의 배너 제목과 `← Projects` 링크를 누르면 목록으로 돌아갑니다.
- 프로젝트별 소개, 기간, 사용 기술, 담당 역할과 회고를 작성하고 GitHub 및 논문 PDF 링크를 연결했습니다.
- 메뉴, 프로필 이미지, 파비콘, 메타 정보와 외부 링크를 개인 프로필에 맞게 수정했습니다.

## 주요 파일

실제로 실행·배포하는 사이트 소스는 **`site/`** 아래에 있습니다. 같은 이름의 파일이 저장소 루트나 `exampleSite/`에도 있을 수 있으므로 수정할 경로를 구분해야 합니다.

```text
MyProfile/
├── README.md
├── LICENSE
├── .github-pages.json                 # 배포용 사이트 경로와 빌드 설정
├── .github/
│   ├── pages_build.py                 # Hugo 빌드 및 배포 URL 경로 보정
│   └── workflows/
│       └── hugo-pages.yml             # main push 시 자동 배포
└── site/
    ├── hugo.toml                      # 사이트 제목, 메뉴, 프로필, Markdown 설정
    ├── pages.json                     # 배포 주소와 테마 설정
    ├── content/
    │   ├── _index.md                  # 홈 본문
    │   ├── posts/
    │   │   └── _index.md              # Posts 안내
    │   └── projects/
    │       ├── _index.md              # 프로젝트 목록
    │       ├── lppls.md
    │       ├── javice.md
    │       ├── piano_rhythm_game.md
    │       ├── egoemotion.md
    │       └── driver-safety.md
    ├── static/
    │   ├── favicon.png                # JH 파비콘
    │   ├── images/                    # 프로필 등 정적 이미지
    │   └── files/
    │       └── egoemotion-IGRF.pdf     # 감정인식 연구 논문
    └── themes/template/
        ├── assets/
        │   ├── css/main.css           # 화면 스타일
        │   └── js/main.js             # 메뉴 등 화면 동작
        └── layouts/
            ├── index.html            # 홈 레이아웃
            ├── _default/
            │   ├── list.html         # 목록 페이지와 상단 배너
            │   └── single.html       # 상세 페이지와 공통 Projects 배너
            └── partials/
                ├── page.html         # 일반 상세 본문
                ├── post.html         # 게시글 본문
                ├── header.html       # 상단 메뉴
                ├── head.html         # 메타 정보, CSS·JS 연결
                ├── footer.html       # 하단 정보
                └── favicon.html      # 파비콘 연결
```

위 구조는 수정과 유지보수에 필요한 주요 파일을 기준으로 정리했습니다.

## 로컬 실행

Git과 Hugo Extended가 필요합니다. 배포용 빌드 스크립트까지 실행하려면 Python 3도 준비해야 합니다. Hugo 배포 버전은 [공식 릴리스 페이지](https://github.com/gohugoio/hugo/releases/tag/v0.167.0)에서 확인할 수 있습니다.

다음 명령은 저장소를 처음 받는 경우를 기준으로 합니다.

```bash
git clone https://github.com/jikim08/MyProfile.git
cd MyProfile
hugo version
python3 --version
```

저장소 루트에서 개발 서버를 실행합니다.

```bash
hugo server --source site --config hugo.toml,pages.json --baseURL http://localhost:1313/ --disableFastRender
```

브라우저에서 http://localhost:1313/ 에 접속합니다. 서버를 종료할 때는 터미널에서 `Ctrl + C`를 누릅니다.

이 테마의 현재 화면은 별도의 프런트엔드 개발 서버나 `npm run dev` 없이 실행할 수 있습니다. 루트 `requirements.txt`는 원본 테마의 보조 도구용이므로 일반적인 사이트 실행에는 설치하지 않아도 됩니다.

## 배포용 빌드

저장소 루트에서 실행합니다.

```bash
python3 .github/pages_build.py --build
```

이 명령은 `site/hugo.toml`과 `site/pages.json`을 읽어 Hugo를 실행하고, 결과를 루트 **`public/`**에 생성합니다. 이후 `/MyProfile/` 경로를 사용하는 GitHub Pages 환경에 맞게 내부 링크와 정적 파일 경로를 보정합니다.

`site/public/`은 로컬 실행 과정에서 생성될 수 있는 결과물입니다. GitHub Actions가 업로드하는 배포 결과물은 루트 `public/`입니다. 내용과 디자인은 생성된 HTML 대신 `site/content/`, `site/themes/template/`, `site/static/`의 원본 파일에서 수정합니다.

## 수정 후 재배포

1. 아래 표에서 수정할 파일을 찾아 내용을 변경합니다.
2. 로컬 서버에서 화면과 링크를 확인합니다.
3. 변경한 원본 파일을 커밋하고 `main`에 push합니다.
4. 저장소의 **Actions → Deploy Hugo to GitHub Pages**에서 빌드와 배포 성공 여부를 확인합니다.
5. 배포 사이트에서 변경 사항을 확인합니다.

| 수정할 내용 | 파일 |
| --- | --- |
| 자기소개와 약력 | `site/content/_index.md` |
| 프로젝트 목록 | `site/content/projects/_index.md` |
| 개별 프로젝트 설명 | `site/content/projects/`의 해당 Markdown 파일 |
| 이름, 소개 문구, 메뉴, SNS 링크 | `site/hugo.toml` |
| 색상, 글꼴, 간격, 애니메이션 | `site/themes/template/assets/css/main.css` |
| 상세 페이지 공통 배너 | `site/themes/template/layouts/_default/single.html` |
| 프로필 사진, PDF, 파비콘 | `site/static/` 아래의 해당 파일 |

예를 들어 홈 소개글을 수정했다면 다음과 같이 반영합니다.

```bash
git add site/content/_index.md
git commit -m "docs: 홈 소개 내용 수정"
git push origin main
```

GitHub Actions는 `main` push를 받아 Hugo 설치, 의존성 준비, 사이트 빌드, 경로 보정과 Pages 배포를 순서대로 실행합니다. 이미 push한 커밋을 다시 배포하려면 Actions의 해당 워크플로에서 **Run workflow**를 실행할 수 있습니다.

## 확인할 때 주의할 점

- 프로젝트 링크에는 원본 파일 확장자 `.md`를 붙이지 않습니다. 예: `/projects/piano_rhythm_game/`.
- GitHub Pages에서는 파일명과 링크의 대소문자를 일치시킵니다. `javice.md`의 페이지 경로는 `/projects/javice/`입니다.
- `site/static/files/egoemotion-IGRF.pdf`는 사이트에서 `files/egoemotion-IGRF.pdf` 경로로 제공됩니다. 배포 주소에서는 `/MyProfile/` 접두 경로가 포함됩니다.
- 표의 셀 안에서 줄을 나눌 때는 `<br>`를 사용합니다. 이를 렌더링하도록 `site/hugo.toml`에 `markup.goldmark.renderer.unsafe = true`를 설정했습니다.
- 배포가 성공했는데 이전 디자인이 보이면 강력 새로고침이나 시크릿 창으로 확인합니다. 실제로 Chrome의 캐시를 지운 뒤 최신 화면이 표시되는 것을 확인했습니다.

## 테마·외부 자료·AI 사용

- **기본 테마:** [Gokarna](https://github.com/gokarna-theme/gokarna-hugo). 원본 테마의 구조와 기능을 바탕으로 개인 콘텐츠와 레이아웃·스타일을 수정했습니다. 원본의 GNU GPLv3 [LICENSE](LICENSE)를 보존했습니다.
- **배포 보조 코드:** 저장소의 `prepare_github_pages.py`로 준비된 `.github/pages_build.py`, 설정 파일과 GitHub Actions 워크플로를 사용합니다.
- **글꼴:** [SUIT](https://github.com/sun-typeface/SUIT)를 CDN으로 불러옵니다.
- **아이콘·수식 표시:** 테마에 포함된 Feather·SVG 아이콘과 KaTeX 설정을 사용합니다. Tistory 아이콘과 개인 SNS 링크를 추가했습니다.
- **AI 활용:** ChatGPT와 Codex를 페이지 구성 및 문구 초안, HTML·CSS 수정안, 오류 원인 분석, README 작성에 활용했습니다. JH 파비콘은 ChatGPT의 이미지 생성 기능으로 제작했습니다.

프로젝트 소개에 적은 기간, 담당 역할과 결과는 작성자의 활동을 기준으로 정리했습니다. 각 프로젝트 저장소와 논문에 대한 권리는 해당 원저작자에게 있습니다.

## 현재 범위와 개선할 점

Posts는 안내와 Tistory 연결을 제공하며, 사이트 내에 게시할 개인 글은 준비 중입니다. 저장소와 빌드 결과에는 원본 테마의 예제 문서 일부가 남아 있어 정리가 필요합니다. 앞으로는 프로젝트 실행 화면을 보완하고, 새 활동과 개발 기록을 추가할 예정입니다.
