Accessing the Cluster
=====================

Request for Access
------------------

Access to the HPC cluster is not granted automatically.

You need to have the following prerequisites:

1. Be a registered member of University of Sussex.
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

After installing putty all you need to do is to type host name "IP address" Port "22"
type youre login and password

At the shell prompt type ``-bash-4.1$ ls -al``::

 -bash-4.1$ ls -al
 total 40
 drwxr-xr-x 17 its-username root     4096 Sep 18 12:52 .
 drwxr-xr-x 36 root  root     4096 Jul 30 16:40 ..
 -rw-------  1 its-username its-username_g 10073 Sep 19 09:22 .bash_history
 -rw-r--r--  1 its-username its-username_g   114 Sep 10 12:35 .bashrc
 drwx------  3 its-username its-username_g    23 Aug  2 12:15 .bright computing
 drwxr-xr-x  3 its-username its-username_g    18 Aug  2 12:17 .cm
 drwxr-xr-x  2 its-username its-username_g    27 Jul 30 07:59 .config
 drwx------  3 its-username its-username_g    24 Jul 28 10:22 .dbus
 drwxr-xr-x  2 its-username its-username_g     6 Aug  9 14:09 .felix
 drwxr-xr-x  2 its-username its-username_g     6 Aug 20 09:13 files
 drwx------  2 its-username its-username_g     6 Sep 16 09:12 .gconf
 drwx------  2 its-username its-username_g    24 Sep 16 09:13 .gconfd
 drwx------  4 its-username its-username_g    32 Aug  2 12:15 .gnome2
 drwx------  2 its-username its-username_g     6 Aug  2 12:15 .gnome2_private
 drwxr-xr-x  3 its-username its-username_g    19 Jul 30 07:58 .matlab
 drwxr-xr-x  4 its-username its-username_g    37 Aug  8 15:26 .mozilla
 drwx------  2 its-username its-username_g    53 Sep  4 15:24 .pulse
 -rw-------  1 its-username its-username_g   256 Aug  8 15:28 .pulse-cookie
 -rw-------  1 its-username its-username_g  1736 Sep 16 09:13 .recently-used.xbel
 drwx------  2 its-username its-username_g    76 Jul 31 11:15 .ssh
 drwxr-xr-x  2 its-username its-username_g    50 Jul 30 07:58 .subversion
 -rw-------  1 its-username its-username_g  2595 Sep 10 12:35 .viminfo
 -rw-------  1 its-username its-username_g  1677 Sep 18 12:52 .Xauthority

`

When you connect via ssh, you can load the tools you need using module load command

example:::

 module load fastqc
 module load gcc

 gcc is needed if you use gcc at all which is most people --
note if you don't load the gcc module, you will use the system's gcc
version which does not support the recent Inel cpus we have on certain
nodes.






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
