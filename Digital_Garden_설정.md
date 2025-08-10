# 🌱 Digital Garden 설정 가이드

## 1️⃣ Obsidian Digital Garden 플러그인 설치
1. Settings → Community Plugins → Browse
2. "Digital Garden" 검색 후 설치
3. 플러그인 활성화

## 2️⃣ GitHub 저장소 생성
1. GitHub에서 새 저장소 생성 (예: `foundation-notes-garden`)
2. Public으로 설정
3. README 없이 빈 저장소로 생성

## 3️⃣ Vercel 계정 및 연동
1. [Vercel](https://vercel.com) 가입 (GitHub 계정으로)
2. Digital Garden 템플릿 배포:
   ```
   https://github.com/oleeskild/digitalgarden
   ```
3. "Deploy to Vercel" 버튼 클릭
4. 저장소 이름 설정 후 배포

## 4️⃣ Obsidian 플러그인 설정
Settings → Digital Garden에서:
1. **GitHub repo name**: `username/foundation-notes-garden`
2. **GitHub username**: GitHub 사용자명
3. **GitHub token**: Personal Access Token 생성
   - GitHub → Settings → Developer settings → Personal access tokens
   - repo 권한 체크
4. **Base URL**: Vercel에서 받은 URL

## 5️⃣ 노트 공개 설정

### 공개할 노트에 추가:
```yaml
---
dg-publish: true
dg-home: false
---
```

### 홈페이지로 설정할 노트:
```yaml
---
dg-publish: true
dg-home: true
---
```

## 6️⃣ 공개 전략 제안

### ✅ 공개 추천
- `README.md` (홈페이지로)
- `templates/` 폴더 (다른 사람 참고용)
- `examples/` 폴더 (예제)
- 완성된 주간 회고

### ❌ 비공개 추천
- 진행 중인 강의노트
- 개인 문제풀이
- CLAUDE.md
- QuickAdd 설정 가이드

## 7️⃣ 배포 방법
1. 공개할 노트에 `dg-publish: true` 추가
2. Command Palette (Cmd+P)
3. "Digital Garden: Publish Single Note" 또는 "Publish Multiple Notes"
4. 몇 분 후 Vercel URL에서 확인

## 💡 팁
- 한 번 설정하면 이후엔 노트만 publish하면 자동 배포
- 이미지도 자동으로 업로드됨
- 노트 간 링크 자동 변환
- 그래프 뷰도 웹에서 볼 수 있음

## 🔗 유용한 링크
- [Digital Garden 플러그인 문서](https://dg-docs.ole.dev/)
- [템플릿 저장소](https://github.com/oleeskild/digitalgarden)