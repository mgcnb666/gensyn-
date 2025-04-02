# gensyn-
第一步安装node


curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash


第2步安装其他依赖项



sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl screen git yarn && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt update && sudo apt install -y yarn



第3步克隆gensyn仓库并进入

git clone https://github.com/gensyn-ai/rl-swarm && cd rl-swarm

sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 1

第4步打开使用screen后台


screen -S gensyn





第5步安装cloudflare

wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64

sudo mv cloudflared-linux-amd64 /usr/local/bin/cloudflared


sudo chmod +x /usr/local/bin/cloudflared



第6步启动gensyn

./run_rl_swarm.sh



然后等出现Visit this url and login : 打开一个新的服务器窗口输入


cloudflared tunnel --url http://localhost:3000


然后等待一会会出现




--------------+
2025-04-01T05:47:23Z INF |  Your quick Tunnel has been created! Visit it at (it may take some time to be reachable):  |
2025-04-01T05:47:23Z INF |  这里有一个网站用浏览器打开这个网站使用邮箱登录不要使用谷歌                                         |
2025-04-01T05:47:23Z INF +--------------------------------------------------------------------------------------------+
2025-04-01T05:47:23Z INF Cannot determine default configuration path. No file [config.yml config.yaml] in [~/.cloudflared ~/.cloudflare-warp ~/cloudflare-warp /etc/cloudflared /usr/local/etc/cloudflared]
2025-04-01T05:47:23Z INF Version 2025.2.1 (Checksum afdfadd1ef552e66bffc35246fe30a9bd578356d2d386de95585ccfc432472b8)


第7步在打开一个服务器窗口输入

pip install --upgrade jinja2

export PATH="$HOME/.local/bin:$PATH"


source ~/.bashrc




第8步回到第一个窗口


Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N] 

这里输入n就启动了然后就成功了你可以在看下日志

 20%|████████▊                                   | 4/20 [05:27<20:16, 76.02s/it]
出现这个就是在运行了然后 Ctrl + A，然后按 D保存退出



