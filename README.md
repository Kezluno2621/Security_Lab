# Kezluno Security Lab · GitHub Pages 정적 버전

서버·로그인·설치 없이 동작하는 정보보안 학습 및 실습 기록 앱입니다.

## GitHub Pages에 올리기
1. GitHub에서 저장소를 만듭니다. 예: security-lab
2. 이 폴더의 **내용물**을 저장소 최상위에 업로드하고 커밋합니다. index.html이 최상위에 있어야 합니다.
3. 저장소 Settings → Pages → Build and deployment에서 Source를 **Deploy from a branch**로 선택합니다.
4. Branch를 **main**, 폴더를 **/(root)**로 선택하고 Save를 누릅니다.
5. 배포가 끝나면 Pages 화면에 표시되는 주소로 접속합니다.

빌드 도구는 필요 없습니다. app.js, style.css, index.html이 배포 파일이며 .nojekyll도 함께 올려 주세요.
공식 안내: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 기록 저장과 이동
- 데이터는 해당 주소의 브라우저 localStorage에 저장됩니다. 사이트 코드나 GitHub 저장소로 업로드되지 않습니다.
- 기기·브라우저·도메인 간 자동 동기화는 없습니다. 브라우저 데이터 삭제 시 기록도 지워질 수 있습니다.
- 하단 JSON 백업으로 파일을 보관하고, 다른 기기에서 JSON 복원으로 불러오세요. 복원은 기존 기록을 교체합니다.
- 기존 Sites 앱에서 JSON 백업을 받은 뒤 이 버전에서 JSON 복원으로 가져올 수 있습니다.
- 주간 목표와 우선순위 선택은 '주간 목표 저장'을 누르면 저장됩니다. 작업은 '기록 저장', 반복 체크는 체크 즉시 저장됩니다.
- GitHub Pages 버전에는 로그인 제한이 없습니다. 개인 증빙은 공개 저장소에 올리지 말고 접근 권한이 설정된 링크로 관리하세요.

## 수정
app.tsx는 편집 가능한 원본입니다. 현재 배포 파일 app.js는 React가 포함된 번들로 외부 CDN 없이 동작합니다.
원본을 수정하려면 Node.js 환경에서 아래 명령을 실행하세요.

```sh
npm install --no-save react@19.2.6 react-dom@19.2.6 esbuild@0.28.0
npx esbuild app.tsx --bundle --minify --jsx=automatic --outfile=app.js --define:process.env.NODE_ENV='"production"'
```

CSS는 style.css에서 직접 수정할 수 있습니다. 초기 작업 10개는 모두 미확인으로 시작합니다.
