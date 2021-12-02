{
    "title": "Bandwidth use cases",
    "linkTitle": "Bandwidth use cases",
    "weight": "230"
}This topic presents three bandwidth scenarios, with suggested unified configuration (UCONF) setting required to implement each of the following use cases:

-   [Limiting overall bandwidth](#Limit)
-   [Prioritizing data transfer](#Prioriti)
-   [Controlling the bandwidth depending on the profile](#Control)

<span id="Limit"></span>

## Limit overall bandwidth

To limit the global bandwidth for all incoming and outgoing connections to, for example 100 KB/s, use the configuration:

```
uconf:cft.server.bandwidth.enable=yes
uconf:cft.server.bandwidth.cos.0.max\_rate\_in=100
uconf:cft.server.bandwidth.cos.0.max\_rate\_out=100
```
<span id="Control"></span>

## Prioritizing data transfer

```
uconf:cft.server.bandwidth.enable=yes
uconf:cft.server.bandwidth.cos=4
uconf:cft.server.bandwidth.cos.1.weight\_in=80
uconf:cft.server.bandwidth.cos.1.weight\_out=80
uconf:cft.server.bandwidth.cos.2.weight\_in=15
uconf:cft.server.bandwidth.cos.2.weight\_out=15
uconf:cft.server.bandwidth.cos.3.weight\_in=5
uconf:cft.server.bandwidth.cos.3.weight\_out=5
```

## Control the bandwidth depending on the profile

Limit the bandwidth on COS1 to 100, COS2 to 50 KB, and COS3 to 25. Note that you can only configure this option directly in Transfer CFT.

```
uconf:cft.server.bandwidth.enable=yes
uconf:cft.server.bandwidth.cos=4
uconf:cft.server.bandwidth.cos.0.max\_rate\_in=-1
uconf:cft.server.bandwidth.cos.0.max\_rate\_out=-1
uconf:cft.server.bandwidth.cos.1.max\_rate\_in=100
uconf:cft.server.bandwidth.cos.1.max\_rate\_out=100
uconf:cft.server.bandwidth.cos.2.max\_rate\_in=50
uconf:cft.server.bandwidth.cos.2.max\_rate\_out=50
uconf:cft.server.bandwidth.cos.3.max\_rate\_in=25
uconf:cft.server.bandwidth.cos.3.max\_rate\_out=25
```
```
CFTSEND id=PROF1, COS=1,…
CFTSEND id=PROF2, COS=2,…
CFTRECV id=PROF3, COS=3,…
```
<span id="Prioriti"></span>

## 

Related topics

-   [Managing bandwidth control](../t_bandwidth)
