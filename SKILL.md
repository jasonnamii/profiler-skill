---
name: profiler-skill
description: |
  범용 인물 프로파일링 엔진. 웹 리서치 기반 7축 분석(경력DNA·의사결정·비전·평판·개성·관계망·현재상황) → DNA 5~7대 도출 → 강점·약점 판정 → 30초 엘베피치 자동 생성. 트리거: 인물프로파일링, 인물리서치, 인물분석, DNA프로파일링, 사람분석, person profile, person research, profiler, 인물조사, 인물검색, CEO프로파일, 대표프로파일, 투자자프로파일, 파트너프로파일, 경쟁자프로파일, 인물정보, 인물배경, 인물이력, 경력분석. NOT: 채용역량평가(→직접수행), 조직분석(→management-skill), 정책기획(→policy-planning), 일반리서치(→research-skill).
---

# Profiler Skill — 프로파일러 스킬

---


## Skill Boundaries

- **하는 것** — 범용 인물 프로파일링 엔진.
- **안 하는 것** — 채용역량평가(→직접수행), 조직분석(→management-skill), 정책기획(→policy-planning), 일반리서치(→research-skill).

## When to Use

- 사용자가 "분석해줘", "프로파일링해줘", "리서치해줘", "조사해줘", "profile" 같은 표현으로 발동
- 미팅·협상·투자 전 인물 파악시, 파트너·경쟁자 분석시, 엘베피치 준비시.
- **안 쓸 때** — 채용역량평가(→직접수행), 조직분석(→management-skill), 정책기획(→policy-planning), 일반리서치(→research-skill).


## Prerequisites

| # | 체크 | 미충족 시 |
|---|------|-----------|
| 1 | 대상·입력 명확 (스킬 발동 의도 확인) | 1줄 확인 후 진입 |
| 2 | references/ 폴더 접근 가능 | inline fallback |


## ⛔ 절대 규칙

| # | 규칙 |
|---|------|
| 1 | 발동 조건 외 임의 실행 금지 |
| 2 | 출력 형식 준수 — 내부 라벨 사용자 노출 금지 |
| 3 | UP 존댓말·호칭 규칙 우선 적용 |

### 자체 점검 (self-check)
SKILL.md ≤10KB · P1 ≥5개 · Gotchas 존재 확인 후 수정 완료.

---

## §1 PURPOSE

웹 공개정보 기반으로 인물을 다각도 분석하여, **"이 사람이 누구인지 30초 안에 설명할 수 있는"** 프로필을 생성한다.

핵심 질문: **어떤 사람이고 → 무엇을 하는 사람이고 → 요즘 어떤 상황이고 → 어떻게 접근해야 하는가**

## §2 PIPELINE

```
P1 프레임   →  P2 리서치   →  P3 프로파일링  →  P4 엘베피치  →  §3.5 리포트 변환
(목적·축설정)   (축별 웹조사)   (DNA·강약점도출)   (수렴→30초피치)   (3막 서사 변환)
```

| Phase | 핵심 동작 | 스킬 호출 | 산출물 | 실패 조건 |
|-------|----------|----------|--------|----------|
| P1 | 대상+목적 확인 → 7축 중 적용축 선정 (→ references/7-axis-framework.md) | — | 분석 프레임 | 대상·목적 미확인 |
| P2 | **Skill("research-frame")** → 축별 독립 웹 리서치 (→ references/p2-research-phase.md) | **research-frame** 필수 | 축별 발견 정리 | 스킬 미호출 / 소스 1개 이하/축 |
| P3 | 패턴 추출 → DNA·강약점·의사결정 도출 (→ references/p3-profiling-rules.md) | — | §3 중간 산출물 | 증거 없는 DNA |
| P4 | Layer 1→2→3 수렴 → 엘베피치 직접 실행 (→ references/p4-elevator-pitch.md) | 직접 실행 (trigger-dictionary 별도 호출 불필요) | 엘베피치 | 피치 미생성 |
| §3.5 | §3 중간 산출물 → 3막 서사 템플릿으로 변환 (→ references/s35-report-conversion.md) | — | **최종 리포트** | §3 직접 출력 / 서사 톤 미준수 |

### P1 프레임 설정

**GATE**: 대상 인물명 + 분석 목적 확인 → 미제공시 질문

**축 선정**: → **references/7-axis-framework.md** 참조

### P2 웹 리서치

**research-frame 연동:** DEEP 분석 시 Skill('research-frame') 호출 필수. **LIGHT 자체분석:** 웹서치 3~5건으로 7축 스캔 가능 — research-frame 호출 없이 자체 수행. 확신도 상한 50 적용.

상세 가이드 → **references/p2-research-phase.md** 참조

### P3 프로파일링

상세 규칙 → **references/p3-profiling-rules.md** 참조

### P4 엘베피치 도출

상세 가이드 → **references/p4-elevator-pitch.md** 참조

## §3 분석 중간 산출물

중간 산출물 구조 → **references/s3-intermediate-outputs.md** 참조

**CRITICAL**: 이 중간 산출물은 내부 분석용이다. 최종 리포트는 §3.5에서 변환한다.

## §3.5 리포트 변환

상세 변환 규칙 & 3막 템플릿 → **references/s35-report-conversion.md** 참조


### 🚨 MUST cascade → shaper-skill
모든 산출물 shaper-skill MUST 경유. → `shaper-skill/references/_common/cascade-must.md`


## §4 깊이 제어 (Depth Control)

→ **references/depth-control.md** 참조

## §5~6 품질 규칙 & 주의사항

→ **references/quality-gotchas.md** 참조

---

## CRITICAL RULES (HUB LEVEL)

1. **모든 깊이에서 `Skill("research-frame")` 호출 필수**
2. **§3.5 리포트 변환 필수** — 중간 산출물 직접 출력 금지 (가장 흔한 실수)
3. **증거 없는 DNA 금지** — 추론만으로 도출 시 "추정" 태그 필수
4. **테이블 과잉 금지** — 최종 리포트는 산문 우선 (프로필 카드·타임라인만 허용)

## 예시

발동 후 스킬 프로토콜에 따라 단계별 실행 → 산출물 생성.

---


## §INV NO_WORK_LABEL
산출물·대화 작업 라벨 ZERO. → `shaper-skill/references/no-work-label.md`


## Output Path

| 산출물 | 경로 |
|---|---|
| 주 산출물 | `mnt/outputs/profiler-skill_{topic}_{YYYY-MM-DD}.md` |
| 형식 | 리포트로, 프로필로, 엘베피치로, .md로. |
| 리서치 결과 (해당 시) | `{VAULT}/_skills research/profiler-skill/{YYYY-MM-DD}_{topic}.md` |

## Reference Index

| 파일 | 내용 | 언제 |
|---|---|---|
| `references/7-axis-framework.md` | 7 axis framework | 해당 단계 진입 시 |
| `references/depth-control.md` | depth control | 해당 단계 진입 시 |
| `references/p2-research-phase.md` | p2 research phase | 해당 단계 진입 시 |
| `references/p3-profiling-rules.md` | p3 profiling rules | 해당 단계 진입 시 |
| `references/p4-elevator-pitch.md` | p4 elevator pitch | 해당 단계 진입 시 |
| `references/quality-gotchas.md` | quality gotchas | 해당 단계 진입 시 |
| `references/s3-intermediate-outputs.md` | s3 intermediate outputs | 해당 단계 진입 시 |
| `references/s35-report-conversion.md` | s35 report conversion | 해당 단계 진입 시 |


## Next Phase

본 스킬 작업 후 자연스럽게 이어지는 흐름:

- 후속 작업 → `직접수행`
- 후속 작업 → `management-skill`
- 후속 작업 → `policy-planning`
- 후속 작업 → `research-skill`

## Failure Modes (Gotchas)

| 함정 | 대응 |
|---|---|
| 실존 인물 사실과 다른 내용 생성 | 웹 검색 기반 확인 후 작성. 불확실은 명시 |
| 주관적 판단 과잉 | DNA·강점·약점은 공개 정보 기반으로만 |
| 개인정보 민감 항목 | 공개된 정보만. 사생활 영역 배제 |
| 엘베피치 과잉 압축 | 30초 제약 내 핵심 1문장 유지 |


## ❌ WRONG vs ✅ CORRECT

```
❌ WRONG: 트리거 단어만 보고 발동 — 본질·범위 확인 ✗ → 오발동·범위 이탈
✅ CORRECT: Skill Boundaries·When to Use 확인 후 발동 → 본질 작업만 수행
```
