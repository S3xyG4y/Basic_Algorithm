정렬(sorting): 데이터를 특정한 기준에 따라서 순서대로 나열하는것

정렬 종류:
    1. 선택 정렬 - 여러 데이터가 무작위로 나열되어 있을때, "이 중에서 가장 작은 데이터를 선택해 맨앞에 있는 데이터와 바꾸고, 그 다음으로 작은 데이터를 선택해 앞에서 두 번째 데이터와 바꾸는 과정을 반복한다 (가장 원시적인 방법이며, 매번 가장 작은 것을 선택해서 "선택" 정렬이다.)
    
    (나의 정의 - 인덱스가 가장 낮은 순서부터 차례대로 매 데이터를 넣을때 마다 리스트 전체에서 가장 작은 값이 뭔지 찾아서 해당 인덱스에 넣는다)

    2. 삽입 정렬 - 특정한 데이터를 적절한 위치에 삽입한다

    (나의 정의 - 인덱스가 가장 낮은 순서부터 인덱스를 점차 확장해 가면서 그때마다 새로 추가된 데이터와 정렬된 데이터와 비교하여 알맞는 인덱스에 새로 추가된 데이터를 넣습니다.)

    3. 퀵 정렬 - 기준(피벗)을 먼저 정한다 -> 피벗을 기준으로 더 큰 수와 더 작은 수로 구분되는 2개의 리스트가 생성된다 해당 리스트를 정렬한다.

    4. 계수 정렬 - 1. 선형 시간 복잡도: O(n + k)로, n은 원소 개수, k는 원소 중 최대값입니다, 2. 안정 정렬: 동일한 값의 원소 순서가 정렬 후에도 유지됩니다, 3. 제한된 상황에서 사용: 계수 정렬은 정수 또는 정수로 변환 가능한 자료형에만 적용할 수 있으며, 입력 데이터의 범위가 작을 때 효과적입니다.
    -> 추가: 원소의 순서가 정렬 후에도 유지라는 말은 다음과 같습니다.
            --> 정렬 전 [(3, 'A'), (1, 'A'), (2, 'A'), (2, 'B'), (3, 'B')]
            --> 정렬 후 [(1, 'A'), (2, 'A'), (2, 'B'), (3, 'A'), (3, 'B')]
            --> 이런식으로 숫자를 키라고 지정하여 정렬 했을시 여전히 A, B의 순서는 유지됩니다.
    -> 추가: 데이터의 범위가 작다는건 최댓값과 최솟값의 차이가 작다는걸 의미합니다.


-파이썬 sort와 sorted 차이-

파이썬의 내장 함수인 sort와 sorted는 모두 리스트를 정렬하는 데 사용되지만, 사용 방식과 결과가 다릅니다.

sort:
* sort 메소드는 리스트 객체의 메소드로, 원본 리스트를 정렬된 상태로 변경합니다(즉, 원본 리스트가 수정됩니다).
* 반환 값은 None입니다.
* 리스트 객체에만 사용할 수 있습니다.

예시:
    numbers = [4, 2, 1, 3]
    numbers.sort()
    print(numbers)  # 출력: [1, 2, 3, 4]

sorted:
* sorted 함수는 원본 리스트에 영향을 주지 않고, 정렬된 새로운 리스트를 반환합니다.
* 다양한 반복 가능한(iterable) 객체에 사용할 수 있습니다 (예: 리스트, 튜플, 딕셔너리).
* sorted 함수는 원본 데이터를 수정하지 않으므로, 원본 데이터의 순서를 유지하려는 경우 유용합니다.

예시:
    numbers = [4, 2, 1, 3]
    sorted_numbers = sorted(numbers)
    print(sorted_numbers)  # 출력: [1, 2, 3, 4]
    print(numbers)  # 출력: [4, 2, 1, 3] (원본 리스트는 변경되지 않음)

요약하면, sort 메소드는 원본 리스트를 정렬하고 반환 값이 없으며, 리스트 객체에만 사용할 수 있습니다. 반면에, sorted 함수는 원본 리스트를 변경하지 않고 정렬된 새로운 리스트를 반환하며, 다양한 반복 가능한 객체에 사용할 수 있습니다.

----------------------------------------------------------------
위에서 아래로

문제: 하나의 수열에는 다양한 수가 존재한다. 이러한 수는 크기에 상관없이 나열되어 있다. 이 수를 큰 수부터 작은 수의 순서로 정렬해야 한다. 수열을 내림차순으로 정렬하는 프로그램을 만드시오.

입력 조건

첫째 줄에 수열에 속해 있는 수의 개수 N이 주어진다.(1 <= N <= 500)
둘째 줄부터 N + 1번째 줄까지 N개의 수가 입력된다.
수의 범위는 1 이상 100,000 이하의 자연수이다.

출력 조건

입력으로 주어진 수열이 내림차순으로 정렬된 결과를 공백으로 구분하여 출력한다.

입력 예시

3
15
27
12

출력 예시

27 15 12

=>6-10.py 참조
----------------------------------------------------------------
성적이 낮은 순서로 학생 출력하기

N명의 학생 정보가 있다. 학생 정보는 학생의 이름과 학생의 성적으로 구분된다. 각 학생의 이름과 성적 정보가 주어졌을 때 성적이 낮은 순서대로 학생의 이름을 출력하는 프로그램을 작성하시오.

입력
첫 번째 줄에 학생의 수 N이 입력된다. (1<= N <= 100,000)

두 번째 줄부터 N + 1번째 줄에는 학생의 이름을 나타내는 문자열 A와 학생의 성적을 나타내는 정수 B가 공백으로 구분되어 입력된다. 문자열 A의 길이와 학생의 성적은 100 이하의 자연수이다.

출력
모든 학생의 이름을 성적이 낮은 순서대로 출력한다. 성적이 동일한 학생들의 순서는 자유롭게 출력해도 괜찮다.
<입력 예시>
2
홍길동 95
이순신 77

<출력 예시>
이순신 홍길동

=> 6-11.py
----------------------------------------------------------------
두 배열의 원소 교체

동빈이는 두 개의 배열 A와 B를 가지고 있다. 두 배열은 N개의 원소로 구성되어 있으며, 배열의 원소는 모두 자연수이다
동빈이는 최대 K 번의 바꿔치기 연산을 수행할 수 있는데, 바꿔치기 연산이란 배열 A에 있는 원소 하나와 배열 B에 있는 원소 하나를 골라서 두 원소를 서로 바꾸는 것을 말한다

동빈이의 최종 목표는 배열 A의 모든 원소의 합이 최대가 되도록 하는 것이며, 여러분은 동빈이를 도와야한다
N, K, 그리고 배열 A와 B의 정보가 주어졌을 때, 최대 K 번의 바꿔치기 연산을 수행하여 만들 수 있는 배열 A의 모든 원소의 합의 최댓값을 출력하는 프로그램을 작성하라

예를 들어 N = 5, K = 3이고, 배열 A와 B가 다음과 같다고 해보자
배열 A = [1, 2, 5, 4, 3]
배열 B = [5, 5, 6, 6, 5]

이 경우, 다음과 같이 세 번의 연산을 수행할 수 있다
연산 1) 배열 A의 원소 '1'과 배열 B의 원소 '6'을 바꾸기
연산 2) 배열 A의 원소 '2'와 배열 B의 원소 '6'을 바꾸기
연산 3) 배열 A의 원소 '3'과 배열 B의 원소 '5'를 바꾸기
세 번의 연산 이후 배열 A와 배열 B의 상태는 다음과 같이 구성될 것이다
배열 A = [6, 6, 5, 4, 5]
배열 B = [3, 5, 1, 2, 5]
이때 배열 A의 모든 원소의 합은 26이 되며, 이보다 더 합을 크게 만들 수는 없다

입력
첫 번째 줄: N, K 가 공백으로 구분되어 입력 (1 <= N <= 100,000, 0 <= K <= N)
두 번째 줄: 배열 A의 원소들이 공백으로 구분되어 입력 (원소 a < 10,000,000인 자연수)
세 번째 줄: 배열 B의 원소들이 공백으로 구분되어 입력 (원소 b < 10,000,000인 자연수)

출력
최대 K번 바꿔치기 연산을 수행해서 가장 최대의 합을 갖는 A의 모든 원소 값의 합을 출력

=> 6-12.py 참조