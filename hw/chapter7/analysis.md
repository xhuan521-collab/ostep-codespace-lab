# Chapter 7 CPU Scheduling Analysis
## Q1 Workload: -l 100,200,300
### Prediction
- FIFO: Avg Turnaround ≈333.33; Avg Response≈133.33
- SJF: Avg Turnaround ≈333.33; Avg Response≈133.33
Observation: When jobs arrive at exactly same time, SJF produces same result as FIFO.

### Simulator observation
[Paste your terminal output from q1_fifo.txt and q1_sjf.txt]

## Q2 Workload: -l 300,200,100
### Prediction
- FIFO: Avg Turnaround≈466.67; Avg Response≈266.67
- SJF: Avg Turnaround≈333.33; Avg Response≈133.33
Observation: FIFO suffers convoy effect. Long job runs first and delays short jobs. SJF picks shortest job regardless input order and gives better turnaround.

### Simulator observation
[Paste output q2_fifo.txt q2_sjf.txt]

## Q3 RR different quantum (-l 100,200,300)
### Prediction
1. quantum=10: Very good response time, poor turnaround time. Frequent context switch.
2. quantum=100: Middle case. Response remains low, turnaround improves compared to q=10.
3. quantum=1000: RR behaves exactly like FIFO. Response becomes worse; turnaround matches FIFO result.

Key rule for RR: Small quantum → better response, worse turnaround; Large quantum converges to FIFO.

### Simulator observation
[Paste outputs q3_rr_q10.txt q3_rr_q100.txt q3_rr_q1000.txt]

## Q4 When to choose SJF vs RR
- SJF: Batch‑processing workloads. Optimize for turnaround time. Job run‑times known in advance. Not good for interactive response.
- RR: Interactive / time‑sharing systems. Prioritize low response time for every job. Job runtime unknown. Trade‑off: higher average turnaround time.

## Q5 Convoy Effect
Convoy effect occurs under FIFO scheduling: few long CPU‑bound jobs occupy CPU, many short jobs wait behind them, degrading average turnaround time.
Mitigation: Use SJF / preemptive scheduling like RR or SRJF. FIFO cannot avoid convoy effect.

## Formula
- Turnaround Time = Completion Time − Arrival Time
- Response Time = First‑Run Time − Arrival Time
- Wait Time = Turnaround Time − Job CPU burst length