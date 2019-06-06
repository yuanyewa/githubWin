# githubWin
instructions and toolkit to use github from windows using proxy

.ssh/config
Host github.com
        HostName github.com
        User git
        port 22
        ProxyCommand nc -x change_to_yours.com:1080 -X 5 %h %p

Create ssh key:
ssh-keygen -t rsa -b 4096 -C "your@email.com"
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
clip < ~/.ssh/id_rsa.pub

To verify it works:
ssh -T git@github.com
Expected output:
Hi you! You've successfully authenticated, but GitHub does not provide shell access.
