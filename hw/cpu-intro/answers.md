# cpu-intro Q1‑Q8 Answers
Command: ./process-run.py -l 5:100,5:100

## Q1
Prediction: A A A A A B B B B B
Actual:
Time 0‑4: run A
Time 5‑9: run B
Explanation: Both processes are CPU‑intensive with no I/O. Process A runs to completion first, then process B runs to completion. Total time 10 time units.

## Q2
Prediction: 1 context switch
Actual: 1 context switch
Explanation: Only one switch when A finishes and switches to B.

## Q3 Turnaround time A
Prediction: 5
Actual: 5
Explanation: A starts at time 0 and finishes at time 4; turnaround = 5.

## Q4 Turnaround time B
Prediction: 10
Actual: 10
Explanation: B arrives at time 0, finishes at time9; turnaround =10.

## Q5 Average turnaround time
Prediction: (5 + 10) / 2 = 7.5
Actual: 7.5
Explanation: Average of turnaround time of process A and B.

## Q6 Response time A
Prediction: 0
Actual: 0
Explanation: Process A gets CPU immediately at time 0, no waiting.

## Q7 Response time B
Prediction:5
Actual:5
Explanation: B is ready at time 0 but first runs at time 5; response time = 5.

## Q8 Average response time
Prediction: (0 +5)/2 =2.5
Actual:2.5
Explanation: Average response time of A and B.