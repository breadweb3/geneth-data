# geneth-data
data are stored in https://drive.google.com/drive/folders/1VeGzhapY1F7jzFFxLnQMqle6grEKQ-e3
where 1-3129184.tar.xz is exported blocks since genesis block to block 3129184 (2021-09-03T19:50:24+00:00) and 3129184.tar.xz is exported preimage for block 3129184

# import data
## build geneth
```
git clone git@github.com:breadweb3/geneth.git
cd geneth
make geneth
```
remember: use breadweb3 forked geneth which contains a fix to import geneth blocks

## import blocks
download data from https://drive.google.com/drive/folders/1VeGzhapY1F7jzFFxLnQMqle6grEKQ-e3 and import all blocks or only the last block with the following commands

### import all blocks from 1 to 3129184
```
tar -xJf 1-3129184.tar.xz
build/bin/geneth -nousb import ./1-3129184
```

### import only 3129184
```
tar -xJf 3129184.tar.xz
build/bin/geneth -nousb import-preimages ./3129184
```

# run geneth console
```
build/bin/geneth -nousb -nodiscover console
```
no you can use `eth.getBalance` to check account balance at that time or use any commands or web3 scripts on your own