# BCC-Install-Instructions
BCC install instructions
```
git clone https://github.com/iovisor/bcc.git                                                                                 
sudo apt install -y bison build-essential cmake flex git libedit-dev \                                                       
  libllvm3.7 llvm-3.7-dev libclang-3.7-dev python zlib1g-dev libelf-dev                                                      
sudo apt install -y luajit luajit-5.1-dev                                                                                    
sudo apt install -y iperf iperf3 netperf                                                                                     
mkdir bcc/build; cd bcc/build                                                                                                
cmake .. -DCMAKE_INSTALL_PREFIX=/usr                                                                                         
make help                                                                                 # list make targets; make list not present
make                                                                                                                         
sudo make install                                                                                                            
                                                                                                                             
# BCC module not found so PYTHONPATH needs updating "from bpf import BCC" 
# tried python2 -m pip install bpf
echo "some examples:                                                                                                         
sudo /usr/share/bcc/tools/execsnoop                                                                                          
PYTHONPATH=/usr/lib/python2.7/dist-packages /usr/share/bcc/tools/execsnoop                # take PYTHONPATH from make install output
sudo PYTHONPATH=/usr/lib/python2.7/dist-packages /usr/share/bcc/tools/execsnoop                                              
PYTHONPATH=/usr/lib/python2.7/dist-packages python ../examples/hello_world.py                                                
sudo PYTHONPATH=/usr/lib/python2.7/dist-packages python ../examples/networking/                                              
sudo PYTHONPATH=/usr/lib/python2.7/dist-packages python ../examples/tracing/bitehist.py                                      
sudo PYTHONPATH=/usr/lib/python2.7/dist-packages /usr/share/bcc/tools/capable
```


