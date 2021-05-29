# Cache
### Cache란?
Localty를 활용해 컴퓨터의 효율을 증대시키는 임시 저장 공간 혹은 기술.  
Memory Hierarchy에서 k Level과 K+1 Level의 관계에 Cache의 개념이 적용됨.  ex) CPU Reg <-> Cache, Cache <-> RAM, RAM <-> Local Disk
  
##### Localty란?  
- Tempolar Localty : 한 번 접근한 데이터는 빠른 시간 내에 다시 접근할 확률이 높은 성질  
- Spatial Localty : 접근한 데이터의 인접한 영역에 저장된 데이터도 사용할 가능성이 높은 성질

### Hit or Miss
- Cache Hit : 필요로 하는 데이터가 Load 되어 있다.
- Cache Miss : 필요로 하는 데이터가 Load 되어 있지 않다.(찾아와야 한다)

