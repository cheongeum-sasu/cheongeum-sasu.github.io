# 청음사수 · Cheongeum Sasu

시각장애 사격(VI Shooting) 선수 **박성모**의 프로젝트 랜딩페이지입니다.
국제 등급분류(WSPS SH-VI) 취득과 국제대회 출전 과정을 사실 그대로 기록합니다.

> **청음사수(聽音射手)** — 소리를 들어 조준하는 사수.
> 시각장애 사격은 광학 조준경 대신 음향조준장치를 사용하며,
> 총구가 표적 중심에 가까울수록 조준음의 주파수가 높아집니다.

- 사수 · Shooter: **박성모** (SH-VI, 저시력)
- 부사수 · VI Assistant: **미정 (TBD)**
- 종목 · Events: 10m 공기소총 (SH-VI), NS 파라 바이애슬론
- Instagram: <https://www.instagram.com/lucid_mo>
- YouTube: <https://youtube.com/@lucid_mo>

배포 사이트: <https://cheongeum-sasu.github.io/>

---

## 구성

외부 빌드 도구 없이 그대로 배포되는 정적 사이트입니다.

| 파일 | 설명 |
| --- | --- |
| `index.html` | 랜딩페이지 본문. CSS·JS 인라인, 외부 라이브러리 없음. |
| `og-image.png` | 공유 미리보기용 Open Graph 이미지 (1200×630). 과녁 아이콘 단일 디자인. |
| `favicon.svg` | 과녁 파비콘 (벡터, 기본). |
| `favicon-96.png` | 과녁 파비콘 (96×96 PNG). 구글 검색결과 파비콘 노출용(48px 배수). |
| `apple-touch-icon.png` | iOS 홈 화면 아이콘 (180×180). |
| `sitemap.xml` | 검색엔진용 사이트맵. |
| `robots.txt` | 크롤러 정책 + 사이트맵 위치. |
| `README.md` | 이 문서. |

## 주요 특징

- **단일 파일 정적 페이지** — `index.html` 하나로 완결. CDN·프레임워크 없음.
- **음향조준 인터랙티브 데모** — 표적 위에서 조준점을 움직이면 중심 근접도에 따라
  조준음 주파수가 바뀝니다. Web Audio API로 실제 소리를 재생하며, **소리는 기본 꺼짐**이고
  토글로 켤 수 있습니다.
- **접근성 (시각장애 선수 프로젝트이므로 타협 없이)**
  - 시맨틱 마크업, 건너뛰기 링크, 명확한 포커스 표시.
  - 데모는 키보드(방향키/Home)로 조작 가능하고 `role="slider"`와 `aria-live`로 상태를 읽어줍니다.
  - `prefers-reduced-motion` 대응, 라이트/다크 모드 모두 충분한 명도 대비.
  - **데모 없이도 페이지가 완결됩니다** — JS/오디오가 없어도 동일한 원리를 텍스트 대체 설명으로 제공합니다.
- **SEO / 공유** — `<title>`, meta description·keywords, Open Graph·Twitter 카드,
  JSON-LD 구조화 데이터(WebSite + ProfilePage + Person), 과녁 아이콘 파비콘 세트.
- **국문 기본, 필요한 곳에 영문 병기** (해외 연맹·스폰서 대응).

## 로컬 미리보기

정적 파일이라 별도 빌드가 필요 없습니다. 저장소를 받은 뒤 아무 정적 서버로 열면 됩니다.

```bash
# Python 3
python3 -m http.server 8000
# 그 후 http://localhost:8000 접속
```

브라우저에서 `index.html`을 직접 열어도 되지만, 오디오/공유 태그 확인을 위해
로컬 서버로 여는 것을 권장합니다.

## 배포 (GitHub Pages)

이 저장소는 사용자/조직 페이지 저장소(`cheongeum-sasu.github.io`)입니다.

1. `main` 브랜치에 `index.html` 등을 병합합니다.
2. GitHub 저장소 **Settings → Pages** 에서 Source를 **Deploy from a branch**,
   Branch를 **`main` / `(root)`** 로 설정합니다.
3. 몇 분 뒤 <https://cheongeum-sasu.github.io/> 에서 공개됩니다.

커스텀 도메인을 사용할 경우 루트에 `CNAME` 파일을 추가하고 Pages 설정에서 도메인을 지정합니다.

## OG 이미지 · 파비콘

`og-image.png`(1200×630)와 파비콘(`favicon.svg` / `favicon-96.png` / `apple-touch-icon.png`)은
모두 **같은 과녁 아이콘 디자인**입니다 — 흰 배경, 짙은 동심원 2개, 붉은 중심점(`#d24a34`).
교체 시 크기와 파일명을 유지하면 `index.html` 메타 태그를 수정할 필요가 없습니다.
OG 이미지를 교체하면 `index.html`의 `og:image` URL 쿼리(`?v=2`)를 올려
카카오·페이스북 캐시를 무효화하세요. (카카오는
<https://developers.kakao.com/tool/debugger/sharing> 에서 수동 캐시 초기화도 가능합니다.)

## 검색엔진 등록 (필수)

"청음사수 / 박성모 / 시각장애 사격" 검색 노출을 위해 **저장소 관리자가 1회 직접 등록**해야 합니다.
특히 **네이버는 등록하지 않으면 사실상 수집되지 않습니다.**

1. **구글 서치콘솔** — <https://search.google.com/search-console>
   - `https://cheongeum-sasu.github.io/` 를 URL 접두어 속성으로 추가.
   - HTML 태그 방식 선택 시 발급되는
     `<meta name="google-site-verification" content="...">` 태그를 `index.html`의 `<head>`에 추가.
   - 확인 후 **Sitemaps 메뉴에 `sitemap.xml` 제출**, "URL 검사 → 색인 생성 요청" 실행.
2. **네이버 서치어드바이저** — <https://searchadvisor.naver.com/>
   - 사이트 등록 후 발급되는
     `<meta name="naver-site-verification" content="...">` 태그를 `<head>`에 추가.
   - 소유 확인 후 **요청 → 사이트맵 제출**(`sitemap.xml`)과 **웹 페이지 수집 요청** 실행.
3. (선택) **다음(Daum) 검색등록** — <https://register.search.daum.net/index.daum>

등록 후 반영까지 보통 며칠~몇 주가 걸립니다. "청음사수"는 고유 명칭이라 색인만 되면
상위 노출이 빠르지만, "시각장애"·"박성모" 같은 일반/동명이인 키워드는
인스타그램·유튜브·언론 보도 등 **외부 링크가 이 사이트를 가리키게 하는 것**이 가장 효과적입니다.
(인스타·유튜브 프로필에 사이트 주소를 걸어 두는 것부터 시작하세요.)

## 표기 원칙

- 과장·감성 카피를 배제하고 **검증 가능한 사실**만 서술합니다.
- 확정 일정과 목표(미확정)를 명확히 구분해 표기합니다.
  현재 국제 등급분류(WSPS SH-VI)는 **미보유** 상태이며, 로드맵의 대회 일정은
  **목표이지 확정 출전이 아닙니다.**

## 참고 자료

- World Shooting Para Sport — <https://www.paralympic.org/shooting>
- 대한장애인사격연맹 — <https://ksfd.kosad.kr/>
- IDECUP — <https://www.idecup.eu/>
- Ecoaims VIS500 음향조준장치 — <https://www.ecoaims.com/products/para-sport/vis500-aiming-device-set/>
- Anschütz 9015 — <https://www.anschuetz-sport.com/en/sport/luftgewehre/luftgewehr-disziplinen/basismodelle-9015-disziplin-frei/>

## 용어

| 약어 | 풀네임 | 뜻 |
| --- | --- | --- |
| WSPS | World Shooting Para Sport | 국제 패럴림픽 사격 종목 체계 |
| SH-VI | Shooting – Visually Impaired | 시각장애 사격 등급분류 |
| IDECUP | — | 제4회 WSPS 그랑프리 대회명 (2027, 독일 랑엘스하임) |
| VI | Visually Impaired | 시각장애 |
