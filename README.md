# 가속시험 통합계산기 (신뢰성분석)

순수 HTML/CSS/JavaScript로 만든 신뢰성 가속시험 계산기입니다.
서버(Python)가 전혀 필요 없어서 **GitHub Pages에 그대로 올리면 바로 동작**합니다.

## 포함된 기능 (5개 탭)
1. 온도가속 (Arrhenius Model)
2. 온습도가속 (Arrhenius-Peck Model)
3. 열피로가속 (Thermal Cycling: Coffin-Manson / Modified Norris-Landzberg)
4. Weibull 시험시간비 계산기
5. 수명데이터 분석 (Weibull MLE 적합, MTTF/B10/B1, 확률도표)

- 활성화에너지(Ea) 참고 DB 190여 개, Weibull Beta/Eta 참고 DB, Coffin-Manson m지수 가이드 DB 내장
- 계산 결과 엑셀(.xlsx) 내보내기 지원 (xlsx.js 사용)
- Weibull 확률도표는 Chart.js로 렌더링

## GitHub Pages로 배포하는 방법

1. GitHub 계정으로 로그인 → 새 저장소(Repository) 생성 (예: `inzi-reliability-calc`)
   - Public으로 설정 (Pages 무료 사용을 위해 Public 권장)
2. 이 저장소에 `index.html` 파일을 그대로 업로드 (루트 경로에 위치해야 합니다)
   - GitHub 웹에서: 저장소 페이지 → "Add file" → "Upload files" → `index.html` 선택 → Commit
3. 저장소 상단 메뉴 **Settings** → 좌측 **Pages** 클릭
4. **Build and deployment** → Source: **Deploy from a branch** 선택
5. Branch: **main** (또는 master), 폴더: **/ (root)** 선택 후 **Save**
6. 1~2분 정도 기다리면 상단에 배포된 사이트 주소가 나타납니다
   - 형식: `https://<GitHub계정명>.github.io/<저장소이름>/`
7. 그 주소로 접속하면 바로 계산기가 실행됩니다 (서버가 없으므로 잠자기/quota 문제가 없습니다)

## 로컬에서 미리 확인하기
파일이 있는 폴더에서 터미널을 열고:
```
python -m http.server 8000
```
브라우저에서 `http://localhost:8000` 접속하면 바로 확인 가능합니다.

## 참고
- 인터넷 연결이 필요합니다 (Pretendard 폰트, xlsx.js, Chart.js를 CDN에서 불러옵니다).
- 계산 로직(활성화에너지 DB, Weibull 시험시간비 공식, MLE 수명데이터 적합 등)은 원본 Python(tkinter) 코드의 로직을 그대로 JavaScript로 이식한 것입니다.
