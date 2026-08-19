# Design Brief

## Product job
기존 회원이 한슬기 트레이너의 운동 철학과 실제 변화 기록을 보고 10·20·30·50회 중 상담할 회차를 선택해 재등록 상담으로 이어지게 한다.

## Direction
기존 재등록 페이지의 짙은 네이비와 골드 톤을 유지하되, 여러 회원의 실제 자세 변화 기록이 이어지는 세로형 에디토리얼 템플릿으로 확장한다.

## Brand reading
- Immutable identity: 1986 FITNESS 이름, 실제 센터 사진, 운동의 지속을 돕는 태도
- Repeatable shapes/materials: 어두운 면, 얇은 골드 선, 큰 숫자, 비교 사진의 세로 리듬
- Existing inconsistencies to remove: 특정 회원 이름과 바디프로필 목표에 종속된 카피
- Media provenance: 사용자가 2026-08-19 제공한 카카오톡 사진 7장

## Reference synthesis
- Structure comes from: 현재 로컬 박민석 재등록 페이지의 관계 → 변화 → 제안 → 가격 → 상담 흐름
- Interaction comes from: 기존 회차 선택 버튼과 선택 결과 영역
- Visual tone comes from: 기존 1986 네이비·크림·골드 토큰과 제공 사진의 비교 구도
- Hook/copy energy comes from: 사용자가 제공한 “사람은 다 다르다” 메시지
- Motion/media behavior comes from: 사진 레일의 순차 진입과 회차 선택 상태 전환
- The final screen will not copy: 기존 회원명, 개인 목표, 개인 가격, 바디프로필 카피

## Reference evidence
- Exact page/section/state inspected: 로컬 `index.html`의 hero, journey, roadmap, plan 선택 상태
- Desktop/mobile behavior observed: 데스크톱 2열, 모바일 1열 전환 및 선택 카드 강조

## Reference implementation map
| Reference evidence | Extracted principle | Local component | Motion/state | Mobile translation | Acceptance evidence |
|---|---|---|---|---|---|
| 기존 hero | 짧은 긴장과 약속 | `.hero` | 문장 3단 순차 진입 | 카피 우선, 사진 아래 이동 | 데스크톱·390px 캡처 |
| 제공 비교 사진 7장 | 실제 변화가 신뢰를 만든다 | `.record-rail` | 스크롤 순차 reveal | 가로 스냅 레일 | 모바일 스크롤 확인 |
| 기존 plan 선택 | 회차 비교 후 하나를 선택 | `.plan-grid` | 선택 강조와 요약 갱신 | 2열 그리드 | 클릭 상태 확인 |

## Signature composition and component
- Signature composition: 첫 화면의 대형 문장과 실제 기록 사진이 맞물리는 비대칭 분할
- Signature component: 7개의 변화 기록을 넘겨보는 가로형 기록 레일

## Motion storyboard
| Beat | Trigger | Elements | From → to | Duration/ease | Purpose | Reduced motion |
|---|---|---|---|---|---|---|
| 기준을 세우다 | 첫 진입 | eyebrow, h1, note | 아래 24px/투명 → 정위치/불투명 | 700ms ease-out | 메시지 순서 형성 | 최종 상태 |
| 변화를 기록하다 | 스크롤 | record cards | 아래 30px → 정위치 | 550ms ease-out stagger | 실제 증거의 연속성 | 최종 상태 |
| 회차를 정하다 | 클릭 | plan, summary | 중립 → 골드 강조 | 240ms | 선택 피드백 | 즉시 전환 |

## References
| Role | Source | Adapt | Do not copy |
|---|---|---|---|
| Structure | 로컬 기존 재등록 페이지 | 관계-변화-선택 흐름 | 개인 이름과 목표 |
| Visual | 사용자 제공 사진 7장 | 실제 비교 기록 | 결과 수치의 임의 해석 |
| Copy | 사용자 제공 문장 | 개인 기준과 지속 메시지 | 과장된 감량 보장 |

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
1. 사람마다 다른 기준과 속도
2. 실제 변화 기록과 한슬기 트레이너의 설계 방식
3. 10·20·30·50회 가격 선택 및 상담

## Behavior that must remain unchanged
- 회차 선택 시 하단 상담 요약이 갱신된다.
- 가격은 한 곳의 데이터만 바꾸면 전체에 반영된다.

## Anti-template decisions
- Generic pattern being rejected: 동일 크기 카드만 나열된 PT 가격표
- Project-specific replacement: 실제 기록 레일과 ‘기준-설계-지속’ 서사를 먼저 보여준 뒤 가격을 선택

## Responsive and motion contract
- Desktop media behavior: hero 2열, 기록 카드 3열 가로 레일
- Mobile media behavior: hero 이미지 하단 이동, 기록 레일 82vw 스냅
- Scroll reveal grammar: 30px 아래에서 순차 진입
- Reduced-motion fallback: 모든 콘텐츠 즉시 최종 상태
- Text-clipping viewports: 320/360/390/430px에서 가로 넘침 없음

## Verification captures
- Desktop first viewport: 구현 후 캡처 예정
- Desktop representative flow: 구현 후 캡처 예정
- Mobile 390px: 구현 후 캡처 예정
- Signature motion: 구현 후 순차 상태 확인 예정
