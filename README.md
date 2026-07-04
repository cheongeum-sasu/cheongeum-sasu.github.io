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
| `og-image.png` | 카카오·인스타 등 공유 미리보기용 Open Graph 이미지 (1200×630). |
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
- **SEO / 공유** — `<title>`, meta description, Open Graph·Twitter 카드, JSON-LD 구조화 데이터.
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

## OG 이미지 갱신

`og-image.png`는 공유 미리보기 카드입니다. 교체 시 **1200×630** 크기(PNG/JPG)를 유지하고
파일명을 그대로 두면 `index.html`의 메타 태그를 수정할 필요가 없습니다.

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
