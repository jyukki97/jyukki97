# [백준]2493 탑


https://www.acmicpc.net/problem/2493

# 풀이:

현재 탑의 높이보다 더 높은 위치에 있는 탑을 찾아야 하므로 스택을 이용하도록 한다.

탑의 맨 오른쪽 부터 계산을 시작한다.

현재 위치에 탑의 높이가 스택의 top에 있는 탑의 높이보다 높다면, 스택의 top을  pop 하고, 그 탑의 수신탑의 위치값을 현재 탑의 위치로 바꿔준다.

스택의 top의 있는 탑의 높이가 현재 위치의 탑의 높이보다 작거나 같을 때까지 반복하고,

스택에 현재 탑을 push해준다.



왼쪽 끝까지 모든 탑을 확인했다면, 수신탑의 위치값을 출력해준다. 만약 수신탑을 찾지 못한 탑들은 0으로 출력한다.



# **코드:** 

사용언어 :  python

```python
n,a,s=int(input()),[10**9]+list(map(int,input().split())),[0]
c=['0']*n
for i in range(n,0,-1):
    while a[s[-1]]<a[i]:
        c[s[-1]-1]=str(i)
        s.pop()
    s+=[i]
print(" ".join(c))
```