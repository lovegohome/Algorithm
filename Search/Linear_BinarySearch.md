# 알고리즘이란?

> 문제를 해결하려고 하는데, 어떻게 해결하면 좋을까를 고민
> 그래서 그 해결과정을 단계적으로, step by step으로 진행하는 방법을 안내. 
>
> 직관적으로 설명하면, 입력에서 출력까지의 중간 과정을 알고리즘 이라고 한다.
> 그 중간에 정렬, 재귀, 검색 등의 알고리즘이 있다. 
> code로는 for문, 비교.
>
> 입력 = value, index
> 출력 = 어디에 있는지, index
>
> 어떻게 찾아야 빨리 찾을 수 있을까? 
> [ 시간, 비용 ]을 고려한 알고리즘 비교
> 비교도 컴퓨터 입장에서 하나의 연산이다.  



## 1. Search

> 검색 알고리즘 = 내가 원하는 데이터를 찾는 방법

**- 종류는?**

1. **linear Search**
   선형검색, 순차검색, Sequential Search, 차례대로 검색한다는 뜻
   출력 : 위치 정보(index)
2. **Binary Search**
   이진검색
   출력 : 위치 정보(index)
3. **Hash**
   출력 : 내가 원하는 데이터를 찾는다. 



## 2. Linear Search

```python
def search(array, key):				# list, key = 찾으려는 값

	for i in range(array):			# 리스트에서 for
		if list1[i] == key:			# 찾으려는 값이 리스트 안의 값과 같다면
			return i				# 그 값의 리스트 index 반환

array1 = ['a', 'b', 'c', 'd']
key = 'c'

print(search(array1, key))
```



> 실행횟수 몇 번 등이 중요한 게 아니라, 
> 코드에서  무엇이 중요한가 위주로 보자. 
>
> 위의 코드에서 **가장 중요한 부분, 가장 힘을 들인 곳은?**
> **[ list1[i] == key: ]**
> 이렇게 Sequential Search는 compare, 비교하는 것에 가장 큰 힘을 들이고 있다.. 

> +복잡도
>
> 그 결과 값을 구하는데까지 
> 최소로 든 시간 복잡도 = O(1), 한 번에 찾는 것
> 최악으로 든 시간 복잡도 = O(n), n번째, 맨 마지막에 찾는 것. 
>
> 즉, linear search의 최악의 경우 시간 복잡도 = O(n)



## 3. Complexity, 복잡도

1. Time Complexity( 시간 복잡도 ) : 
   실행하는데 필요한 시간 ( 처리 시간 )
   얼마나 연산을 적게 하는가. 시간 효율성 
2. space complexity( 공간 복잡도 ) : 
   메모리 ( 기억 공간 )와 파일 공간
   컴퓨터 메모리를 얼마나 적게 먹는가. 

> * 위의 __복잡도가 낮은 알고리즘__이 좋은 알고리즘이다.
>
> * 어떤 과정을 처리하는데 __처리 시간이 짧을수록__, 컴퓨터의 __메모리를 적게 사용할수록__ 좋은 알고리즘

### - Big-O notation

- 알고리즘의 Time Complexity는 주로 Big-O notation을 사용하여 나타낸다.
- 어떠한 문제를 해결 하기 위한 방법은 다양하기 때문에 ***방법(알고리즘) 간에 효율성을 비교***하기 위해 **빅오(big-O) 표기법**을 보통 가장 많이 사용한다. 

* 빅-오 표기법 특징

  * ![img](https://t1.daumcdn.net/cfile/tistory/999AF63E5C7EB21A1D) 

  * ![img](https://t1.daumcdn.net/cfile/tistory/9907BB4F5C7EB2CD02) 

    = 힘이 가장 쌘 애만 남고 나머지는 무시

    (참고로, n이 매우 큰 숫자라는 것을 가정한다.)

    

    ex-1. 
    그러면 이 2가지 경우 중 어떤 게 시간 복잡도가 클까? 
    빅오표기법으로 보면
    $$
    f(n) = n^2+2n+3
    $$

    $$
    g(n) = n^2
    $$

     이렇게 둘 다 똑같다.
    $$
    O(n^2)
    $$
    그렇기 때문에 빅오표기법은 가장 큰 차수가 뭔지만 비교하면 된다. 

    

    ex-2. 
    이 두 가지도 동일하다. 가장 큰 차수의 계수도 신경 안 쓴다.
    $$
    f(n) = 2n^2	-> O(n^2)
    $$

    $$
    g(n) = n^2	-> O(n^2)
    $$

    

  * 시간복잡도가 크다 = 차수(order)가 크다. 

    ​								= 비효율적이다. 

   

* 알고리즘의 성능평가 : 최선, 최악, 평균 유형(best, worst, average case)
  그 중 **최악의 경우**로 알고리즘 성능을 파악한다.

 <img src="Algorithm.assets/image-20210620014835679.png" alt="image-20210620014835679" style="zoom:67%;" /> 

- 따라서, 가장 효율 좋은 건 초록색 O(1)
- 가장 효율이 안 좋은 건 O(2^n)
  - linear search의 시간 복잡도 = O(n)
  - binary search의 시간 복잡도 = O(log n)

<img src="Algorithm.assets/image-20210620015250245.png" alt="image-20210620015250245" style="zoom: 67%;" /> 
 :icecream: 중요! 
이건 sort에서 복잡해질 거기 때문에 잘 알아둬야 함. 

<img src="Algorithm.assets/image-20210620020240917.png" alt="image-20210620020240917" style="zoom:67%;" />





## 4. Binary Search

- linear search의 최악의 시간 복잡도를 대신할 효율적인 알고리즘

- 이진검색, sequence형을 둘로 나눠서 검색하는 알고리즘 

- 꼭 **정렬(sort)**가 되어 있어야 한다. 

   **ex** ) list2 = [11, 12, 13, 14, 15, **16**, 17, 18, 19, 20, 21]
  가운데 index를 계산하는 방법 = ( 맨 왼쪽의 index + 맨 오른쪽의 index) / 2 )
  cf. 홀수개일 땐 가운데가 2개. 그 중 왼쪽 index부터 체크.

  - 이 때, 최소의 경우 = 1회. 

  - 최악의 경우는? 4번 
    $$
    log_2 n
    $$

  binary search는 반을 계속 날리는 방식이라 위의 식과 같다. 
  증명 참조: https://jwoop.tistory.com/9

- 

```python
def BinarySearch(array, key, low, high)
	if low > high:		# 예외 처리
         return false # 맨 끝까지 찾았는데도 못 찾은 경우

	mid = (low+high) / 2  # 나눈 몫.

	if value < array[mid]: # 찾는 값이 가운데 기준 왼쪽 
		return binarySearch(array, value, low, mid-1)
	elif array[mid] < value: # 찾는 값이 가운데 기준 오른쪽 
		return binarySearch(array, value, mid+1, high)
    else:
		return mid
```

- 이 함수의 특징: 재귀함수, 
  계속해서 구간을 다르게 하면서 자기 함수를 콜한다. 

  > **binary search**는 **재귀함수**로 이루어져 있다. 
  >
  > 후에 재귀 알고리즘 나올 거라 기억하자. 

- Binary Search의 최악의 경우 Time Complexity

  : O(n) = log(n)



## 5. Compare

> Binary vs Linear 

- 비교의 입장에서 보면 최소는 동일. 
- 그러나 최악의 경우에는 binary가 유리
- 기본적인 차이점은,
  `Linear Search` : 정렬이 되든, 안되든 상관이 없다. 한 쪽에서부터 **순차적**으로 같은지만 확인한다.
  `Binary Search` : 필수적으로 **정렬**이 되어 있는 상태이어야 한다.



# cf. 참고사항

- 코드를 실제로 구현해보자. 외우는 것이 아니라 이렇게 나오는 구나를 직접 보고 실험해보기 
- 

![bigO notation](Algorithm.assets/bigO notation.png)



![image-20210620022414023](Algorithm.assets/image-20210620022414023.png)



출처 및 참고 ]

1. https://github.com/GyungBin-Park
2. https://jwoop.tistory.com/9
3. https://mangkyu.tistory.com/102 
4. https://noahlogs.tistory.com/27 

