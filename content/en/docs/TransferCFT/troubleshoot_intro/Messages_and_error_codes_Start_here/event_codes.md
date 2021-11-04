{
    "title": "DIAGP: Event  codes",
    "linkTitle": "Event codes",
    "weight": "430"
}This code is common to all protocols. When a value is specific to a
protocol, the indication appears in brackets.

In the case of the PeSIT protocol, this code forms part of the "eNNsNN"-type
PeSIT DIAGP.

<span class="autonumber"></span>Event Codes for all protocols

<table>
   <th>
      <tr>
<th><p>Code</p>         </th>
<th><p>Meaning </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>00</p>         </td>
         <td><p>VFABORTD - Transfer abort request by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></p>         </td>
      </tr>
      <tr>
         <td><p>01</p>         </td>
         <td><p>VFCAND - Transfer interrupt request by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></p>         </td>
      </tr>
      <tr>
         <td><p>02</p>         </td>
         <td><p>VFCANR - Response to a transfer interrupt indication</p>         </td>
      </tr>
      <tr>
         <td><p>03</p>         </td>
         <td><p>VFCHKD - Request to set a synchronization point</p>         </td>
      </tr>
      <tr>
         <td><p>04</p>         </td>
         <td><p>VFCHKR - Response to a synchronization point indication</p>         </td>
      </tr>
      <tr>
         <td><p>05</p>         </td>
         <td><p>VFCLOSD - Request to close file</p>         </td>
      </tr>
      <tr>
         <td><p>06</p>         </td>
         <td><p>VFCLOSRN - Negative response to a file close indication</p>         </td>
      </tr>
      <tr>
         <td><p>07</p>         </td>
         <td><p>VFCLOSRP - Positive response to a file close indication</p>         </td>
      </tr>
      <tr>
         <td><p>08</p>         </td>
         <td><p>VFCONRN - Negative response to a connect indication</p>         </td>
      </tr>
      <tr>
         <td><p>09</p>         </td>
         <td><p>VFCREAD - Request to create a file</p>         </td>
      </tr>
      <tr>
         <td><p>10</p>         </td>
         <td><p>VFCREARN - Negative response to a file create indication</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>VFCREARP - Positive response to a file create indication</p>         </td>
      </tr>
      <tr>
         <td><p>12</p>         </td>
         <td><p>VFDATAD - Request to send data</p>         </td>
      </tr>
      <tr>
         <td><p>13</p>         </td>
         <td><p>VFDSELD- Request to select a file</p>         </td>
      </tr>
      <tr>
         <td><p>14</p>         </td>
         <td><p>VFDSELRN - Negative response to a select indication</p>         </td>
      </tr>
      <tr>
         <td><p>15</p>         </td>
         <td><p>VFDSELRP - Positive response to a select indication</p>         </td>
      </tr>
      <tr>
         <td><p>16</p>         </td>
         <td><p>VFDTNDD - End of data request</p>         </td>
      </tr>
      <tr>
         <td><p>17</p>         </td>
         <td><p>VFECOND - Request to connect in WRITE mode</p>         </td>
      </tr>
      <tr>
         <td><p>18</p>         </td>
         <td><p>VFECONRP - Positive response to a connect indication</p>         </td>
      </tr>
      <tr>
         <td><p>19</p>         </td>
         <td><p>VFLCOND - Request to connect in READ mode</p>         </td>
      </tr>
      <tr>
         <td><p>20</p>         </td>
         <td><p>VFLCONRP - Positive response to a connect indication</p>         </td>
      </tr>
      <tr>
         <td><p>21</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>22</p>         </td>
         <td><p>VFOMSGD - Request to send a message</p>         </td>
      </tr>
      <tr>
         <td><p>23</p>         </td>
         <td><p>VFOMSGRN - Negative response to a message indication</p>         </td>
      </tr>
      <tr>
         <td><p>24</p>         </td>
         <td><p>VFOMSGRP - Positive response to a message indication</p>         </td>
      </tr>
      <tr>
         <td><p>25</p>         </td>
         <td><p>VFOPEND - Request to open a file</p>         </td>
      </tr>
      <tr>
         <td><p>26</p>         </td>
         <td><p>VFOPENRN - Negative response to a file open indication</p>         </td>
      </tr>
      <tr>
         <td><p>27</p>         </td>
         <td><p>VFOPENRP - Positive response to a file open indication</p>         </td>
      </tr>
      <tr>
         <td><p>28</p>         </td>
         <td><p>VFRDY - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>29</p>         </td>
         <td><p>VFRDYD - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>30</p>         </td>
         <td><p>VFREADD - Request to read a file</p>         </td>
      </tr>
      <tr>
         <td><p>31</p>         </td>
         <td><p>VFREADRN - Negative response to a read request</p>         </td>
      </tr>
      <tr>
         <td><p>32</p>         </td>
         <td><p>VFREADRP - Positive response to a read request</p>         </td>
      </tr>
      <tr>
         <td><p>33</p>         </td>
         <td><p>VFRELD - Network close request</p>         </td>
      </tr>
      <tr>
         <td><p>34</p>         </td>
         <td><p>VFRELR - Response to network close request</p>         </td>
      </tr>
      <tr>
         <td><p>35</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>36</p>         </td>
         <td><p>VFRSTAR - Response to a re-synchronization request</p>         </td>
      </tr>
      <tr>
         <td><p>37</p>         </td>
         <td><p>VFSELD - Request to select a file</p>         </td>
      </tr>
      <tr>
         <td><p>38</p>         </td>
         <td><p>VFSELRN - Negative response to a select request</p>         </td>
      </tr>
      <tr>
         <td><p>39</p>         </td>
         <td><p>VFSELRP - Positive response to a select request</p>         </td>
      </tr>
      <tr>
         <td><p>40</p>         </td>
         <td><p>VFTRD - Request to start up a new transfer</p>         </td>
      </tr>
      <tr>
         <td><p>41</p>         </td>
         <td><p>VFTRNDD - Request to end a transfer</p>         </td>
      </tr>
      <tr>
         <td><p>42</p>         </td>
         <td><p>VFTRNDR - Response to an end of transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>43</p>         </td>
         <td><p>VFTRNDRN - Negative response to an end of transfer</p>         </td>
      </tr>
      <tr>
         <td><p>44</p>         </td>
         <td><p>VFTRNDRP - Positive response to an end of transfer</p>         </td>
      </tr>
      <tr>
         <td><p>45</p>         </td>
         <td><p>VFWRITD - Request to write a file</p>         </td>
      </tr>
      <tr>
         <td><p>46</p>         </td>
         <td><p>VFWRITRN - Negative response to a write request</p>         </td>
      </tr>
      <tr>
         <td><p>47</p>         </td>
         <td><p>VFWRITRP - Positive response to a write request</p>         </td>
      </tr>
      <tr>
         <td><p>48</p>         </td>
         <td><p>VLOGD - Request to send a pre-logon message</p>         </td>
      </tr>
      <tr>
         <td><p>49</p>         </td>
         <td><p>VLOGRN - Negative response to a pre-logon message</p>         </td>
      </tr>
      <tr>
         <td><p>50</p>         </td>
         <td><p>VLOGRP - Positive response to a pre-logon message</p>         </td>
      </tr>
      <tr>
         <td><p>51</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>52</p>         </td>
         <td><p>VNCONRP (NETWORK) - Positive response to an incoming call</p>         </td>
      </tr>
      <tr>
         <td><p>53</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>54</p>         </td>
         <td><p>VNRELC (NETWORK) - Confirmation of network outage</p>         </td>
      </tr>
      <tr>
         <td><p>55</p>         </td>
         <td><p>VNRELI (NETWORK) - Network outage indication</p>         </td>
      </tr>
      <tr>
         <td><p>56</p>         </td>
         <td><p>VRABORT (PESIT) - Reception of an ABORT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>57</p>         </td>
         <td><p>VRACK (PESIT) - Reception of a pre-logon acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>58</p>         </td>
         <td><p>VRACON (PESIT) - Reception of an AckCONNECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>59</p>         </td>
         <td><p>VRACREAN (PESIT) Reception of a negative AckCREATE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>60</p>         </td>
         <td><p>VRACREAP (PESIT) Reception of a positive AckCREATE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>61</p>         </td>
         <td><p>VRACRFN (PESIT) - Reception of a negative AckCRF FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>62</p>         </td>
         <td><p>VRACRFP (PESIT) - Reception of a positive AckCRF FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>63 </p>         </td>
         <td><p>VRADSELN (PESIT) - Reception of
a negative AckDESELECT FPDU </p>         </td>
      </tr>
      <tr>
         <td><p>64</p>         </td>
         <td><p>VRADSELP (PESIT) - Reception of a positive AckDESELECT
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>65</p>         </td>
         <td><p>VRAIDT (PESIT) - Reception of an AckCANCEL FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>66</p>         </td>
         <td><p>VRAOMSGN (PESIT) - Reception of a negative AckMESSAGE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>67</p>         </td>
         <td><p>VRAOMSGP (PESIT) Reception of a positive AckMESSAGE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>68</p>         </td>
         <td><p>VRAORFN (PESIT) - Reception of a negative AckORF FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>69</p>         </td>
         <td><p>VRAORFP (PESIT) - Reception of a positive AckORF FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>70</p>         </td>
         <td><p>VRAREADN (PESIT) - Reception of a negative AckREAD FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>71</p>         </td>
         <td><p>VRAREADP (PESIT) - Reception of a positive AckREAD FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>72</p>         </td>
         <td><p>VRARESY (PESIT) - Reception of an AckRESYN FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>73</p>         </td>
         <td><p>VRASELN (PESIT) - Reception of a negative AckSELECT
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>74</p>         </td>
         <td><p>VRASELP (PESIT) - Reception of a positive AckSELECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>75</p>         </td>
         <td><p>VRASY (PESIT) - Reception of a synchronization acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>76</p>         </td>
         <td><p>VRATRNDN (PESIT) - Reception of a negative AckTRANSFER.END
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>77</p>         </td>
         <td><p>VRATRNDP (PESIT) - Reception of a positive AckTRANSFER.END
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>78</p>         </td>
         <td><p>VRAWRITN (PESIT) - Reception of a negative AckWRITE
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>79</p>         </td>
         <td><p>VRAWRITP (PESIT) - Reception of a positive AckWRITE
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>80</p>         </td>
         <td><p>VRCON (PESIT) - Reception of a CONNECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>81</p>         </td>
         <td><p>VRCREA (PESIT) - Reception of a CREATE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>82</p>         </td>
         <td><p>VRCRF (PESIT) - Reception of a CRF (Close Remote File)
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>83</p>         </td>
         <td><p>VRDSEL (PESIT) - Reception of a DESLECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>84</p>         </td>
         <td><p>VRDTF (PESIT) - Reception of a DATA FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>85</p>         </td>
         <td><p>VRDTFDA (PESIT) - Reception of a DATA (Start) FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>86</p>         </td>
         <td><p>VRDTFFA (PESIT) - Reception of a DATA (End) FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>87</p>         </td>
         <td><p>VRDTFMA (PESIT) - Reception of an end of DATA (Middle)
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>88</p>         </td>
         <td><p>VRDTND (PESIT) - Reception of an end of DATA FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>89</p>         </td>
         <td><p>VRIDT (PESIT) - Reception of a CANCEL FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>90</p>         </td>
         <td><p>VRLOG (PESIT) - Reception of a pre-logon message</p>         </td>
      </tr>
      <tr>
         <td><p>91</p>         </td>
         <td><p>VRNACCN (NETWORK) - Outgoing call refused</p>         </td>
      </tr>
      <tr>
         <td><p>92</p>         </td>
         <td><p>VRNACCP (NETWORK) - Outgoing call accepted</p>         </td>
      </tr>
      <tr>
         <td><p>93</p>         </td>
         <td><p>VRNCON (NETWORK) - Incoming call indication</p>         </td>
      </tr>
      <tr>
         <td><p>94</p>         </td>
         <td><p>VROMSG (PESIT) - Reception of a MESSAGE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>95</p>         </td>
         <td><p>VRORF (PESIT) - Received an ORF (Open Remote File)
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>96</p>         </td>
         <td><p>VRRCON (PESIT) - Received a Release CONNECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>97</p>         </td>
         <td><p>VRRDY (NETWORK) - Network ready-to-send indication</p>         </td>
      </tr>
      <tr>
         <td><p>98</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>99</p>         </td>
         <td><p>VRREAD (PESIT) - Reception of a READ FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>100</p>         </td>
         <td><p>VRREL (PESIT) - Reception of a RELEASE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>101</p>         </td>
         <td><p>VRRELCF (PESIT) - Reception of a RELEASE Confirm FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>102</p>         </td>
         <td><p>VRRESY (PESIT) - Reception of a RE-SYNCHRONIZATION FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>103</p>         </td>
         <td><p>VRSEL (PESIT) - Reception of a SELECT FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>104</p>         </td>
         <td><p>VRSY (PESIT) - Reception of a SYNCHRONIZATION FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>105</p>         </td>
         <td><p>VRTRND (PESIT) - Reception of a TRANSFER.END FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>106</p>         </td>
         <td><p>VRWRIT (PESIT) - Reception of a WRITE FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>107</p>         </td>
         <td><p>VVTIMO - Time-out</p>         </td>
      </tr>
      <tr>
         <td><p>108</p>         </td>
         <td><p>VFDATA1 - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>109</p>         </td>
         <td><p>VRDTF1 - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>110</p>         </td>
         <td><p>VVERCRC - Detection of a CRC error</p>         </td>
      </tr>
      <tr>
         <td><p>111</p>         </td>
         <td><p>VVERR - Detection of an inconsistent FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>112</p>         </td>
         <td><p>VIABORTS - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>113</p>         </td>
         <td><p>VIABORTC - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>114</p>         </td>
         <td><p>VIRSTR - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>115</p>         </td>
         <td><p>VINACCN - Internal induction for the automaton table</p>         </td>
      </tr>
      <tr>
         <td><p>116</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>117</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>118</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>119</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>120</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>121</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>122</p>         </td>
         <td><p>VRODMSG (PESIT) - Received a MESSAGE (Start) FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>123</p>         </td>
         <td><p>VROMMSG (PESIT) - Received a MESSAGE (Middle)
FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>124</p>         </td>
         <td><p>VROFMSG (PESIT) - Received a MESSAGE (End) FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>125</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>126</p>         </td>
         <td><p>VFCD (ODETTE) - Change direction request</p>         </td>
      </tr>
      <tr>
         <td><p>127</p>         </td>
         <td><p>VRASSID (ODETTE) Received an SSID (acknowledgment)</p>         </td>
      </tr>
      <tr>
         <td><p>128</p>         </td>
         <td><p>VRCD (ODETTE) - Reception of a CD (Change Direction)</p>         </td>
      </tr>
      <tr>
         <td><p>129</p>         </td>
         <td><p>VRCDT (ODETTE) - Reception of a CDT (Set Credit)</p>         </td>
      </tr>
      <tr>
         <td><p>130</p>         </td>
         <td><p>VREERP (ODETTE) - Reception of an EERP (End To End
Response)</p>         </td>
      </tr>
      <tr>
         <td><p>131</p>         </td>
         <td><p>VREFNA (ODETTE) - Reception of an EFNA (End File Negative
Answer)</p>         </td>
      </tr>
      <tr>
         <td><p>132</p>         </td>
         <td><p>VREFPA (ODETTE) - Reception of an EFPA (End File Positive
Answer)</p>         </td>
      </tr>
      <tr>
         <td><p>133</p>         </td>
         <td><p>VREFID (ODETTE) - Reception of an EFID (End File Identification)</p>         </td>
      </tr>
      <tr>
         <td><p>134</p>         </td>
         <td><p>VRESID (ODETTE) - Reception of an ESID (End Session
Identification)</p>         </td>
      </tr>
      <tr>
         <td><p>135</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>136</p>         </td>
         <td><p>Not used</p>         </td>
      </tr>
      <tr>
         <td><p>137</p>         </td>
         <td><p>VRRSSID (ODETTE) - Received an SSID (Start Session
Identification) FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>138</p>         </td>
         <td><p>VRRTR (ODETTE) - Received an RTR (Ready To Receive)</p>         </td>
      </tr>
      <tr>
         <td><p>139</p>         </td>
         <td><p>VRSFNA (ODETTE) - Reception of an SFNA (Start File
Negative Answer)</p>         </td>
      </tr>
      <tr>
         <td><p>140</p>         </td>
         <td><p>VRSFPA (ODETTE) - Reception of an SFPA (Start File
Positive Answer)</p>         </td>
      </tr>
      <tr>
         <td><p>141</p>         </td>
         <td><p>VRSFID (ODETTE) - Reception of an SFID (Start File
Identification)</p>         </td>
      </tr>
      <tr>
         <td><p>142</p>         </td>
         <td><p>VRSSID (ODETTE) - Reception of an SFID (Start File
Identification)</p>         </td>
      </tr>
      <tr>
         <td><p>143</p>         </td>
         <td><p>VRSSRM (ODETTE) - Reception of an SSRM (Start Session
Ready Message)</p>         </td>
      </tr>
      <tr>
         <td><p>144</p>         </td>
         <td><p>VIESID (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr>
         <td><p>145</p>         </td>
         <td><p>VISSID (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr>
         <td><p>146</p>         </td>
         <td><p>VIRREAD (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr>
         <td><p>147</p>         </td>
         <td><p>VIDSEL (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
      <tr>
         <td><p>148</p>         </td>
         <td><p>VIABORTCD (ODETTE) - Internal induction for the automaton
table</p>         </td>
      </tr>
   </tbody>
</table>
