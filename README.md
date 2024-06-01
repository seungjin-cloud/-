# 시험 결과 보고 웹 애플리케이션

이 웹 애플리케이션은 시험 결과 보고를 위한 양식 작성을 빠르게 할 수 있게 도와줍니다.

## 기능
1. **양식 입력**: 결과 보고 양식을 입력할 수 있습니다.
2. **시험지명 설정**: 시험명을 입력할 수 있습니다. 
3. **점수 입력**: 학생의 이름과 점수를 입력할 수 있습니다.
4. **결과 생성 및 복사**: 입력된 정보를 바탕으로 양식에 정보가 입력된 결과를 생성하고, 복사할 수 있습니다.
5. **결과 초기화**: 생성된 결과를 초기화할 수 있습니다.

## 사용 방법

### 1. 학생 정보 입력
1. `이름` 필드에 학생의 이름을 입력합니다.
2. `점수` 필드에 학생의 점수를 입력합니다.
3. `점수` 필드에 점수를 입력하고 Enter 키를 누르면 결과가 자동으로 생성됩니다.

-이름 점수 기입 후 결과가 생성되면 입력 포커스가 다시 이름으로 오게 됩니다. 따라서 연속적인 처리를 가능케 합니다.
### 2. 결과 관리
- `복사` 버튼을 클릭하면 생성된 결과를 클립보드에 복사할 수 있습니다.
- `리셋` 버튼을 클릭하면 모든 결과가 초기화됩니다.

### 다음 항목들은 기본값이 존재하며 수정 가능합니다.

#### 양식
- tag 사용법
  
  학생: {name}
  
  시험명: {examName}
  
  점수: {score} ({passed})
  
  총점: {maxScore}
  
  통과 점수(이상): {passCriteria}
  
  통과 여부: {passed}
  
#### 시험지명
- 현재 날짜에 따라 자동으로 설정됩니다.

#### 옵션
- `문항 수`: 기본값은 15입니다. 필요에 따라 변경할 수 있습니다.
- `통과 기준`: 기본값은 12입니다. 필요에 따라 변경할 수 있습니다.

## 개발자 가이드

### 코드 구조

- `index.html`: 주요 HTML 파일로, 전체 UI와 레이아웃을 정의합니다.
- `style` 태그: 기본 스타일을 정의합니다.
- `script` 태그: 양식 자동 완성, 결과 생성 및 관리 기능을 포함한 JavaScript 코드를 포함합니다.

### 주요 함수

- `setDefaultExamName()`: 페이지 로드 시 시험지명을 자동으로 설정합니다.
- `checkTab(event)`: Tab 키 입력 시 점수 입력란으로 포커스를 이동합니다.
- `checkEnter(event)`: Enter 키 입력 시 결과를 자동으로 생성합니다.
- `submitForm()`: 입력된 정보를 바탕으로 결과를 생성합니다.
- `copyResults()`: 생성된 결과를 클립보드에 복사합니다.
- `resetResults()`: 생성된 결과를 초기화합니다.

### 페이지 로드 시 초기 설정

- 페이지 로드 시 `setDefaultExamName()` 함수가 호출되어 시험지명이 자동으로 설정됩니다.
- `양식 입력` 텍스트 영역에 기본 양식이 자동으로 설정됩니다.
- `이름` 입력란에 자동으로 포커스가 이동합니다.
