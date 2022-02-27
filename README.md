# Installing dependencies

## 1. LibTorch

bash
wget https://download.pytorch.org/libtorch/lts/1.8/cpu/libtorch-cxx11-abi-shared-with-deps-1.8.2%2Bcpu.zip 
unzip libtorch-cxx11-abi-shared-with-deps-1.8.2%2Bcpu.zip

## 2. OpenCV

bash
sudo apt-get install libopencv-dev python3-opencv 

## 3. BIP
### 0. Installing dependencies for BIP
bash
sudo apt-get update
sudo apt-get install ant cmake g++ default-jre default-jdk

### 1. Getting BIP source code
bash
git clone https://gricad-gitlab.univ-grenoble-alpes.fr/verimag/bip/compiler.git

### 2. Compiling source code
bash
cd compiler/distribution
./single-archive-dist.sh

cd build/bip-full
source ./setup.sh

#### to reactivate Bip Compiler
source /root/compiler/distribution/build/bip-full/setup.sh

# Building C++ executable for image classification

bash
cd learn
source setup.sh
cp limit ../../model/ext-cpp

# Executing the BIP model

bash
cd model
source compile_run_bip.sh -c learn Compound
./system -s
