GIT
===

#基本操作
查询config
```
git config --system --list
git config --global --list
git config --local --list
```
配置config
```Bash
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
git config --global push.default matching
git config --global core.quotepath false
git config --global unset "configName"
```

```Bash
git init
git add example1.txt
git add example2.txt example2.txt
git add .
git commit -m "wrote a readme file"
```

```Bash
git pull
git push
```

```Bash
git status -sb
git log
```


#SSHkey
```Bash
ssh-keygen -t ed25519 -C "email@example.com"
```

```Bash
ssh-keygen -p -f ~/.ssh/id_ed25519 #exchange
```

自动运行ssh-agent：以下内容粘贴到~/.profile 或 ~/.bashrc文件中。
```Bash
env=~/.ssh/agent.env

agent_load_env () { test -f "$env" && . "$env" >| /dev/null ; }

agent_start () {
    (umask 077; ssh-agent >| "$env")
    . env=~/.ssh/agent.env

agent_load_env () { test -f "$env" && . "$env" >| /dev/null ; }

agent_start () {
    (umask 077; ssh-agent >| "$env")
    . "$env" >| /dev/null ; }

agent_load_env

# agent_run_state: 0=agent running w/ key; 1=agent w/o key; 2= agent not running
agent_run_state=$(ssh-add -l >| /dev/null 2>&1; echo $?)

if [ ! "$SSH_AUTH_SOCK" ] || [ $agent_run_state = 2 ]; then
    agent_start
    ssh-add
elif [ "$SSH_AUTH_SOCK" ] && [ $agent_run_state = 1 ]; then
    ssh-add
fi

unset env

if [ ! "$SSH_AUTH_SOCK" ] || [ $agent_run_state = 2 ]; then
    agent_start
    ssh-add
elif [ "$SSH_AUTH_SOCK" ] && [ $agent_run_state = 1 ]; then
    ssh-add
fi

unset env
```

手动启动
```Bash
# start the ssh-agent in the background
eval "$(ssh-agent -s)"
```

SSH 私钥添加到 ssh-agent
```Bash
ssh-add ~/.ssh/id_ed25519
```

将 SSH 密钥添加到 GitHub 上的帐户
>将 SSH 公钥复制到剪贴板
```Bash
clip < ~/.ssh/id_ed25519.pub
```

>运行
```Bash
ssh -T git@github.com
```

新SSHkey
>复制并运行  把现有的 ssh key都删掉，这句命令行如果你多打一个空格，可能就要重装系统了，建议复制运行。
```Bash
rm -rf ~/.ssh/*
```

>可参考上面理解
```Bash
ssh-keygen -t rsa -b 4096 -C "email@example.com"
```

```Bash
cat ~/.ssh/id_rsa.pub
```

```Bash
ssh -T git@github.com
```
