### 批量计算 ###

批量计算（BatchCompute）是一种适用于并行批处理作业的分布式云服务。批量计算可支持有向无环图（DAG）的批处理作业，系统自动完成资源管理，作业调度和数据加载，并按实际使用量计费。

而此页面集中展示了用户提交的所有批量计算作业的主要信息，如下图：

<img src="../images/batch_index.png" width="600" alt="batch jobs info">

该页面主要支持以下几种操作：

1.点击 **Info** ，可看到作业的详细信息，包括各任务的状态和详细的配置信息，如下图所示:

<img src="../images/batch_info.png" width="600" alt="detailed info of a batch job">

2.点击 **Get Output** ，可以获取作业所有任务在各节点上的标准输出流和标准错误流的输出，如下图所示：

<img src="../images/batch_output.png" width="600" alt="output toggle for a job">

随后点击其中一个项的标准输出流或标准错误流可以查看该任务节点的标准输出流或标准错误流的输出，如下图所示：

<img src="../images/batch_detail.png" width="600" alt="detailed output for a job">

**注意**：该页面每2s自动更新一次，并只展示最后100行的输出。

3.点击作业项中的**stop**可以强行停止正在运行的作业。 若你发现任务配置错误请及时停止，以减少资源浪费。

4.点击 **Create Batch Job** ，可以创建新的Batch作业，详看[作业创建及作业配置](batch/create.md)。

关于批量计算系统的详细介绍，请参看[批量计算系统](batch/README.md)。