{
    "title": "DIAGP: Event  codes",
    "linkTitle": "Event codes",
    "weight": "450"
}This code is common to all protocols. When a value is specific to a
protocol, the indication appears in brackets.

In the case of the PeSIT protocol, this code forms part of the "eNNsNN"-type
PeSIT DIAGP.

Event Codes for all protocols

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Code</p></th>
         <th>            <p>Meaning </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>00</p>         </td>
         <td width="82.122%">            <p>VFABORTD - Transfer abort request by <span>Transfer CFT</span></p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>01</p>         </td>
         <td width="82.122%">            <p>VFCAND - Transfer interrupt request by <span>Transfer CFT</span></p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>02</p>         </td>
         <td width="82.122%">            <p>VFCANR - Response to a transfer interrupt indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>03</p>         </td>
         <td width="82.122%">            <p>VFCHKD - Request to set a synchronization point</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>04</p>         </td>
         <td width="82.122%">            <p>VFCHKR - Response to a synchronization point indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>05</p>         </td>
         <td width="82.122%">            <p>VFCLOSD - Request to close file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>06</p>         </td>
         <td width="82.122%">            <p>VFCLOSRN - Negative response to a file close indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>07</p>         </td>
         <td width="82.122%">            <p>VFCLOSRP - Positive response to a file close indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>08</p>         </td>
         <td width="82.122%">            <p>VFCONRN - Negative response to a connect indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>09</p>         </td>
         <td width="82.122%">            <p>VFCREAD - Request to create a file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>10</p>         </td>
         <td width="82.122%">            <p>VFCREARN - Negative response to a file create indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>11</p>         </td>
         <td width="82.122%">            <p>VFCREARP - Positive response to a file create indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>12</p>         </td>
         <td width="82.122%">            <p>VFDATAD - Request to send data</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>13</p>         </td>
         <td width="82.122%">            <p>VFDSELD- Request to select a file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>14</p>         </td>
         <td width="82.122%">            <p>VFDSELRN - Negative response to a select indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>15</p>         </td>
         <td width="82.122%">            <p>VFDSELRP - Positive response to a select indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>16</p>         </td>
         <td width="82.122%">            <p>VFDTNDD - End of data request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>17</p>         </td>
         <td width="82.122%">            <p>VFECOND - Request to connect in WRITE mode</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>18</p>         </td>
         <td width="82.122%">            <p>VFECONRP - Positive response to a connect indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>19</p>         </td>
         <td width="82.122%">            <p>VFLCOND - Request to connect in READ mode</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>20</p>         </td>
         <td width="82.122%">            <p>VFLCONRP - Positive response to a connect indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>21</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>22</p>         </td>
         <td width="82.122%">            <p>VFOMSGD - Request to send a message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>23</p>         </td>
         <td width="82.122%">            <p>VFOMSGRN - Negative response to a message indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>24</p>         </td>
         <td width="82.122%">            <p>VFOMSGRP - Positive response to a message indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>25</p>         </td>
         <td width="82.122%">            <p>VFOPEND - Request to open a file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>26</p>         </td>
         <td width="82.122%">            <p>VFOPENRN - Negative response to a file open indication</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>27</p>         </td>
         <td width="82.122%">            <p>VFOPENRP - Positive response to a file open indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>28</p>         </td>
         <td width="82.122%">            <p>VFRDY - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>29</p>         </td>
         <td width="82.122%">            <p>VFRDYD - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>30</p>         </td>
         <td width="82.122%">            <p>VFREADD - Request to read a file</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>31</p>         </td>
         <td width="82.122%">            <p>VFREADRN - Negative response to a read request</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>32</p>         </td>
         <td width="82.122%">            <p>VFREADRP - Positive response to a read request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>33</p>         </td>
         <td width="82.122%">            <p>VFRELD - Network close request</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>34</p>         </td>
         <td width="82.122%">            <p>VFRELR - Response to network close request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>35</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>36</p>         </td>
         <td width="82.122%">            <p>VFRSTAR - Response to a re-synchronization request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>37</p>         </td>
         <td width="82.122%">            <p>VFSELD - Request to select a file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>38</p>         </td>
         <td width="82.122%">            <p>VFSELRN - Negative response to a select request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>39</p>         </td>
         <td width="82.122%">            <p>VFSELRP - Positive response to a select request</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>40</p>         </td>
         <td width="82.122%">            <p>VFTRD - Request to start up a new transfer</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>41</p>         </td>
         <td width="82.122%">            <p>VFTRNDD - Request to end a transfer</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>42</p>         </td>
         <td width="82.122%">            <p>VFTRNDR - Response to an end of transfer request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>43</p>         </td>
         <td width="82.122%">            <p>VFTRNDRN - Negative response to an end of transfer</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>44</p>         </td>
         <td width="82.122%">            <p>VFTRNDRP - Positive response to an end of transfer</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>45</p>         </td>
         <td width="82.122%">            <p>VFWRITD - Request to write a file</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>46</p>         </td>
         <td width="82.122%">            <p>VFWRITRN - Negative response to a write request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>47</p>         </td>
         <td width="82.122%">            <p>VFWRITRP - Positive response to a write request</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>48</p>         </td>
         <td width="82.122%">            <p>VLOGD - Request to send a pre-logon message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>49</p>         </td>
         <td width="82.122%">            <p>VLOGRN - Negative response to a pre-logon message</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>50</p>         </td>
         <td width="82.122%">            <p>VLOGRP - Positive response to a pre-logon message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>51</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>52</p>         </td>
         <td width="82.122%">            <p>VNCONRP (NETWORK) - Positive response to an incoming call</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>53</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>54</p>         </td>
         <td width="82.122%">            <p>VNRELC (NETWORK) - Confirmation of network outage</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>55</p>         </td>
         <td width="82.122%">            <p>VNRELI (NETWORK) - Network outage indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>56</p>         </td>
         <td width="82.122%">            <p>VRABORT (PESIT) - Reception of an ABORT FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>57</p>         </td>
         <td width="82.122%">            <p>VRACK (PESIT) - Reception of a pre-logon acknowledgment</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>58</p>         </td>
         <td width="82.122%">            <p>VRACON (PESIT) - Reception of an AckCONNECT FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>59</p>         </td>
         <td width="82.122%">            <p>VRACREAN (PESIT) Reception of a negative AckCREATE FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>60</p>         </td>
         <td width="82.122%">            <p>VRACREAP (PESIT) Reception of a positive AckCREATE FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>61</p>         </td>
         <td width="82.122%">            <p>VRACRFN (PESIT) - Reception of a negative AckCRF FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>62</p>         </td>
         <td width="82.122%">            <p>VRACRFP (PESIT) - Reception of a positive AckCRF FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>63 </p>         </td>
         <td width="82.122%">            <p>VRADSELN (PESIT) - Reception of
a negative AckDESELECT FPDU </p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>64</p>         </td>
         <td width="82.122%">            <p>VRADSELP (PESIT) - Reception of a positive AckDESELECT
FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>65</p>         </td>
         <td width="82.122%">            <p>VRAIDT (PESIT) - Reception of an AckCANCEL FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>66</p>         </td>
         <td width="82.122%">            <p>VRAOMSGN (PESIT) - Reception of a negative AckMESSAGE FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>67</p>         </td>
         <td width="82.122%">            <p>VRAOMSGP (PESIT) Reception of a positive AckMESSAGE FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>68</p>         </td>
         <td width="82.122%">            <p>VRAORFN (PESIT) - Reception of a negative AckORF FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>69</p>         </td>
         <td width="82.122%">            <p>VRAORFP (PESIT) - Reception of a positive AckORF FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>70</p>         </td>
         <td width="82.122%">            <p>VRAREADN (PESIT) - Reception of a negative AckREAD FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>71</p>         </td>
         <td width="82.122%">            <p>VRAREADP (PESIT) - Reception of a positive AckREAD FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>72</p>         </td>
         <td width="82.122%">            <p>VRARESY (PESIT) - Reception of an AckRESYN FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>73</p>         </td>
         <td width="82.122%">            <p>VRASELN (PESIT) - Reception of a negative AckSELECT
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>74</p>         </td>
         <td width="82.122%">            <p>VRASELP (PESIT) - Reception of a positive AckSELECT FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>75</p>         </td>
         <td width="82.122%">            <p>VRASY (PESIT) - Reception of a synchronization acknowledgment</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>76</p>         </td>
         <td width="82.122%">            <p>VRATRNDN (PESIT) - Reception of a negative AckTRANSFER.END
FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>77</p>         </td>
         <td width="82.122%">            <p>VRATRNDP (PESIT) - Reception of a positive AckTRANSFER.END
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>78</p>         </td>
         <td width="82.122%">            <p>VRAWRITN (PESIT) - Reception of a negative AckWRITE
FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>79</p>         </td>
         <td width="82.122%">            <p>VRAWRITP (PESIT) - Reception of a positive AckWRITE
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>80</p>         </td>
         <td width="82.122%">            <p>VRCON (PESIT) - Reception of a CONNECT FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>81</p>         </td>
         <td width="82.122%">            <p>VRCREA (PESIT) - Reception of a CREATE FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>82</p>         </td>
         <td width="82.122%">            <p>VRCRF (PESIT) - Reception of a CRF (Close Remote File)
FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>83</p>         </td>
         <td width="82.122%">            <p>VRDSEL (PESIT) - Reception of a DESLECT FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>84</p>         </td>
         <td width="82.122%">            <p>VRDTF (PESIT) - Reception of a DATA FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>85</p>         </td>
         <td width="82.122%">            <p>VRDTFDA (PESIT) - Reception of a DATA (Start) FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>86</p>         </td>
         <td width="82.122%">            <p>VRDTFFA (PESIT) - Reception of a DATA (End) FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>87</p>         </td>
         <td width="82.122%">            <p>VRDTFMA (PESIT) - Reception of an end of DATA (Middle)
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>88</p>         </td>
         <td width="82.122%">            <p>VRDTND (PESIT) - Reception of an end of DATA FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>89</p>         </td>
         <td width="82.122%">            <p>VRIDT (PESIT) - Reception of a CANCEL FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>90</p>         </td>
         <td width="82.122%">            <p>VRLOG (PESIT) - Reception of a pre-logon message</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>91</p>         </td>
         <td width="82.122%">            <p>VRNACCN (NETWORK) - Outgoing call refused</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>92</p>         </td>
         <td width="82.122%">            <p>VRNACCP (NETWORK) - Outgoing call accepted</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>93</p>         </td>
         <td width="82.122%">            <p>VRNCON (NETWORK) - Incoming call indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>94</p>         </td>
         <td width="82.122%">            <p>VROMSG (PESIT) - Reception of a MESSAGE FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>95</p>         </td>
         <td width="82.122%">            <p>VRORF (PESIT) - Received an ORF (Open Remote File)
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>96</p>         </td>
         <td width="82.122%">            <p>VRRCON (PESIT) - Received a Release CONNECT FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>97</p>         </td>
         <td width="82.122%">            <p>VRRDY (NETWORK) - Network ready-to-send indication</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>98</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>99</p>         </td>
         <td width="82.122%">            <p>VRREAD (PESIT) - Reception of a READ FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>100</p>         </td>
         <td width="82.122%">            <p>VRREL (PESIT) - Reception of a RELEASE FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>101</p>         </td>
         <td width="82.122%">            <p>VRRELCF (PESIT) - Reception of a RELEASE Confirm FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>102</p>         </td>
         <td width="82.122%">            <p>VRRESY (PESIT) - Reception of a RE-SYNCHRONIZATION FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>103</p>         </td>
         <td width="82.122%">            <p>VRSEL (PESIT) - Reception of a SELECT FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>104</p>         </td>
         <td width="82.122%">            <p>VRSY (PESIT) - Reception of a SYNCHRONIZATION FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>105</p>         </td>
         <td width="82.122%">            <p>VRTRND (PESIT) - Reception of a TRANSFER.END FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>106</p>         </td>
         <td width="82.122%">            <p>VRWRIT (PESIT) - Reception of a WRITE FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>107</p>         </td>
         <td width="82.122%">            <p>VVTIMO - Time-out</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>108</p>         </td>
         <td width="82.122%">            <p>VFDATA1 - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>109</p>         </td>
         <td width="82.122%">            <p>VRDTF1 - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>110</p>         </td>
         <td width="82.122%">            <p>VVERCRC - Detection of a CRC error</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>111</p>         </td>
         <td width="82.122%">            <p>VVERR - Detection of an inconsistent FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>112</p>         </td>
         <td width="82.122%">            <p>VIABORTS - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>113</p>         </td>
         <td width="82.122%">            <p>VIABORTC - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>114</p>         </td>
         <td width="82.122%">            <p>VIRSTR - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>115</p>         </td>
         <td width="82.122%">            <p>VINACCN - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>116</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>117</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>118</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>119</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>120</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>121</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>122</p>         </td>
         <td width="82.122%">            <p>VRODMSG (PESIT) - Received a MESSAGE (Start) FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>123</p>         </td>
         <td width="82.122%">            <p>VROMMSG (PESIT) - Received a MESSAGE (Middle)
FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>124</p>         </td>
         <td width="82.122%">            <p>VROFMSG (PESIT) - Received a MESSAGE (End) FPDU</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>125</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>126</p>         </td>
         <td width="82.122%">            <p>VFCD (ODETTE) - Change direction request</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>127</p>         </td>
         <td width="82.122%">            <p>VRASSID (ODETTE) Received an SSID (acknowledgment)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>128</p>         </td>
         <td width="82.122%">            <p>VRCD (ODETTE) - Reception of a CD (Change Direction)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>129</p>         </td>
         <td width="82.122%">            <p>VRCDT (ODETTE) - Reception of a CDT (Set Credit)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>130</p>         </td>
         <td width="82.122%">            <p>VREERP (ODETTE) - Reception of an EERP (End To End
Response)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>131</p>         </td>
         <td width="82.122%">            <p>VREFNA (ODETTE) - Reception of an EFNA (End File Negative
Answer)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>132</p>         </td>
         <td width="82.122%">            <p>VREFPA (ODETTE) - Reception of an EFPA (End File Positive
Answer)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>133</p>         </td>
         <td width="82.122%">            <p>VREFID (ODETTE) - Reception of an EFID (End File Identification)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>134</p>         </td>
         <td width="82.122%">            <p>VRESID (ODETTE) - Reception of an ESID (End Session
Identification)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>135</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>136</p>         </td>
         <td width="82.122%">            <p>Not used</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>137</p>         </td>
         <td width="82.122%">            <p>VRRSSID (ODETTE) - Received an SSID (Start Session
Identification) FPDU</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>138</p>         </td>
         <td width="82.122%">            <p>VRRTR (ODETTE) - Received an RTR (Ready To Receive)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>139</p>         </td>
         <td width="82.122%">            <p>VRSFNA (ODETTE) - Reception of an SFNA (Start File
Negative Answer)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>140</p>         </td>
         <td width="82.122%">            <p>VRSFPA (ODETTE) - Reception of an SFPA (Start File
Positive Answer)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>141</p>         </td>
         <td width="82.122%">            <p>VRSFID (ODETTE) - Reception of an SFID (Start File
Identification)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>142</p>         </td>
         <td width="82.122%">            <p>VRSSID (ODETTE) - Reception of an SFID (Start File
Identification)</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>143</p>         </td>
         <td width="82.122%">            <p>VRSSRM (ODETTE) - Reception of an SSRM (Start Session
Ready Message)</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>144</p>         </td>
         <td width="82.122%">            <p>VIESID (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>145</p>         </td>
         <td width="82.122%">            <p>VISSID (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>146</p>         </td>
         <td width="82.122%">            <p>VIRREAD (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="17.878%">            <p>147</p>         </td>
         <td width="82.122%">            <p>VIDSEL (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="17.878%">            <p>148</p>         </td>
         <td width="82.122%">            <p>VIABORTCD (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
   </tbody>
</table>
