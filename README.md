# Brand Design Guide — 브랜드 기초설계 → 디자인 기초설계 도우미

> BIBX Foundation(브랜드 기초설계 6섹션)과 Design·BI Build List(디자인 기초설계)를 베이스로,
> **브랜드 설계 → 디자인 설계**를 인지·행동·조형 이론 근거와 함께 도출하는 도구
> 미팅룸 내부용 · 자매 도구 [copywrite](https://jungpyo-mtr.github.io/copywrite-tool/)와 같은 방식

---

## 빠른 시작 (팀원용)

### 1. 일반 사용자 — 브라우저만 있으면 OK

1. **이 페이지로 이동** → https://jungpyo-mtr.github.io/brand-design-guide/
2. STAGE A(브랜드 기초설계) to-do 폼을 채운다 (6섹션, 이론은 호버/펼침으로 근거 제공)
3. 우측에 자동 생성된 프롬프트가 보임
4. **복사 버튼** 클릭
5. 본인이 쓰는 Claude(웹·Code 무관)에 붙여넣기
6. 브랜드 브리프 → STAGE B(디자인 제안 + 미리보기) → 디자인 브리프 순으로 진행 (각 단계 ⌘P로 PDF)

> 완성 예시가 궁금하면 우측 상단 **데모** 링크(`demo-meetingroom.html`)를 참고.

### 2. Claude Code 사용자 — 에이전트 직접 설치 시 더 편함

GUI를 거치지 않고 Claude Code에서 곧바로 호출 가능.

**설치 (폴더 통째로 + 심볼릭 링크 1개)**:
```bash
# 1. 레포 클론 (폴더 이름은 brand-design-guide로 통일)
git clone https://github.com/jungpyo-mtr/brand-design-guide.git brand-design-guide

# 2. 사용자 레벨 .claude/agents/로 이동
mv brand-design-guide ~/.claude/agents/

# 3. Claude Code가 인식하도록 심볼릭 링크 생성
cd ~/.claude/agents && ln -s brand-design-guide/brand-design-guide.md brand-design-guide.md
```

**사용**: "브랜드 설계 도와줘", "디자인 기초설계 잡아줘" 등 평범하게 요청하면 자동 invoke.

---

## 도구 구성

| 파일 | 역할 |
|---|---|
| `brand-design-guide.md` | 에이전트 정의 (역할·베이스 문서·STAGE A/B 프로세스·출력 형식·운영 규칙) |
| `index.html` | 브라우저 GUI 툴 — to-do 입력 + 이론 호버/펼침, 브랜드 완료 시 디자인 제안 자동 생성 + 실시간 미리보기, 단계별 PDF 브리프 |
| `demo-meetingroom.html` | 미팅룸 자체 브랜드로 채운 완성 예시 |

GUI(`index.html`)는 입력·미리보기·프롬프트 생성을 담당하고, 깊은 추론·정합성 점검·상충 해소는 에이전트가 담당하는 **하이브리드** 구조입니다.

---

## 핵심 흐름

```
STAGE A. 브랜드 기초설계 (BIBX 6섹션)  →  [브랜드 브리프 PDF]
   ↓ 그 결과를 근거로
STAGE B. 디자인 기초설계 (자동 제안 + 미리보기 + 이론 설명)  →  [디자인 브리프 PDF]
```

핵심 원칙: **"감"이 아니라 "근거"로.** to-do로 빠르게 쓰고, 이론은 그 답을 더 정확하게 만드는 도구입니다.

---

## 업데이트 배포 (관리자)

```bash
cd ~/.claude/agents/brand-design-guide
./deploy.sh "변경 요약"   # 커밋 + 푸시 → GitHub Pages 자동 반영 (1~2분)
```
