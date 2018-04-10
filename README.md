# http4s HttpApp vs HttpStream benches

Two bench types, where RPS = Requests per second:

10 seconds of 50k RPS
60 seconds of 50k RPS

Test code and JARs available [here](https://github.com/jmcardon/IOPort/tree/httpstream)

Assembled using sbt-assembly and ran with `nohup java -jar <jarname> &` on amazon m4.4xlarge machine, dedicated instance for both server and test machine, using gatling.

## HttpStream benches
1. 10s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpstream_test1/)
    2. [link](https://josecardona.ca/gatling/httpstream_test2/)
    3. [link](https://josecardona.ca/gatling/httpstream_test3/)
1. 60s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpstream_longtest1/)
    2. [link](https://josecardona.ca/gatling/httpstream_longtest2/)

## HttpApp benches
1. 10s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpapp_test1/)
    2. [link](https://josecardona.ca/gatling/httpapp_test2/)
    3. [link](https://josecardona.ca/gatling/httpapp_test3/)
1. 60s 50k RPS
    1. [link](https://josecardona.ca/gatling/httpapp_longtest1/)
    2. [link](https://josecardona.ca/gatling/httpapp_longtest2/)
