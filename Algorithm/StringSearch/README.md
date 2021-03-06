# 문자열 알고리즘

## 패턴 검색 알고리즘

- 문자 하나하나씩 비교하는 알고리즘

## 라빈-카프 알고리즘

- 문자열 검색을 위해 해시 값 함수를 사용하는 알고리즘
- 패턴의 해시 값과 본문 속 문자열 해시 값만을 비교한다.
- 최악의 시간복잡도는 **O(MN)**이지만 **평균적으로는 빠른 속도**를 가진다.

### 패턴의 해쉬값을 계산하기

- 각 자리의 숫자에 자리값을 곱하여 더한다.
- 4321은 문자열이 아닌 정수 4321가 된다.
- 이전의 해쉬값이 틀리면 맨 앞자리수를 빼고 다음 숫자를 맨 뒤로 넣는다. (**sliding window 기법**)
- 문자열의 길이가 커지면 길이를 일정자리수로 맞추기 위해 mod 연산을 취하지만, 해쉬값만 일치하고 문자열이 일치하지 않을 수 있어 다시 문자열 일치를 검사해야한다.
- 문자열의 길이가 커지면 길이를 일정자리수로 맞추기 위해 mod 연산을 취하지만, 해쉬값만 일치하고 문자열이 일치하지 않을 수 있어 다시 문자열 일치를 검사해야한다.

## 보이어-무어 알고리즘

- 오른쪽에서 왼쪽으로 비교(끝쪽부터 비교하기)
- 몇칸을 이동할 지 미리 계산해놓고 오른쪽 끝 문자가 일치하면 계산한 칸만큼 이동
- 나쁜문자와 착한접미사를 모두 사용해야 보이어 무어 알고리즘을 제대로 사용 가능
- 불일치가 된 문자열이 패턴에 포함된 문자열이면 skip 배열을 통해 끝을 맞추기

### skip 배열

- (패턴문자열의 길이 -1) - 각 패턴문자의 인덱스

## KMP 알고리즘

- 불일치가 발생한 텍스트 문자열의 앞부분에 어떤 문자가 있는지 미리 알고있으므로, 확인한 문자열을 제외하고 그 뒤부터 비교하는 문자열 알고리즘
- 본문 포인터는 두고, 패턴 포인터를 움직이면서 일치했던 부분은 제외하고 확인한다.
- 패턴을 이용해서 부분일치 테이블을 작성한다. → 매칭이 실패하면 패턴 포인터가 돌아갈 곳 계산한다.
- 대부분의 ctrl + F 는 KMP 알고리즘을 사용하여 구현되는 경우가 많다.
