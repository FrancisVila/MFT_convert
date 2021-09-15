{
    "title": "Configuring Transfer CFT parameters",
    "linkTitle": "Configuring Transfer CFT parameters",
    "weight": "310"
}From the Main Menu, enter the command cft and press Enter to open the Manager Menu.

1.  Select option 1 Customization and press ENTER.
2.  In the Customization screen, select option 1 CFT parameters and press ENTER.
3.  You can select option **2 Interpret the selected member**.

## <span id="Interpreting a parameter source"></span>Interpreting a parameter source

The parameter file that you selected in the previous step, option 1 Editing the parameter source member, is interpreted by CFTUTIL. The options are confirmed before being interpreted. To interpret or update a parameter source, select option 2 Interpret selected member in the Customization screen. The following screen is displayed.

The parameter and partner files can be created, re-created, or updated prior to interpretation. If this is the first time that you are interpreting a parameter source, you must first create it.

-   Select 1= Create for each time you interpret a new parameter source.

<!-- -->

-   Select 2 = Update to change existing command parameters. You can modify many of the Transfer CFT parameters while CFT is running, but some configuration command changes cannot be applied dynamically. For more information, refer to the Transfer CFT online documentation.

If you select 1 Configuration interpretation, Transfer CFT displays following messages.

View messages

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTU20I CFT OS/400</p>
            <p>CFTU20I Version 3.2.1 2015/03/15</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2015</p>
            <p>CFTU20I ====&gt; Starting Session on 02/04/2013 Time is 09:28:19</p>
            <p>CFTU20I</p>
            <p>CFTU00I CFTFILE _ Correct (type=param,mode=create,fname=CFTPROD/PARM1) CFTU20I Number of Command(s) 1</p>
            <p>CFTU20I Number of error(s) 0</p>
            <p>CFTU20I Ending Session on 02/04/2013 Time is 09:28:20</p>
            <p>CFTU20I Session active for 0:00:01</p>
            <p>Press ENTER to end terminal session.</p>
            <p>CFTU20I</p>
            <p>CFTU20I CFT OS/400</p>
            <p>CFTU20I Version 3.0.1 2013/03/15</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2012</p>
            <p>CFTU20I ====&gt; Starting Session on 02/04/2013 Time is 09:29:20</p>
            <p>CFTU20I</p>
            <p>CFTU00I CFTFILE _ Correct (type=part,mode=create,fname=CFTPROD/PART1 )</p>
            <p>CFTU20I Number of Command(s) 1</p>
            <p>CFTU20I Number of error(s) 0</p>
            <p>CFTU20I Ending Session on 02/04/2015 Time is 09:29:22</p>
            <p>CFTU20I Session active for 0:00:02</p>
            <p>Press ENTER to end terminal session.</p>
            <p>CFTU20I</p>
            <p>CFTU20I CFT OS/400</p>
            <p>CFTU20I Version 3.2.1 2015/03/15</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2015</p>
            <p>CFTU20I ====&gt; Starting Session on 02/04/2013 Time is 09:29:24</p>
            <p>CFTU20I Parameters file :+CFTPARM</p>
            <p>CFTU20I</p>
            <p>CFTU00I CFTPARM _ Correct (MODE=REPLACE,ID=IDPARM0,CAT=IDCAT0,COM=IDCOM0,LOG</p>
            <p>=</p>
            <p>CFTU00I IDLOG0,NET=TCP0,PROT=PESITANY,MAXTASK=4,TRANTASK=8</p>
            <p>CFTU00I ,MAXTRANS=32,BUFSIZE=32000,KEY='£CFTPROD/KEY',DEF</p>
            <p>CFTU00I AULT=IDFDEFT,PART=CFT400,WAITRESP=900,EXECSF='*LIB</p>
            <p>CFTU00I L/CFTSRC(B_EXECSF)',EXECRF='*LIBL/CFTSRC(B_EXECRF)</p>
            <p>CFTU00I ',PARTFNAM='+CFTPART')</p>
            <p>CFTU00I CFTCAT _ Correct (MODE=REPLACE,ID=IDCAT0,FNAME='+CFTCAT',SHARE=NO,UP</p>
            <p>CFTU00I DAT=0,WSCAN=1,ST=2,RT=2,SX=1,RX=1)</p>
            <p>CFTU00I CFTCOM _ Correct (MODE=REPLACE,ID=IDCOM0,TYPE=FILE,NAME='+CFTCOM',WS</p>
            <p>CFTU00I CAN=10)</p>
            <p>CFTU00I CFTLOG _ Correct (MODE=REPLACE,ID=IDLOG0,FNAME='CFTPROD/LOG1',AFNAM</p>
            <p>CFTU00I E='CFTPROD/ALOG1',MAXREC=15000,SWITCH=1300,EXEC=</p>
            <p>'</p>
            <p>CFTU00I *LIBL/CFTSRC(B_EXECLOG)',OPERMSG=255,NOTIFY='</p>
            <p>CFTU00I ')</p>
            <p>CFTU00I CFTNET _ Correct (MODE=REPLACE,ID=TCP0,MAXCNX=32,CALL=INOUT,TYPE=TCP</p>
            <p>CFTU00I ,HOST=INADDR_ANY)</p>
            <p>CFTU00I CFTPROT _ Correct (MODE=REPLACE,ID=PESITANY,NET=TCP0,TYPE=PESIT,PROF=</p>
            <p>CFTU00I ANY,CONCAT=YES,SEGMENT=YES,MULTART=YES,SCOMP=0,RCO</p>
            <p>CFTU00I MP=0,SCHKW=2,RCHKW=2,SPACING=512,RPACING=512,SAP=6</p>
            <p>CFTU00I 5535,RRUSIZE=32000,SRUSIZE=32000,RTO=250,DISCTC=40</p>
            <p>CFTU00I 0,DISCTD=200,DISCTR=10,DISCTS=400)</p>
            <p>CFTU00I CFTPART _ Correct (MODE=REPLACE,ID=BOUCLE,NSPART=LOOP,NRPART=LOOP,PRO</p>
            <p>CFTU00I T=PESITANY,SAP=65535,SYST='OS400')</p>
            <p>CFTU00I CFTTCP _ Correct (MODE=REPLACE,ID=BOUCLE,CNXOUT=16,CNXIN=16,CNXINOUT</p>
            <p>CFTU00I =16,HOST=127.0.0.1)</p>
            <p>CFTU00I CFTPART _ Correct (MODE=REPLACE,ID=CIBLE,NSPART=AS400,NRPART=CIBLE,PR</p>
            <p>CFTU00I OT=PESITANY,SAP=65531,SYST='OS400')</p>
            <p>CFTU00I CFTTCP _ Correct (MODE=REPLACE,ID=CIBLE,CNXOUT=16,CNXIN=16,CNXINOUT=</p>
            <p>CFTU00I 16,HOST=CIBLE)</p>
            <p>CFTU00I CFTSEND _ Correct (MODE=REPLACE,ID=TSTIMPL,IMPL=YES,FNAME='QGPL/QAUOO</p>
            <p>CFTU00I PT',EXEC='*LIBL/CFTSRC(B_EXECSIMP)',FCODE=EBCDIC)</p>
            <p>CFTU00I CFTSEND _ Correct (MODE=REPLACE,ID=TSTNCOMP,IMPL=NO,FCODE=EBCDIC,NCOM</p>
            <p>CFTU00I P=0)</p>
            <p>CFTU00I CFTSEND _ Correct (MODE=REPLACE,ID=IDFDEFT,IMPL=NO,FCODE=EBCDIC)</p>
            <p>CFTU00I CFTRECV _ Correct (MODE=REPLACE,ID=SRC400,FTYPE='S',FDISP=BOTH,FACTIO</p>
            <p>CFTU00I N=ERASE,FCODE=EBCDIC,FRECFM='F',FNAME='CFTPROD/UT</p>
            <p>CFTU00I IN(R_?PARM)')</p>
            <p>CFTU00I CFTRECV _ Correct (MODE=REPLACE,ID=SRCFILE,FDISP=BOTH,FACTION=ERASE,F</p>
            <p>CFTU00I CODE=EBCDIC,FRECFM='F',FNAME='CFTPROD/UTIN(R_?PAR</p>
            <p>CFTU00I M)')</p>
            <p>CFTU00I CFTRECV _ Correct (MODE=REPLACE,ID=COMMUT,FDISP=BOTH,FACTION=DELETE,F</p>
            <p>CFTU00I CODE=BINARY,FRECFM='V',FSPACE=65535,FNAME='CFTPROD</p>
            <p>CFTU00I P/R_?IDTU')</p>
            <p>CFTU00I CFTRECV _ Correct (MODE=REPLACE,ID=IDFDEFT,FDISP=BOTH,FACTION=DELETE</p>
            <p>,</p>
            <p>CFTU00I FCODE=EBCDIC,FRECFM='F',FSPACE=65535,FNAME='CFTPROD</p>
            <p>CFTU00I /R_?IDTU')</p>
            <p>CFTU00I CFTRECV _ Correct (MODE=REPLACE,ID=SAVEFILE,FDISP=BOTH,FACTION=DELETE</p>
            <p>CFTU00I ,FCODE=BINARY,FTYPE='Z',FNAME='CFTPROD/R_?IDTU')</p>
            <p>CFTU00I RETURN _ Correct (CODE=0)</p>
            <p>CFTU20I Number of Command(s) 18</p>
            <p>CFTU20I Number of error(s) 0</p>
            <p>CFTU20I Ending Session on 02/04/2013 Time is 09:29:25</p>
            <p>CFTU20I Session active for 0:00:01</p>
         </td>
      </tr>
   </tbody>
</table>

An interpretation is considered to be valid when all messages are displayed as Correct.

If an interpretation error is detected, modify the invalid parameter or parameter, and select **2 Repeat the interpretation**. When you select 2 Repeat the interpretation, only messages concerning configuration commands are displayed.
