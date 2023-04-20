# Vision Document for Parallel ClamAV Project
**Created:**&nbsp;&nbsp; April 20<sup>th</sup>, 2023  
**Updated:**&nbsp; 04-20-23 @ 7:52 PM
---

&nbsp;
### Index of Contents

1. [Introduction](#1-introduction)
2. [Users & User-Level Goals]()
3. [Summary of System Features]()
4. [Project Risks]()
5. [Development Schedule]()

---


&nbsp;
## 1 &nbsp;&nbsp; Introduction

The following are some starting points related to the project's introduction:

**What is the project?**  

* A wrapper for the ClamAV (linux anti-virus) package that increases clamscan efficiency by enabling multi-processed scans, while
* Affecting ClamAV's originally intended interfacing & functionality as little as possible, and
* Making it as easy as possible for the user to set up and run parallel scans


**Why is the project?**

* ClamAV's clamscan only uses one process, on one thread/core, to complete a scan of the given directory, and there is no parallel scanning capability offered natively with clamscan
* ClamAV does offer a separate daemon package that implements clamdscan, a daemon version of clamscan that provides a multi-processing option; however, this option doesn't tend to work hassle free, if it does at all
* This forces users to have to suffer through single process scans, which can take an incredibly long time depending on the directories being scanned, their size, and the performance of the system's hardware
* Parallel-ClamAV intends to mitigate these issues


**How will be the project?**

* the parallel-clamav system will 'wrap' around the exisiting ClamAV package so that it can add new functionality while keeping all that ClamAV originally had to offer
* the system will add multi-processing functionality by breaking down desired scan process into atomic pieces that can be fed to parallelization manager
* parallelization manager starts a new process for each atomic piece, for as many threads are available to service the processes
* each concurrent process stores its scan's output such that only it can access the data at a given time
* once all processing has completed, data manager will go through data of each atomic piece and combine it into a single output for the user



&nbsp;
## 2 &nbsp;&nbsp; Users & User-Level Goals

...


&nbsp;
## 3 &nbsp;&nbsp; Summary of System Features

...


&nbsp;
## 4 &nbsp;&nbsp; Project Risks

...


&nbsp;
## 5 &nbsp;&nbsp; Development Schedule

...
