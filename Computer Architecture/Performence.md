<h5>Responce Time</h5>
일을 수행하는 데 얼마나 걸리는가?

<h5>Throughput</h5>
단위 시간 당 총 작업량

<h5>Define Performance</h5>
$$\text{Performence} = \frac{1}{\text{Excution Time}}$$

<h5>CPU Time</h5>
전반적인 시스템의 시간 측정에는 `Elapsed Time(경과 시간)`이 쓰인다. 이는 `Processing(처리)`, `I/O(입출력)`, `OS overhead(운영체제 처리)`, `Idle time(대기 시간)` 등의 모든 요인을 고려한 총 `Responce Time`이라고 말할 수 있다.

`CPU Time`은 주어진 일을 처리하는 데 걸리는 시간이다. 순수한 `CPU`의 성능에 주목한다. 그러므로 위의 수많은 요소들을 배제한다.

그럼 `CPU Time`은 어떻게 구할까? [[Clock]] 개념이 필요하다.

$$\begin{align*} \text{CPU Time}&= \text{CPU Clock Cycles}\times \text{Clock Cycle Time} \\ &= \frac{\text{CPU Clock Cycles}}{\text{Clock Rate}}\end{align*}$$

성능 향상을 위해선 다음과 같은 일을 수행해야 한다.
* Reducing number of Clock Cycles
* Incresing Clock Rate(Clock Frequency)

Hardware designer must often trade off clock rate against cycle count.