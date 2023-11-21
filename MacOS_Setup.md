# Building on MacOS 

NOTE: Commands are using `\` as marker for line continuations

### Brew
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### CMake
```sh
brew install cmake
```

### Boost
```sh
sudo chown -R $(whoami) /usr/local/lib/pkgconfig
brew install boost
```

### Gtest

```sh
git clone https://github.com/google/googletest.git googletest.git
cd googletest.git
git checkout release-1.8.1

mkdir _build && cd _build
cmake -DCMAKE_CXX_COMPILER="clang++" -DCMAKE_BUILD_TYPE=Release -DCMAKE_POSITION_INDEPENDENT_CODE=ON ..
make
sudo make install
cd ../..
sudo rm -R googletest.git
```

### Google benchmark

```sh
git clone https://github.com/google/benchmark.git google.benchmark.git
cd google.benchmark.git
git checkout v1.5.0

mkdir _build && cd _build
cmake -DCMAKE_CXX_COMPILER="clang++" -DCMAKE_BUILD_TYPE=Release -DBENCHMARK_ENABLE_GTEST_TESTS=OFF ..
make
sudo make install
cd ../..
sudo rm -R google.benchmark.git
```
**_Note_** <br>
When running make there could be error as shown below:  <br>
/Users/ljw/google.benchmark.git/src/complexity.cc:85:10: error: variable 'sigma_gn' set but not used [-Werror,-Wunused-but-set-variable] <br>
  double sigma_gn = 0.0; <br>
         ^
Solution: comment out the code lines involving sigma_gn in the /src/complexity.cc file <br>

### Mongo

mongo-c

```sh
git clone https://github.com/mongodb/mongo-c-driver.git mongo-c-driver.git
cd mongo-c-driver.git
git checkout 1.15.1

mkdir _build && cd _build
cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr/local ..
make
sudo make install
cd ../..
sudo rm -R mongo-c-driver.git
```

mongocxx

```sh
git clone https://github.com/mongodb/mongo-cxx-driver.git mongo-cxx-driver.git 
cd mongo-c-driver.git 
git checkout r3.7.0 

mkdir _build && cd _build 
cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release \ 
    -DCMAKE_INSTALL_PREFIX=/usr/local .. 
make 
sudo make install 
cd ../.. 
sudo rm -R mongo-c-driver.git 
```

### ZMQ

libzmq
```sh
git clone https://github.com/zeromq/libzmq libzmq.git
cd libzmq.git
git checkout v4.3.2

mkdir _build && cd _build
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local ..
make
sudo make install
cd ../..
sudo rm -R libzmq.git
```

cppzmq
```sh
git clone https://github.com/zeromq/cppzmq.git cppzmq.git
cd cppzmq.git
git checkout v4.4.1

mkdir _build && cd _build
cmake -DCMAKE_BUILD_TYPE=Release -DCPPZMQ_BUILD_TESTS=OFF -DCMAKE_INSTALL_PREFIX=/usr/local ..
make
sudo make install
cd ../..
sudo rm -R cppzmq.git
```

### Rocks

rocks
```sh
git clone https://github.com/facebook/rocksdb.git rocksdb.git
cd rocksdb.git
git checkout v8.6.7

mkdir _build && cd _build
cmake -DCMAKE_BUILD_TYPE=Release -DWITH_TESTS=OFF -DCMAKE_INSTALL_PREFIX=/usr/local -DWITH_SNAPPY=1 ..
make
sudo make install
cd ../..
sudo rm -R rocksdb.git
```

### Blockchain

```sh
git clone https://github.com/proximax-storage/cpp-xpx-chain.git
cd cpp-xpx-chain

mkdir _build && cd _build
cmake -DCMAKE_BUILD_TYPE=Release
make publish && make -j 4
```


