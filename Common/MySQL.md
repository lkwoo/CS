## Query Example
``` sql
SELECT ANIMAL_ID, NAME, DATETIME
from ANIMAL_INS
order by NAME asc, DATETIME desc
limit 3


SELECT count(distinct(name))
from ANIMAL_INS
where name is not null -- 'count' don't count null, but just wrote


SELECT NAME, count(NAME) as COUNT
from ANIMAL_INS
where NAME is not null
group by NAME
having count(NAME) > 1
order by NAME


SELECT HOUR(DATETIME), count(*) as count
from ANIMAL_OUTS
where HOUR(DATETIME) >= 9 and HOUR(DATETIME) <= 19
group by HOUR(DATETIME)
order by HOUR(DATETIME) asc


SELECT ANIMAL_TYPE, if(NAME is not null, NAME, "No name") as NAME, SEX_UPON_INTAKE
from ANIMAL_INS
order by ANIMAL_ID


SELECT A.ANIMAL_ID, A.ANIMAL_TYPE, A.NAME
from ANIMAL_INS A join ANIMAL_OUTS B on A.ANIMAL_ID = B.ANIMAL_ID
where A.SEX_UPON_INTAKE != B.SEX_UPON_OUTCOME


SELECT ANIMAL_ID, NAME
from ANIMAL_INS
where (NAME like "%EL%") and(ANIMAL_TYPE = "Dog")
order by NAME


SELECT ANIMAL_ID, NAME, if(SEX_UPON_INTAKE like "%Neutered%" or SEX_UPON_INTAKE like "%Spayed%", "O", "X") as 중성화
from ANIMAL_INS
order by ANIMAL_ID


SELECT ANIMAL_ID, NAME, DATE_FORMAT(DATETIME, "%Y-%m-%d") as 날짜
from ANIMAL_INS
order by ANIMAL_ID
```
