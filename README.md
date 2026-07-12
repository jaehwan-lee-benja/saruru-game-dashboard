# 사르르 게임 · 관리 대시보드 🎮

사르르목장 게임(별도 게임 사이트)의 **관리자 전용** 운영 대시보드.

- **로그인 필수** — Google OAuth. 등록 관리자(designerbenja) 계정만 열람.
  - 현재는 클라이언트 이메일 게이트. M2(실데이터) 연동 시 `game` 스키마 **RLS**(`auth.jwt()->>'email'`)로 승격.
- **정적 프론트** — 단일 `index.html`, 빌드 없음. GitHub Pages(main 루트) 배포.
- Supabase: multi-store `rstazttwlghsorpzsugy` (game 데이터 연동은 M2).

## 섹션
1. **게임 현황·통계** — 플레이·랭킹·치트 검증 요약 (M2 카카오 로그인 후 실데이터, 현재 목업).
2. **멤버십·사르르목장 연결** — 게임↔CRM 멤버십 연결 *구조/틀*. 실 PII 연동은 crm 조율 + 유저 승인 게이트.
3. **고객 게임 상호작용** — 게임별 참여·이벤트/캠페인 영역.
4. **공통 공지** — 고객 대상 공지 배너.
5. **똥피하기 · 픽셀소 레퍼런스 10선** — 우리 젖소 캐릭터 디자인 참고 갤러리.
   - ⚠ 저작권 회피: 각 이미지는 원본 스프라이트가 아니라 **해당 스타일을 오마주한 오리지널 도트**(캔버스 렌더). 실제 원본은 각 카드의 출처 링크 참조.

## 통일 규약
도메인별 관리 대시보드 = `github.io/<domain>-dashboard/` + Supabase(로그인·RLS). 프론트만 이 레포에.

## 배포
main 브랜치 루트를 GitHub Pages로 서빙. push = 배포. 라이브: `https://jaehwan-lee-benja.github.io/saruru-game-dashboard/`

⚠ 공유 DB(`game`/`crm` 스키마) DDL·PII 연동은 conductor → supabase-guardian → 유저 승인 게이트(프로젝트 CLAUDE.md).
