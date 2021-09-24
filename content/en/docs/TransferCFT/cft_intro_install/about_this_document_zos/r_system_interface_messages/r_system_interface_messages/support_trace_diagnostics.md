{
    "title": "Axway support files error diagnostics",
    "linkTitle": "Axway support files error diagnostics",
    "weight": "270"
}The following complementary diagnostics are available on request by Axway support using the SGTRACE tool.

-   SGTRACE 4:
    -   Traces the file read/write actions. This value must be used for codes S=0 and S=9
-   SGTRACE 8:
    -   Traces the file read/write actions. This value must be used for codes S=4, 8, C, F
-   SGTRACE 2: traces the errors

<!-- -->

-   SGTRACE 128: traces the module calls and returns

The modules concerned are:

-   S=0: SGF3ACC, SGF3STAT, SIFM, SGF3VSAM, SGF3REN

<!-- -->

-   S=9: SGF3SV99

<!-- -->

-   S=4, 8, C, F: SGF3C, SIDM

Related topics

[About the operator interface commands](../../../t_start_servers_jobs_zos/t_system_environment_zos/r_about_operator_interface_commands)

[Diagnostic commands](../../../t_start_servers_jobs_zos/t_system_environment_zos/c_diagnostic_commands)
