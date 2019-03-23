# envoy 入门

[envoy.yaml](envoy.yaml) 是一个静态配置示例，首先需要跑通。

[envoy-xds.yaml](envoy-xds.yaml) 则是一个动态示例，主要实现了从 **文件** 动态加载 route 和 cluster 配置。

> 那为什么不实验加载 listener 和 endpoint 呢？
>
> 因为我司已自研了服务发现（discovery）和配置管理（sven）中间件。直接改 discovery 和 sven 来支持 xds 有难度。
> 所以，准备通过 sven 下发服务 id 和对应的 http 接口的 path。然后通过一个简单的 agent 从 discovery 实时读取服务节点信息，再生成对应的 xds yaml 文件。
