{
    "title": "Bandwidth use cases",
    "linkTitle": "Bandwidth use cases",
    "weight": "250"
}This topic presents three bandwidth scenarios, with suggested unified configuration (UCONF) setting required to implement each of the following use cases:

-   [Limiting overall bandwidth](#limit)
-   [Prioritizing data transfer](#prioriti)
-   [Controlling the bandwidth depending on the profile](#control)

## <span id="Limit"></span>Limit overall bandwidth

To limit the global bandwidth for all incoming and outgoing connections to, for example 100 KB/s, use the configuration:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>uconf:cft.server.bandwidth.enable=yes<br/>uconf:cft.server.bandwidth.cos.0.max_rate_in=100<br/>uconf:cft.server.bandwidth.cos.0.max_rate_out=100         </td>
      </tr>
   </tbody>
</table>

## <span id="Control"></span>Prioritizing data transfer

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>uconf:cft.server.bandwidth.enable=yes<br/>uconf:cft.server.bandwidth.cos=4<br/>uconf:cft.server.bandwidth.cos.1.weight_in=80
<br/>uconf:cft.server.bandwidth.cos.1.weight_out=80
<br/>uconf:cft.server.bandwidth.cos.2.weight_in=15
<br/>uconf:cft.server.bandwidth.cos.2.weight_out=15
<br/>uconf:cft.server.bandwidth.cos.3.weight_in=5
<br/>uconf:cft.server.bandwidth.cos.3.weight_out=5         </td>
      </tr>
   </tbody>
</table>

## Control the bandwidth depending on the profile

Limit the bandwidth on COS1 to 100, COS2 to 50 KB, and COS3 to 25. Note that you can only configure this option directly in Transfer CFT.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>uconf:cft.server.bandwidth.enable=yes<br/>uconf:cft.server.bandwidth.cos=4<br/>uconf:cft.server.bandwidth.cos.0.max_rate_in=-1<br/>uconf:cft.server.bandwidth.cos.0.max_rate_out=-1<br/>uconf:cft.server.bandwidth.cos.1.max_rate_in=100<br/>uconf:cft.server.bandwidth.cos.1.max_rate_out=100<br/>uconf:cft.server.bandwidth.cos.2.max_rate_in=50<br/>uconf:cft.server.bandwidth.cos.2.max_rate_out=50<br/>uconf:cft.server.bandwidth.cos.3.max_rate_in=25<br/>uconf:cft.server.bandwidth.cos.3.max_rate_out=25</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTSEND id=PROF1, COS=1,…<br/>CFTSEND id=PROF2, COS=2,…<br/>CFTRECV id=PROF3, COS=3,…         </td>
      </tr>
   </tbody>
</table>

## <span id="Prioriti"></span>

Related topics

-   [Managing bandwidth control](../t_bandwidth)
