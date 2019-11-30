# 安装系统
16.04 & 18.04 LTS 通用

## 切换国内镜像
Software&Update--->aliyun
</br>
Accounts--->Auto Login

## 下载各类安装包(先开始以节省时间)
* Anaconda3:https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.2.0-Linux-x86_64.sh
* Pycharm:https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=linux&code=PCC
* 搜狗输入法:https://pinyin.sogou.com/linux/?r=pinyin
* WPS:https://wdl1.cache.wps.cn/wps/download/ep/Linux2019/8722/wps-office_11.1.0.8722_amd64.deb

## 创建用户
```bash
sudo passwd root
sudo gpasswd -a $USER input
```

## 安装基本包
```bash
sudo apt-get update
sudo apt-get dist-upgrade

sudo apt install pip
sudo apt install python3-pip

sudo apt-get install git

sudo apt-get install vim

sudo apt-get install zsh
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
sudo chsh -s /usr/bin/zsh

sudo apt-get install rar
sudo apt-get install unrar
sudo apt-get install p7zip-rar

sudo apt-get install aria2

sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
sudo apt-get install dkms synaptic build-essential

sudo apt update
sudo apt upgrade
sudo apt install gnome-tweak-tool

sudo apt install libinput-tools

sudo apt install fonts-wqy-microhei fonts-wqy-zenhei

sudo apt install docky

sudo apt install neofetch
```

## 配置远程访问
```bash
sudo apt-get install dconf-editor
sudo apt install openssh-server
systemctl status sshd.service
sudo vim /etc/ssh/sshd_config
sudo vim /etc/ssh/ssh_config
sudo vim ~/.ssh/config
```
Dconf-editor--->org > gnome > desktop > remote-access，取消requlre-encryption
```bash
sudo apt-get install xrdp
sudo apt-get install vnc4server
sudo apt-get install tightvncserver
sudo apt-get install xubuntu-desktop
sudo apt-get isntall gnome
echo "xfce4-session" >~/.xsession
  #sudo vim /etc/xrdp/startwm.sh
  #在./etc/X11/Xsession前一行输入xfce4-session
sudo service xrdp restart
```

## 自动升级NVDIA显卡驱动
Software&Update--->Additional Drivers--->(Recommended)
```bash
reboot
  #等待系统重启……
nvidia-smi
  #输出显卡当前的状态说明驱动安装成功
ifconfig
  #获取远程IP,记下
```

## 安装软件
* 安装typora
```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt update
sudo apt install typora
```

* 安装Anaconda3
  ```bash
  bash ~/Downloads/Anaconda3-5.2.0-Linux-x86_64.sh
  conda --version
    #输出5.2.0说明Anaconda安装成功
  sudo pip install conda
   ```
  * 配置TensorFlow环境
  ```bash
  conda create --name tf_gpu_env tensorflow-gpu
    #以上为最新版TensorFlow,若需要低版本,如1.8：conda create --name tf_1.8_gpu_env tensorflow-gpu=1.8 python=3.6
  source activate tf_gpu_env
    #与上一步骤环境名保持一致,如1.8：source activate tf_1.8_gpu_env
  sudo pip install pandas
  sudo pip install scikit-learn
  sudo pip install msgpack
  sudo pip install seaborn
  sudo pip install scikit_image
  sudo pip install tflearn
  sudo pip install keras
  sudo pip install matplotlib
  sudo pip install opencv-python
  sudo pip install plotly
  pip install dicom
  pip install pydicom
  pip install SimpleITK
  pip install pyautogui
  #source deactivate
  ```
    * 安装jupyter notebook
  ```bash
  conda install jupyter notebook
  jt -t chesterish -f firacode -fs 13 -cellw 90% -ofs 11 -dfs 11 -mathfs 120 -cursw 3 -cursc o -T -N -kl
  ```

  * 安装Spyder
  ```bash
  conda install spyder
  ```

  ```bash
  conda info
    #查询安装信息
  conda list
    #查询已经安装的库
  conda update 
    #更新库

  ```bash
  #Spyder打不开
  pip install --upgrade QtPy PyQt5
  #查看所有可更新的模块
  pip list --outdated
  pip install --upgrade -i https://pypi.douban.com/simple [moudle_name]
  #更新所有的模块
  pip-review --local --interactive
  source ~/.bashrc

  #查看tensorflow版本和安装路径
  python
  import tensorflow as tf
  tf.__version__
  tf.__path__
  ```

* 安装搜狗拼音
```bash
sudo apt install fcitx
sudo apt install libopencc1 fcitx-libs fcitx-libs-qt
sudo dpkg -i ~/Downloads/sogoupinyin_*_amd64.deb
  #缺乏依赖则：sudo apt install -f
```
Settings--->Region&Language--->fcitx
Fctix Configuration--->+添加搜狗拼音

* 安装Pycharm
```bash

sudo dpkg -i ~/Downloads/pycharm-community-2019.1.3.tar.gz
sudo gedit /usr/share/applications/Pycharm.desktop
```

* 安装WPS
```bash
sudo dpkg -i ~/Downloads/wps-office_11.1.0.8722_amd64.deb
sudo apt-get remove libreoffice-common
sudo apt-get remove unity-webapps-common
```
