## **Brew** <br>
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

## **Cmake** <br>
brew install cmake <br> 

## **Boost** <br>
sudo chown -R $(whoami) /usr/local/lib/pkgconfig <br>
brew install boost <br>

## **Gtest** <br>
git clone https://github.com/google/googletest.git googletest.git <br>
cd googletest.git <br>
git checkout release-1.8.1 <br>
mkdir _build && cd _build <br>
cmake -DCMAKE_CXX_COMPILER="clang++" -DCMAKE_BUILD_TYPE=Release -DCMAKE_POSITION_INDEPENDENT_CODE=ON .. <br>
make <br>
sudo make install <br>
cd ../.. <br>
sudo rm -R googletest.git <br>

## **Google benchmark** <br>
git clone https://github.com/google/benchmark.git google.benchmark.git <br>
cd google.benchmark.git <br>
git checkout v1.5.0 <br>

mkdir _build && cd _build <br>
cmake -DCMAKE_CXX_COMPILER="clang++" -DCMAKE_BUILD_TYPE=Release -DBENCHMARK_ENABLE_GTEST_TESTS=OFF .. <br>
make <br>
sudo make install <br>
cd ../.. <br>
sudo rm -R google.benchmark.git <br>

**_Note_** <br>
When running make there could be error as shown below:  <br>
/Users/ljw/google.benchmark.git/src/complexity.cc:85:10: error: variable 'sigma_gn' set but not used [-Werror,-Wunused-but-set-variable] <br>
  double sigma_gn = 0.0; <br>
         ^
Solution: comment out the code lines involving sigma_gn in the /src/complexity.cc file <br>

## **Mongo** <br>
**mongoc** <br>
git clone https://github.com/mongodb/mongo-c-driver.git mongo-c-driver.git <br>
cd mongo-c-driver.git <br>
git checkout 1.15.1 <br>
mkdir _build && cd _build <br>
cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release \ <br>
    -DCMAKE_INSTALL_PREFIX=/usr/local .. <br>
make <br>
sudo make install <br>
cd ../.. <br>
sudo rm -R mongo-c-driver.git <br>

**mongo-cxx** <br>
git clone https://github.com/mongodb/mongo-cxx-driver.git mongo-cxx-driver.git <br>
cd mongo-c-driver.git <br>
git checkout r3.7.0 <br>

mkdir _build && cd _build <br>
cmake -DENABLE_AUTOMATIC_INIT_AND_CLEANUP=OFF -DCMAKE_BUILD_TYPE=Release \ <br> 
    -DCMAKE_INSTALL_PREFIX=/usr/local .. <br>
make <br>
sudo make install <br>
cd ../.. <br>
sudo rm -R mongo-c-driver.git <br>
