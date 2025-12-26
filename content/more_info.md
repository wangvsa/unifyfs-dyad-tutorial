## Why Should I Care?

Scientific applications on HPC systems are generating and consuming data at unprecedented rates. As file sizes grow and access patterns become increasingly intensive, contention for shared parallel file systems has become a major bottleneck, limiting both application performance and system scalability. To address this challenge, modern HPC architectures—including the fastest supercomputers in the U.S., Japan, and Singapore—have adopted high-speed node-local storage technologies built on non-volatile memory (NVM). 
These local storage tiers offer improved I/O performance by eliminating shared contention and enabling bandwidth that scales with node count. However, their distributed and ephemeral nature makes them difficult to use directly, particularly for applications that expect a shared namespace or require standard POSIX interfaces.

This tutorial introduces practical techniques and tools that make it easier to leverage node-local storage for accelerating HPC I/O. We begin with an in-depth exploration of UnifyFS, a user-level, ephemeral file system that creates a unified file namespace across the node-local storage of all compute nodes in a job. UnifyFS allows applications to benefit from the performance of local storage without requiring modifications to application code or I/O libraries. It intercepts standard POSIX calls, providing transparent access to distributed files while supporting high-throughput, bursty I/O patterns common in scientific workloads. The tutorial will cover UnifyFS’s architecture, tunable I/O consistency semantics, integration with common HPC I/O libraries, and real-world deployment practices.

We'll then introduce DYAD, a data management system designed specifically for read-heavy workloads, such as deep learning and data analytics. Unlike traditional scientific simulations, deep learning training involves random access to large datasets, frequent data shuffling, and repeated full-dataset reads across multiple epochs. DYAD addresses these challenges through a locality-aware caching framework that leverages node-local storage and inter-node coordination. It introduces innovations such as streaming RPC over RDMA for high-performance data movement and coordinated file-level transfers to reduce redundant I/O. We explain how DYAD integrates with data loaders in PyTorch and demonstrate its performance advantages over conventional caching layers and parallel file systems.

Finally, we'll do a hands-on session where attendees will deploy and experiment with UnifyFS and DYAD in a controlled environment. Participants will run sample applications using MPI and AI frameworks, observe I/O performance with and without node-local storage, and gain practical experience configuring these systems. For accessibility, exercises will be supported through lightweight container-based environments that can be run locally on laptops, as well as on compatible external HPC systems.
Throughout the tutorial, we connect theoretical concepts to real-world practice, providing attendees with a deeper understanding of the I/O bottlenecks in HPC workflows and equipping them with actionable knowledge to apply node-local storage solutions in their own work.


## Materials:

The presentation slides will be distributed (as well as made publicly available online) to the audience during the tutorial. 

**UnifyFS:**

- Code: https://github.com/llnl/unifyfs
- Documentation: https://unifyfs.readthedocs.io/
- Tutorial at ECP 2022 Annual Meeting:
    - Slides: https://unifyfs.readthedocs.io/en/dev/_downloads/873468dca3dd4bcc322bc2645d5c71ca/UnifyFS-tutorial-May2022.pdf
    - Video: https://www.youtube.com/watch?v=FmQVJplyVdw&embeds_referring_euri=https%3A%2F%2Funifyfs.readthedocs.io%2Fen%2Fdev%2Foverview.html&feature=emb_imp_woyt

**DYAD:**
- Code: https://github.com/flux-framework/dyad
- Documentation: https://dyad.readthedocs.io/
- Tutorial at ECP 2023 Annual Meeting:
https://github.com/flux-framework/Tutorials/blob/8f38ba5116a5dad1b5c6bd6a63b6b80f5d042eef/2023-ECP/JupyterNotebook/ecp23-flux-dyad.ipynb#L10 
- Tutorial at JLESC 2024 Workshop:
https://github.com/flux-framework/Tutorials/blob/8f38ba5116a5dad1b5c6bd6a63b6b80f5d042eef/2024-RIKEN-AWS/JupyterNotebook/tutorial/notebook/04_dyad_dlio.ipynb 
