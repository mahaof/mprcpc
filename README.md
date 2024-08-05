基于Zookeeper的多线程模式开发的分布式RPC通信框架
关键技术
基于Protobuf作为RPC编码组件：完成了对于服务提供方和消费方的编解码。
基于多线程编程：通过消息队里完成了框架日志系统，提高系统健壮性容错能力。
使用Zookeeper作为注册中心：实现了分布式的一致性，提供基于接口的方法的透明调用，使服务消费方能够动态查找和调用服务，提高了系统的灵活性和可扩展性。
依赖包
muduo
zookeeper
框架部署运行
在mprpc目录下的autobuild.sh自动部署。执行：

        
bash
复制代码运行
sh autobuild.sh

    
也可在build目录下自动连接编译：

        
bash
复制代码运行
cmake ..
make

    
在provider目录下启动服务器：

        
bash
复制代码运行
./provider -i test.conf

    
在consumer目录下启动客户端发起rpc请求：

        
bash
复制代码运行
./consumer -i test.conf

    
test.conf文件中包含provider服务器的ip和port的配置以及对应的Zookeeper的ip和端口号。Zookeeper默认端口号2181，可以在Zookeeper的conf目录下自行更改服务器的端口号。
