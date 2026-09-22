# sses

sses command

Summary: Checks for SSE/SSE2/SSE3 availability.

Description

If you want to know if SSE, SSE2, and SSE3 are available in your processor, you may want to use this command. Note that it won't work on Linux systems as this command is not ready because it uses Windows call (IsProcessorFeaturePresent).

If you're going to explore more about this call, which is internally used in C++ Windows programs, see this doc: https://docs.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-isprocessorfeaturepresent

Command usage

* sses
