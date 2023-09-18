<h5>Clock</h5>
컴퓨터 부품은 `Clock` 신호에 맞춰 움직인다. `CPU`는 명령어 사이클에 맞추어 명령어를 실행한다. 속도는 $\text{Hz}$로 표기한다. (1초에 몇 번?) 속도가 빠를수록 그만큼 발열이 심하다.

<h5>Clock Cycle</h5>
`CPU`가 명령어를 실행하기 위해 데이터를 가져오고, 해석하고, 실행하는 단계이다.

한 클럭에 걸리는 시간을 `Clock Period`, `Clock Cycle Time`이라 한다.

<h5>Clock Rate</h5>
`CPU`의 초당 클럭 사이클 수를 칭한다. `Clock Frequency`라고도 한다.

<h5>CPI</h5>
`CPI(명령어당 클럭 사이클 수)`는 프로그램의 특정 명령어를 수행하는데 소요되는 평균 클럭 사이클 수이다. `CPU`에 의해 결정되며 명령어에 따라 `CPI`가 다르다.
$$\text{Clock Cycles}=\text{Instruction Count}\times\text{Cycles per Instruction}$$
`Clock Cycles(클럭 사이클 수)`는 명령어의 개수와 명령어당 클럭 사이클 수를 곱하여 계산한다.