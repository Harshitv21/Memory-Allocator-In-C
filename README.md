# Memory Allocator in C

<p align="left">
      <a href="https://code.visualstudio.com/">
         <img alt="Vs Code Badge" title="Vscode" src="https://custom-icon-badges.demolab.com/badge/Made%20with-vscode-blue?style=for-the-badge&logo=visualstudiocode&logoColor=white"/></a>
      <a href="https://learn.microsoft.com/en-us/windows/wsl/install">
         <img alt="WSL Badge" title="WSL" src="https://custom-icon-badges.demolab.com/badge/-WSL-blue?style=for-the-badge&logo=linux&logoColor=black"/></a>
</p>

The goal of this project was to implement a pretty basic memory allocator to better understand the memory allocation by writting our own `malloc()`, `calloc()`, `realloc()` and `free()`. <br/>
By implementing these functions on our own we will be able to understand the intuition behind the working of these functions.

## Docs

A step-by-step beginner friendly guide can be found [here](https://github.com/Harshitv21/Memory-Allocator-In-C/blob/main/Docs/Memory%20Allocator.md) for anyone who wants to implement or try it for yourself. <br/>
Source code for this project can be found [here](https://github.com/Harshitv21/Memory-Allocator-In-C/blob/main/src/memAlloc.c).

## Compiling and using our memory allocator

We’ll be compiling our memory allocator and then run a utility like **ls** using our memory allocator.

First compile it as a library file.

```bash
$ gcc -o memAlloc.so -fPIC -shared memAlloc.c
```

Set the environment variable `LD_PRELOAD` to the path of a shared object, this way our file will be loaded before any other library.

```bash
$ export LD_PRELOAD=$PWD/memAlloc.so
```

Now to test,

```bash
$ ls
memAlloc.c		memAlloc.so
```

And now our memory allocator is serving `ls`!.
