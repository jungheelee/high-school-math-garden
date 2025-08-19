# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

고1 수학 50일 완성 프로젝트 - 주 2회 학습으로 온라인 강의와 문제집을 병행하며 체계적으로 학습하는 Obsidian 기반 노트 시스템

## Repository Structure

```
foundation-notes/
├── 📚 templates/           # 노트 템플릿
│   ├── weekly-study.md     # 주간 학습 계획 (핵심)
│   ├── lecture-note.md     # 강의 노트
│   └── problem-solving.md  # 문제풀이 오답노트
├── 📝 examples/            # 템플릿 사용 예제
├── 📖 50days-math/         # 실제 학습 노트
│   ├── lectures/           # 강의노트
│   ├── problems/           # 문제풀이
│   └── weekly/             # 주간 단위 학습 관리
└── 📂 class_folder/        # Metadata Menu 클래스 정의
    └── 영상강의목록테스트.md  # 45개 강의 목록 관리
```

## Key Features

### 주 2회 학습 시스템
- 화요일/토요일 또는 수요일/일요일 학습
- 강의 1개 + 문제풀이를 한 세션으로 진행
- 주간 노트로 모든 진도 통합 관리

### 메타데이터 구조
- **최소화된 필드**: 필수 정보만 기록
- **영상강의 목록**: Metadata Menu로 45개 강의 드롭다운 선택
- **이해도 체크**: 별점으로 간단히 표시

### 템플릿 활용
- **weekly-study.md**: 주간 학습 목표, 진도, 회고
- **lecture-note.md**: 스스로 점검, 연결고리 찾기
- **problem-solving.md**: 오답 중심 기록

## Workflow

### 월요일: 주간 계획
1. QuickAdd 매크로로 주간노트 생성
2. 영상강의 2개 선택
3. 학습 일정 설정

### 화/토 학습 세션
1. 강의 시청 → 이해도 체크
2. 관련 문제 풀이 → 오답 기록
3. 궁금한 점 메모

### 주말: 회고 & 계획
1. 주간 회고 작성
2. 다음 주 계획 수립
3. 선생님 세션 질문 정리

## Plugins Used
- **Templater**: 템플릿 자동화
- **QuickAdd**: 빠른 노트 생성
- **Metadata Menu**: 강의 목록 관리
- **Dataview**: 진도 통계 (예정)

## Notes for Claude
- 주 2회 학습에 최적화된 간단한 구조 유지
- 불필요한 메타데이터 추가 지양
- 주간노트 중심의 통합 관리 지향
- 한국어 수학 용어 사용