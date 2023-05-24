# AiffelEX

# Code Peer Review
- 코더: 장연준
- 리뷰어: 김창완

1. 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
- O, O
-interation 40000기준 Loss값 2933.7164로 ex1번 통과
-ex2번 rmse가 141.223값으로 150이하기때문에 통과  

```python
print("MSE: ",mse)
print("RMSE: ", mse**0.5)
```

2. 주석을 보고 작성자의 코드가 이해되었나요? - O
- 지금까지 했던 과정이라 그런지 주석이 필요한곳에만 달려있다고 생각  
	- 과정에 간략하게 다 적혀져 있어 필요한 곳에 있다고 판단

3. 코드가 에러를 유발할 가능성이 존재? - X
- 1번은 정상적으로 동작 확인  
- 2번은 RMSE binding은 안되어있으나 전체 프로세스에 오류가 걸릴만한 일은 없음

4. 코드 작성자가 코드를 제대로 이해하고 작성했나요 - O
- LEARNING_RATE변수가 대문자인 이유 빼고는 모든 프로세스를 이해
- 나머지는 의견교환시 문제 없었음
- 
5. 코드가 간결한가요? - O
- 현재 그렇게 큰 프로젝트가 아니다보니 주석없이 봐도 문제가 없을 정도로 깔끔
- 오히려 train.drop으로 컬럼떨구는걸 다시 remind가능해서 좋았음

# 코드개선 여부
다만 for i in range(1, 40001)에서 num_interations 변수를 할당해 반복횟수를 정해주는게 좋아보임  
- 오류방지와 유지보수에서 유리  
또한 위에서 지적했듯이 LEARNING_RATE가 기본적으로는 const가 아닌걸로 알고 있음  
- 다음 경사하강법 step 컨트롤 불가, 전체 수렴의 speed가 내려가는 문제, 수렴 지점에서 불필요한 떨림 발생 문제 때문\
- RMSE 바인딩은 필요함
