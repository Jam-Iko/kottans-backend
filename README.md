# kottans-backend

## Git and GitHub

I have read about Git before, but I have never tried running it in Terminal or for my projects, so the actual hands-on experience was new.

I was surprised that Git can be a safety net and a trap at the same time - you can use it to explore, to fix bugs, to time travel basically, but it also benevolently allows you to lose your progress with some "push --force", as if confirming "Yes, you can take this ride... to misery".


## Unix Shell

![Linux Survival completed](task_unix_shell/Module4.png)

My previous experience with CLI was limited to basic commands (i.e. Modules 1-2 of Linux Survival), so almost anything beyond that point was new to me. 

I found that expansions (especially brace expansions) were surprisingly fun. Another element of surprise (okay, not that surprising) was that I need to adopt better directory naming practices, since it took me a fair amount of attempts to effectively move files between directories, with most of my attempts ending up with "No such file or directory".

I was particularly interested in redirection commands and want to use them asap.


## Git Collaboration

![Udacity GitHub Collaboration](task_git_collaboration/Udacity_GitHub.png)

Practiced creating pull requests again. Enjoyed CS50 reunion. 

Got a better understanding of `git rebase -i`. 
[Learn Git Branching](learngitbranching.js.org) is starting to make a lot more sense :laughing:. 

Found some neat flags that I intend to use in my work, such as `--grep` or `git log --oneline --graph --decorate --all`.


## Python Basics 1

[HackerRank profile](https://www.hackerrank.com/jamie_ikonnikova)

Even though it took me the longest time to complete this section, I appreciate the challenge and strongly believe that practicing exercises from both sets of assignments made me a better programmer.

I have especially liked [Code Wars](https://www.codewars.com), because this resource encourages you to come up with concise and beautiful solutions, as well as [Practice Python](https://www.practicepython.org), because along with the fun exercises the materials were very helpful. 

Among new things I have encountered, were python libraries BeautifulSoup and requests. 

I was surprised at how much I’ve started to appreciate the list/dictionary comprehensions. 

I intend to use whatever is the most appropriate and applicable solution for the problems I encounter :)


## Memory Management

* What's going to happen if program reaches maximum limit of stack ?

The program receives a Segmentation Fault that occurs due to stack overflow.

* What's going to happen if program requests a big (more then 128KB) memory allocation on heap ?

In Linux, if you request a large block of memory via malloc(), the C library will create such an anonymous mapping instead of using heap memory.

* What's the difference between Text and Data memory segments ?

The text segment has r-x priviledges, is read-only, stores all of the code and literals. The text segment maps binary file in memory, but writes to this area earn your program a Segmentation Fault.
The data segment holds the contents for static and global variables initialized in source code.


<details><summary>vmmap output</summary>
<p>

```
REGION TYPE                      START - END             [ VSIZE  RSDNT  DIRTY   SWAP] PRT/MAX SHRMOD PURGE    REGION DETAIL
__DATA                 0000000101252000-0000000101260000 [   56K    48K    48K     8K] rw-/rwx SM=COW          /bin/bash
Kernel Alloc Once      000000010126a000-000000010126c000 [    8K     4K     4K     0K] rw-/rwx SM=COW          
MALLOC metadata        000000010126d000-000000010126e000 [    4K     4K     4K     0K] rw-/rwx SM=COW          
MALLOC metadata        000000010126f000-0000000101273000 [   16K    16K    16K     0K] rw-/rwx SM=COW          
MALLOC metadata        0000000101275000-0000000101279000 [   16K    16K    16K     0K] rw-/rwx SM=COW          
MALLOC_LARGE           000000010127b000-0000000101296000 [  108K     8K     8K   100K] rw-/rwx SM=COW          DefaultMallocZone_0x10126c000
MALLOC_LARGE (empty)   00000001012d7000-00000001012e8000 [   68K     0K     0K    68K] rw-/rwx SM=COW          
__DATA                 0000000108ea6000-0000000108edf000 [  228K     8K     8K    20K] rw-/rwx SM=COW          /usr/lib/dyld
MALLOC_TINY            00007f91bb400000-00007f91bb800000 [ 4096K   444K   444K   120K] rw-/rwx SM=COW          DefaultMallocZone_0x10126c000
MALLOC_SMALL           00007f91bb800000-00007f91bd800000 [ 32.0M    88K    88K   128K] rw-/rwx SM=COW          DefaultMallocZone_0x10126c000
Stack                  00007ffeee230000-00007ffeeea30000 [ 8192K    16K    16K    16K] rw-/rwx SM=COW          thread 0
__DATA                 00007fffa7dac000-00007fffa7dad000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/libSystem.B.dylib
__DATA                 00007fffa7dd8000-00007fffa7de0000 [   32K    24K    12K     0K] rw-/rwx SM=COW          /usr/lib/libc++.1.dylib
__DATA                 00007fffa7de0000-00007fffa7de4000 [   16K    12K     0K     4K] rw-/rwx SM=COW          /usr/lib/libc++abi.dylib
__DATA                 00007fffa80bb000-00007fffa80bf000 [   16K     4K     4K     0K] rw-/rwx SM=COW          /usr/lib/libncurses.5.4.dylib
__DATA                 00007fffa8258000-00007fffa83e5000 [ 1588K   712K    24K     8K] rw-/rwx SM=COW          /usr/lib/libobjc.A.dylib
__DATA                 00007fffa8655000-00007fffa8656000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libcache.dylib
__DATA                 00007fffa8656000-00007fffa8658000 [    8K     8K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libcommonCrypto.dylib
__DATA                 00007fffa8658000-00007fffa865a000 [    8K     0K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libcompiler_rt.dylib
__DATA                 00007fffa865a000-00007fffa865b000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libcopyfile.dylib
__DATA                 00007fffa865b000-00007fffa8664000 [   36K    12K     0K     4K] rw-/rwx SM=COW          /usr/lib/system/libcorecrypto.dylib
__DATA                 00007fffa866e000-00007fffa8687000 [  100K    44K     8K     8K] rw-/rwx SM=COW          /usr/lib/system/libdispatch.dylib
__DATA                 00007fffa8687000-00007fffa868b000 [   16K    16K     8K     0K] rw-/rwx SM=COW          /usr/lib/system/libdyld.dylib
__DATA                 00007fffa868b000-00007fffa868c000 [    4K     0K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libkeymgr.dylib
__DATA                 00007fffa868d000-00007fffa868e000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libmacho.dylib
__DATA                 00007fffa868e000-00007fffa868f000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libquarantine.dylib
__DATA                 00007fffa868f000-00007fffa8690000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libremovefile.dylib
__DATA                 00007fffa8690000-00007fffa8692000 [    8K     8K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_asl.dylib
__DATA                 00007fffa8692000-00007fffa8693000 [    4K     0K     0K     4K] rw-/rwx SM=COW          /usr/lib/system/libsystem_blocks.dylib
__DATA                 00007fffa8693000-00007fffa869c000 [   36K    32K    16K     4K] rw-/rwx SM=COW          /usr/lib/system/libsystem_c.dylib
__DATA                 00007fffa869c000-00007fffa869d000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_configuration.dylib
__DATA                 00007fffa869d000-00007fffa869e000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_coreservices.dylib
__DATA                 00007fffa869e000-00007fffa86a1000 [   12K     8K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_darwin.dylib
__DATA                 00007fffa86a1000-00007fffa86a2000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_dnssd.dylib
__DATA                 00007fffa86a2000-00007fffa86a5000 [   12K    12K     8K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_info.dylib
__DATA                 00007fffa86a5000-00007fffa86a8000 [   12K    12K     4K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_kernel.dylib
__DATA                 00007fffa86a8000-00007fffa86a9000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_m.dylib
__DATA                 00007fffa86a9000-00007fffa86ac000 [   12K    12K     8K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_malloc.dylib
__DATA                 00007fffa86ac000-00007fffa86ae000 [    8K     8K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_networkextension.dylib
__DATA                 00007fffa86ae000-00007fffa86af000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_notify.dylib
__DATA                 00007fffa86af000-00007fffa86b0000 [    4K     4K     4K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_platform.dylib
__DATA                 00007fffa86b0000-00007fffa86b2000 [    8K     4K     4K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_pthread.dylib
__DATA                 00007fffa86b2000-00007fffa86b3000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_sandbox.dylib
__DATA                 00007fffa86b3000-00007fffa86b4000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_secinit.dylib
__DATA                 00007fffa86b4000-00007fffa86b5000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_symptoms.dylib
__DATA                 00007fffa86b5000-00007fffa86b7000 [    8K     8K     4K     0K] rw-/rwx SM=COW          /usr/lib/system/libsystem_trace.dylib
__DATA                 00007fffa86b7000-00007fffa86b8000 [    4K     4K     0K     0K] rw-/rwx SM=COW          /usr/lib/system/libunwind.dylib
__DATA                 00007fffa86b8000-00007fffa86bf000 [   28K    24K     8K     4K] rw-/rwx SM=COW          /usr/lib/system/libxpc.dylib
```

</p>
</details>

Memory Mapping Segment - `00007fffa7dac000-00007fffa7dad000`
Stack - `00007ffeee230000-00007ffeeea30000`
Heap - `000000010127b000-0000000101296000`


There was a lot of new information that still needs processing. I have regained respect for C with regard to memory management and became more conscious about Python's overhead. 