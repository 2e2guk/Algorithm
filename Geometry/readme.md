# 계산 기하 알고리즘 #

-> 계산 기하 라는 분야는, 기하학적인 문제를 컴퓨터로 해결하는 영역이다. 항상 ㅈ같은 부동소수점 오차와 함께 한다.^^

## CCW(외적) ##

-> 고등학교 때 기하와 벡터를 배운 사람이라면(저는 연배가 좀 있어서 배웠습니다), 평면벡터의 내적에 대해 알고 있을 것이다. 그런데 이제 어떤 선생님들은 흑마법인 외적에 대해서 알려주곤 하셨다. 

주요 사용처는, 삼각형의 넓이를 구할 때였다. (외적의 크기) / 2는 삼각형의 넓이였다.(혹은 이걸 "신발끈 공식" 으로 알고 계신 분들도 계실 거다)

여튼, 이런 외적은, 계산 기하 영역에서, **세 개의 점의 위치 관계를 파악**할 때 많이 사용한다. 외적값의 부호를 주로 많이 사용하는데, 주의할 점은, 외적은, **계산 순서에 따라서 결괏값이 달라진다는 것이다**(교환법칙이 성립하지 않음)

외적값의 부호를 판단하는 것은 쉽다. 그냥 두 벡터 a, b에 대해서, a X b를 계산해야 한다면, a->b방향으로, 오른손의 네 손가락을 감고, 엄지 방향이 가리키는 곳이 위쪽이면 +, 아래쪽이면 -이다. 

여튼, 이렇게 구한 외적값의 부호가

**양수인 경우** : 반시계 방향으로 점들이 배열되어 있다. 

**음수인 경우** : 시계 방향으로 점들이 배열되어 있다. 

본인은 기하와 벡터 학습자이기에, 평면벡터, 위치벡터 이런 말들에 대해 이미 배웠기에, 만약 자신이 기하와 벡터를 배우지 않았다면, 벡터에 대해서 공부해 보는 것을 추천한다. 


