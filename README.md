##PROJECT DOCUMENTATION

# Iter-mpi-matrix-vetor.py:
The code can be run using the following command:


$mpirun -n 4 python Iter-mpi-matrix-vetor.py

-argument following '-n' is a integer that defines the number of parallel processors to run the code logic on.
-prints out the running time of each node
-code consists of comments.


# StarCluster and Mpich2 Configurations:
Following are the configurations that the StarCluster on our EC2 instance is running on. These values can be changed in the ".starcluster/Config" file under [aws info]:

###########
[aws info]
AWS_ACCESS_KEY_ID =#your_aws_access_key_id
AWS_SECRET_ACCESS_KEY = #your_secret_access_key
AWS_USER_ID=#your userid

[key mykey]
KEY_LOCATION=~/.ssh/mykey.rsa

[cluster smallcluster]
KEYNAME = mykey
CLUSTER_SIZE = 8
CLUSTER_USER = sgeadmin
CLUSTER_SHELL = bash
NODE_IMAGE_ID = ami-3393a45a
NODE_INSTANCE_TYPE = t1.micro
MASTER_INSTANCE_TYPE = t1.micro
PLUGINS = mpich2
##########


# How to run the program:

1.Log into th EC2 instance using: "ssh -i my_key.pem host@server-name"

2.Start your already created cluster by using: "starcluster start -x cluster-name"

3.If you have previously not created a cluster use this: "starcluster start cluster-name" 

4.Once cluster has started type: $ su - sgeadmin

5.Now you may run your .py file using the method stated under "Iter-mpi-matrix-vetor.py" heading of this page.






