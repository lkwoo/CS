# Cache
### Cache란?
Localty를 활용해 컴퓨터의 효율을 증대시키는 임시 저장 공간 혹은 기술.  
Memory Hierarchy에서 k Level과 K+1 Level의 관계에 Cache의 개념이 적용됨.  ex) CPU Reg <-> Cache, Cache <-> RAM, RAM <-> Local Disk
  
##### Localty란?  
- Temporal Localty : 한 번 접근한 데이터는 빠른 시간 내에 다시 접근할 확률이 높은 성질  
- Spatial Localty : 접근한 데이터의 인접한 영역에 저장된 데이터도 사용할 가능성이 높은 성질

### Hit or Miss
- Cache Hit : 필요로 하는 데이터가 Load 되어 있다.
- Cache Miss : 필요로 하는 데이터가 Load 되어 있지 않다.(찾아와야 한다)

### Type of Miss
- Cold Miss : 데이터를 처음 사용하는 경우 보통은 Load 되어 있지 않다. 누구에게나 처음은 있는 법.
- Conflict Miss : Fully Associative Mapping 방식이 아닐 때, (특히 Direct Mapping 방식일 때)사용되는 데이터보다 Cache의 공간이 큼에도 Cache의 일부만을 사용해 불필요한 Miss가 발생한다. 비유하자면 바지에 주머니가 여러 갠데 강박증으로 인해 하나만 사용한다. 근데 물건을 두 개라서 하나는 꼭 손에 쥐고 다닌다.   
그럼 Fully Associative 방식을 쓰면 되지 않나요? 그럼 Cache 자체가 느려집니다. 또 전력 소비도 커집니다.
- Capacity miss : 필요한 데이터의 용량이 Cache 보다 큰 경우.  
그럼 Cache의 크기를 키우면 되지 않나요? 그럼 Cache 자체가 느려집니다. 또 전력 소비도 커집니다.
