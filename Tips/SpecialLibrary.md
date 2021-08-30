
## icecream 
<출처> https://towardsdatascience.com/do-not-use-print-for-debugging-in-python-anymore-6767b6f1866d
- print 대신 사용하며 debugging에 편리
- ic(`variable/object/function`) : variable/object/function 이름과 값을 반환
- ic() : 언제, 몇 번째 줄에서 해당 코드가 실행되었는지 반환
- `ic.disable()`, `ic.enable()` : 사용 해제/ 활성화
- `ic.configureOutput(prefix=' (원하는 값) ' )`: 원래 code는 `ic |` 로 반환하나, `ic` 자리에 `다른 원하는 값`을 넣고 싶을 때 사용할 수 있음

```python
from icecream import ic

# example1
a = 0
ic(a) # print(a)

# example2
if a == 0:
  ic()
else:
  ic()

# icecream 해제/활성화
ic.disable()
ic.enable()

# configureOutput1 - Debug
ic.configureOutput(prefix='Debug | ')

# configureOutput2 - not datetime 
from datetime import datetime
def now():
    return f'[{datetime.now()}] '
    
ic.configureOutput(prefix=now)
ic('test')
```
