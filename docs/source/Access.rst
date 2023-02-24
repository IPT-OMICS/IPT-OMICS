Accessing the Cluster
=====================

Request for Access
------------------

Access to the HPC cluster is not granted automatically.

You need to have the following prerequisites:

1. Be a registered member of Institut Pasteur de Tunis.
2. Have an active IT Services computing account.

To request for access, please email:

- Contact IPT IT Support Team 


Please include your  username, department, research group and supervisor's name (if applicable).


From Linux & OS X
-----------------

Once your account is set up, you can SSH to the login nodes using your *ITS username and password*:

First open your'e terminal

.. code-block:: bash

   ssh <username>@<host>

e.g. ``ssh -X ab123@192.168.100.211``, where ``<host>`` is ``192.168.100.211`` (the login node) and the *-X* option is to forward X sessions, see man page for SSH (``man ssh``).




.. Tip::
   
From Windows
------------

.. toctree::

   windows-login
   windows-file-transfer
   windows-mount-research-volumes

Connecting to the cluster using windows
-------------------------------------------
Once you have gained youre login information all you need to do is to install
putty from Putty<https://www.putty.org> 

After installing putty all you need to do is to type host name "IP address" and port "22" Enter your login information and password. 


When you connect via ssh, you can load the tools you need using module load command

example:::

 module load fastqc
 






Next Steps
----------

Once you can login to the login nodes, you then have a few options:

* See the :doc:`software` section for information about the
  cluster's provided software, such as compilers, SDKs, common
  programming libraries and packages, and other useful scientific
  software such as Matlab, R, Mathematica.
* To jump right in and start compiling, or testing your code runs on the
  cluster, read :doc:`interactive`.
* To start writing batch, or *headless* jobs for submission to the
  cluster see :doc:`running-jobs`.
