{
    "title": "Building API in C",
    "linkTitle": "Building API in C",
    "weight": "280"
}# <span id="Building_API_in_C"></span>Building an API in C

This section explains how to build Transfer CFT API samples in C. You can also refer to the Transfer CFT *User Guide [About APIs](../../../../about_this_document_zos/using_apis) topics* for information such as links to sample files.

The API samples and the makefile used to build them are located in your Transfer CFT &lt;installdir>\\runtime\\src\\capi directory.

## Prerequisites

The following steps require that you have Microsoft Visual Studio (VS) and a compiler, such as Visual C++, installed on your computer.

## Procedure

1.  From the Windows Start menu, select **All programs > Axway software > \[Transfer CFT name\] > Transfer CFT > Command Prompt**.  
    This opens a command window, which executes profile.bat.
2.  In the same command window, initialize the VS environment by executing the appropriate vcvarsall.bat based on your system architecture.
    -   Windows 32 bits: `<ProgramFiles>\<VS directory>\VC\vcvarsall.bat x86`
    -   Windows 64 bits: `<ProgramFiles>\<VS directory>\VC\vcvarsall.bat amd64`
    -   Windows Itanium: `<ProgramFiles>\<VS directory>\VC\vcvarsall.bat ia64`
3.  To set the CPU environment variable enter the following command based on your Transfer CFT architecture.
    -   Windows 32 bits:     `set CPU=X86`
    -   Windows 64 bits:     `set CPU=AMD64`
    -   Windows Itanium: ` set CPU=IA64`
4.  Go to the directory containing the C source files and makefile:
5.  Enter the command:

## Results

The nmake command generates the following as either 32-bit or 64-bit executable programs, depending on the Transfer CFT architecture. The current directory contains the generated object files and executable programs:

-   api2xmp1.exe
-   api2xmp2.exe
-   apisampl.exe
-   tcftsyn.exe
-   utisyn.exe

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>cd %CFTDIRINSTALL%\runtime\src\capi          </td>
      </tr>
   </tbody>
</table>

## Remove generated files

To remove all of the generated .obj and .exe files, enter the command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><code>nmake /f capi.mak</code>
         </td>
      </tr>
   </tbody>
</table>
