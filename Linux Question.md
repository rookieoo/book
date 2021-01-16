### Question about Linux Encountered

---

[toc]

#### Q: curl: (7) Failed to connect to `raw.githubusercontent.com` port 443: 拒绝连接

---

A: 

1. https://www.ipaddress.com/ query IP address `199.232.96.133`
2. modify `/etc/hosts` file --> add `199.232.96.133    raw.githubusercontent.com`



example: install oh-my-zsh

1. `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" `



