# Subtle Interactions

This page contains information on subtle interactions that are part of `ccf`.

## Environment Isolation

Environment isolation can include some subtle and surprising behavior.

### Different dynamic loaders between AFL and concolic execution

When using AFL's forkserver (as we do), the forkserver is launched outside of the isolated environment, and thus, the dynamic loader of the host system will be used to load the binary.
When using concolic execution, the binary is launched inside the isolated environment, and will thus look for the dynamic loader inside this environment.

This also means that running a binary that is not completely static with concolic execution and environment isolation requires a dynamic loader inside the isolated environment, as well as all dynamic libraries that the binary requires.
Otherwise, a `"file not found"` error will occur, which can be confusing, given that the binary itself exists, but this is due to either the dynamic loader or a required dynamic library missing.
