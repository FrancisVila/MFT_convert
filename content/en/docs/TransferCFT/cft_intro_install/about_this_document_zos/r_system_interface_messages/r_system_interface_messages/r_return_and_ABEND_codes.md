{
    "title": "Return and ABEND codes",
    "linkTitle": "Return and ABEND codes",
    "weight": "250"
}The following table summarizes the major return codes or ABEND codes used by the Transfer CFT z/OS system interface.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">For all ABEND codes, contact the Customer Support Service.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Module</p></th>
         <th>            <p>Type</p></th>
         <th>            <p>Dec.</p></th>
         <th>            <p>Hex.</p></th>
         <th>            <p>Explanation</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>SGFBSAM</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0001</p>         </td>
         <td>            <p>00000001</p>         </td>
         <td>            <p>BCD/File buffer incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGF3C</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0011</p>         </td>
         <td>            <p>00000017</p>         </td>
         <td>            <p>BCF incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SERURG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0091</p>         </td>
         <td>            <p>0000005B</p>         </td>
         <td>            <p>Unexpected TCP error detected</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>MEMCOPY<span> </span></p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0204</p>         </td>
         <td>            <p>000000CC</p>         </td>
         <td>            <p>memcpy/memmove function error</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKWAIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0257</p>         </td>
         <td>            <p>00000101</p>         </td>
         <td>            <p>Private ECB incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKDEQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0304</p>         </td>
         <td>            <p>00000130</p>         </td>
         <td>            <p>DEQ without ENQ</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKENQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0312</p>         </td>
         <td>            <p>00000138</p>         </td>
         <td>            <p>Two ENQs on same resource</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0376</p>         </td>
         <td>            <p>00000178</p>         </td>
         <td>            <p>Out of memory</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SIMM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0376</p>         </td>
         <td>            <p>00000178</p>         </td>
         <td>            <p>Out of memory</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKPOST</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0514</p>         </td>
         <td>            <p>00000202</p>         </td>
         <td>            <p>Private ECB incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKDEQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0560</p>         </td>
         <td>            <p>00000230</p>         </td>
         <td>            <p>Error on major ENQ chain</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKENQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0568</p>         </td>
         <td>            <p>00000238</p>         </td>
         <td>            <p>Error on minor ENQ chain</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKWAIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0769</p>         </td>
         <td>            <p>00000301</p>         </td>
         <td>            <p>Private ECB destroyed</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKDEQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0816</p>         </td>
         <td>            <p>00000330</p>         </td>
         <td>            <p>Error on major ENQ chain</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKENQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0824</p>         </td>
         <td>            <p>00000338</p>         </td>
         <td>            <p>Error on minor ENQ chain</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SIFM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0991</p>         </td>
         <td>            <p>000003DF</p>         </td>
         <td>            <p>File unavailable (RENAME)</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SIFM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0992</p>         </td>
         <td>            <p>000003E0</p>         </td>
         <td>            <p>File unavailable (ENQ)</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SIFM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0993</p>         </td>
         <td>            <p>000003E1</p>         </td>
         <td>            <p>PDS member missing</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGF3ACC</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0994</p>         </td>
         <td>            <p>000003E2</p>         </td>
         <td>            <p>Error in GDG file</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SIFM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0996</p>         </td>
         <td>            <p>000003E4</p>         </td>
         <td>            <p>File not found/already exists</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SIFM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>0999</p>         </td>
         <td>            <p>000003E7</p>         </td>
         <td>            <p>Creation by DDNAME</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGIWARNC</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>0999</p>         </td>
         <td>            <p>000003E7</p>         </td>
         <td>            <p>Parameters of C functions not supported</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKSWAIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>1025</p>         </td>
         <td>            <p>00000401</p>         </td>
         <td>            <p>Private ECB incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKDEQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>1072</p>         </td>
         <td>            <p>00000430</p>         </td>
         <td>            <p>DEQ requested by another task</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGSENQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>1080</p>         </td>
         <td>            <p>00000438</p>         </td>
         <td>            <p>Parameter error</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKMWAIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>1281</p>         </td>
         <td>            <p>00000501</p>         </td>
         <td>            <p>Private ECB incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKENQ</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>1336</p>         </td>
         <td>            <p>00000538</p>         </td>
         <td>            <p>WAIT return error</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGINUCDS</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2300</p>         </td>
         <td>            <p>000008FC</p>         </td>
         <td>            <p>TCBFSA word 1 used</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2483</p>         </td>
         <td>            <p>000009B3</p>         </td>
         <td>            <p>Program not authorized APF</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGFHYPER</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2864</p>         </td>
         <td>            <p>00000B30</p>         </td>
         <td>            <p>HSPSERV SWRITE error</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2881</p>         </td>
         <td>            <p>00000B41</p>         </td>
         <td>            <p>A mandatory task aborted</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2884</p>         </td>
         <td>            <p>00000B44</p>         </td>
         <td>            <p>ECB chain loop</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2885</p>         </td>
         <td>            <p>00000B45</p>         </td>
         <td>            <p>KECB chain loop</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2886</p>         </td>
         <td>            <p>00000B46</p>         </td>
         <td>            <p>Task chain loop</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2887</p>         </td>
         <td>            <p>00000B47</p>         </td>
         <td>            <p>KCP overwritten</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2888</p>         </td>
         <td>            <p>00000B48</p>         </td>
         <td>            <p>Second dispatcher init</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGKCP</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2889</p>         </td>
         <td>            <p>00000B49</p>         </td>
         <td>            <p>Error in task chain</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>MVSBXCRE</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2915</p>         </td>
         <td>            <p>00000B63</p>         </td>
         <td>            <p>Opening error</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>MVSBXCRE</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2916</p>         </td>
         <td>            <p>00000B64</p>         </td>
         <td>            <p>Queue error</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>MVSBXCRE</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2918</p>         </td>
         <td>            <p>00000B66</p>         </td>
         <td>            <p>z/OS system not ESA</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>MVSBXCRE</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2920</p>         </td>
         <td>            <p>00000B68</p>         </td>
         <td>            <p>GQSCAM error</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>IBM3PARM</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2930</p>         </td>
         <td>            <p>00000B72</p>         </td>
         <td>            <p>More than 16 parameters</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2933</p>         </td>
         <td>            <p>00000B76</p>         </td>
         <td>            <p>Semaphore ACR invalid</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2934</p>         </td>
         <td>            <p>00000B77</p>         </td>
         <td>            <p>Semaphore reference invalid</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2935</p>         </td>
         <td>            <p>00000B78</p>         </td>
         <td>            <p>MODE ENQ - message incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2936</p>         </td>
         <td>            <p>00000B78</p>         </td>
         <td>            <p>Semaphore acronym incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISYDEL</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2937</p>         </td>
         <td>            <p>00000B79</p>         </td>
         <td>            <p>Semaphore acronym incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2937</p>         </td>
         <td>            <p>00000B79</p>         </td>
         <td>            <p>Message acronym incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISYDEL</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2938</p>         </td>
         <td>            <p>00000B7A</p>         </td>
         <td>            <p>Message acronym incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2938</p>         </td>
         <td>            <p>00000B7A</p>         </td>
         <td>            <p>Message acronym incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISYDEF</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2939</p>         </td>
         <td>            <p>00000B7B</p>         </td>
         <td>            <p>Zero-length message</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2943</p>         </td>
         <td>            <p>00000B7F</p>         </td>
         <td>            <p>Request to clear a free LOCK</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2945</p>         </td>
         <td>            <p>00000B81</p>         </td>
         <td>            <p>Two requests for same LOCK</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2946</p>         </td>
         <td>            <p>00000B82</p>         </td>
         <td>            <p>LOCK number &gt; 63</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2946</p>         </td>
         <td>            <p>00000B82</p>         </td>
         <td>            <p>LOCK number &gt; 63</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2947</p>         </td>
         <td>            <p>00000B83</p>         </td>
         <td>            <p>Error in length of control data</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SISY</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2948</p>         </td>
         <td>            <p>00000B84</p>         </td>
         <td>            <p>Error in message length</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISYDEL</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2949</p>         </td>
         <td>            <p>00000B85</p>         </td>
         <td>            <p>Semaphore reference incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SITM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2951</p>         </td>
         <td>            <p>00000B87</p>         </td>
         <td>            <p>Unknown function</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SISM</p>         </td>
         <td>            <p>Info</p>         </td>
         <td>            <p>2960</p>         </td>
         <td>            <p>00000B90</p>         </td>
         <td>            <p>Unknown function</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SYMSYSF</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2976</p>         </td>
         <td>            <p>00000BA0</p>         </td>
         <td>            <p>FREEMAIN at 0</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SYMSYSF</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2977</p>         </td>
         <td>            <p>00000BA1</p>         </td>
         <td>            <p>Memory chaining error</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SYMSYSF</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2978</p>         </td>
         <td>            <p>00000BA2</p>         </td>
         <td>            <p>FREEMAIN on a non-allocated area</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SYMSYSF</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2979</p>         </td>
         <td>            <p>00000BA3</p>         </td>
         <td>            <p>Memory area prefix incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SYMSYSF</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2980</p>         </td>
         <td>            <p>00000BA4</p>         </td>
         <td>            <p>No more SAVE AREA</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SYMSYSG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2986</p>         </td>
         <td>            <p>00000BAA</p>         </td>
         <td>            <p>Memory area prefix incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SYMSYSG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2987</p>         </td>
         <td>            <p>00000BAB</p>         </td>
         <td>            <p>Memory area prefix incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SYMSYSG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2988</p>         </td>
         <td>            <p>00000BAC</p>         </td>
         <td>            <p>Parameters incorrect</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SYMSYSG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2989</p>         </td>
         <td>            <p>00000BAD</p>         </td>
         <td>            <p>Memory area used</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SYMSYSG</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2990</p>         </td>
         <td>            <p>00000BAE</p>         </td>
         <td>            <p>No SAVE AREA left</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGIDEXIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2991</p>         </td>
         <td>            <p>00000BAF</p>         </td>
         <td>            <p>CRAB incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGIDEXIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2992</p>         </td>
         <td>            <p>00000BB0</p>         </td>
         <td>            <p>End of work stack overrun</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2993</p>         </td>
         <td>            <p>00000BB1</p>         </td>
         <td>            <p>CLINK incorrect</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2994</p>         </td>
         <td>            <p>00000BB2</p>         </td>
         <td>            <p>C-program, pre-4.50 version</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2995</p>         </td>
         <td>            <p>00000BB3</p>         </td>
         <td>            <p>DSA end delimiter overwritten</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2996</p>         </td>
         <td>            <p>00000BB4</p>         </td>
         <td>            <p>Routing of C program</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SGIDINIT</p>         </td>
         <td>            <p>ABEND</p>         </td>
         <td>            <p>2997</p>         </td>
         <td>            <p>00000BB5</p>         </td>
         <td>            <p>Routing of C program</p>         </td>
      </tr>
   </tbody>
</table>
