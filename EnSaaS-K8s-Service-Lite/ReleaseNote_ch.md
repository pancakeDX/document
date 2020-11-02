### EnSaaS-K8s-Service Lite 4.1.0- (2020-10-28)

#### Added:
- 合并Service instance相关功能，角色支持：globalAdmin、subscriptionAdmin和subscriptionUser
- API支持job相关的功能，方便派发job。
- API支持支持cluster，workspace和namespace的备份还原。当前备份还原的存储支持S3，方式为yaml文件创建备份还原
- API支持用户创建LoadBalancer和nodeport service
- API支持用户创建PV和PVC

#### Updated：
- 将CRD的版本从v1beta1升级到v1（K8S 1.19版本之后v1beta1将会废弃）
- 修改CRD资源的group信息，v1版本的CRD不支持以k8s.io结尾的group，修改为edgecloud.ensaas.io
- 重构了metric获取的逻辑，添加查看ns,ws,node资源的API
- 加入Applications页面
- 取消application和service页面的工具箱；
- top_navbar添加Home 按钮

#### Fixed:
- clusteragent和kubeensaas长时间运行会重启的问题
- 查看有两个container的pod会出错的问题
- 优化application/node绑定quotas的文字描述和翻译；
- 优化用户没有资源权限时的提示；
- 修改web kubectl刚打开时会闪现空白框的问题；
- overview页面，quota页面，scale quota页面的limitsDisk改为PVC Disk；
- 修改scale quota页面，pod和quota_usage table等的显示问题；
- 当集群权限是workspaceOwner时候，在quota页面没有权限删除quota, 将operation设为disabled；
- 在global页面，circle text当used是0, 数值显示问题；
- 新建user页面，对于已经存在的用户没有给以提示信息的问题；
- 新建cluster失败问题；
- 统计summary的样式问题；

#### Component
- kubeensaas-lite：v-4.1.0
- clusteragent-lite：v-4.1.0
- mp-ui-lite：v-4.1.0

#### Note:
- 从EnSaaS-K8s-Service 4.0.11后，拆分出EnSaaS-K8s-Service Lite，用于IoTSuite Edge的场景
- EnSaaS-K8s-Service Lite的新建了一个chart，chart包中包含了所需的服务