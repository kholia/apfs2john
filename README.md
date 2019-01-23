## Usage

### Compile the source code

The following libraries are needed (including the -dev/-devel packages):

* FUSE 2.6 or greater
* ICU (Only on Linux)
* zlib
* bzip2
* libattr (on some Linux distributions)

Development tools:
* cmake
* gcc-c++ (or clang++)
* git (for cloning)

Example for Linux:
```
sudo apt update
sudo apt install fuse libfuse-dev libicu-dev bzip2 libbz2-dev cmake gcc-c++ git libattr1-dev
```
Clone the repository:
```
git clone https://github.com/kholia/apfs2john.git
cd apfs-fuse
git submodule init
git submodule update
```
The driver uses Apple's lzfse library and includes it as a submodule.

Compile the driver:
```
mkdir build
cd build
cmake ..
make
```
After compilation, the binaries are located in `bin`.

### Extract the hash

Sample commands to extract hashes,

```
$ sudo ./bin/apfs-dump-quick /dev/sdc1 log.txt
```

```
$ ./bin/apfs-dump-quick sample-truncated-openwall.raw log.txt
```

The `kpartx` command will be useful when dealing with disk images.
