# 메모리 단편화
- Memory의 빈 공간은 있지만 할당할 수 없는 상태

## External Fragmentation
- 프로세스 사이 사이의 공간이 애매해서 새로운 프로세스를 올릴 수 없는 상태
- Paging 기법으로 해결 : 가상메모리사용, 외부 단편화 해결, 내부 단편화 존재
    - 보조기억장치를 이용한 가상메모리를 같은 크기의 블록으로 나눈 것이 Page
    - RAM을 페이지와 같은 크기로 나눈 것이 Frame
    - Paging 기법이란 사용하지 않는 Frame을 Page에 옮기고, 필요한 메모리를 Page 단위로 Frame에 옮기는 기법.
    - Page와 Frame을 대응시키기 위해 Page Mapping과정이 필요해서 Paging Table을 만든다
    - Paging 기법을 통해 연속적이지 않은 공간 활용

## Internal Fragmentation
- 할당된 메모리를 충분히 활용하지 않아 남은 빈 공간이 많은 상태
- Segmentation 기법으로 해결 : 가상메모리사용, 내부 단편화 해결, 외부 단편화 존재
    - Segmentation은 가상메모리를 서로 크기가 다른 논리적 단위인 Segment로 분할
    - 각 Segment는 연속적인 공간에 저장
    - Segment들의 크기가 다르기 때문에 미리 분할해 둘 수 없고 메모리에 적재될 때 빈 공간을 찾아 할당한다.
    - Mapping을 위해 Segment Table이 필요(각 Segment 항목별 시작주소와 길이 정보)
    - 프로세스가 필요한 메모리 만큼 할당해주기 때문에 내부단편화 X

