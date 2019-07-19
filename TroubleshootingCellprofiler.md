# 2019-07-01 - KBW - Troubleshooting CellProfiler Installation

When initially trying to use CellProfiler, I had some issues during the installation process. This was primarily due to the fact that CellProfiler only uses Python 2.7 (They are developing a new version that will be built on Python 3) and is fairly sensitive to versions of libraries it needs. Also, I was having some issues with permissions as well. I will walk through these issues here.

## Pay attention to pip version

One subtle mistake that person could make during the installation process is not using the correct version of pip. Given that there are separate versions of pip for Python 2.7 and for Python 3, you could just be mistakenly trying to install CellProfiler with the wrong version of pip. I say this because the command install CellProfiler is this:

```bash
user@comp5:~/Cellprofiler$ pip install -e .
```

Seems pretty straightforward but that assumption could lead to some trouble. The `pip` command could be specifying either pip for python 2.7 or some version of python3. There should be a `pip2.7` command to specify which of the two versions you are trying to use. Use this command. If you do not do this, you will likely get an error saying that you do not have the correct version of Python and you will be confused.

This also applies to prerequisite libraries you are installing as well.

## Permission Errors

Another issue that you might run into when installing is permission errors. Here is what I got when I ran the command for installation suggested by CellProfiler documentation:

```bash
user@comp5:~/Cellprofiler$ pip2.7 install -e .

ERROR: Could not install packages due to an EnvironmentError: [Errno 13] Permission denied: '/usr/bin/cellprofiler'
Consider using the `--user` option or check the permissions.
```

You can try to run it with the `--user` flag as suggested but this is what I got when I did that:

```bash
user@comp5:~/Cellprofiler$ pip2.7 install -e . --user

ERROR: Could not install packages due to an EnvironmentError: [Errno 13] Permission denied: '/usr/bin/cellprofiler'
Check the permissions.
```

The only way that I was able to get by these permission errors was to install it using sudo:

```bash
user@comp5:~/Cellprofiler$ sudo pip2.7 install -e .
```

## Libraries having been installed incorrectly or in an incompatible manner

Now this is where a installation complication lies. Proper installation of certain libraries and packages is incredibly important on RedHat systems and it really matters here. If you do not so this you will get an error that looks like this:

```bash
Notice: /Stage[main]/Neutron::Db::Sync/Exec[neutron-db-sync]/returns: ImportError: cannot import name UnrewindableBodyError Error: /Stage[main]/Neutron::Db::Sync/Exec[neutron-db-sync]: Failed to call refresh: neutron-db-manage upgrade heads returned 1 instead of one of [0] Error: /Stage[main]/Neutron::Db::Sync/Exec[neutron-db-sync]: neutron-db-manage upgrade heads returned 1 instead of one of [0] Notice: /Stage[main]/Neutron::Deps/Anchor[neutron::service::begin]: Triggered 'refresh' from 1 events Error: Failed to apply catalog: Execution of '/usr/bin/nova-manage cell_v2 list_cells --verbose' returned 1: Traceback (most recent call last): File "/usr/bin/nova-manage", line 6, in <module> from nova.cmd.manage import main File "/usr/lib/python2.7/site-packages/nova/cmd/manage.py", line 77, in <module> from nova.api.ec2 import ec2utils File "/usr/lib/python2.7/site-packages/nova/api/ec2/ec2utils.py", line 25, in <module> from nova import cache_utils File "/usr/lib/python2.7/site-packages/nova/cache_utils.py", line 22, in <module> import nova.conf File "/usr/lib/python2.7/site-packages/nova/conf/__init__.py", line 27, in <module> from nova.conf import cinder File "/usr/lib/python2.7/site-packages/nova/conf/cinder.py", line 16, in <module> from keystoneauth1 import loading as ks_loading File "/usr/lib/python2.7/site-packages/keystoneauth1/loading/__init__.py", line 13, in <module> from keystoneauth1.loading import adapter File "/usr/lib/python2.7/site-packages/keystoneauth1/loading/adapter.py", line 13, in <module> from keystoneauth1 import adapter File "/usr/lib/python2.7/site-packages/keystoneauth1/adapter.py", line 18, in <module> from keystoneauth1 import session File "/usr/lib/python2.7/site-packages/keystoneauth1/session.py", line 26, in <module> import requests File "/usr/lib/python2.7/site-packages/requests/__init__.py", line 43, in <module> import urllib3 File "/usr/lib/python2.7/site-packages/urllib3/__init__.py", line 8, in <module> from .connectionpool import ( File "/usr/lib/python2.7/site-packages/urllib3/connectionpool.py", line 35, in <module> from .connection import ( File "/usr/lib/python2.7/site-packages/urllib3/connection.py", line 44, in <module> from .util.ssl_ import ( File "/usr/lib/python2.7/site-packages/urllib3/util/__init__.py", line 4, in <module> from .request import make_headers File "/usr/lib/python2.7/site-packages/urllib3/util/request.py", line 5, in <module> from ..exceptions import UnrewindableBodyError ImportError: cannot import name UnrewindableBodyError
```

If you have `urllib3` installed via pip, and `requests` installed via yum you will have this issue, even if you have the correct packages installed. The same will apply if you have `urllib3` installed via yum, and `requests` installed via pip. Here's what I did to fix the issue (__Again, Make sure that you are installing for the correct version of Python__):

```bash
sudo pip2.7 uninstall requests

sudo pip2.7 uninstall urllib3

sudo yum remove python-urllib3

sudo yum remove python-requests

# confirm that all those libraries have been removed

sudo yum install python-urllib3

sudo yum install python-requests
```

Just be aware that this will only work for systems that are running Fedora, Redhat, or CentOS.
