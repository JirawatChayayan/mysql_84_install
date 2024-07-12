# mysql_84_install
Link and configuration for native password

## Prerequisites
1. **MySQL Server 8.4.1 LTS**: [Download MySQL Server](https://dev.mysql.com/downloads/mysql/)
2. **MySQL Workbench**: [Download MySQL Workbench](https://dev.mysql.com/downloads/workbench/)

## Configuration

### Set Native Password Authentication
Follow these steps to configure MySQL to use the `mysql_native_password` authentication plugin:

1. **Locate and Edit `my.ini` Configuration File**:
   - On Windows, this file is usually located at `C:\ProgramData\MySQL\MySQL Server 8.0\my.ini`.
   
2. **Add the Following Configuration**:
   Open `my.ini` and add the following line under the `[mysqld]` section:

   ```ini
   [mysqld]
   mysql_native_password=ON
   ```
   ![image](https://github.com/user-attachments/assets/e5896c75-9138-4196-92cc-975c2fa57ac0)

3. Restart MySQL Service:
   - On Windows:
       1. Open the Services management console (services.msc).
       2. Locate the MySQL service (e.g., MySQL84).
       3. Right-click on it and select "Restart".
4.Verify the Configuration:
   - Ensure that the MySQL service starts successfully with the new configuration.

Set User for Native Password
   - After configuring MySQL to use mysql_native_password, set existing users to use this authentication plugin:
      1. Open MySQL Workbench or connect to MySQL using the command line.
      2. Execute the following SQL command:
      ```sql
      ALTER USER '<user>'@'<host>' IDENTIFIED WITH mysql_native_password BY '<password>';
      ```

