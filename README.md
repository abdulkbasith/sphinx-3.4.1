# sphinx-3.4.1

Sphinx is a free, dual-licensed search server. Sphinx is written in C++, and focuses on query performance and search relevance.

The primary client API is currently SphinxQL, a dialect of SQL. Almost any MySQL connector should work. Additionally, basic HTTP/JSON API and native APIs for a number of languages (PHP, Python, Ruby, C, Java) are provided.


indexer --all -> to initially create the indexes

indexer --all --rotate ->  to update the indexes

## Install Sphinx 3.4.1 on Centos 7

To install Sphinx 3.4.1, follow these steps:

1. Install the remi repository:

   yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y

2. Install the required dependencies:

   yum install -y gcc-c++ libtool automake mysql-devel mariadb-devel postgresql-devel unixODBC-devel

3. Download and extract the Sphinx source archive:

   cd /opt && wget http://sphinxsearch.com/files/sphinx-3.4.1-efbcc65-linux-amd64-glibc2.12.tar.gz && tar -xzvf sphinx-3.4.1-efbcc65-linux-amd64-glibc2.12.tar.gz

4. Copy the Sphinx binaries to `/bin/`:

   cp sphinx-3.4.1/bin/* /bin/ && cp /bin/searchd /bin/sphinx

5. Create the necessary directories:

   mkdir /etc/sphinx /var/lib/sphinx /var/lib/sphinx/data /var/log/sphinx

6. Reload the system daemon and start and enable the Sphinx service:

   systemctl daemon-reload
   systemctl start sphinx
   systemctl enable sphinx

   Once you have completed these steps, Sphinx will be installed and running on your system.

