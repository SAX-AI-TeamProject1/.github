# K-NAVI

삼성 AXI 1차 프로젝트 — 수신호를 통한 로봇 제어와 이동간 장애물 감지

카메라로 신호수(작업자)의 수신호를 인식해 물류 이동 로봇을 정지/서행/좌회전/우회전시키고,
이동 중에는 장애물을 감지해 사고를 줄이는 것을 목표로 합니다.

## 데모

<img src="https://raw.githubusercontent.com/SAX-AI-TeamProject1/.github/main/profile/assets/demo-pipeline.png" alt="Signal-Vision 실시간 수신호 인식 → RViz LaserScan → Gazebo 창고 시뮬레이션" width="100%" />

왼쪽 위: 웹캠 영상에서 실시간으로 수신호(`left_go`)를 인식하는 Signal-Vision 추론 패널.
오른쪽 위·아래: 인식된 신호를 받아 Gazebo 창고 시뮬레이션에서 로봇이 반응하는 모습.
왼쪽 아래: RViz에서 본 LaserScan 기반 장애물 감지.

## 저장소 구성

| 저장소 | 역할 |
|---|---|
| [Signal-Vision](https://github.com/SAX-AI-TeamProject1/Signal-Vision) | 웹캠 → MediaPipe 손/포즈 랜드마크 → LSTM 수신호 분류 |
| [Signal-Simulation](https://github.com/SAX-AI-TeamProject1/Signal-Simulation) | ROS 2 + Gazebo. Signal-Vision의 결과를 로봇의 정지/서행/목적지 설정, 라이다로 충돌 예측하여 서행 및 비상 정지 |
| [Signal-transport-perception](https://github.com/SAX-AI-TeamProject1/Signal-transport-perception) | YOLO 기반 이동간 장애물 인지 |
| [Industrial-data](https://github.com/SAX-AI-TeamProject1/Industrial-data) | 학습/검증용 데이터셋 |
