Ubuntu装机美化+CUDA cuDNN+Tensorflow GPU版

# 安装系统

16.04 & 18.04 LTS
你

Software&Update--->aliyun
Accounts--->Auto Login
#同时开始下载Anaconda3、Pycharm、搜狗输入法、WPS
#https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.2.0-Linux-x86_64.sh
#https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=linux&code=PCC
#https://pinyin.sogou.com/linux/?r=pinyin
#https://wdl1.cache.wps.cn/wps/download/ep/Linux2019/8722/wps-office_11.1.0.8722_amd64.deb

`sudo apt-get update`
`sudo apt-get dist-upgrade`
sudo passwd root
`#sudo gpasswd -a $USER input`
`sudo apt install openssh-server`
`systemctl status sshd.service #查看服务状态`
`vim/etc/ssh/sshd_config #服务器端配置文件`
`vim/etc/ssh/ssh_config # 客户端配置文件默认配置文件`
`vim ~/.ssh/config #用户配置文件`
`sudo apt-get install dconf-editor`
`Dconf-editor--->org > gnome > desktop > remote-access，取消requlre-encryption`
`sudo apt-get install xrdp`
`sudo apt-get install vnc4server`
`sudo apt-get install tightvncserver`
`sudo apt-get install xubuntu-desktop`
`sudo apt-get isntall gnome`
`echo "xfce4-session" >~/.xsession`
`#sudo vim /etc/xrdp/startwm.sh`
`#在./etc/X11/Xsession前一行输入xfce4-session`
`sudo service xrdp restart`

`sudo apt install pip`
`sudo apt install python3-pip`
`sudo apt-get install git`
`sudo apt-get install vim`
`sudo apt-get install zsh`
`wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh`
`sudo chsh -s /usr/bin/zsh`
`sudo apt install fcitx`
`sudo add-apt-repository ppa:graphics-drivers/ppa`
`sudo apt-get update`
`sudo apt-get install dkms synaptic build-essential`

`Software&Update--->Additional Drivers--->recommended`
`reboot`
`nvidia-smi`
`#输出显卡当前的状态说明驱动安装成功`
`ifconfig`
`#获取远程IP`

`sudo apt install gnome-tweak-tool`
`sudo apt install libinput-tools`
`sudo apt install fonts-wqy-microhei fonts-wqy-zenhei`
`sudo dpkg -i sogoupinyin_*_amd64.deb`
`#缺乏依赖则：sudo apt install -f`
`Settings--->Region&Language--->fcitx`
`Fctix Configuration--->+添加搜狗拼音`
`sudo apt install docky`
`sudo apt install neofetch`
`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE`
`sudo add-apt-repository 'deb https://typora.io/linux ./'`
`sudo apt update`
`sudo apt install typora`
`wget -nv -O Release.key \ https://build.opensuse.org/projects/home:manuelschneid3r/public_key`
`sudo apt-key add - < Release.key`
`sudo apt update`
`sudo sh -c "echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_18.04/ /' > /etc/apt/sources.list.d/home:manuelschneid3r.list"`
`sudo apt update`
`sudo apt install albert`
`sudo apt install python-gi python-gi-cairo python3-gi python3-gi-cairo gir1.2-gtk-3.0`
`sudo pip3 install popupdict`

`bash ~/Downloads/Anaconda3-5.2.0-Linux-x86_64.sh`
`conda --version`
`#输出5.2.0说明Anaconda安装成功`
`conda create --name tf_gpu_env tensorflow-gpu`
`#或者：conda create --name tf_1.8_gpu_env tensorflow-gpu=1.8 python=3.6`
`source activate tf_gpu_env`
`#或者：source activate tf_1.8_gpu_env`
`#source deactivate`
`conda install jupyter notebook`
`conda install spyder`
`#查询安装信息`
`conda info`
`#查询已经安装的库`
`conda list`
`#更新库`
`conda update` 

`anaconda search -t conda tensorflow`
`anaconda show aaronzs/tensorflow-gpu`
`#anaconda show jjh_cio_testing/tensorflow-gpu`

`conda install -c https://conda.anaconda.org/anaconda/linux-64 tensorflow=1.8`
`pip install --ignore-installed tensorflow-gpu`

`#Spyder打不开`

`pip install --upgrade QtPy PyQt5`

`#查看所有可更新的模块`

`pip list --outdated`

`pip install --upgrade -i https://pypi.douban.com/simple [moudle_name]`

`#更新所有的模块`

`pip-review --local --interactive`

`source ~/.bashrc`
`source ~/.zshrc`

# 多版本切换（ java 等）

sudo update-alternatives --install <link> <name> <path> <priority>
sudo update-alternatives --remove <name> <path>
sudo update-alternatives --config <name>

#查看tensorflow版本和安装路径
python
import tensorflow as tf
tf.__version__
tf.__path__

jt -t chesterish -f firacode -fs 13 -cellw 90% -ofs 11 -dfs 11 -mathfs 120 -cursw 3 -cursc o -T -N -kl
