# http4s HttpApp vs HttpStream benches

Two bench types, where RPS = Requests per second:

10 seconds of (Attempted) 50k RPS
60 seconds of (Attempted) 50k RPS

Test code and JARs available [here](https://github.com/jmcardon/IOPort/tree/httpstream)

Assembled using sbt-assembly and ran with `nohup java -jar <jarname> &` on amazon m4.4xlarge machine, dedicated instance for both server and test machine, using gatling.

## HttpStream benches

1. 60s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpstream_longtest1/)
    2. [link](https://josecardona.ca/gatling/httpstream_longtest2/)
2. 10s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpstream_test1/)
    2. [link](https://josecardona.ca/gatling/httpstream_test2/)
    3. [link](https://josecardona.ca/gatling/httpstream_test3/)
    
### Stats for 60s for HttpStream

```
Executions
            Total   OK      KO
            3000000 3000000 0
Mean req/s  46875   46875   -

Response Time (ms)
                Total   OK      KO
Min             0       0       -
50th percentile 88      88      -
75th percentile 226     226     -
95th percentile 1686    1686    -
99th percentile 2239    2240    -
Max             14558   14558   -
Mean            257     257     -
Std Deviation   500     500     -
```
```
Executions
            Total       OK          KO
            3000000     3000000     0
Mean req/s  47619.048   47619.048   -

Response Time (ms)
                Total   OK      KO
Min             0       0       -
50th percentile 72      72      -
75th percentile 174     174     -
95th percentile 1125    1126    -
99th percentile 1854    1854    -
Max             7957    7957    -
Mean            184     184     -
Std Deviation   364     364     -
```

## HttpApp benches

1. 60s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpapp_longtest1/)
    2. [link](https://josecardona.ca/gatling/httpapp_longtest2/)
2. 10s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpapp_test1/)
    2. [link](https://josecardona.ca/gatling/httpapp_test2/)
    3. [link](https://josecardona.ca/gatling/httpapp_test3/)
    
### Stats for 60s for HttpApp
    
```
Executions
            Total   OK          KO
            3000000     3000000     0
Mean req/s  49180.328   49180.328   -

Response Time (ms)
                Total       OK      KO
Min             0	    0	    -
50th percentile	4	    4	    -
75th percentile	6	    6	    -
95th percentile	77	    77	    -
99th percentile	265	    265	    -
Max	        3178	    3178    -
Mean	        17	    17	    -
Std Deviation	57	    57	    -
```
```
Executions
            Total       OK          KO
            3000000     3000000     0
Mean req/s  49180.328   49180.328   -
Response Time (ms)
                Total   OK      KO
Min             0       0       -
50th percentile 3       3       -
75th percentile 5       5       -
95th percentile 53      53      -
99th percentile 216     216     -
Max             3025	3025    -
Mean            13      13      -
Std Deviation   48      48      -
```
    
## TL;DR

Most important tests are the four 60s 50k RPS tests.

HttpApp improves throughput by >2k RPS and has less outliers. In general, it seems to have more stable results with
a lower variance and spread, with a significantly worse worst-case, but only a very small amount of responses.


