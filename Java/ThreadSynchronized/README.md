# Synchronized
Synchronized는 한국어로 동기화라고 불리며 한정된 자원을 두고 작업들 간의 작업 순서를 정하는 것을 말합니다.
작업 순서는 상호배제(Mutex)와 협동(Cooperation) 개념을 사용하여 순서를 정합니다.

Synchronized를 적용하면 lock이 걸리는데 Implicit lock과 Explicit lock으로 나누어집니다.


## Implicit lock
Implicit lock은 public synchronized void add(){} 처럼 synchronized 키워드를 사용하면 JVM에서 synchronized을 읽고 해당 객체에 Monitor 상호배제 방식을 자동으로 적용해줍니다. JVM이 객체가 가지고 있는 객체 헤더의 Mark Word를 이용하여 상호배제를 합니다.

**단점**
으로는 JVM이 자동으로 상호배제를 해주기 때문에 작업 순서를 조절할 수 없어 Thead의 접근성에 대한 공평성에 문제가 발생할 수 있습니다.
이를 해결하기 위해 Java에서 java.util.concurrent.lock 클래스르 제공하여 구체적인 부분들을 조작할 수 있는 lock 방식을 제공해줍니다. 이를 Explicit lock이라고 불립니다.

## Explicit lock

