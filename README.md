# 사용자 가이드
anyframe widget의 기능에 대한 자동화 테스트를 수행하는 brity works project 이다.

## 1. 준비사항

### Birty works 준비
* Knox portal의 Brity Works 포탈에서 Brity Works Designer를 다운받아 설치한다.

### Widget 테스트를 위한 코드 빌드하기

1. AUI 소스코드를 내려받는다. (anyframe-widget git 이용)

2. npm install 명령을 통해 필요한 패키지를 설치한다.

	* Python, Node js가 설치되어 있어야 한다.

	* Grunt가 설치되어 있지 않은 경우 아래 명령어로 설치한다.
		
		**npm install -g grunt-cli**

3. widget_test 디렉토리 아래에 lib 폴더를 생성한다.
	
	**mkdir anyframe_widget\widget_test\lib**

4. 생성한 lib 디렉토리를 path로 설정하여 테스트 코드를 빌드한다.
	
	**grunt --path=widget_test/lib**

### <a name="로컬서버">테스트를 위한 로컬서버 실행하기</a>
1. 테스트 디렉토리(widget_test)로 이동하여 로컬서버를 띄운다.

	**npx http-server** (또는 **npx http-server@0.9.0**)
	* 실행이 실패하는 경우, node 버전(12.2.0 이상)과 npm 버전(6.9.0 이상)을 확인해 본다.

## 2. 자동화 테스트
### 시작하기
1. [테스트를 위해서 로컬서버를 실행](#로컬서버)한다.
2. Anyframe_UI_Test.proj 파일을 선택 실행한다. (Brity works가 실행된다)

### 설정
   * targetChrome 변수
        - true: chrome browser를 대상으로 테스트를 진행한다.
        - **false**: IE browser를 대상으로 테스트를 진행한다. (기본설정)
   * debug 변수
        - true: 실행 중에 상태에 대한 로그를 추가적으로 출력한다.
        - **false**: 테스트의 성공 여부만 출력한다. (기본설정)

### 전체 위젯 테스트
   * **RunTestSuites** 프로세스를 선택하고 실행버튼을 눌러 실행한다.
   * 실행이 끝나면 로그파일을 통해서 실행 결과를 확인해 볼 수 있다.
        
	log file path: {anyframe_auto_test path}\Histories\{실행시점}_RunTestSuites\Log\AUITestLog.txt
### 개별 위젯 테스트
   * 테스트하기 원하는 위젯을 선택한다.
   * TS_{widget name} 작업을 선택하고 실행버튼을 눌러 실행한다.
   * 실행이 끝나면 로그파일을 통해서 실행 결과를 확인해 볼 수 있다.
        
	log file path: {anyframe_auto_test path}\Histories\{실행시점}_TS{widget name}\Log\AUITestLog.txt
