# UAM-Vertical-Rise




1. Qt creator 실행 
  - GCS의 UI를 바꾸기 위해 GCS를 바로 실행시키지 않고 Qt creator를 실행

2. qgroundcontrol.pro 열기
  -  GCS를 실행시키기 위해 다른 파일의 코드와 합쳐 꾸미는 코드 파일을 여는 것임

3. build 후 실행
  - UI를 바꾸고 이를 컴파일 하기위해 build버튼을 누른 후 실행하면 GCS가 실행

4. github에서 CKU_final2.world, asphalt_plane 파일을 다운로드 받은 후
   CKU_final2.world를 PX4-Autopilot/ Tools/ simulation/ gazebo/ sitl_gazebo/ worlds로 복사
   asphalt_plane을 Home/.gazebo/models로 복사


5. 1번째 Terminal 실행
  - 가제보를 실행시키기 위해 터미널을 열음

6. PX4를 활용한 가제보를 실행시키기 위해 cd PX4-Autopilot 입력 후 디렉토리 이동
  - 실행시킬 파일이 PX4-Autopilot 폴더 안에 있기 때문에 해당 디렉토리로 이동

7. 해당 디렉토리로 이동 후 불러올 월드맵과 같은 좌표를 설정하기 위해 아래 코드를 입력
    (가톨릭 관동대의 좌표)
    export PX4_HOME_LAT=37.73675
    export PX4_HOME_LON=128.87407
    export PX4_HOME_ATL=20


8. 다중 드론 및 드론의 수, 드론의 모델, 자신이 실행 시키고 싶은 월드 순으로 -n, -m, -w로 입력해야함
  - multiple run.sh 파일의 구조를 분석한 결과 -n, -m, -w 순으로 인식하도록 코딩 되어있기 때문에 순서대로 입력해야 함

9.이를 실행 시키 위해 실행 파일이 있는 해당 파일 경로로 진입하여 실행 코드를 입력

10Tools/simulation/gazebo/sitl_multiple_run.sh -n 3 -m typhoon_h480 -w CKU_final2 입력

11.가제보를 실행시키면 GCS와 연동을 확인해야함.

12.연동이 되었다면 상단 중간에 Vehicle 1~3을 개별적으로 선택 가능
  - 위에서 -n을 3으로 설정했기 때문에 3대가 나타남

13. Vehicle 1~3을 선택하고 좌측 상단 구석 세로 툴바에서 Plan 클릭 후,  좌측 상단 구석 세로 툴바에서 이륙지점, 착륙지점 비행 경로, 리턴 설정 가능
    우측 세로 툴바에서 속도, 고도, 카메라 설정 가능

14. Plan을 설정했다면 업로드를 해야하는데 상단 툴바에서 upload버튼을 클릭해 기체에 Plan을 업로드 후, 좌측 상단 구석의 툴바에서 Fly버튼을 클릭

15. 좌측 툴바에서 임무 설정한 기체를 선택하여 arm버튼 클릭 후 mission start버튼 클릭 후, 화면 하단의 슬라이드를 우측으로 스와이프 하면 임무 실행
