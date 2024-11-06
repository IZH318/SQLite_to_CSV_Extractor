# SQLite to CSV 추출 도구 (SQLite to CSV Extractor)
![_2024_11_07_02_16_27_57-ezgif com-optimize](https://github.com/user-attachments/assets/275267cb-ad62-4c94-8989-aa144880c973) <BR>
`SQLite to CSV Extractor`는 SQLite 데이터베이스에서 모든 테이블을 추출하여 각 테이블을 CSV 파일로 저장하는 Python 스크립트입니다. <BR> <BR>
이 도구는 간단한 GUI를 통해 사용자가 SQLite 파일을 선택하고, CSV 파일을 저장할 폴더를 선택할 수 있도록 도와줍니다.

<BR>

## 🔍 주요 기능
- SQLite 데이터베이스의 모든 테이블에 대해 순차적으로 CSV 파일을 생성합니다.
- 사용자는 입력된 데이터베이스 파일과 출력 디렉토리를 쉽게 선택할 수 있습니다.

<BR>

## 💾 다운로드 <BR>
| Program                                | URL                                                | 필수여부 | 비고                                                                                           |
|----------------------------------------|----------------------------------------------------|----------|------------------------------------------------------------------------------------------------|
| `Python`            | [Download](https://www.python.org/downloads/release/python-390/)   | 필수     | ◼ Python Script 동작, 파이썬 3.9.0 버전 또는 그 이상 사용 가능 |
| `반디집`             | [Download](https://kr.bandisoft.com/bandizip/)   | 필수     | ◼ (* 다른 압축 프로그램 사용 가능) |

<BR>

## 🛠️ 설치

### ※ exe 파일을 사용 할 사용자는 해당 작업을 생략하고 '⏩ 사용 방법'으로 이동하면 됩니다. <BR> <BR>

1. Python 설치 파일을 실행 합니다. <BR> <BR>

2. Python을 설치합니다. <BR> <BR>
![2024-11-06 07 20 58](https://github.com/user-attachments/assets/66362323-9dea-4bd5-bd76-4f1c268c567b) <BR>
**[ ※ 주의 ] Python 설치 시 Add python.exe to PATH 에 반드시 체크 후 Install Now 클릭** <BR>
(📌 미처 누르지 못했다면 설치 파일 다시 실행 또는 제거 후 재 설치) <BR> <BR>
![2024-11-06 07 21 25](https://github.com/user-attachments/assets/0d83ce4b-c5f1-44cc-855e-87b974cf24b3) <BR>
**[ ※ 주의 ] 설치 후 Disable path length limit 기능을 사용할 수 있도록 반드시 클릭** <BR>
(📌 미처 누르지 못했다면 설치 파일 다시 실행 후 작업 또는 제거 후 재 설치) <BR> <BR>

3. cmd 실행 후 아래 내용을 참고하여 필요한 패키지를 업데이트(선택) 또는 설치 합니다. <BR> <BR>
3-1. **(선택사항, 생략가능) Python Package Update** <BR> <BR>
(* 두 코드 중 하나 선택) <BR>
`pip install --upgrade pip` <BR>
or <BR>
`python -m pip install --upgrade pip` <BR> <BR>
**[ ※ 주의 ] 만약 위 명령어 사용 중 ERROR: Could not install packages due to an EnvironmentError: [WinError 5] 액세스가 거부되었습니다: (생략) Consider using the `--user` option or check the permissions. 과 같은 오류가 나왔다면 끝에 `--user`를 붙여서 입력** <BR> <BR>
(* 권한 오류 발생시 두 코드 중 하나 선택) <BR>
`pip install --upgrade pip --user` <BR>
or <BR>
`python -m pip install --upgrade pip --user` <BR>
<BR> <BR> <BR>
3-2. **(필수) pandas Package 설치** <BR> <BR>
`pip install pandas` <BR>
or <BR>
`python -m pip install pandas` <BR> <BR>
**[ ※ 주의 ] 만약 위 명령어 사용 중 ERROR: Could not install packages due to an EnvironmentError: [WinError 5] 액세스가 거부되었습니다: (생략) Consider using the `--user` option or check the permissions. 과 같은 오류가 나왔다면 끝에 `--user`를 붙여서 입력** <BR> <BR>
(* 권한 오류 발생시 두 코드 중 하나 선택) <BR>
`pip install pandas --user` <BR>
or <BR>
`python -m pip install pandas --user` <BR>
<BR> <BR> <BR>
Windows 환경 사용자는 `00. Install_required_Python_packages.bat` 을 실행하여 필요 패키지를 한 번에 설치할 수 있습니다.

<BR>

## ⏩ 사용 방법

### 1. 프로그램 실행 후 파일 및 CSV 파일 저장 경로 지정
- Python 스크립트를 실행하면 GUI 창이 열리고, 사용자는 순차적으로 아래와 같은 파일 선택 대화상자가 표시됩니다.
   - **Select SQLite Database File**: 추출하려는 데이터베이스 파일을 선택합니다.
   - **Select Folder to Save CSV Files**: 추출된 CSV 파일을 저장할 폴더를 선택합니다.

<BR>

### 2. 확인 및 사용자 입력

작업을 진행하기 전에, **CSV로 추출할 테이블 개수**와 **출력 폴더**에 대한 확인을 요청합니다.
- **Do you want to proceed with exporting (전체 테이블 수) tables to CSV? ([Y]/[N])**
  - `Y`를 입력하면 작업이 계속 진행됩니다.
  - `N`을 입력하면 프로그램이 종료됩니다.

<BR>

### 3. 작업 진행

- 선택한 데이터베이스 파일에서 모든 테이블을 추출하여 사용자가 지정한 경로에 DB 파일 이름으로 폴더를 생성한 다음 해당 폴더에 CSV 형식으로 파일을 저장합니다.
- 각 테이블의 데이터를 순차적으로 추출하여 CSV로 저장하며, 작업 진행 상태를 출력합니다.

<BR>

### 4. 작업 완료 후

모든 테이블이 CSV 파일로 성공적으로 추출되면, 완료 메시지가 출력됩니다. <BR>
사용자에게는 작업이 완료되었음을 알려주는 메시지와 함께 Enter 키를 눌러 종료하도록 안내합니다.

<BR>

## ⚖️ 라이센스

이 프로젝트는 [GNU Lesser General Public License v2.1](LICENSE)에 따라 라이선스가 부여됩니다.

<BR> <BR> <BR>
