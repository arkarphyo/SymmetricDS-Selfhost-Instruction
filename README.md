# SymmetricDS-Selfhost-Instruction

To install SymmetricDS on Ubuntu, you can follow these steps. This guide assumes you're using Ubuntu 20.04 or later:
1. Install Java

SymmetricDS requires Java 8 or higher. You can install OpenJDK 11, which is commonly used for running SymmetricDS:

sudo apt update
sudo apt install openjdk-11-jdk

Verify the installation by checking the Java version:

java -version

2. Download SymmetricDS

Visit the official SymmetricDS download page (https://www.symmetricds.org/download) to get the latest version. You can also use wget to download it directly. For example:

wget https://github.com/JumpMind/symmetric-ds/releases/download/symmetricds-3.12.0/symmetricds-3.12.0.tar.gz

Replace the URL with the latest release if necessary.
3. Extract SymmetricDS

After downloading the tarball, extract it:

tar -xvzf symmetricds-3.12.0.tar.gz

This will create a directory named symmetricds-3.12.0 (or the version you downloaded).
4. Set Up SymmetricDS

Navigate to the extracted directory:

cd symmetricds-3.12.0

Now, configure the SymmetricDS instance. Create a properties file for your configuration:

cp conf/symmetric-server.properties.sample conf/symmetric-server.properties

Edit the properties file to configure your database connections and replication settings:

nano conf/symmetric-server.properties

Make sure to modify the properties related to your source and target databases, such as:

    db.driver (e.g., com.microsoft.sqlserver.jdbc.SQLServerDriver for MSSQL)
    db.url (e.g., jdbc:sqlserver://localhost:1433;databaseName=your_database_name)
    db.user and db.password

5. Start SymmetricDS

Start the SymmetricDS server by running:

bin/sym

This will start the server, and it will begin managing the database replication according to the configurations you've set.
6. Verify Installation

Check the SymmetricDS logs to ensure everything is running correctly:

tail -f logs/symmetric.log

You should see log entries indicating that the server has started successfully.
7. Access the Web Console

SymmetricDS also provides a web-based management interface, which you can access by navigating to:

http://localhost:31415

Login using the default credentials (admin/admin) or the credentials you've configured.

That’s it! Your SymmetricDS instance should now be running and ready to manage database replication. Would you like more details on configuring replication for specific databases?
