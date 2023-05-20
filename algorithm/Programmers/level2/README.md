## Programmers School Algorithm Level_2

### 1. 최댓값과 최솟값
- 문제 설명 :  문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.
예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.

- 해결 방법 : string to integer와 integer to string 함수를 알고 있다면 어렵지 않게 해결이 가능한 기본적인 문자열 문제이다.
- string to integer -> stoi(string)
- integer to string -> to_string(int)


### 2. JadenCase 문자열 만들기
- 문제 설명 :  JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

- 해결 방법 : 문자열을 다루는 방법에 대해 물어보는 문제이며 공백 문자를 기준으로 처음 시작하는 단어가 알파벳 소문자면 대문자로 바꾸고 그게 아닐경우 숫자는 그대로 대문자는 소문자로 바꾸면 되는 간단한 문제이다.

### 3. 최솟값 만들기
- 문제 설명 :  길이가 같은 배열 A, B 두개가 있습니다. 각 배열은 자연수로 이루어져 있습니다. 
배열 A, B에서 각각 한 개의 숫자를 뽑아 두 수를 곱합니다. 이러한 과정을 배열의 길이만큼 반복하며, 두 수를 곱한 값을 누적하여 더합니다. 이때 최종적으로 누적된 값이 최소가 되도록 만드는 것이 목표입니다. (단, 각 배열에서 k번째 숫자를 뽑았다면 다음에 k번째 숫자는 다시 뽑을 수 없습니다.)

- 해결 방법 : 두 수의 곱셈의 결과가 가장 최소가 되는 누적값을 구하는 문제이다. 두 수의 곱세의 결과가 최소가 되려면 가장 작은값과 가장 큰 값을 곱해주면 되므로 하나의 배열은 오름차순 하나의 배열은 내림차순으로 정렬 후 각각의 원소를 곱해주면 최소값을 만들 수 있다.

### 4. 숫자의 표현
- 문제 설명 :  자연수 n이 매개변수로 주어질 때, 연속된 자연수들로 n을 표현하는 방법의 수를 return하는 solution를 완성해주세요.

- 해결 방법 : 해당 문제는 주어진 N을 연속된 자연수들로 표현하는 방법의 수를 반환하는 문제이다. 이 문제는 주어진 n부터 시작하여 1까지 순회를 돌면서 누적된 합이 주어진 N값가 같다면 카운트를 1개 증가하고 누적된 만큼 다시 뒤로 돌아가는 방법으로 정답을 구하면 쉽게 구할 수 있다.

### 5. 다음 큰 숫자
- 문제 설명 :  자연수 n이 주어졌을 때, n의 다음 큰 숫자는 다음과 같이 정의 합니다.
조건 1. n의 다음 큰 숫자는 n보다 큰 자연수 입니다.
조건 2. n의 다음 큰 숫자와 n은 2진수로 변환했을 때 1의 갯수가 같습니다.
조건 3. n의 다음 큰 숫자는 조건 1, 2를 만족하는 수 중 가장 작은 수 입니다.
예를 들어서 78(1001110)의 다음 큰 숫자는 83(1010011)입니다.
자연수 n이 매개변수로 주어질 때, n의 다음 큰 숫자를 return 하는 solution 함수를 완성해주세요.

- 해결 방법 : 해당 문제의 가장 어려운 점은 10진수를 2진수로 변환하는 방법이다. 함수를 만들어서 사용할 수 있지만. STL <bitset> 라이브러리를 사용하여 쉽게 해결할 수 있다. 다만 bitset<>().to_string() 함수는 변환할 자리수를 상수로 미리 정해줘야 한다는 점을 기억해야 하며 주어진 문제의 정수 표현값을 최대 20자릿수이므로 20으로 고정해서 문제를 해결하면 쉽게 해결이 가능했다.


### 6. 이진 변환 반복하기
- 문제 설명 :  0과 1로 이루어진 문자열 s가 매개변수로 주어집니다. s가 "1"이 될 때까지 계속해서 s에 이진 변환을 가했을 때, 이진 변환의 횟수와 변환 과정에서 제거된 모든 0의 개수를 각각 배열에 담아 return 하도록 solution 함수를 완성해주세요.

- 해결 방법 : string의 0을 모두 제거한 길이를 이진수로 변환후 다시 그 이진수에서 다시 0을 모두 제거하는 방식으로 최종 길이가 1이 될 때까지 반복하면 되는 문제로 자리수를 고정하고 0을 모두 제거하는 방식으로 하면 bitset 함수를 사용가능하다.

### 7. 피보나치수
- 문제 설명 : 2 이상의 n이 입력되었을 때, n번째 피보나치 수를 1234567으로 나눈 나머지를 리턴하는 함수, solution을 완성해 주세요

- 해결 방법 : 아주 간단한 피보나치 문제이지만 그냥 단순하게 재귀적으로 문제를 해결한다면 n값이 상당히 높은 경우 시간초과를 피할 수 없다. 이 때 이미 계산했던 값은 배열의 저장을 해서 다음 계산에는 저장된 값을 사용하는 메모제이션 기법을 사용해서 풀어야 하는 문제이며 해당 방식에 대해서 알고만 있다면 쉽게 해결이 가능한 문제이다.   