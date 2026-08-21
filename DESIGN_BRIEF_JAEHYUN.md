# Design Brief

## Product job
기존 회원이 재현 트레이너와 지금까지 만든 체력·움직임·수행 기반을 확인하고, 다음 기간의 체형·근력 목표를 선택해 재등록 상담으로 이어지게 한다.

## Direction
기존 재등록 페이지의 정보 흐름과 가격 체계는 유지하되, ‘소통하는 즐거운 수업 → 꾸준한 출석 → 눈에 보이는 결과’라는 재현 트레이너만의 경험을 중심에 둔다.

## Brand reading
- Immutable identity: 1986 FITNESS, 실제 회원 기록, 운동의 지속
- Repeatable materials: 어두운 잉크 면, 크림 텍스트, 절제된 골드, 큰 한국어 문장
- Existing inconsistencies to remove: 채지훈 이름, 습관만을 강조한 남성 회원 전용 카피와 사진
- Media provenance: 사용자가 2026-08-21 제공한 재현 트레이너 및 프로젝트 사진 12장

## Reference evidence
- 로컬 채지훈 재등록 페이지의 hero, statement, record rail, method, plan 선택 상태를 확인했다.
- 사용자 제공 사진은 트레이너 코칭, 바디프로필, 대회, 라이프 목표까지 수업의 관계와 결과를 함께 보여준다.
- 데스크톱은 2열 hero와 4열 가격표, 모바일은 세로 hero·가로 스냅 기록·2열 가격표가 핵심이다.

## Reference synthesis
- Structure comes from: 기존 재등록 템플릿의 관계 → 근거 → 방법 → 옵션 흐름
- Interaction comes from: 회차 선택과 선택 요약 갱신
- Visual tone comes from: 1986 네이비·크림·골드 토큰과 실제 사진
- Hook/copy energy comes from: 사용자의 재등록 멘트와 소통·재미·출석 철학
- Motion/media behavior comes from: 짧은 진입 모션과 가로 기록 레일
- The final screen will not copy: 다른 트레이너 이름, 사진, 개인 철학 문장

## Reference implementation map
| Reference evidence | Extracted principle | Local component | Motion/state | Mobile translation | Acceptance evidence |
|---|---|---|---|---|---|
| 기존 hero | 첫 화면에서 가치와 인물을 함께 전달 | `.hero` | 카피와 사진 순차 진입 | 카피 위, 사진 아래 | 브라우저 첫 화면 확인 |
| 제공 사진 12장 | 관계와 결과가 함께 신뢰를 만든다 | `.record-rail` | 스크롤 reveal | 82vw 가로 스냅 | 이미지 12장 로드 확인 |
| 기존 가격 선택 | 기간별 목표를 비교해 상담 진입 | `.plan-grid` | 선택 강조와 요약 갱신 | 2열 그리드 | 클릭 후 문구 갱신 확인 |

## Signature composition and component
- Signature composition: ‘재밌어서 계속 나오고, 계속해서 변한다’는 문장과 코칭 현장 사진의 결합
- Signature component: 코칭 → 바디프로필 → 무대 → 라이프 목표가 이어지는 12장 프로젝트 레일

## Motion storyboard
| Beat | Trigger | Elements | From → to | Duration/ease | Purpose | Reduced motion |
|---|---|---|---|---|---|---|
| 관계를 열다 | 첫 진입 | hero copy/media | 아래 24px·투명 → 정위치·불투명 | 750ms ease-out | 트레이너 철학을 순서대로 전달 | 즉시 최종 상태 |
| 결과를 쌓다 | 스크롤 | record cards | 아래 30px → 정위치 | 550ms stagger | 꾸준한 기록의 축적 표현 | 즉시 최종 상태 |
| 다음 목표를 고르다 | 클릭 | plan/summary | 중립 → 골드 강조 | 250ms | 선택 피드백 제공 | 즉시 전환 |

## Tokens
- Font: Pretendard/Apple SD Gothic Neo/system sans
- Text: cream, muted gray
- Surface: ink, navy, cream
- Accent: restrained gold
- Spacing: 8, 12, 20, 32, 48, 72, 112
- Radius: 0–6px
- Motion: 250ms interaction, 550–750ms reveal

## Copy ladder
- Hook: 재밌어서 계속 나오고, 계속해서 변합니다.
- Value: 소통으로 현재를 확인하고 출석을 결과로 연결한다.
- Proof: 실제 코칭·바디프로필·대회·라이프 목표 기록
- CTA: 다음 목표에 맞는 재등록 회차 선택

## Screen priorities
1. 소통과 재미가 만드는 꾸준한 출석
2. 지금까지 만든 기반을 다음 결과로 연결해야 하는 이유
3. 실제 프로젝트 기록과 동일 가격의 재등록 옵션

## Behavior that must remain unchanged
- 10·20·30·50회 가격과 할인율 계산 방식
- 회차 선택 시 상담 요약 문구 갱신
- GitHub Pages 하위 경로에서 작동하는 상대 이미지 경로

## Anti-template decisions
- Generic pattern being rejected: 과장된 할인 배지와 검정·빨강 중심의 전형적인 헬스장 광고
- Project-specific replacement: 코칭 현장과 회원의 중요한 목표 기록을 함께 보여주는 관계 중심 에디토리얼 구성

## Responsive and motion contract
- Desktop media behavior: 2열 hero, 가로 프로젝트 레일, 4열 가격표
- Mobile media behavior: hero 이미지 하단, 82vw 스냅 레일, 2열 가격표
- Main image: 인물 절단 방지를 위해 contain
- Viewports: 320 / 360 / 390 / 430 / desktop
- Reduced-motion final state: 모든 콘텐츠가 애니메이션 없이 즉시 표시

## Verification captures
- Desktop first viewport: hero 카피와 메인 사진 절단 여부 확인
- Desktop representative flow: 실제 기록과 가격 선택 확인
- Mobile 390px: 가로 넘침, 텍스트 절단, 가격 카드 확인
- Signature motion: 기록 reveal과 회차 선택 상태 확인

