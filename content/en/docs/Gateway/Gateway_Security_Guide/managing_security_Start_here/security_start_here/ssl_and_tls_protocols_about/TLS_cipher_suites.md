{
    "title": "TLS cipher suites",
    "linkTitle": "TLS cipher suites",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Security

<span class="mc-variable suite_variables.GatewayName variable">Gateway</span> supports the cipher suites listed in this section. The availability of the ciphers is conditioned by various factors, as shown in the table.

<table>
   <thead>
      <tr>
<th style="text-align: left;" class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: bold; padding-left: 2px; padding-right: 2px"><p><strong>Cipher suite</strong></p>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: bold; padding-left: 2px; padding-right: 2px"><strong>SSL V3</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>TLS 1.0</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>TLS 1.1</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>TLS 1.2</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>Is strong Cipher</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>Usable with Secure Relay (TLS termination)</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>Usable on Gateway direct connections</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>Requires unlimited crypto-graphy</strong>         </th>
<th class="TableStyle-SynchTaskMap-HeadE-Column1-Header1" style="vertical-align: top; font-weight: normal; padding-left: 2px; padding-right: 2px"><strong>Available in FIPS mode</strong><br />
         </th>
<th class="TableStyle-SynchTaskMap-HeadD-Column1-Header1" style="vertical-align: top; font-weight: bold; padding-left: 2px; padding-right: 2px">Requires certificate         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_256_GCM_SHA384         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_1" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_2" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_3" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_4" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_7" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_8" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_9" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_256_CBC_SHA384         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_10" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_11" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_12" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_13" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_14" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_16" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_18" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_128_GCM_SHA256         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_19" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_20" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_21" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_22" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_23" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_25" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_27" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_128_CBC_SHA256         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_28" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_29" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_30" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_31" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_32" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_34" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_36" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_256_CBC_SHA         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_37" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_38" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_39" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_40" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_41" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_43" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_45" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_AES_128_CBC_SHA         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_46" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_47" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_48" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_49" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_50" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_52" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_54" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_3DES_EDE_CBC_SHA         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_55" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_56" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_57" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_58" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_59" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_61" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_63" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_ECDSA_WITH_RC4_128_SHA         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_64" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_65" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_66" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_67" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_68" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_5" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_70" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_71" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_72" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_RSA_WITH_AES_256_GCM_SHA384         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_73" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_74" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_75" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_76" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_77" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_78" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_79" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_80" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_81" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_82" /></p>         </td>
      </tr>
      <tr>
         <td>ECDHE_RSA_WITH_AES_128_GCM_SHA256         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_83" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_84" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_85" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_86" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_87" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_88" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_89" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_90" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_91" /></p>         </td>
      </tr>
      <tr>
         <td>DHE_RSA_WITH_AES_256_GCM_SHA384         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_92" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_93" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_94" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_95" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_96" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_97" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_98" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_99" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_100" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_101" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_AES_128_GCM_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_102" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_103" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_104" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_105" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_106" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_107" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_108" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_109" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_110" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_AES_256_CBC_SHA384</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_111" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_112" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_113" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_114" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_115" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_116" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_117" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_118" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_119" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_120" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_AES_128_CBC_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_121" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_123" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_125" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_127" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_128" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_129" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_130" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_131" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_132" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_AES_256_CBC_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_133" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_136" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_139" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_142" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_143" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_144" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_145" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_146" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_147" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_148" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_AES_128_CBC_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_149" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_152" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_155" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_158" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_159" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_160" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_161" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_162" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_163" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_256_GCM_SHA384</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_164" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_166" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_168" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_170" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_171" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_172" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_173" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_174" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_175" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_176" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_128_GCM_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_177" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_179" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_181" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_183" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_184" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_185" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_186" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_187" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_188" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_256_CBC_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_189" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_191" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_193" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_195" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_196" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_197" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_198" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_199" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_200" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_201" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_128_CBC_SHA256</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_202" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_204" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_206" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_208" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_209" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_210" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_211" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_212" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_213" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_AES_256_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_214" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_216" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_217" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_218" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_219" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_220" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_221" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_222" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_223" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_224" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_AES_128_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_225" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_226" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_227" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_228" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_229" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_230" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_231" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_232" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_233" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_AES_256_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_234" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_235" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_236" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_237" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_238" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_239" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_240" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_241" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_242" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_243" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_AES_128_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_244" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_245" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_246" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_247" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_248" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_249" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_250" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_251" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_252" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_256_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_253" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_254" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_255" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_256" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_257" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_258" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_259" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_260" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_261" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_262" /></p>         </td>
      </tr>
      <tr>
         <td><p>RSA_WITH_AES_128_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_263" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_264" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_265" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_266" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_267" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_268" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_269" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_270" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_271" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_3DES_EDE_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_273" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_274" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_275" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_276" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_277" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_278" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_279" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_280" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_281" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_3DES_EDE_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_283" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_284" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_285" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_286" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_287" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_288" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_289" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_290" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_291" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_RC4_128_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_293" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_296" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_297" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_298" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_299" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_300" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_301" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_302" /></p>         </td>
      </tr>
      <tr>
         <td><p>ECDHE_RSA_WITH_NULL_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_303" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_305" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_306" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_307" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_308" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_309" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_310" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_311" /></p>         </td>
      </tr>
      <tr>
         <td><p>DHE_RSA_WITH_DES_CBC_SHA</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_320" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_321" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_322" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_323" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_324" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_325" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_326" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_3DES_EDE_CBC_SHA</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_328" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_329" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_330" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_331" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_332" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_333" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_334" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_335" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_RC4_128_SHA</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_336" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_337" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_338" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_339" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_340" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_341" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_342" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_DES_CBC_SHA</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_343" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_344" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_345" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_346" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_347" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_348" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_349" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_RC4_128_MD5</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_350" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_351" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_352" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_353" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_354" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_355" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_356" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_NULL_SHA256</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_394" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_395" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_396" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_397" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_398" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_399" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_400" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_NULL_SHA</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_401" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_402" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_403" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_404" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_405" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_406" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_407" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>RSA_WITH_NULL_MD5</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_408" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_409" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_410" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_411" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_412" /></p>         </td>
         <td><p>D</p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_413" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_414" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_327" /></p>         </td>
      </tr>
      <tr>
         <td>RSA_ANON_WITH_NULL_MD5         </td>
         <td>          </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_411" /></p>         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_414" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_NULL_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_414" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_RC4_128_MD5</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_414" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_RC4_128_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_414" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_DES_CBC_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_414" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_3DES_EDE_CBC_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_98" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_AES_128_CBC_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_98" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>RSA_ANON_WITH_AES_256_CBC_SHA</p>         </td>
         <td>          </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_411" />         </td>
         <td><img src="/Images/Gateway/nOK.png" class="img_412" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_497" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_413" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_98" />         </td>
         <td><img src="/Images/Gateway/OK.png" class="img_98" />         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><table>
   <tbody>
      <tr>
         <td><p>NULL_WITH_NULL_NULL</p>         </td>
      </tr>
   </tbody>
</table>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_491" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_492" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_493" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_494" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_495" /></p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_496" /></p>         </td>
         <td><p><img src="/Images/Gateway/OK.png" class="img_497" /></p>         </td>
         <td><p> </p>         </td>
         <td><p><img src="/Images/Gateway/nOK.png" class="img_498" /></p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

Comments about the table above:

**D** : Disabled by default in <span class="mc-variable suite_variables.SecureRelayName variable" style="font-style: normal;">Secure Relay</span>

### Strong ciphers / weak ciphers

By default, on a new installation, only strong ciphers can be selected in TLS profiles. For compatibility reasons, a parameter was added: <span class="code">\[tls\]enable\_weak\_ciphers</span>, which enables all supported ciphers.

When <span class="code">enable\_weak\_cipher </span>is set to *yes* and a weak cipher is selected:

• a warning message is shown on selection

• it will no longer be available in transfers if the <span class="code">enable\_weak\_cipher </span>option is switched to *no* (a warning message will be shown).

**Ciphers using the MD5 hash algorithm**: the parameter:` [monitor]enable_md5_hash_algorithm` (not recommended) enables ciphers using the MD5 hash algorithm. When `enable_md5_hash_algorithm `is set to *no* and a cipher suite using the MD5 hash algorithm is selected:

• The cipher is no longer available for the TLS handshake and in the TLS security profile configuration

Strong cryptography / weak cryptography: selecting strong cipher suites does not necessarily means all cryptographic parameters are strong. For example, the TLS\_DHE ciphers might still accept weak 1024 bit DH key generation parameters. To control this behavior, a parameter was added: \[tls\]enable\_weak\_ciphers, which – when set to “no” – would only allow the recommended 2048 bit or higher DH key generation parameters (please see the DHE key exchange in TLS section for more details) for DHE key exchange.

Note. For compatibility reasons, the default value for the \[tls\]enable\_weak\_ciphers is “yes”. It is strongly recommended to set this parameter to “no”.

### Strong cryptography / weak cryptography

Selecting strong cipher suites does not necessarily imply that all cryptographic parameters are strong. For example, the TLS\_DHE ciphers might still accept weak 1024-bit DH key generation parameters. To control this behavior, Gateway offers a parameter: `[tls]enable_weak_ciphers`, which – when set to `no `– only allows the recommended 2048-bit or higher DH key generation parameters.

> **Note:**
>
> For compatibility reasons, the parameter’s default value is yes. We strongly recommend to set this parameter to no.

For more information, see Managing TLS &gt; <a href="../managing_tls#Avoiding_weak_crypto" class="MCXref xref">Avoiding weak cryptography</a>

Related topics

<a href="../tls_security_profiles__gui_" class="MCXref xref">Managing TLS Security Profiles</a>

<a href="../managing_tls" class="MCXref xref">Managing TLS</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
