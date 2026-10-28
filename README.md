# 플레이스 리포트 (FACTER)

마케팅 대행 고객사의 네이버 플레이스·광고 성과 대시보드.

- 화면: 이 저장소의 `index.html` (GitHub Pages)
- 데이터·로그인: Supabase 프로젝트 `facter-place-report` (서울)
  - 테이블: `stores`, `months`, `coupons`, `members`
  - RLS: `members`에 등록된 이메일만 읽기/쓰기
- AI 캡처 판독: Supabase Edge Function `ai-read` (Secrets에 `ANTHROPIC_API_KEY` 필요)

페이지에는 공개용(publishable) 키만 들어 있고, 고객 데이터는 로그인한 팀원에게만 내려갑니다.

## 팀원 추가
Supabase › SQL Editor:
```sql
insert into public.members(email) values ('팀원@이메일.com');
```
