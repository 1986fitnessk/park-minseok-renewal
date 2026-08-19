# Design Brief

## Product job
기존 남성 회원이 채지훈 트레이너의 실제 변화 기록과 꾸준함 중심 철학을 보고 10·20·30·50회 중 상담할 회차를 선택해 재등록으로 이어지게 한다.

## Direction
한슬기 트레이너 페이지의 네이비·크림·골드 에디토리얼 구조를 유지하면서, 감량과 등·어깨 체형 변화 기록을 중심으로 현실적인 루틴의 가치를 강조한다.

## Brand reading
- Immutable identity: 1986 FITNESS, 실제 회원 기록, 운동을 계속하게 만드는 운영 철학
- Repeatable shapes/materials: 어두운 면, 얇은 골드 선, 큰 문장, 세로형 실제 변화 사진
- Existing inconsistencies to remove: 한슬기 트레이너 이름과 개인 기준·속도 중심 카피
- Media provenance: 사용자가 2026-08-19 제공한 실제 남성 회원 변화 기록 6장

## Reference synthesis
- Structure comes from: 한슬기 트레이너 재등록 페이지의 철학 → 기록 → 방법 → 가격 선택 흐름
- Interaction comes from: 기존 회차 선택 버튼과 선택 결과 영역
- Visual tone comes from: 기존 1986 네이비·크림·골드 토큰과 실제 비교 사진
- Hook/copy energy comes from: 사용자가 제공한 “타고난 의지보다 꾸준함과 습관” 메시지
- Motion/media behavior comes from: 사진 레일의 순차 진입과 회차 선택 상태 전환
- The final screen will not copy: 한슬기 트레이너 이름, 개인 기준 카피, 사진

## Reference evidence
- Exact page/section/state inspected: 로컬 한슬기 페이지의 hero, philosophy, record rail, method, plan 선택 상태와 제공 사진 6장
- Desktop/mobile behavior observed: 데스크톱 2열 hero와 4열 가격표, 모바일 hero 재배치·가로 스냅 기록·2열 가격표

## Reference implementation map
| Reference evidence | Extracted principle | Local component | Motion/state | Mobile translation | Acceptance evidence |
|---|---|---|---|---|---|
| 한슬기 hero | 짧은 긴장과 약속 | `.hero` | 카피와 사진 순차 진입 | 카피 우선, 사진 아래 이동 | 브라우저 확인 |
| 실제 변화 사진 6장 | 반복된 기록이 신뢰를 만든다 | `.record-rail` | 스크롤 순차 reveal | 82vw 가로 스냅 | 모바일 폭 확인 |
| 기존 plan 선택 | 기간과 목표를 함께 비교 | `.plan-grid` | 선택 강조와 요약 갱신 | 2열 그리드 | 클릭 상태 확인 |

## Signature composition and component
- Signature composition: ‘의지보다 습관’ 대형 문장과 실제 등 변화 기록이 맞물리는 첫 화면
- Signature component: 감량부터 등·어깨 발달까지 이어지는 6개의 실제 변화 기록 레일

## Motion storyboard
| Beat | Trigger | Elements | From → to | Duration/ease | Purpose | Reduced motion |
|---|---|---|---|---|---|---|
| 습관을 세우다 | 첫 진입 | eyebrow, h1, note | 아래 24px/투명 → 정위치/불투명 | 700ms ease-out | 철학의 읽기 순서 형성 | 최종 상태 |
| 변화를 쌓다 | 스크롤 | record cards | 아래 30px → 정위치 | 550ms ease-out stagger | 실제 기록의 축적 표현 | 최종 상태 |
| 기간을 선택하다 | 클릭 | plan, summary | 중립 → 골드 강조 | 240ms | 재등록 선택 피드백 | 즉시 전환 |

## References
| Role | Source | Adapt | Do not copy |
|---|---|---|---|
| Structure | 로컬 한슬기 재등록 페이지 | 철학-기록-방법-선택 흐름 | 트레이너명과 개인 카피 |
| Visual | 사용자 제공 사진 6장 | 실제 남성 회원 변화 기록 | 임의의 감량 수치나 기간 |
| Copy | 사용자 제공 소개글 | 꾸준함·습관·현실적 루틴 | 결과 보장 표현 |

## Tokens
- Font: Pretendard/Apple SD Gothic Neo/system sans
- Text colors: cream, muted gray
- Surface colors: ink, navy
- Accent and semantic colors: restrained gold
- Spacing steps: 8, 12, 20, 32, 48, 72, 112
- Radius: 0–6px
- Border and shadow: 1px translucent cream/gold, minimal shadow
- Motion: 240ms interaction, 550–700ms reveal

## Screen priorities
1. 타고난 의지보다 꾸준함과 습관
2. 실제 남성 회원의 감량과 체형 변화 기록
3. 동일 가격의 10·20·30·50회 재등록 선택

## Behavior that must remain unchanged
- 회차 선택 시 하단 상담 요약이 갱신된다.
- 가격과 할인율은 한 곳의 데이터에서 계산된다.

## Anti-template decisions
- Generic pattern being rejected: 남성 타깃을 이유로 검정·빨강과 과장 문구를 사용한 헬스장 광고
- Project-specific replacement: 실제 변화 기록과 현실적인 루틴 철학을 먼저 보여준 뒤 기간별 선택으로 연결

## Responsive and motion contract
- Desktop media behavior: hero 2열, 기록 카드 가로 레일, 가격 4열
- Mobile media behavior: hero 이미지 하단 이동, 기록 82vw 스냅, 가격 2열
- Scroll reveal grammar: 30px 아래에서 순차 진입
- Reduced-motion fallback: 모든 콘텐츠 즉시 최종 상태
- Text-clipping viewports: 320/360/390/430px에서 가로 넘침 없음

## Verification captures
- Desktop first viewport: 구현 후 브라우저 확인
- Desktop representative flow: 구현 후 브라우저 확인
- Mobile 390px: 구현 후 확인
- Signature motion: 순차 진입 및 선택 상태 확인
