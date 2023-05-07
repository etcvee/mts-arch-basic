| Конфигурация              | Latency, ms (без кеша) | Latency, ms (с кешом) | Req/s (без кеша) | Req/s (с кешом) |
| ------------------------- | ---------------------- | --------------------- | ---------------- | --------------- |
| 1 thread / 1 connection   | 13.89                  | 6.15                  | 268.29           | 521.28          |
| 10 thread / 10 connection | 36.27                  | 14.46                 | 279.66           | 809.39          |
| 50 thread / 50 connection | 0                      | 118.65                | 0                | 0.20            |

<pre>
[parallels@fedora module_06]$ ./start.sh
without cache
Running 1m test @ http://localhost:8081/
  1 threads and 1 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     7.57ms   13.89ms 276.81ms   89.05%
    Req/Sec   270.87     72.80   414.00     65.76%
  Latency Distribution
     50%    2.74ms
     75%    3.57ms
     90%   23.45ms
     99%   47.21ms
  16120 requests in 1.00m, 4.60MB read
Requests/sec:    268.29
Transfer/sec:     78.34KB
Running 1m test @ http://localhost:8081/
  10 threads and 10 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    36.27ms   17.56ms 173.25ms   77.98%
    Req/Sec    28.07      9.47   140.00     71.02%
  Latency Distribution
     50%   29.77ms
     75%   40.97ms
     90%   66.56ms
     99%   85.13ms
  16805 requests in 1.00m, 4.78MB read
Requests/sec:    279.66
Transfer/sec:     81.41KB
Running 1m test @ http://localhost:8081/
  50 threads and 50 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     0.00us    0.00us   0.00us    -nan%
    Req/Sec     0.00      0.00     0.00      -nan%
  Latency Distribution
     50%    0.00us
     75%    0.00us
     90%    0.00us
     99%    0.00us
  0 requests in 1.00m, 0.00B read
Requests/sec:      0.00
Transfer/sec:       0.00B
</pre>

<pre>[parallels@fedora module_06]$ ./start.sh
with cache
Running 1m test @ http://localhost:8082/
  1 threads and 1 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     6.15ms   11.53ms 137.19ms   87.46%
    Req/Sec   525.76    154.39   820.00     63.96%
  Latency Distribution
     50%    1.39ms
     75%    1.84ms
     90%   23.43ms
     99%   46.70ms
  31317 requests in 1.00m, 8.84MB read
Requests/sec:    521.28
Transfer/sec:    150.68KB
Running 1m test @ http://localhost:8082/
  10 threads and 10 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    14.46ms   11.73ms 153.83ms   83.43%
    Req/Sec    81.61     33.85   450.00     83.30%
  Latency Distribution
     50%   11.09ms
     75%   13.88ms
     90%   31.31ms
     99%   55.84ms
  48626 requests in 1.00m, 13.93MB read
Requests/sec:    809.39
Transfer/sec:    237.36KB
Running 1m test @ http://localhost:8082/
  50 threads and 50 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   118.65ms   15.12ms 133.41ms   83.33%
    Req/Sec     5.08      2.31    10.00     83.33%
  Latency Distribution
     50%  123.05ms
     75%  124.36ms
     90%  133.14ms
     99%  133.41ms
  12 requests in 1.00m, 3.50KB read
Requests/sec:      0.20
Transfer/sec:      59.66B
</pre>