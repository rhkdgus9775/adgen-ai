# adgen-ai 영상 생성 파이프라인 설계

1. 스토리보드 자동 생성
   - 입력: 키워드 (예: "의자")
   - 출력: 장면별 구성을 담은 md 파일
   - 구현됨: generate_ad.py

2. 장면별 영상 클립 생성 (Runway / Pika)
   - 각 SCENE의 Visual Prompt를 API에 전달
   - 결과: scene01.mp4, scene02.mp4, ... 저장 예정
   - 상태: 설계 완료, API 연동 단계 예정

3. 나레이션 음성 합성 (TTS)
   - 각 SCENE의 Voiceover 문장을 TTS API로 전송
   - 결과: scene01.mp3, scene02.mp3, ...
   - 상태: 설계 완료, voice gen 스크립트 예정

4. 자막 및 온스크린 텍스트
   - 스토리보드에서 SRT(시간정보) 자동 생성
   - Shorts/Reels에 바로 올릴 수 있는 캡션 형태 유지
   - 상태: 초안 완료 (의자 예시)

5. 최종 합성
   - ffmpeg로 scene별 mp4와 mp3를 합치고 순서대로 붙여서
     15초짜리 최종 광고 mp4 산출
   - 상태: 예정 (render_video.py 계획)
