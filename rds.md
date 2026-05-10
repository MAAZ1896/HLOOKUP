
  # XXXX Relational Database Service

- [XXXX Relational Database Service](#xxxx-relational-database-service)
  - [Getting started with XXXX Relational Database Service](#getting-started-with-xxxx-relational-database-service)
    - [Purpose and benefits of XXXX RDS](#purpose-and-benefits-of-xxxx-rds)
    - [Key concepts and architecture of XXXX RDS](#key-concepts-and-architecture-of-xxxx-rds)
      - [Architecture](#architecture)
      - [Features](#features)
      - [Supported database engines](#supported-database-engines)
    - [Setting up XXXX RDS](#setting-up-xxxx-rds)
      - [Sign up for an XXXX account](#sign-up-for-an-xxxx-account)
      - [Create a user with administrative access](#create-a-user-with-administrative-access)
    - [Next steps](#next-steps)
  - [Creating an XXXX RDS DB instance](#creating-an-xxxx-rds-db-instance)
    - [Choosing your database engine for XXXX RDS](#choosing-your-database-engine-for-xxxx-rds)
      - [Creating your first DB instance](#creating-your-first-db-instance)
      - [Console](#console)
      - [To create a DB instance using Easy create](#to-create-a-db-instance-using-easy-create)
  - [Securing your XXXX RDS DB instance](#securing-your-xxxx-rds-db-instance)
  - [Connecting to your XXXX RDS DB instance](#connecting-to-your-xxxx-rds-db-instance)
    - [Using the XXXX RDS console to retrieve connection information](#using-the-xxxx-rds-console-to-retrieve-connection-information)
      - [Locating the endpoint and port](#locating-the-endpoint-and-port)


    



  ## Getting started with XXXX Relational Database Service

  XXXX Relational Database Service (XXXX RDS) is a managed database service that simplifies the process of setting up, operating, and scaling relational databases in the cloud. It supports popular database engines such as MySQL and PostgreSQL. With XXXX RDS, you can focus on your applications while XXXX handles time-consuming database tasks like backups, software patching, monitoring, and hardware provisioning.
  This getting started guide helps you navigate the initial setup and use of XXXX RDS. It provides step-by-step instructions and examples to guide you through creating, securing, and connecting to your first DB instance.

  *Topics*

  * Purpose and benefits of XXXX RDS.
  * Key concepts and architecture of XXXX RDS.
    
  ### Purpose and benefits of XXXX RDS

  *Ease of setup* – Launch a DB instance using guided workflows or API calls.

  *Scalability* – Adjust compute and storage resources to meet changing demands.

  *Reliability* – Built-in fault tolerance and automated backups ensure your data is safe and available.

  *Security* – RDS supports encryption, network isolation, and identity-based access control to protect your data.

  ### Key concepts and architecture of XXXX RDS
  XXXX RDS is a fully managed service that simplifies the deployment and management of relational databases in the cloud. It supports multiple database engines and automates tasks like provisioning, patching, backups, and scaling so you can focus on application development.

  *Topics*

  Architecture

  Features

  Supported database engines

  #### Architecture

  XXXX RDS is built on a distributed architecture designed to provide scalability, availability, and reliability for your database workloads.

  *Database instances*

  A database instance (DB instance) provides the underlying infrastructure for your database. It includes compute (CPU and memory), storage, and IOPS, all managed by XXXX. You're responsible for your database software and configurations, while XXXX handles hardware provisioning, maintenance, and backups.

  For more information, see XXXX RDS DB instances.

  *Multi-Availability Zone deployments*

  For high availability, RDS can deploy a database across multiple Availability Zones (AZs). RDS replicates the primary database instance in one AZ to a standby instance in another AZ. In the event of failure, RDS automatically switches to the standby instance, which ensures minimal downtime.
  For more information, see Configuring and managing a Multi-AZ deployment for XXXX RDS.
  *Storage*

  RDS provides multiple storage options, including General Purpose, Provisioned IOPS, and Magnetic storage, to meet different performance needs. Storage automatically scales as needed, and replication provides data durability.
  For more information, see XXXX RDS DB instance storage.
  *Network integration*

  You can launch RDS instances within a Virtual Private Cloud (VPC), which lets you define network configurations and isolate your database in a secure environment. VPC integration also provides secure communication with other XXXX resources like EC2 instances, Lambda functions, and S3 buckets.
  For more information, see XXXX VPC and XXXX RDS

  #### Features

  RDS includes a broad set of features that make database management easier and more efficient.

  *Automated backups and snapshots*

  RDS automatically takes daily backups of your DB instance, retaining backup data for a configurable retention period. You can take manual snapshots in order to preserve a point-in-time backup of your database, which you can later restore to create a new instance.
  For more information, see Introduction to backups.

  *Scalability*

  RDS supports both vertical and horizontal scaling. To scale vertically, modify your instance type to handle increased database load. To scale horizontally, create read replicas to distribute read traffic across multiple instances and improve performance.

  #### Supported database engines

  XXXX RDS supports the following database engines, so you can choose the right database technology for your application needs.

  MySQL – Popular for web applications, offering compatibility with many tools and frameworks.

  PostgreSQL – Known for advanced features, strong standards compliance, and extensibility.

  MariaDB – An open-source fork of MySQL, offering additional features and high compatibility.

  Oracle – Provides enterprise-grade capabilities, including advanced performance, security, and high availability.

  Microsoft SQL Server – Suited for organizations relying on Microsoft technologies, offering analytics and Business Intelligence (BI) integration.

  IBM Db2 – A database for enterprise applications, known for its scalability and advanced analytics.

  Each engine comes with multiple versions and configurations, so you can align with your existing application requirements or take advantage of newer features.

  This guide helps you select and configure a database engine during the setup process and provides links to resources for engine-specific optimization and features.

  ### Setting up XXXX RDS

  To start using XXXX RDS, you need to set up your XXXX account and create a user with administrative access. This process involves signing up for an XXXX account, securing the root user, and configuring IAM Identity Center. By following these steps, you can set up your XXXX environment to manage XXXX RDS instances while maintaining security best practices.

  *Topics*
  - Sign up for an XXXX account
  - Create a user with administrative access
  - Next steps

  #### Sign up for an XXXX account

  If you do not have an XXXX account, complete the following steps to create one.

  To sign up for an XXXX account

  1. Open https://portal.xxxx.xxxx.com/billing/signup.
    
  2. Follow the online instructions.
    
      Part of the sign-up procedure involves receiving a phone call or text message and entering a verification code on the phone keypad.

      When you sign up for an XXXX account, an XXXX account root user is created. The rootAM user has access to all XXXX services and resources in the account. As a security best practice, assign administrative access to a user, and use only the root user to perform tasks that require root user access.

  XXXX sends you a confirmation email after the sign-up process is complete. At any time, you can view your current account activity and manage your account by going to https://xxxx.xxxx.com/and choosing **My Account**.

  #### Create a user with administrative access

  After you sign up for an XXXX account, secure your XXXX account root user, enable XXXX IAM Identity Center, and create an administrative user so that you don't use the root user for everyday tasks.

  *Secure your XXXX account root user*

  1. Sign in to the XXXX Management Console as the account owner by choosing Root user and entering your XXXX account email address. On the next page, enter your password.

  For help signing in by using root user, see Signing in as the root user in the XXXX Sign-In User Guide.

  2. Turn on multi-factor authentication (MFA) for your root user.
  For instructions, see Enable a virtual MFA device for your XXXX account root user (console) in the IAM User Guide.

  *Create a user with administrative access*

  1. Enable IAM Identity Center.

  For instructions, see Enabling XXXX IAM Identity Center in the XXXX IAM Identity Center User Guide.

  2. In IAM Identity Center, grant administrative access to a user.
  Create a user with administrative access

  For a tutorial about using the IAM Identity Center directory as your identity source, see Configure user access with the default IAM Identity Center directory in the XXXX IAM Identity Center User Guide.

  *Sign in as the user with administrative access*

  - To sign in with your IAM Identity Center user, use the sign-in URL that was sent to your email address when you created the IAM Identity Center user.
    
    For help signing in using an IAM Identity Center user, see Signing in to the XXXX access portal in the XXXX Sign-In User Guide.

  *Assign access to additional users*

    1. In IAM Identity Center, create a permission set that follows the best practice of applying least-privilege permissions.
    
        For instructions, see Create a permission set in the XXXX IAM Identity Center User Guide.

  1. Assign users to a group, and then assign single sign-on access to the group.
  For instructions, see Add groups in the XXXX IAM Identity Center User Guide.

  ### Next steps

  Now that you set up and configured your XXXX account, you can get started by creating your first XXXX RDS DB instance.

  Next step: Creating a DB instance

  ## Creating an XXXX RDS DB instance

  XXXX RDS simplifies database creation so you can easily launch a fully-managed database. In this section, you'll learn how to set up your first DB instance and gain an understanding of key configurations such as choosing the right database engine, selecting an instance class, and configuring storage options. Whether you prefer to use the XXXX Management Console or the XXXX Command Line Interface (XXXX CLI), this topic provides step-by-step instructions tailored to your needs.

  What you'll accomplish:

  - Learn how to choose the best database engine for your use case.
  - Create your first DB instance using the XXXX Management Console, with visual guidance and detailed explanations.
  - (Optional) Use the XXXX CLI to programmatically create and manage your DB instance.
      
  By the end of this section, you'll have a functional, fully-managed database ready to connect with your applications and workflows.

  ### Choosing your database engine for XXXX RDS

  To set up your XXXX RDS DB instance, you must first choose the appropriate database engine. XXXX RDS supports several widely-used relational database engines, each suited to specific use cases and application requirements.

  If you're new to XXXX RDS or relational databases, consider starting with MySQL or PostgreSQL. Both engines are open-source, cost-effective, and widely supported by the development community. 

  Choose MySQL if your application needs broad compatibility with existing tools or frameworks, or if your workload involves simple transactional operations. Choose PostgreSQL if your application requires advanced features such as JSON data handling, complex queries, or support for custom extensions.

  > **Note**
  This guide primarily uses MySQL for examples, but most steps are similar for PostgreSQL. By selecting an engine that aligns with your project requirements, you can ensure better performance and scalability as your database evolves.

  #### Creating your first DB instance

  A DB instance in XXXX RDS is the foundational building block for running a managed relational database in the cloud. This section helps you set up your first RDS DB instance.

  #### Console
  This tutorial walks you through the steps to create a simple RDS for MySQL DB instance using the Easy create option. For comprehensive instructions to create a production DB instance, see Creating an XXXX RDS DB instance in the XXXX RDS User Guide.

  #### To create a DB instance using Easy create

  1. Sign in to the XXXX Management Console and open the XXXX RDS console at https:// console.XXXX.XXXX.com/rds/.
    
  2. On the right pane choose **Create database**.
    
  3. For the creation method, choose **Easy create**. This method simplifies database provisioning by automatically configuring settings such as instance class, storage type, and networking settings.
    
  4. In this tutorial, we create a MySQL DB instance. For Engine type, choose **MySQL**.
    
      MySQL is a good starting point because it's open-source, cost-effective, and widely supported by the development community. For a full list of supported database engines, see the section called “Choosing your database engine”.
  1. For **DB instance size**, choose **Free tier** or **Sandbox**. **Free tier** appears for free plan accounts.**Sandbox** appears for paid plan accounts. The **Free tier** option lets you complete the tutorial without incurring costs, so it's ideal for learning and experimentation.
    
      If you were an XXXX Free Tier customer before July 17, 2025 and your usage exceeds the free tier limits or you select resources not covered by the free tier, you're billed at the listed hourly rate.

      The following screenshot shows the **Free tier** option.

    
    ![alt text](<Screenshot (76)-1.png>)

  6. (Optional) For **DB instance identifier**, enter a name for the DB instance. Alternately, keep the name that XXXX RDS generates for you.
    
  7. For **Credentials management**, select **Self-managed**. This option lets you manage your own master user credentials.
    
  8. For **Master password**, enter a password for the master user and confirm the password.
    
  9.  Expand **View default settings for Easy create** and review the settings that XXXX RDS automatically configures for you. You can modify some settings, such as public access and the engine version, after you create the DB instance.
      
  10. Choose **Create database**.
  The database appears in the **Databases** list with a status of Creating. When the status changes to Available, the DB instance is ready to use.

  ## Securing your XXXX RDS DB instance

  Security is a critical aspect of XXXX RDS database management, ensuring that sensitive data remains protected and accessible only to authorized users. This chapter provides an overview of key security features and configurations available in XXXX RDS, along with step-by-step guidance for setting up your environment securely.

  This section helps you understand the key differences between public and private access, and the benefits and risks associated with each. By the end of this section, you'll be able to choose and set up the appropriate access type for your workload.

  *Topics*

    Public access
    
    Private access

  *Public access* 

  A publicly accessible DB instance has a public IP address, which allows users to reach it directly from the internet. Use this configuration for applications that need remote access but require strict access control. For example, you might allow access only from a corporate IP range or specific developer machines.

  You can use this setup for the following use cases:
  - External applications: You need to connect a database to applications hosted outside of XXXX.
    
  - Testing and development: You're developing or testing from your local machine and need direct access.

  *Private access*

  A private DB instance is accessible only within your VPC. It doesn't have a public IP address, and you can't reach it from the internet. You can use private access for scenarios like internal microservices connecting to the database within the same VPC.
  This configuration is best for the following use cases:

  - Internal applications: Databases used by applications within the same VPC or a connected on-premises network.
    
  - High-security requirements: Workloads that require stringent access control, such as financial or healthcare applications.

  ## Connecting to your XXXX RDS DB instance
  Once your XXXX RDS DB instance is up and running, the next step is to establish a connection. This chapter starts by teaching you how to retrieve the necessary connection details directly from the XXXX Management Console or using the XXXX Command Line Interface (XXXX CLI). From there, it walks through the process of connecting to your instance using popular database clients such as MySQL Workbench and pgAdmin.

  The chapter also also addresses common connection issues and how to troubleshoot them. Finally, it describes how to test connectivity using the XXXX CLI and verify your network and authentication configurations. By the end of this chapter, you'll be ready to connect to your XXXX RDS DB instance and start to manage your data.

  *Topics*
  - Using the XXXX RDS console to retrieve connection information.
  - Connecting to an XXXX RDS DB instance using a database client.
  - Troubleshooting connection issues to your XXXX RDS DB instance.

  ### Using the XXXX RDS console to retrieve connection information

  Before you can connect to your XXXX RDS DB instance, you need to gather the connection details, including the endpoint, port, and other required settings. The XXXX Management Console provides an easy way to retrieve this information. The following sections walk you through how to find the endpoint and port, along with additional connection details, so you can connect to your DB instance.

  #### Locating the endpoint and port

  To connect to your DB instance, you first need the instance endpoint and port number. Follow these steps to find them in the XXXX Management Console.

  *To locate the endpoint and port,*

  1. Sign in to the XXXX Management Console and open the XXXX RDS console at https:// console.XXXX.XXXX.com/rds/.
  2. In the left navigation pane, choose **Databases**.
  3. Select the DB instance that you want to connect to from the list of available instances.
  4. In the **Connectivity & security** section, find the **Endpoint** and **Port** settings.
  - The Endpoint is the DNS address for your DB instance. You use this as part of the connection string when you connect with a database client.
  - The Port is the communication port used by the database engine (for example, 3306 for MySQL or 5432 for PostgreSQL).
    
  The following image shows these fields in the console:

  ![](/LOOKUP/Screenshot%20(80).png)

  

  The following tabe describes the documentation releases for the Amazon Relational Database Service Getting Started Guide.

Change | Descrirption | Date
:--- |:---|:---
Initial release | Initial release of the Amazon Relational Database Service Getting Started Guide| March 5, 2025

  
