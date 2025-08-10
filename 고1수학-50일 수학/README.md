# 고1 수학 학습 진도표

## 📚 전체 단원 목록
- [ ] 01 수와 연산
- [ ] 02 문자와 식
- [ ] 03 곱셈 공식과 인수분해
- [ ] 04 방정식
- [ ] 05 부등식
- [ ] 06 함수
- [ ] 07 여러 가지 도형
- [ ] 08 도형의 성질
- [ ] 09 삼각비와 원의 성질
- [ ] 10 도형의 방정식

## 📂 폴더 구조
```
고1수학-50일 수학/
├── 강의노트/       # 강의 시청 후 정리
├── 문제풀이/       # 문제 풀이 기록
├── 주간기록/       # 주별 학습 계획 및 회고
└── README.md      # 전체 진도 현황 (이 파일)
```

## 🎯 학습 목표
- 주당 최소 2개 강의 시청
- 강의별 관련 문제 풀이
- 주 1회 선생님 세션으로 질문 해결

## 📊 진도 현황 (자동 집계)

### 📚 최근 강의 노트 (최근 7개)
```dataview
TABLE 
  테마번호 as "단원",
  강의제목 as "강의",
  시청상태 as "상태",
  작성일 as "날짜"
FROM "고1수학-50일 수학/강의노트"
SORT 작성일 DESC
LIMIT 7
```

### ✏️ 최근 문제풀이 기록 (최근 5개)
```dataview
TABLE
  테마번호 as "단원",
  length(완료문제) as "✅",
  length(오답문제) as "❌",
  length(질문예정) as "❓",
  작성일 as "날짜"
FROM "고1수학-50일 수학/문제풀이"
SORT 작성일 DESC
LIMIT 5
```

### 📅 주간 학습 통계
```dataview
TABLE
  length(완료강의) as "완료 강의",
  length(목표강의) as "목표 강의",
  문제풀이완료 as "문제 진도",
  선생님세션 as "세션"
FROM "고1수학-50일 수학/주간기록"
SORT 주차 DESC
LIMIT 4
```

### 🎯 THEME별 진도 요약
```dataview
TABLE 
  length(rows) as "강의 수",
  length(filter(rows, (r) => r.시청상태 = "✅완료")) as "완료",
  length(filter(rows, (r) => r.시청상태 = "🔵진행중")) as "진행중"
FROM "고1수학-50일 수학/강의노트"
GROUP BY THEME
```

### 📈 이번 주 학습 요약
```dataview
TABLE WITHOUT ID
  주차 as "주차",
  length(완료강의) + "/" + length(목표강의) as "강의 진도",
  문제풀이완료 as "문제 진도"
FROM "고1수학-50일 수학/주간기록"
SORT 주차 DESC
LIMIT 1
```