---
title: "ClangCompile Task | Microsoft Docs"
description: Describes the purpose and parameters of the MSBuild ClangCompile task, which wraps the C++ compiler tool, clang.exe.
ms.date: "03/10/2019"
ms.topic: "reference"
f1_keywords:
  - "vc.task.clangcompile"
dev_langs:
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords:
  - "MSBuild (C++), ClangCompile task"
  - "ClangCompile task (MSBuild (C++))"
author: tylermsft
ms.author: twhitney
ms.workload:
  - "multiple"
---
# ClangCompile task

Wraps the Microsoft C++ compiler tool, clang.exe.

## Parameters

The following table describes the parameters of the **ClangCompile** task.

|Parameter|Description|
|---------------|-----------------|
|**AdditionalIncludeDirectories**|Optional **string[]** parameter.<br/><br/>Specifies one or more directories to add to the include path; separate with semi-colons if more than one.<br/><br/>Use `-I[path]`.|
|**AdditionalOptions**|Optional **string** parameter.|
|**BufferSecurityCheck**|Optional **string** parameter.<br/><br/>The Security Check helps detect stack-buffer over-runs, a common attempted attack upon a program's security. <br/><br/>Use `fstack-protector`.|
|**BuildingInIde**|Optional **bool** parameter.|
|**CLanguageStandard**|Optional **string** parameter.<br/><br/>Determines the C language standard.<br/><br/>Use `std=[value]` with value of **c89**, **c99**, **c11**, **gnu99**, or **gnu11**.|
|**ClangVersion**|Optional **string** parameter.|
|**CompileAs**|Optional **string** parameter.<br/><br/>Select compile language option for .c and .cpp files. Default will detect based on .c or .cpp extention.<br/><br/>Use `-x c`, `-x c++`.|
|**CppLanguageStandard**|Optional **string** parameter.<br/><br/>Determines the C++ language standard.<br/><br/>Use `std=[value]` with value of **c++98**, **c++11**, **c++1y**, **gnu++98**, **gnu++11**, or **gnu++1y**.|
|**DataLevelLinking**|Optional **bool** parameter.<br/><br/>Enables linker optimizations to remove unused data by emitting each data item in a separate section.|
|**DebugInformationFormat**|Optional **string** parameter.<br/><br/>Specifies the type of debugging information generated by the compiler.<br/><br/>**None**, produces no debugging information, so compilation may be faster (use `g0`).<br/>**FullDebug**, generate DWARF2 debug information (use `g2 -gdwarf-2`).<br/>**LineNumber**, generate Line Number information only (use `gline-tables-only`).|
|**EnableNeonCodegen**|Optional **bool** parameter.<br/><br/>Enables code generation for NEON floating point hardware. This is applicable for arm architecture only.|
|**ExceptionHandling**|Optional **string** parameter.<br/><br/>Specifies the model of exception handling to be used by the compiler.<br/><br/>**Disabled**, disable exception handling (use `fno-exceptions`).<br/>**Enabled**, enable exception handling (use `fexceptions`).<br/>**UnwindTables**, generates any needed static data, but does not affect the code generated (use `funwind-tables`).|
|**FloatABI**|Optional **string** parameter.<br/><br/>Selection option to choose the floating point ABI.<br/><br/>**soft**, causes compiler to generate output containing library calls for floating-point operations (use `mfloat-abi=soft`).<br/>**softfp**, allows the generation of code using hardware floating-point instructions, but still uses the soft-float calling conventions (use `mfloat-abi=softfp`).<br/>**hard**, allows generation of floating-point instructions and uses FPU-specific calling conventions (use `mfloat-abi=hard`).|
|**ForcedIncludeFiles**|Optional **string[]** parameter.<br/><br/>One or more forced include files.<br/><br/>Use `-include [name]`.|
|**FunctionLevelLinking**|Optional **bool** parameter.<br/><br/>Allows the compiler to package individual functions in the form of packaged functions (COMDATs). Required for edit and continue to work.<br/><br/>Use `ffunction-sections`.|
|**GccToolChain**|Optional **string** parameter.<br/><br/>Folder path to Gcc Tool Chain.|
|**GNUMode**|Optional **bool** parameter.<br/><br/>|
|**MSCompatibility**|Optional **bool** parameter.<br/><br/>Enable full Microsoft C++ compatibility.|
|**MSCompatibilityVersion**|Optional **string** parameter.<br/><br/>Dot-separated value representing the Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default)).|
|**MSExtensions**|Optional **bool** parameter.<br/><br/>Accept some non-standard constructs supported by the Microsoft compiler.|
|**MSCompilerVersion**|Optional **string** parameter.<br/><br/>Microsoft compiler version number to report in _MSC_VER (0 = don't define it (default)).|
|**MSVCErrorReport**|Optional **bool** parameter.<br/><br/>Report errors which Visual Studio can use to parse for file and line information.|
|**ObjectFileName**|Optional **string** parameter.<br/><br/>Specifies a name to override the default object file name; can be file or directory name.<br/><br/>Use `/Fo[name]`.|
|**OmitFramePointers**|Optional **bool** parameter.<br/><br/>Suppresses creation of frame pointers on the call stack.|
|**Optimization**|Optional **string** parameter.<br/><br/>Specifies the optimization level for the application.<br/><br/>**Custom**, custom optimization.<br/>**Disabled**, disable optimization (use `O0`).<br/>**MinSize**, optimize for size (use `Os`).<br/>**MaxSpeed**, optimize for speed (use `O2`).<br/>**Full**, expensive optimizations (use `O3`).|
|**PositionIndependentCode**|Optional **bool** parameter.<br/><br/>Generate Position Independent Code (PIC) for use in a shared library.|
|**PrecompiledHeader**|Optional **string** parameter.<br/><br/>Enables creation or use of a precompiled header during the build.|
|**PrecompiledHeaderFile**|Optional **string** parameter.<br/><br/>Specifies header file name to use for precompiled header file. This file will be also added to **Forced Include Files** during build.|
|**PrecompiledHeaderOutputFileDirectory**|Optional **string** parameter.<br/><br/>Specifies the directory for the generated precompiled header. This directory will be also added to **Additional Include Directories** during build.|
|**PrecompiledHeaderCompileAs**|Optional **string** parameter.<br/><br/>Select compile language option for precompiled header file.<br/><br/>Use `-x c-header`, `-x c++-header`.|
|**PreprocessorDefinitions**|Optional **string[]** parameter.<br/><br/>Defines a preprocessing symbols for your source file.<br/><br/>Use `-D`.|
|**RuntimeLibrary**|Optional **string** parameter.<br/><br/>Specify runtime library for linking.<br/><br/>Use `MSVC /MT`, `/MTd`, `/MD`, `/MDd` switches.<br/><br/>**MultiThreaded**, causes your application to use the multithread, static version of the run-time library.<br/>**MultiThreadedDebug**, defines _DEBUG and _MT. This option also causes the compiler to place the library name LIBCMTD.lib into the .obj file so that the linker will use LIBCMTD.lib to resolve external symbols.<br/>**MultiThreadedDLL**, causes your application to use the multithread- and DLL-specific version of the run-time library. Defines _MT and _DLL and causes the compiler to place the library name MSVCRT.lib into the .obj file.<br/>**MultiThreadedDebugDLL**, defines _DEBUG, _MT, and _DLL and causes your application to use the debug multithread- and DLL-specific version of the run-time library. It also causes the compiler to place the library name MSVCRTD.lib into the .obj file.|
|**RuntimeTypeInfo**|Optional **bool** parameter.<br/><br/>Adds code for checking C++ object types at run time (runtime type information).<br/><br/>Use `frtti`, `fno-rtti`.|
|**ShowIncludes**|Optional **bool** parameter.<br/><br/>Generates a list of include files with compiler output.<br/><br/>Use `-H`.|
|**Sources**|Required **ITaskItem[]** parameter.|
|**StrictAliasing**|Optional **bool** parameter.<br/><br/>Assume the strictest aliasing rules. An object of one type will never be assumed to reside at the same address as an object of a different type.|
|**Sysroot**|Optional **string** parameter.<br/><br/>Folder path to the root directory for headers and libraries.|
|**TargetArch**|Optional **string** parameter.<br/><br/>Target Architecture.|
|**ThumbMode**|Optional **string** parameter.<br/><br/>Generate code that executes for thumb microarchitecture. This is applicable for arm architecture only.<br/><br/>**Thumb**, generate Thumb code (use `mthumb`).<br/>**ARM**, generate Arm code (use `marm`).<br/>**Disabled**, option not applicable for chosen platform.|
|**TrackerLogDirectory**|Optional **string** parameter.<br/><br/>Tracker Log Directory.|
|**TreatWarningAsError**|Optional **bool** parameter.<br/><br/>Treats all compiler warnings as errors.<br/><br/>For a new project, it may be best to use `/WX` in all compilations; resolving all warnings will ensure the fewest possible hard-to-find code defects.|
|**UndefinePreprocessorDefinitions**|Optional **string[]** parameter.<br/><br/>Specifies one or more preprocessor undefines.<br/><br/>Use `-U [macro]`.|
|**UndefineAllPreprocessorDefinitions**|Optional **bool** parameter.<br/><br/>Undefine all previously defined preprocessor values.<br/><br/>Use `-undef`.|
|**UseMultiToolTask**|Optional **bool** parameter.<br/><br/>Multi-processor Compilation.|
|**UseShortEnums**|Optional **bool** parameter.<br/><br/>Enum type uses only as many bytes required by input set of possible values.|
|**Verbose**|Optional **bool** parameter.<br/><br/>Show commands to run and use verbose output.|
|**WarningLevel**|Optional **string** parameter.<br/><br/>Select how strict you want the compiler to be about code errors. Other flags should be added directly to **Additional Options** (se `/w`, `/Weverything`).<br/><br/>**TurnOffAllWarnings**, disables all compiler warnings (use `w`).<br/>**EnableAllWarnings**, enables all warnings, including those disabled by default (use `Wall`).|

## See also

[Task reference](../msbuild/msbuild-task-reference.md)
