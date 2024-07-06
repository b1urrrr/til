## inner class 대신 nested class를 사용하자
- inner class는 outer class를 참조하고 있기 때문에, 메모리 누수가 발생 가능
- outer class를 참조해야하는 경우에는 nested class의 인자로 값을 넘겨받아 사용할 것
