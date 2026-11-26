# Move Party — GitHub Pages 배포 (카메라 모션 모드)

## 1. 배포 (5분)
1. GitHub에서 새 저장소 생성 (예: `move-party`)
2. 이 폴더의 모든 파일을 그대로 업로드 (index.html, mp/, fonts/, robots.txt)
3. **(권장) 모델 파일 1개 추가** — 아래 링크를 PC 브라우저로 열어 받은 파일을 `mp/pose_landmarker_lite.task` 로 업로드
   https://storage.googleapis.com/mediapipe-models/pose_landmarker/pose_landmarker_lite/float16/1/pose_landmarker_lite.task
   - 추가하면 외부 서버 연결이 0개가 됩니다. 안 해도 동작합니다 (Google의 고정 경로에서 자동으로 받음).
4. Settings → Pages → Branch: `main` / root → Save
5. iPad Safari에서 `https://<아이디>.github.io/move-party/` 열기 → 공유 → **홈 화면에 추가** (전체화면 앱처럼 실행)

## 2. 플레이
- iPad를 가로로 세워 TV 앞에 고정 → HDMI 미러링 → 2~3m 뒤로
- 첫 실행 시 카메라 권한 "허용"
- 메뉴는 손을 버튼 위에 1초 올려두면 선택됩니다 (터치도 가능)

## 3. 보안 구조
- 카메라 영상은 iPad 안에서만 분석되고 **어디로도 전송·저장·녹화되지 않음** (서버 없음, 전송 코드 없음)
- CSP로 네트워크를 자기 사이트 + Google 모델 경로 1개로만 제한 → 코드가 바뀌어도 외부로 보낼 수 없음
- 다른 사이트에 끼워 넣어진(iframe) 상태에서는 카메라를 아예 켜지 않음
- 앱이 백그라운드로 가면 카메라 즉시 꺼짐, 켜져 있는 동안 화면에 "Camera on" 표시
- 링크를 아는 사람이 접속해도 **그 사람 기기의 카메라**만 쓰일 뿐, 우리 집 카메라는 볼 수 없음
- 저장되는 것은 게임 설정과 최고 점수(iPad 브라우저 내부)뿐
- 요구 사항: iPadOS 16.4 이상 Safari
