### Information Directory

---

[toc]

#### Person Information

---

Information that is saved on the system

List:

##### 1. Github

---

| username              | name     | password    |
| --------------------- | -------- | ----------- |
| solomonrookie@163.com | rookieoo | 147258Wang. |

+ generate `.ssh` file

  ```sh
  (base) rookie@rookie-PC:~$ ssh-keygen -t rsa -C "solomonrookie@163.com"
  ```

  

+ to view `.ssh/id_rsa.pub` file --> add to github

  ```sh
  cat id_rsa.pub
  ```

  

+ testing

  ```sh
  (base) rookie@rookie-PC:~$ ssh -T git@github.com
  ```



+ setting

  ```sh
  (base) rookie@rookie-PC:~$ git config --global user.name "rookieoo"
  (base) rookie@rookie-PC:~$ git config --global user.email "solomonrookie@163.com"
  ```



##### 2. email

---

