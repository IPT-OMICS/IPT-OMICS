Cluster Structure
=================

The HPC cluster OMICS was formed with the help of institut pasteur de tunis et institut pasteut de paris . 



.. _structure-hardware:

Hardware
--------

.. _fig-cluster-structure:

.. graphviz:: cluster.dot

There are 3 main parts to the cluster, as shown in the :ref:`cluster diagram <fig-cluster-structure>` above: 

* **Administrative nodes**

  **Master** - Cluster management node, for privileged users only.

* **Service nodes**

  **NFS** - File servers for home and research storage.

* **Worker nodes**

  **Compute** - Total figures for current hardware in operation are:


  +------------------+---------+
  |Physical Cores    | 120     |
  +------------------+---------+
  |Total RAM (GB)    | 750     |
  +------------------+---------+
  |Total Storage (TB)| 95      |
  +------------------+---------+

  All CPU's are Intel, x86_64 or 64 bit architecture, and all of nodes uses the same number of cpu.

  The highest memory node in the cluster has 380GB of RAM .

  .. tip::

     It is safe to assume you can address 2GB of memory per *slot* when profiling jobs on the cluster. See :doc:`Running Jobs <batch>` for more infomation about *slots* and how to allocate resources for your job.

  .. tip::

     When running batch jobs, the *scheduler* will distribute your work to the compute nodes. You don't interact with the nodes directly. Alternatively, the batch system allows you to use the system :doc:`interactively <interactive>`, i.e. perform tasks in a shell environment.

.. _hardware-gpu-nodes:

  **GPU** - There are currently 5 GPU nodes on the cluster:

  +-----------+---------------------+------------------+
  | Node      | GPU Model           |     Memory    |
  +===========+=====================+==================+
  | node01    | 4x Nvidia Tesla M10 | 8GB per card  |
  +-----------+---------------------+------------------+
  | node02    | 4x Nvidia Tesla M10 | 8GB per card  |
  +-----------+---------------------+------------------+
  | node03    | 4x Nvidia Tesla M10 | 8GB per card  |
  +-----------+---------------------+------------------+
  | node04    | 4x Nvidia Tesla M10 | 8GB per card  |
  +-----------+---------------------+------------------+
  | node05    | 4x Nvidia Tesla M10 | 8GB per card  |
  +-----------+---------------------+------------------+
  +===========+=====================+==================+


Operating System
----------------

- `Scientific Linux <http://scientificlinux.org/>`_
- `Ubuntu <https://ubuntu.com>`_


