=======
CLOP++
=======

This is another implementation of a C++ command line parser.

The main difference is the way it's handling command line options. It doesn't use GNU option style with short and long options. Instead it uses the PowerShell style:

- There is no short or long options
- Instead if there is enough characters on an option for distinguishing from all other options, it will select this option. For example, if the command -"list"* has the following options:

  - verbose
  - details
  - date
  - folder
  - force

The command *"list -v"* will be understood as *"list -verbose" as *"verbose"* is the only option beginning with *"v"*. *"-ve"*, *"-ver"*, ..., *"-verbose"* are also valid.

The command *"list -d"* won't be understood as there are two options beginning with *"d"*. But *"list -da"* will be understood a *"list -date"*.

The same for *"force"* and *"folder"*, at least three letters are needed for distinguishing from the two options.


- This is a C++17 library
- It's a header only library


Requirements
------------

- The library uses *{fmt}* formatting library. If required, it will fetch it from the web
- It's built using *cmake*
- It works with Windows's *cl* (Visual Studio 2019), *clang* and *gcc*.
