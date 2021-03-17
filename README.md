# FOX ToolKit precompiled
FOX ToolKit Website: http://www.fox-toolkit.org/

Good ToolKit, especially not bloated beyond imagination like Qt nor trying to be
more than what a ToolKit and fail like Qt. The only downside are ready to download
precompiled Windows shared and static libraries.

This repository here contains a precompiled FOX static library which already
include PNG and JPEG library statically linked. This way the FOX library can be
just statically linked and call it a day. A proper way is using FOX as shared
library but that would required trailing PNG and JPEG DLL alongside.

This static library is compiled and tested using Visual Studio 2019 Community Edition
on 64-Bit Windows. 32-Bit can be compiled too if required.

Future Plans? Turn this into a NuGet Package. We seriously need a FOX NuGet Package.

# Usage in Visual Studio 2019

In Project Settings Dialog apply these changes:
- "C/C++" -> "General" -> "Additional Include Directories": Add the path to "include" directory.
- "C/C++" -> "Preprocessor" -> "Preprocessor Definitions": Add to the list the following symbols:
  - WIN32
- "Linker" -> "General" -> "Additional Library Directories": Add the path to "lib" directory.
- "Linker" -> "Input" -> "Additional Dependencies": Add to the list "FOX-1.7.lib"
- Make sure you are using "Multithreaded DLL" runtime library

If all goes well you should be able now to compile your application with FOX
statically linked into the executable. There is no need to trail along a FOX DLL.
