# Move Party

가족용 모션 게임 — iPad를 TV에 미러링하고 카메라 앞에서 몸으로 플레이 (Fruit Slash · Sprint Dash · Beat Punch)

## 플레이
- 진행자 iPad: Safari에서 사이트 열기 → 공유 → 홈 화면에 추가 → 아이콘으로 실행 → Tap to start → 카메라 허용
- 1 기기 = 1명. 추가 인원(최대 3명)은 메뉴의 **+ Add players with QR** → 각자 폰으로 QR 스캔 → Join → 카메라 허용 → 폰을 세워 두고 전신이 보이게 뒤로

## 보안 구조
- 카메라 영상은 어떤 기기에서도 밖으로 나가지 않음 (전송·저장·녹화 코드 없음)
- 추가 인원 폰은 자기 기기에서 동작 인식 후 **관절 좌표 숫자만** 진행자 iPad로 전송 (WebRTC 암호화)
- QR에는 매번 새로 만드는 128비트 키 + 진행자 iPad 인증서 지문이 들어 있어, 키가 없거나 다른 기기로 위장하면 접속 거부
- 강퇴 시 키 자동 교체 / New code 로 언제든 교체
- 기기끼리 서로를 찾는 데만 무료 PeerJS 매칭 서버 사용 (접속 정보만 보이고 게임 데이터는 보이지 않음)
- CSP로 네트워크를 이 사이트·모델 경로·PeerJS로만 제한

## (권장) 모델 파일 직접 올리기
PC 브라우저로 받아 `mp/pose_landmarker_lite.task` 로 업로드하면 Google 서버 연결도 없어짐:
https://storage.googleapis.com/mediapipe-models/pose_landmarker/pose_landmarker_lite/float16/1/pose_landmarker_lite.task
