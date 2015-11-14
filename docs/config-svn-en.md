Walle's svn configuration guide
===============================


1.Requirements：
-----------

1.1 Svn's directory like flowing, or you can create a svn project in [riouxsvn](https://riouxsvn.com) for test
    - branches
    - tags
    - trunk

1.2 The ssh-key of the user of php process in host should be added to target servers authorized_keys
    - how to find out the user of php process:

        ```
        ps aux|grep php
        ```
    - how to find out the ssh-key of user:

        ```
        su user-name && cat ~/.ssh/id_rsa.pub
        ```
    - how to add a ssh-key to remote server:

          ```
          su user-name && ssh-copy-id -i ~/.ssh/id_rsa.pub remote_user@remote_server
          # need remote_user's password
          ```
2.Configuration
---------------

![](https://github.com/meolu/walle-web/blob/master/screenshots/base-svn.jpg)
![](https://github.com/meolu/walle-web/blob/master/screenshots/task.jpg)

3.Detection
-----------

if project's configuration works after detection, have a try to deploy : )

![](https://github.com/meolu/walle-web/blob/master/screenshots/detection.png)

4.Deployment
------------
In svn mode, you can deploy all code, or deploy specified files incrementally.

- Rsync all code

    ```
    *
    ```
-  Rsync specified files incrementally

    ```
    file_name1
    file_name2
    ```
-  Rsync specified files of specified version incrementally

    ```
    file_name1 commit_id
    file_name2 commit_id
    ```

![](https://github.com/meolu/walle-web/blob/master/screenshots/walle-svn-submit.jpg)