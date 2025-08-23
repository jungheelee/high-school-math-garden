---
dg-publish: true
permalink: /math-dashboard/
title: 고1 수학 대시보드
---

# 고1 수학 학습 대시보드

## 📊 전체 진도 현황
```dataviewjs
const pages = dv.pages('"50days-math/weekly"');
const 총완료 = pages.map(p => (p.완료강의 || []).length).array().reduce((a,b) => a+b, 0);
const 진도율 = Math.round(총완료/45*100);

dv.table(["현재 진도", "다음 목표"], 
  [[`🎯 수학(상): ${총완료}/45강 (${진도율}%)`, "📅 수학(하): 0/34강"]]
);
```

## 📅 최근 4주 학습 현황
```dataview
TABLE
  주차 as "주차",
  length(계획강의) as "📋 계획",
  length(완료강의) as "✅ 완료",
  choice(문제풀이완료, "✅", "❌") as "📝 문제"
FROM "50days-math/weekly"
SORT 주차 DESC
LIMIT 4
```

## 📈 이번 달 학습 분석
```dataviewjs
const today = dv.date("today");
const monthStr = today.toFormat("yyyy-MM");
const monthKor = today.toFormat("M월");

const pages = dv.pages('"50days-math/weekly"')
  .where(p => p.file.name.includes(monthStr));

const 계획총합 = pages.map(p => (p.계획강의 || []).length).array().reduce((a,b) => a+b, 0);
const 완료총합 = pages.map(p => (p.완료강의 || []).length).array().reduce((a,b) => a+b, 0);
const 문제완료 = pages.where(p => p.문제풀이완료).length;
const 주차수 = pages.length;

dv.paragraph(`
📊 **${monthKor} 학습 요약**
- 활동 주차: ${주차수}주
- 강의 진도: ${계획총합}강 계획 → ${완료총합}강 완료
- 달성률: ${Math.round(완료총합/계획총합*100)}%
- 주평균: ${(완료총합/주차수).toFixed(1)}강
- 문제풀이: ${문제완료}/${주차수}주 완료
`);
```

## 📚 전체 커리큘럼

### 📘 수학(상) - 45강 [현재 진행중]
```dataviewjs
// 현재 완료한 강의 수를 실제 데이터에서 가져오기
const allPages = dv.pages('"50days-math/weekly"');
const 완료강의수 = allPages
  .map(p => (p.완료강의 || []).length)
  .array()
  .reduce((a,b) => a+b, 0);
const 주당강의수 = 2; // 주 2회, 회당 1강

// 수학(상) 계산
const 수학상_남은강의 = 45 - 완료강의수;
const 수학상_남은주차 = Math.ceil(수학상_남은강의 / 주당강의수);
const 수학상_완료예정 = dv.date("today").plus({weeks: 수학상_남은주차});

dv.paragraph(`
**진도**: ${완료강의수}/45강 (${Math.round(완료강의수/45*100)}%)  
**예상 완료**: ${수학상_완료예정.toFormat("yyyy년 M월")} (약 ${수학상_남은주차}주 소요)
`);
```
- [ ] 01 수와 연산 (1-11강)  
- [ ] 02 문자와 식 (18-21강)  
- [ ] 03 곱셈 공식과 인수분해 (22-32강)
- [ ] 04 방정식 (33-40강)  
- [ ] 05 부등식 (41-45강)  

### 📗 수학(하) - 34강 [예정]
**예상 시작**: 2026년 1월  
**예상 완료**: 2026년 5월

- [ ] 06 함수 (1-14강)
- [ ] 07 도형의 기본 (15-21강)
- [ ] 08 도형의 성질 (22-30강)
- [ ] 09 도형의 방정식 (31-34강)

## 🗂 프로젝트 구조
```
50days-math/
├── lectures/       # 강의별 정리 (선택)
├── problems/       # 오답노트 (선택)
├── weekly/         # 주간 학습 관리 (핵심)
└── README.md       # 대시보드 (현재 파일)
```

## 💡 사용법
1. **매주 월요일**: 주간기록 생성 → 영상강의 2개 선택, 학습 시작
2. **화~금 집중 학습**: 강의 시청 → 문제풀이 → 체크
3. **주말 확인**: 이 대시보드에서 진도 확인 및 모르는/어려운 문제 물어보기

---
*주 2회, 꾸준히*