+++
# This title is used as the og:title on Hugo's internal
# opengraph structured data template on the home page.
# See https://ogp.me/ and https://gohugo.io/templates/internal#open-graph.
title = "Home"
layout = "single"
+++

[<img src="https://www.sca-hpcasia2026.jp/img/common/img_logo.png" style="max-width:200px;float:right" alt="SCA Logo" />](https://www.sca-hpcasia2026.jp/index.html)

## SCA/HPAsia 2026 Tutorial: Accelerating HPC Application I/O with Fast Node-Local Storage

13:30 - 16:30, Mon, January 26, 2026 

Osaka International Convention Center, Osaka, Japan

**Presenters:**
- [Chen Wang](https://wangchen.io), Nanyang Technological University, Singapore
- [Jae-Seung Yeom](https://people.llnl.gov/yeom2), Computer Scientist, Lawrence Livermore National Laboratory, US
<!-- - [Michela Taufer](https://globalcomputing.group/about.html), Professor, University of Tennessee Knoxville, US -->

---

### Introduction

As HPC applications grow in complexity and scale, I/O (Input/Output) performance remains a persistent bottleneck. Many modern workloads, including coupled simulations, AI integration, and in-situ analytics generate and consume large volumes of data that stress shared parallel file systems. 
This tutorial introduces two tools, [UnifyFS](https://github.com/llnl/unifyfs) and [DYAD](https://github.com/flux-framework/dyad), for accelerating application I/O with fast node-local storage.

UnifyFS is a user-level file system that provides a shared namespace backed by node-local storage, enabling scalable, high-throughput I/O for write-heavy workloads. DYAD complements this by improving data locality of dependent workflow components (e.g., simulation and analysis) to speed up I/O performance for read-heavy workloads. 

This hands-on tutorial will guide participants through:
- The challenges of I/O performance at scale in HPC environments
- The design and capabilities of UnifyFS and DYAD
- How to deploy and configure these tools on HPC systems
- Integration with HPC applications (e.g., scientific simulations and AI training) and I/O libraries (e.g., MPI-IO, HDF5)
- Use cases demonstrating I/O acceleration

Participants will gain practical experience through exercises and real-world examples that highlight how to reduce I/O time, alleviate pressure on shared storage, and optimize coupled workflows.

### Target Audience

This tutorial is designed for a broad range of HPC practitioners, with a focus on beginner to intermediate-level attendees. Approximately 40% of the content will introduce core concepts and motivations for node-local storage systems in HPC, while the remaining 60% will explore intermediate topics such as integrating UnifyFS and DYAD into real applications, performance tuning, and deployment best practices.

*Prior experience with UnifyFS or DYAD is not required.*


### Tutorial Structure (Tentative)


| Time          | Event                                         |
| :-------------| :-------------------------------------------- |
| 13:30 - 14:00 | Introduction and Motivation                   |
| 14:00 - 14:35 | Deep Dive: UnifyFS                            |
| 14:35 - 14:50 | Break                                         |
| 14:50 - 15:25 | Deep Dive: DYAD                               |
| 15:25 - 16:15 | Hands-on Session and Interactive Walkthrough  |
| 16:15 - 16:30 | Wrap-up and Q&A                               |
