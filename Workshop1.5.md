  

# Provisioning of a BDCS-CE service instance


    Note: if you are an Oracle employee following the GainAccessToGSECloud instructions to use a GSE Deal Server, you can skip this lab and move to lab 300.


## Introduction

In this lab, you learn how to provision a **Oracle Big Data Cloud Service - Compute Edition (BDCS-CE)** cluster.  

The Oracle Big Data Cloud Service - Compute Edition (BDCS-CE) enables you to rapidly, securely, and cost-effectively leverage the power of an elastic, integrated Big Data Infrastructure to unlock the value in Big Data.   In this lab, we will walk you through the steps to quickly configure and create a Big Data Cloud Service instance.  When done you will see how to view the configuration and layout of your instance using the Oracle Big Data Console, the Ambari management interface and how to access your instance using SSH to your servers using a command line terminal.  The tutorial will also show how to add additional nodes to a Hadoop cluster, monitor jobs, set access rules, modify configuration settings and view activity on the Hadoop cluster.  



## Objectives

- Learn how to provision a BDCS-CE instance
- Learn how to access BDCS-CE

## Required Artifacts

- Access to an Oracle Public Cloud identity domain (by following GainAccessToCloud or GainAccessToGSECloud)
- A provisioned Storage Cloud instance (included the Replication Policy setup, as described in GainAccessToCloud or GainAccessToGSECloud)

# Provision a new BDCS-CE Instance

## Provision BDCS-CE

### **STEP 1**: Navigate/login to the Oracle Cloud My Services Dashboard  

- ![](images/300/snap0011988.jpg) 

### **STEP 2**: Click the Create Instance link (in the Create Instance box under the Welcome layer)

### **STEP 3**: Click All Services, then click Create next to Big Data - Compute Edition

- ![](images/200/DashboardCreate.gif)  

### **STEP 3**: Click Create Service on the BDCS-CE services page

- ![](images/200/snap0012020.jpg)  

### **STEP 4**: Fill in the Service Name and Description and click Next

- ![](images/200/snap0012021.jpg)  

### **STEP 5**: In the Cluster Configuration section, choose **Full** for the Deployment Profile and choose **1** for the Number of Nodes.

- ![](images/200/BDCScreate1.gif)  


### **STEP 6**: In the Credentials section, define your SSH public key and the desired username/password to use for the BDCS-CE cluster administrator.

- SSH Public Key: Define a value for a VM Public Key, use a file with a VM Public Key or create a new key. The easiest choice if new to this environment may be to create a new key. Choose to Create a New Key and hit the Enter button.   Once you hit Enter, a File Folder Window will pop up to allow you to control where on your local computer you wish to store your SSH Key file (ex: sshkeybundle.zip).  Make sure and write down the location of this SSH key file.   The SSH Public Key field will then get filled in automatically.
= Administrative User: Define the user id for the administration user for your instance. (We suggest you leave it at its default: bdcsce_admin)
- Password: Enter a password to set for the administration user.
- Confirm Password: Verify the password for the administration user.
- ![](images/200/BDCScreate2.gif)  

### **STEP 7**: In the Cloud Storage Credentials section, XXXXXXXXXX.

- ![](images/200/BDCScreate3.gif)  

### **STEP 8**: In the Associations section, leave the checkboxes unchecked for now.

- Associations will automatically create the necessary Access Rules between services.  For this workshop, we'll show you how to manually define Access Rules at a later point.

### **STEP 9**: Click Next.

### **STEP 10**: Click Create.

- ![](images/200/snap0012022.jpg)  

### **STEP 11**: Wait for the BDCS-CE instance to be provisioned.

- While being provisioned, the Status will say "Creating service".  You can click on the status to get more information.
- As of 17.2.5, it can take about 15-20 minutes to finish creating the service.
- ![](images/200/snap0012023.jpg)  

### **STEP 12**: When the BDCS-CE instance is provisioned, click on the name of the instance to go to the Service Overview page.
- ![](images/200/snap0012069.jpg)  

### **STEP 13**: Review the details on the Service Overview Page
Sections include:
- Overview – displays the number of nodes, aggregate OCPU, Memory, and Storage
- Administration – displays if there are any patches available.
- Services Overview – displays summary information of the new Big Data Cloud Service.  This includes the Ambari Server Host whose IP address you can use to access Ambari from a URL in a browser.  As well as highlighting the Administrative user you created as well as the Cloud Storage Container and the Spark Thrift Server (part of the default configuration).  Ambari is a Hadoop management web UI that can accessed through your Ambari Host Server IP address and port 8080 (ex:  http://xxx.xxx.xxx.xxx:8080).  Note: to use Ambari, you will need to enable a Network Access rule for port 8080.  Also, your Ambari credentials will be your BDCS-CE username and password you defined when you created this instance. 
- Resources – displays information on the resources associated with your Service.  As you scale out and add more nodes, the new nodes as well as their Public IP address, OCPUs, Memory and Storage will be displayed.
- Associations – displays information on any additional resources associated with your Service. 


### **STEP 14**: Review the Access Rules for your cluster
For now, you don't need to make changes.  In a later tutorial, we will use this to allow SSH access.  This is also the place where you can enable Ambari access (port 8080) which is disabled by default.
- ![](images/200/AccessRules.gif)  


### **STEP 15**: Access the Big Data Cluster Console
- Launch the Big Data Cluster Console for your BDCS-CE cluster.  If this is your first time, you will likely need to allow your browser to accept the self-signed certificate for the web console application.
- You will be asked to provide a username/password.  Use the username and password you defined earlier when you created the BDCS-CE instance (the username defaults to bdcsce_admin).  
  ![](images/300/firstLogin.gif)



# What you Learned

- Learned how to provision a BDCS-CE instance
- Learned how to access BDCS-CE

# Next Steps

- Create a Event Hub Cloud Service from Service console

![](images/300/ServiceDetails.png)