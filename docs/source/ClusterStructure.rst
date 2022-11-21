Cluster Structure
=================

The HPC cluster at Sussex was originally formed out of two separate clusters developed by IT Services (ITS) and the School of Mathematical and Physical Sciences (MPS). That later merged into what is now the university's cluster.

.. note::

   The hardware that makes up the compute nodes is quite varied, reflecting the number of different groups within the university that have contributed money and hardware at different times.

.. _structure-hardware:

Hardware
--------

.. _fig-cluster-structure:

.. graphviz:: cluster.dot

There are 3 main parts to the cluster, as shown in the :ref:`cluster diagram <fig-cluster-structure>` above: 

* **Administrative nodes**

  **Master** - Cluster management node, for privileged users only.

  **Login** - Your primary gateway to the cluster; for submitting your jobs.

* **Service nodes**

  **NFS** - File servers for home and research storage.

  **Lustre** - Specialised distributed file system for I/O intensive jobs.

  **Cluster** - Deployment, monitoring and other services for the cluster.

  **Grid** - GridPP infrastructure servers.

* **Worker nodes**

  **Compute** - Total figures for current hardware in operation are:

  +------------------+---------+
  |Logical Cores     | 3140    |
  +------------------+---------+
  |Physical Cores    | 3004    |
  +------------------+---------+
  |Total RAM (GB)    | 11941.3 |
  +------------------+---------+
  |Total Lustre (TB) | 270.8   |
  +------------------+---------+
  |Total NFS (TB)    | 60      |
  +------------------+---------+

  All CPU's are AMD64, x86_64 or 64 bit architecture, made up of a mixture of Intel and AMD nodes varying from 8 cores up to 64 cores per node.

  The highest memory node in the cluster has 512GB of RAM across 64 cores.

  .. tip::

     It is safe to assume you can address 2GB of memory per *slot* when profiling jobs on the cluster. See :doc:`Running Jobs <batch>` for more infomation about *slots* and how to allocate resources for your job.

  .. tip::

     When running batch jobs, the *scheduler* will distribute your work to the compute nodes. You don't interact with the nodes directly. Alternatively, the batch system allows you to use the system :doc:`interactively <interactive>`, i.e. perform tasks in a shell environment. You **must avoid** running jobs directly on the login nodes.

.. _hardware-gpu-nodes:

  **GPU** - There are currently 4 GPU nodes on the cluster:

  +-----------+---------------------+----------------------+---------------+---------------+
  | Node      | Hostgroup           | GPU Model            | CUDA Cores    | Memory        |
  +===========+=====================+======================+===============+===============+
  | node150   | @gpu_nodes_k20m     | 2x Nvidia Tesla K20m | 2496 per card | 4GB per card  |
  +-----------+---------------------+----------------------+---------------+---------------+
  | node151   | @gpu_nodes_k20m     | 2x Nvidia Tesla K20m | 2496 per card | 4GB per card  |
  +-----------+---------------------+----------------------+---------------+---------------+
  | node152   | @gpu_nodes_k20m     | 2x Nvidia Tesla K20m | 2496 per card | 4GB per card  |
  +-----------+---------------------+----------------------+---------------+---------------+
  | node153   | @gpu_nodes_k40m     | 4x Nvidia Tesla K40m | 2800 per card | 12GB per card |
  +-----------+---------------------+----------------------+---------------+---------------+

  **Grid** - Nodes dedicated to running jobs for GridPP infrastructure.

Operating System
----------------

- `Scientific Linux <http://scientificlinux.org/>`_
- `CentOS <http://www.centos.org/>`_

.. note::

   Currently all administrative and compute nodes use SL 6.5 (Carbon). Service nodes use a mix of SL and CentOS 6.5.
