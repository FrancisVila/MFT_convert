{
    "title": "OFTP trace example",
    "linkTitle": "OFTP trace example",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

This topic shows an example of a trace for a typical OFTP R2.0 protocol exchange. The trace is displayed in the Gateway Log file.

Activate the protocol trace using the GUI (right-click the Remote Site and select <span style="font-weight: bold;">Trace mode</span>) or by entering a command such as:

<span class="code" style="font-weight: bold;">[pelctl start\_site](../../../managing_partners_start_here/sites_start_here/managing_local_sites_cli/managing_remote_sites_cli#pelctl_start_site)  -alias remote\_oftp  -trace\_mode</span>


    TRADE123I  11:21:04  [89] CMS File encoded from 'local odette ident' to 'remote odette ident'.
    NET101I    11:21:04  (98) outgoing connection request      [src_add="/0",dest_add="mycomputer/61260"].
    NET104I    11:21:04  (98) outgoing connection confirmation [resp_add="127.0.0.1/2213"].
    ODT101I    11:21:04  Prot trace for: R_OFTP_A        (97    ) req:Read  len:19     Prot:ODETTE             <- R R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    CONX - FPDU: SSRM                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSRMMSG 
                                       Ready 
                                    Message .................. : ODETTE FTP READY                      <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSRMCR 
                                    .................................... : .                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:61     Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    CONX - FPDU: SSID                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDLEV 
                                       Protocol 
                                    Release Level ......... : 5                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCODE 
                                      Initiator's 
                                    Identification Code  : 
                                    OFTP_SITE_B                           <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDPSWD 
                                      Initiator's 
                                    Password ........... :                                       <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSDEB 
                                      Data 
                                    Exchange Buffer Size ...... : 04000                                 <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSR 
                                        Send 
                                    / Receive Capabilities .... : B                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCMPR 
                                      Buffer 
                                    Compression Indicator ... : N                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDREST 
                                      Restart 
                                    Indicator .............. : Y                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSPEC 
                                      Special 
                                    Logic Indicator ........ : N                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCRED 
                                      Credit 
                                    ......................... : 004                                   <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDAUTH 
                                      Secure 
                                    Authentication .......... : Y                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDRSV1 
                                      Reserved 
                                    ....................... :                                       <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDUSER 
                                      User 
                                    Data ...................... :                                       <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:61 
                                        Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    CONX - FPDU: SSID                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDLEV 
                                       Protocol 
                                    Release Level ......... : 5                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCODE 
                                      Initiator's 
                                    Identification Code  : 
                                                                          <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDPSWD 
                                      Initiator's 
                                    Password ........... :                                       <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSDEB 
                                      Data 
                                    Exchange Buffer Size ...... : 04000                                 <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSR 
                                        Send 
                                    / Receive Capabilities .... : B                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCMPR 
                                      Buffer 
                                    Compression Indicator ... : N                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDREST 
                                      Restart 
                                    Indicator .............. : Y                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDSPEC 
                                      Special 
                                    Logic Indicator ........ : N                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCRED 
                                      Credit 
                                    ......................... : 004                                   <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDAUTH 
                                      Secure 
                                    Authentication .......... : Y                                     <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDRSV1 
                                      Reserved 
                                    ....................... :                                       <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDUSER 
                                      User 
                                    Data ...................... :                                       <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       SSIDCR 
                                    .................................... : .                                     <- 
                                R R_OFTP_A 97.
    ODT200I    11:21:04 
                                     R_OFTP_A(97) 
                                connection established with L_OFTP_B.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:1      Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    AUTH - FPDU: SECD                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:192 
                                       Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    AUTH - FPDU: AUCH                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       AUCHCHIL 
                                      Challenge 
                                    Length ............... : 0x00BD                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                       AUCHCHAL 
                                      Challenge 
                                    ...................... : 0...*.H........0...                   <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:21     Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    AUTH - FPDU: AURP                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       AURPRSP 
                                       Challenge 
                                    Response ............. : D...z...!|qJ.T....Ad                  <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:1 
                                         Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    AUTH - FPDU: SECD                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:04 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:330    Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                      Type: 
                                    AUTH - FPDU: AUCH                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       AUCHCHIL 
                                      Challenge 
                                    Length ............... : 0x0147                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:04 
                                       AUCHCHAL 
                                      Challenge 
                                    ...................... : 0...*.H........0...                   <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:21 
                                        Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    AUTH - FPDU: AURP                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                       AURPRSP 
                                       Challenge 
                                    Response ............. : ._..C0~."..q.-mr.Z..                  <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:199    Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    PROT - FPDU: SFID                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDDSN 
                                       Virtual 
                                    File Dataset Name ...... : STREAM                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDRSV1 
                                      Reserved 
                                    ....................... :                                       <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDDATE 
                                      Virtual 
                                    File Date stamp ........ : 20080424                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDTIME 
                                      Virtual 
                                    File Time stamp ........ : 1121040000                            <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDUSER 
                                      User 
                                    Data ...................... :                                       <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDDEST 
                                      Destination 
                                    .................... : remote odette ident                   <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDORIG 
                                      Originator 
                                    ..................... : local odette ident                    <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDFMT 
                                       File 
                                    Format .................... : U                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDLRECL 
                                     Maximum 
                                    Record Size ............ : 00000                                 <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDFSIZ 
                                      File 
                                    Size, (1K blocks) ......... : 0000000000001                         <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDOSIZ 
                                      Original 
                                    File Size, (1K blocks)  : 
                                    0000000000001                         <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDREST 
                                      Restart 
                                    Position ............... : 00000000000000000                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDSEC 
                                       Security 
                                    Level ................. : 03                                    <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDCIPH 
                                      Cipher 
                                    suite selection ......... : 02                                    <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDCOMP 
                                      File 
                                    compression algorithm ..... : 1                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDENV 
                                       File 
                                    enveloping format ......... : 1                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDSIGN 
                                      Signed 
                                    EERP request ............ : Y                                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDDESCL 
                                     Virtual 
                                    File Description length  : 
                                    034                                   <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFIDDESC 
                                      Virtual 
                                    File Description ....... : Odette v2 virtual file description    <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:18 
                                        Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    PROT - FPDU: SFPA                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                       SFPAACNT 
                                      Answer 
                                    Count ................... : 00000000000000000                     <- 
                                R R_OFTP_A 97.
    ODT202I    11:21:05 
                                     R_OFTP_A(97) 
                                [89] beginning of transmission, file name:STREAM, date:20080424, time:1121040000.
    ODT203I    11:21:05 
                                     R_OFTP_A(97) 
                                [89] beginning of transmission from L_OFTP_B, file: e:\working\v613\run_time\tmp\F0000089.ec.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:4000   Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    DATA - FPDU: DATA                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:4000   Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    DATA - FPDU: DATA                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:686    Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    DATA - FPDU: DATA                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:35     Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    PROT - FPDU: EFID                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       EFIDRCNT 
                                      Record 
                                    Count ................... : 00000000000000000                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                       EFIDUCNT 
                                      Unit 
                                    Count ..................... : 00000000000008546                     <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:2 
                                         Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    PROT - FPDU: EFPA                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:05 
                                       EFPACD 
                                        Change 
                                    Direction Indicator ..... : N                                     <- 
                                R R_OFTP_A 97.
    ODT204I    11:21:05 
                                     R_OFTP_A(97) 
                                [89] end of transmission, file name:STREAM, date:20080424, time:1121040000.
    ODT205I    11:21:05 
                                     R_OFTP_A(97) 
                                [89] end of transmission from L_OFTP_B, file: e:\working\v613\run_time\tmp\F0000089.ec.
    AMT524I    11:21:05 
                                     remote 
                                odette ident[89] XFBConnInitParams().
    AMT524I    11:21:05 
                                     remote 
                                    odette ident[89] XFBConnXferNotif(h_Conn=00A52FC8, event=1[XFBCONN_NOTIF_SENT], 
                                h_Params=00A53FA8)..
    ODT101I    11:21:05 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:1      Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:05 
                                      Type: 
                                    PROT - FPDU: CD                                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:06 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:1213 
                                      Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                      Type: 
                                    PROT - FPDU: EERP                                                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPDSN 
                                       Virtual 
                                    File Dataset Name ...... : STREAM                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPRSV1 
                                      Reserved 
                                    ....................... :                                       <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPDATE 
                                      Virtual 
                                    File Date stamp ........ : 20080424                              <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPTIME 
                                      Virtual 
                                    File Time stamp ........ : 1121040000                            <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPUSER 
                                      User 
                                    Data ...................... :                                       <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPDEST 
                                      Destination 
                                    .................... : local odette ident                    <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPORIG 
                                      Originator 
                                    ..................... : remote odette ident                   <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPHSHL 
                                      Virtual 
                                    File hash length ....... : 0x0014                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPHSH 
                                       Virtual 
                                    File hash .............. : ...#+f...'Z..tJ..(.o                  <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPSIGL 
                                      EERP 
                                    signature length .......... : 0x043B                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                       EERPSIG 
                                       EERP 
                                    signature ................. : 0...*.H........0....1.0...+.....      <- 
                                R R_OFTP_A 97.
    AMT524I    11:21:06 
                                     remote 
                                odette ident[89] XFBConnXferNotif() rc=1 ..
    AMT524I    11:21:06 
                                     remote 
                                odette ident[89] XFBConnFreeParams(h_Params=00A53FA8)..
    ODT220I    11:21:06 
                                     R_OFTP_A(97) 
                                [90] receive file acknowledge, file name:STREAM, date:20080424, time:1121040000.
    ODT221I    11:21:06 
                                     R_OFTP_A(97) 
                                [90] receive file acknowledge for L_OFTP_B.
    ODT101I    11:21:06 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:1      Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:06 
                                      Type: 
                                    PROT - FPDU: RTR                                                               <- 
                                S R_OFTP_A 97.
    AMT524I    11:21:06 
                                     local odette 
                                ident[90] XFBConnInitParams().
    AMT524I    11:21:06 
                                     local odette 
                                    ident[90] XFBConnXferNotif(h_Conn=00A52FC8, event=1[XFBCONN_NOTIF_SENT], 
                                h_Params=00A546C0)..
    ODT101I    11:21:06 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Read  len:1 
                                         Prot:ODETTE 
                                                <- 
                                R R_OFTP_A 97.
    ODT101I    11:21:06 
                                      Type: 
                                    PROT - FPDU: CD                                                                <- 
                                R R_OFTP_A 97.
    AMT524I    11:21:06 
                                     local odette 
                                ident[90] XFBConnXferNotif() rc=1 ..
    AMT524I    11:21:06 
                                     local odette 
                                ident[90] XFBConnFreeParams(h_Params=00A546C0)..
    ODT216I    11:21:26 
                                     R_OFTP_A(97) 
                                disconnect request send by L_OFTP_B [reason="Normal session termination"].
    ODT101I    11:21:26 
                                     Prot trace 
                                    for: R_OFTP_A        (97 
                                       ) 
                                    req:Write len:33     Prot:ODETTE 
                                                <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:26 
                                      Type: 
                                    CONX - FPDU: ESID                                                              <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:26 
                                       ESIDREAS 
                                      Reason 
                                    Code .................... : 00                                    <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:26 
                                       ESIDREASL 
                                     Reason 
                                    Text Length ............. : 026                                   <- 
                                S R_OFTP_A 97.
    ODT101I    11:21:26    ESIDREAST  Reason Text .................... : Normal session termination            <- S R_OFTP_A 97.
    NET106I    11:21:26  (98) disconnection indication         [reason="No error (0x0)"] [origin="0"].

Related topics

[OFTP protocol log messages (ODT)](../../../log_messages_about/odette_protocol_(odt))

[About OFTP](../)

[Submitting an OFTP Transfer Request](../oftp_submitting_transfer)

[Monitoring an OFTP transfer](../oftp_monitoring_transfer)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
