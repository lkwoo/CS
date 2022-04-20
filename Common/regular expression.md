### python

##### 단순 문자열 매칭
``` python
import re

text = "hello, world!"
p = "world"   
m = re.findall(p, text) # text에서 p와 매칭되는 결과를 리스트 형식으로 반환
```

##### 컴파일
``` python
import re

text = "I am a boy"
p = re.compile("am") # 이렇게 패턴을 미리 따놓으면 재사용이 쉽다.

m1 = p.findall(text))
m2 = re.findall("am", text)) # m1과 m2는 동일
```

##### 메타문자
```
- ^	문자열의 시작
- $	문자열의 끝
- |	or 
- []	문자 클래스	대괄호 [] 안에 들어있는 문자 중 하나라도 일치하면 매치합니다.[abc]는 ‘a,b,c’ 중 하나와 매칭됩니다.
- \d	숫자를 나타냅니다.	
- \D	숫자가 아닌 모든 문자를 나타냅니다.	
- \w	알파벳 대소문자, 숫자, 밑줄(_)을 나타냅니다.	
- \W	\w에 해당되지 않는 문자들을 나타냅니다.	
- \s	공백, 탭 문자와 매칭됩니다.	
- \S	\s에 매칭되지 않는 모든 문자를 나타냅니다.	
- \n	개행 문자를 나타냅니다.	
- \	이스케이프용 문자. 특별한 의미를 나타내는 기호를 문자 그대로 나타내려고 할 때 사용합니다.	문자열 내에서 $문자를 찾기 위해서는 \$와 같이 나타내어야 합니다.
- .	모든 문자와 대응되는 기호입니다.
```

##### 수량자
```
- *	 0개 이상	cat*는 'ca', 'cat', 'catt', 'cattttttt' 등과 매칭
- +	 1개 이상	*와 달리 해당 문자가 최소 1개 이상일 때 매칭
- ?	 0개 또는 1개 cat?는 'ca', 'cat'와 매칭
- {n}	n개	\d{2}은 55, 19 등 두 자릿수와 매칭
- {n, m}	n개 이상, m개 이하	\w{3, 5}는 알파벳 3~5 자리의 단어와 매칭
- {n,}	n개 이상	s{2,}는 s가 최소 2개 이상 연속된 경우에 매칭
```

##### 예시
``` python
import re

p = "^hello"    # hello로 시작해야 매치
m = re.findall(p, "hello worold, hello")

p = "hello$"    # hello로 끝나야 매치
m = re.findall(p, "hello worold, hello")

p = "apple|banana"   # apple 또는 banana가 포함되면 매치
m = re.findall(p, "I like apple and banana")

# ^ 메타 문자는 문자열의 시작이란 의미였지만, [] 대괄호 안에서는 not의 의미입니다.
p1 = "a|e|i|o|u"     # 알파벳 모음에 매치
p2 = "[aeiou]"     # 상동
p3 = "[^aeiou]"     # 알파벳 모음이 아닌 문자에 매치

m1 = re.findall(p1, "Hello World, have a good day!")
m2 = re.findall(p2, "Hello World, have a good day!") # m1과 동일
m3 = re.findall(p3, "Hello World, have a good day!")

# 범위지정
p1 = "[0-9]"     # 숫자와 매칭. 코드 작은거 먼저 써야함( 9-0 ㄴㄴ)
p2 = "[a-z]"     # 알파벳 소문자와 매칭

m1 = re.findall(p1, "asdf 7890 2348")
m2 = re.findall(p2, "asdf 7890 2348")

# 모든 문자 매칭
p = "d.g"
m = re.findall(p, "dog dig dug dg drg dgg d g") # d로 시작 g로 끝나는 문자 매칭. 공백도 포함

# 대소문자 구분
p = "(?!)abcd" # abcd AbcD 등 대소문자 구분 안 하고 매칭


```
