# 自建MySQL迁移至云数据库MySQL

本文介绍如何使用数据传输 DTS 将自建MySQL数据库迁移至云数据库 MySQL。

数据传输 DTS 支持结构迁移、全量迁移、增量迁移，您可以根据实际情况选择。

## 注意事项

### 源数据库配置要求

连接方式：

- 有公网IP的自建数据库
- 通过专线连接的自建数据库

数据库版本：

- MySQL 5.6
- MySQL 5.7

数据库配置：

- server_id大于1
- binlog开启
- binlog_format为ROW
- binlog_row_image为FULL
- 如选择校验数据一致性，则不能存在数据库`_jdts_check__xxxx`
- 表类型为'BASE TABLE'，需要有主键且没有外键

账号权限：

- GRANT RELOAD, REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'user'@'%';
- GRANT SELECT ON `schemas`.* TO 'user'@'%';
- 开启数据校验时，需要GRANT ALL PRIVILEGES ON `_jdts_check__xxxx`.* TO 'user'@'%';

数据库引擎：

- 建议为InnoDB类型，全量迁移过程中，只有InnoDB等事务引擎可以保证一致性状态，MyISAM或者MEMORY等非事务引擎的状态可能不一致。

### 目标数据库配置要求

数据库类型：

- 云数据库 MySQL，需提前创建云数据库 MySQL实例。

数据库版本：

- 源数据库为MySQL 5.6版 支持迁移为 5.6/5.7 版
- 源数据库为MySQL 5.7版 支持迁移为 5.7 版

账号权限：

- GRANT ALL PRIVILEGES ON `schemas`.* TO 'user'@'%';

数据要求：

- 不能存在与待迁移数据库重名的库。
- 不能存在数据校验库`_jdts_check__xxxx`。



## 操作步骤

1. 创建迁移任务。
   - 任务名称：名称长度不能少于2字符且不超过32个字符，只支持中文、数字、大小写字母、英文下划线及中划线。
   - 源库信息：
     - 数据库类型，选择"有公网IP的自建数据库"或"通过专线连接的自建数据库"。
     - 数据库类型，选择MySQL。
     - 数据库地址，填写数据库的域名或IP，如通过专线连接请填写内网IP。
     - 端口，数据库端口。
     - 账号和密码，请提前确认账号具备相应的权限。
   - 目标库信息：
     - 数据库类型，请选择"云数据库 MySQL"
     - 地域，选择目标实例所在地域。
     - 实例ID，请选择目标实例。
     - 账号和密码，请提前确认账号具备相应的权限。
   - 迁移类型
     
     - 请选择迁移类型，可选择结构迁移、全量迁移、增量迁移。
   - 数据一致性校验
     
     - 如选择全量校验，在全量数据迁移完成后，可在任务列表或详情页开启。
     
     - 说明：
     
       MySQL的全量校验为动态校验，即部分数据如已完成校验，之后该部分数据的变更将不再校验。
     
       MySQL数据一致性校验过程中将持续同步增量数据，但性能会降低，建议源端停止写入后再执行数据一致性校验。
   
   - 选择迁移对象
   
     - 支持按库、表迁移。
   
     - 源库类型为"有公网IP的自建数据库"时，支持**可视化选择**和**JSON**两种方式定义要迁移的库表。
   
     - 源库类型为"通过专线连接的自建数据库"时，只支持通过**JSON**定义要迁移的库表。
   
     - 说明
   
       MySQL系统库不会迁移。
   
       当一个库内包含超过100个表时，不支持按表选择，只可选择当前库或通过JSON方式指定表。
   
2. 启动迁移任务。

   - 在任务列表页或详情页，点击**启动**，启动迁移任务。任务启动后，第一步将执行预检查。
   - 预检查成功后，在预检查弹窗中点击**下一步**，执行数据迁移。

3. 执行数据校验。

   - 如创建任务时选择了"全量校验"，则在全量数据迁移完成后可点击**校验**按钮，执行数据一致性校验。
   - 校验过程中将持续同步增量数据，但性能会降低，建议源端停止写入后再执行数据一致性校验。

4. 结束迁移任务。

   - 迁移类型为结构迁移、全量迁移时，数据迁移完成后，任务自动结束。

   - 迁移类型为增量迁移时，需要手动结束迁移任务，建议目的库数据追上源库时，停止源库写入，检查目的库数据无误后，结束迁移任务。

   - 注意：迁移任务结束后，将不能再次开启。

     

   