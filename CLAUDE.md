# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

쇼핑 리스트 웹 애플리케이션 - Vanilla JavaScript로 구현된 할 일 관리 앱

## 실행 방법

```bash
# 로컬 서버로 실행 (Google Fonts 로드를 위해 권장)
npx serve .
# 또는
python3 -m http.server 8000

# 접속: http://localhost:3000 또는 http://localhost:8000
```

## 주요 기능

| 기능 | 설명 | 사용법 |
|------|------|--------|
| 아이템 추가 | 새 항목 추가 | 입력 후 Enter 또는 추가 버튼 |
| 아이템 체크 | 완료 표시 | 원형 체크박스 클릭 |
| 아이템 수정 | 텍스트 편집 | 항목 텍스트 더블클릭 |
| 아이템 삭제 | 개별 삭제 | × 버튼 클릭 |
| 순서 변경 | 드래그앤드롭 | ☰ 핸들 드래그 |
| 일괄 삭제 | 완료 항목 삭제 | "완료된 항목 삭제" 클릭 |
| 다크모드 | 테마 전환 | 헤더의 🌙/☀️ 버튼 |
| 데이터 저장 | 클라우드 저장 | Supabase (실시간 동기화) |

## 기술 스택

- **HTML5** - 단일 파일 구조
- **CSS3** - CSS 변수로 다크모드 구현
- **Vanilla JavaScript** - 프레임워크 없음
- **Google Fonts** - Noto Sans KR (한글 폰트)
- **Supabase** - 클라우드 데이터베이스 (PostgreSQL)
- **LocalStorage** - 다크모드 설정 저장

## 프로젝트 구조

```
Study-06/
├── index.html    # 메인 앱 (HTML + CSS + JS 통합)
└── CLAUDE.md     # 프로젝트 문서
```

## 데이터 구조

```sql
-- Supabase 테이블: shopping_items
CREATE TABLE shopping_items (
    id SERIAL PRIMARY KEY,
    text TEXT NOT NULL,
    checked BOOLEAN DEFAULT FALSE,
    position INTEGER NOT NULL DEFAULT 0,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
```

```javascript
// LocalStorage 키: 'darkMode' (테마 설정만 로컬 저장)
isDarkMode = true | false
```

## Supabase 설정

- **Project**: HonGongVibeCoding's Project
- **Region**: ap-south-1
- **Table**: shopping_items

## Repository Context

This folder is part of a study series:
- Study-01: Handwritten digit recognition (Python/TensorFlow)
- Study-04: OpenRouter API integration (recipe app)
- Study-05: PDF summarization and AI diary
- **Study-06: Shopping List App (Current)**
