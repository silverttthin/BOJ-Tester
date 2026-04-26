# BOJ Tester

<h2><a href=#english-version>[English]</a></h2>

BOJ Tester는 [백준 온라인 저지(BOJ)](https://www.acmicpc.net)의 문제를 더욱 효율적으로 풀 수 있도록 도와주는 Visual Studio Code 확장 프로그램입니다.
이 확장 기능을 사용하면 vs code 안에서 **문제 파일을 열고**, **문제 정보를 확인하며**, **테스트 케이스 실행,추가,수정,삭제** 및 **코드 제출**을 쉽게 할 수 있습니다.

## 무엇을 기여했는가?

[Issue link](https://github.com/koomin1227/BOJ-Tester/issues/41)

### 🤔

익스텐션의 C++ 컴파일 명령어가 `g++ "{file}" -o "{out}"` 형식으로 고정이였습니다.
mac으로 실행 시 내장 컴파일러인 clang으로 실행됐고 이 컴파일러는 내부적으로 g++ 명령어의 표준이  C++98/03였습니다.
따라서 최신 표준 문법으로 작성한 코드 실행 시 컴파일 오류가 발생했습니다.

### 💡

단순하게 명령어 수행 시 `-std=c++17` 옵션을 추가하면 됩니다. 보편적으로 지원되는 기능으로 추가하기 위해 다음 기능을 추가해 기여했습니다.

<img width="473" height="295" alt="image" src="https://github.com/user-attachments/assets/2bb6b361-c92f-4915-a52f-d04b288d8831" />

이후 setting.json에서 직접 key(언어), value(커스텀 컴파일 옵션)을 입력하는 방식은 ux적으로 꽤 나쁜 것 같다는 피드백을 받고 현재 컴파일 에러가 발생할 확률이 높은 언어인 C, C++에만 한정해
커스텀 컴파일 기능을 제공하는 것으로 수정해 다음처럼 이 오픈소스에 기여했습니다.

<img width="560" height="328" alt="image" src="https://github.com/user-attachments/assets/786a7baf-8535-4c24-a200-316ee496d7f9" />

## 주요 기능

![사용 예](https://github.com/user-attachments/assets/7a163b5f-3525-4a39-97d7-84217c5e3a0d)

### 1. VS Code 안에서 문제 보기

* 문제 번호로 된 파일을 열고 “문제 보기” 버튼을 클릭하면, 오른쪽 패널에 해당 문제의 정보를 띄워줍니다.
* 파일 이름이 문제 번호가 아닐 경우, 직접 문제 번호를 입력하여 문제 정보를 확인할 수 있습니다.

### 2. 테스트 케이스 실행

* 작성한 코드를 파일 확장자에 맞는 언어로 실행하여 테스트할 수 있습니다.
* 단일 테스트 케이스 실행 및 전체 테스트 케이스 실행 기능을 제공합니다.

#### 지원 언어

`Python`, `Java`, `JavaScript`, `C++`, `C`, `Kotlin`, `Swift`, `Go`

### 3. 테스트 케이스 추가하기

* 문제에서 기본으로 제공하는 테스트 케이스 외에 다양한 테스트 케이스를 임의로 추가할 수 있습니다.
* 추가한 테스트 케이스의 값은 수정 및 삭제가 가능합니다.
  ![화면 기록 2025-01-31 오후 7 48 13](https://github.com/user-attachments/assets/0368085c-b8a3-4563-ad36-70295f14cc03)

### 4. IDE 기능 비활성화

* 대부분의 코딩테스트에서는 IDE 의 기능을 사용할 수 없습니다.
* 이에 대비하여 연습할 수 있도록 IDE 기능을 비활성화 할 수 있습니다.

### 5. 코드 제출 기능

* “제출하기” 버튼을 클릭하면 BOJ 제출 창이 열리며, 코드가 클립보드에 자동으로 복사됩니다.
* 제출 페이지에서 손쉽게 코드를 붙여넣고 제출할 수 있습니다.

### 6. 문제 파일 생성

* “문제 파일 생성” 버튼을 클릭하고 문제 번호를 입력하면, 해당 번호의 문제 파일을 자동으로 생성합니다.
* 생성된 문제 파일을 자동으로 열고 문제 정보를 띄워줍니다.

## 요구 사항

BOJ Tester를 사용하려면 해당 프로그래밍 언어의 실행 환경이 필요합니다:

## Extension Settings

BOJ Tester는 다음과 같은 설정을 제공합니다:

* `BOJ-Tester.defaultLanguage`: 문제 파일 생성 시 사용할 기본 확장자 (예: py, java, cpp)
* `BOJ-Tester.customCommands`: 언어별 원하는 커스텀 컴파일 명령어 작성

  * 컴파일 옵션을 직접 지정할 때 사용합니다 (예: `-std=c++17`)

### 설정 방법

1. BOJ Tester 사이드바 열기
2. 사이드바의 제목 오른쪽에 위치한 톱니바퀴 아이콘 클릭
3. 설정창에서 설정 변경

## 알려진 문제

* BOJ 서버가 다운되었거나 네트워크 연결이 불안정한 경우 문제 정보 보기 기능이 원활하지 않을 수 있습니다.
* 테스트 케이스 실행 중 지원되지 않는 확장자를 사용할 경우 오류가 발생할 수 있습니다.

## 개발자

* [koomin1227](https://github.com/koomin1227)

## 문의 및 피드백

문제가 발생하거나 개선이 필요한 사항이 있다면 아래의 링크를 통해 문의해 주세요.

* GitHub 이슈 등록: [GitHub Issues](https://github.com/koomin1227/BOJ-Tester/issues)
* email : [koomin1227@naver.com](mailto:koomin1227@naver.com)

**Enjoy BOJ Tester! 🚀**

---

<div id="english-version"></div>

# BOJ Tester

BOJ Tester is a Visual Studio Code extension that helps you solve problems more efficiently on [Baekjoon Online Judge (BOJ)](https://www.acmicpc.net) which is competitive programming platform.
With this extension, you can **open problem files**, **view problem details**, **run/add/edit/delete test cases**, and **submit code** easily — all inside VS Code.

## What did I contribute?

[Issue link](https://github.com/koomin1227/BOJ-Tester/issues/41)

### 🤔

The extension’s C++ compile command was fixed to the format: `g++ "{file}" -o "{out}"`.
On macOS, it ran with the built-in compiler (clang), and this compiler effectively used the `g++` standard mode of **C++98/03**.
As a result, code written with modern C++ standards caused compilation errors.

### 💡

The simple fix is to add the `-std=c++17` option when running the command.
To add this as a generally useful feature, I implemented the custom compile script feature and contributed it:

<img width="473" height="295" alt="image" src="https://github.com/user-attachments/assets/2bb6b361-c92f-4915-a52f-d04b288d8831" />

Later, I received feedback that directly editing `settings.json` with a key (language) and value (custom compile options) was poor UX.
So I revised the scope to provide custom compile functionality only for **C and C++**, which are the languages most likely to face compilation errors, and contributed this improvement to the project:

<img width="560" height="328" alt="image" src="https://github.com/user-attachments/assets/786a7baf-8535-4c24-a200-316ee496d7f9" />

## Key Features

![사용 예](https://github.com/user-attachments/assets/7a163b5f-3525-4a39-97d7-84217c5e3a0d)

### 1. View problems inside VS Code

* Open a file named with a problem number and click the “View Problem” button to display the problem details in the right panel.
* If the file name is not a problem number, you can manually enter the number to view the problem information.

### 2. Run test cases

* Run your code in the appropriate language based on the file extension.
* Supports running a single test case or running all test cases.

#### Supported Languages

`Python`, `Java`, `JavaScript`, `C++`, `C`, `Kotlin`, `Swift`, `Go`

### 3. Add test cases

* Add arbitrary test cases in addition to the default ones provided by the problem.
* You can edit or delete added test cases.
  ![화면 기록 2025-01-31 오후 7 48 13](https://github.com/user-attachments/assets/0368085c-b8a3-4563-ad36-70295f14cc03)

### 4. Disable IDE features

* Most coding tests do not allow IDE features.
* To help you practice in similar conditions, you can disable IDE features.

### 5. Submit code

* Clicking the “Submit” button opens the BOJ submission page and automatically copies your code to the clipboard.
* You can easily paste and submit your solution on the submission page.

### 6. Create problem files

* Click “Create Problem File” and enter the problem number to automatically generate a problem file for that number.
* The generated file is automatically opened and the problem details are displayed.

## Requirements

To use BOJ Tester, you need a runtime environment for the corresponding programming language:

## Extension Settings

BOJ Tester provides the following settings:

* `BOJ-Tester.defaultLanguage`: Default extension to use when creating problem files (e.g., py, java, cpp)
* `BOJ-Tester.customCommands`: Define custom compile commands per language

  * Used when you want to explicitly set compile options (e.g., `-std=c++17`)

### How to configure

1. Open the BOJ Tester sidebar
2. Click the gear icon on the right side of the sidebar title
3. Change settings in the settings window

## Known Issues

* If the BOJ server is down or the network connection is unstable, the “View Problem” feature may not work smoothly.
* If you use an unsupported file extension while running test cases, an error may occur.

## Developer

* [koomin1227](https://github.com/koomin1227)

## Contact & Feedback

If you encounter issues or have suggestions for improvement, please reach out via the links below.

* GitHub Issues: [GitHub Issues](https://github.com/koomin1227/BOJ-Tester/issues)
* email : [koomin1227@naver.com](mailto:koomin1227@naver.com)

**Enjoy BOJ Tester! 🚀**
