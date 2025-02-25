---
title: "项目"
weight: 3
description: 项目是资源的拥有者，var_oem_name平台上的资源都是以项目向用户提供服务。
---

项目是资源的拥有者，云管平台上的计算资源（如虚拟机、裸金属、镜像、硬盘、快照等）等都以项目为单位向用户提供，用户只有加入项目后才可以使用项目中所有的资源。

项目来源：

- 系统部署完成后，默认创建system项目。
- 在域下新建项目。
- 同步公有云上的项目。

**入口**：在云管平台单击左上角![](../../../images/intro/nav.png)导航菜单，在弹出的左侧菜单栏中单击 **_"认证与安全/认证体系/项目"_** 菜单项，进入项目页面。

![](../../../images/iam/project1.png)


## 新建项目

该功能用于在域下创建项目。

{{% alert title="注意" color="warning" %}}
- 未开启三级权限时，只允许在Default域下新建项目。
{{% /alert %}}

1. 在项目页面，单击列表上方 **_"新建"_** 按钮，进入新建项目页面。
2. 配置以下参数：
    - 名称：设置项目的名称。
    - 域：选择项目所在域。
    - 配额设置：选择项目所在域之后需要根据域内可分配配额为项目设置配额，配额包括CPU、内存、存储、镜像、主机、IP地址、GPU、弹性公网IP、快照、桶、对象大小、对象数量等。
3. 单击 **_"确定"_** 按钮，进入向该项目添加用户(可选)页面。
4. 若需要添加用户，则配置下面参数，配置完成后，单击 **_"加入"_** 按钮，将用户加入项目。
    - 用户：选择加入项目的用户，支持批量选择多个用户。在管理后台下支持选择系统中所有域中的用户。
    - 角色：设置用户加入项目时的角色，不同角色具有不同权限。选择项目所在域中的角色或其他域中共享状态的角色，且角色已绑定权限。
5. 如不需要添加用户，则直接单击 **_"跳过"_** 按钮即可。

## 新建项目标签

1. 在项目页面，鼠标移动至项目的标签字段下的图标，弹窗中单击 **_"编辑标签"_** 按钮，进入编辑标签页面。
2. 单击页面下方的  **_"新建标签"_** 按钮，弹出新建标签对话框。
3. 配置以下参数：
    - 标签键：标签的唯一键，且非空。
    - 标签值：标签键对应的值，且非空。
4. 单击  **_"添加"_** 按钮，完成操作。

## 调整配额

{{% alert title="说明" %}}
**配额规则说明**

- 配额规则一般分为两部分，前半部分为规则的应用范围；后半部分为具体的配额。如设置阿里云平台的虚拟机数量50台等，也有一些规则只有具体的配额，如云账号的个数，即域下只允许创建云账号的个数。
- 配额请填写大于1的整数或负数（负数代表无限制）
- 添加配额规则时，如果新规则的应用范围与已有规则重复，将会覆盖已有规则
- 配额规则可以根据不同条件设置多条。当资源创建时匹配多条配额规则时，将会应用配额数量最小的一条，如默认主机配额为2，阿里云的主机配额限制为5，那么用户可创建的主机数为2。
{{% /alert %}}

{{% alert title="注意" color="warning" %}}
当平台开启三级权限时，但全局设置-配额检查开关关闭时，项目不支持调整配额。配额使用情况页面将不显示。
{{% /alert %}}

1. 在项目页面，单击项目右侧操作列 **_"调整配额"_** 按钮，进入详情-配额使用情况页面。
2. 配额情况如下：
    - 虚拟机配额：默认规则为任意条件下的虚拟机数量、CPU个数、内存容量、磁盘容量、GPU块数的配额限制。支持修改具体配额数。
        - 增加配额：如需要限制平台、云账号、订阅、区域、可用区、虚拟机类型等条件，单击 **_增加配额_** 按钮，新增一条配额信息，并修改条件以及配额数，单击 **_"保存"_** 按钮。
        - 修改配额：默认规则仅支持修改配额数，其他规则可修改条件即配额数。单击规则右侧操作列 **_修改_** 按钮，修改条件即配额数，单击 **_"保存"_** 按钮。
        - 删除配额：默认规则不支持删除。单击规则右侧操作列 **_"删除"_** 按钮，删除一条配额规则。
    - 区域配额：默认规则为任意条件下的IP地址、公网IP地址、弹性公网IP、快照、存储桶、对象数量、对象存储容量、RDS实例、Redis实例、负载均衡实例的配额。支持修改具体配额数。
        - 增加配额：如需要限制平台、云账号、订阅、区域等条件，单击 **_增加配额_** 按钮，新增一条配额信息，并修改条件以及配额数，单击 **_"保存"_** 按钮。
        - 修改配额：默认规则仅支持修改配额数，其他规则可修改条件即配额数。单击规则右侧操作列 **_修改_** 按钮，修改条件即配额数，单击 **_"保存"_** 按钮。
        - 删除配额：默认规则不支持删除。单击规则右侧操作列 **_"删除"_** 按钮，删除一条配额规则。
    - 项目配额：目前仅支持设置安全组配额，支持修改具体配额数。
    - 镜像配额：默认规则为任意类型的镜像数量，支持修改具体的配额数。
        - 增加配额：如需限制镜像类型，单击 **_增加配额_** 按钮，新增一条配额信息，并修改条件以及配额数，单击 **_"保存"_** 按钮。
        - 修改配额：默认规则仅支持修改配额数，其他规则可修改条件即配额数。单击规则右侧操作列 **_修改_** 按钮，修改条件即配额数，单击 **_"保存"_** 按钮。
        - 删除配额：默认规则不支持删除。单击规则右侧操作列 **_"删除"_** 按钮，删除一条配额规则。

## 管理用户/组

该功能用于管理加入项目的用户和组，支持添加或移除以及修改角色等。

### 向项目添加用户/组

该功能用于向项目中添加用户或组。当以组加入项目时，组内的所有用户都将以同样的角色加入项目。

1. 在项目页面，单击项目右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"管理用户/组"_** 菜单项，进入已加入用户/组页面。
2. 单击列表上方 **_"添加"_** 按钮，弹出添加对话框。
3. 配置以下参数：
    - 类型：选择用户或组。
    - 用户/组：选择项目所在域中的用户或组。
    - 角色：选择项目所在域中的角色或其他域中共享状态的角色，且角色已绑定权限。
4. 单击 **_"确定"_** 按钮，完成操作。

### 修改角色

该功能用于修改已加入项目的用户或组的角色。

1. 在项目页面，单击项目右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"管理用户/组"_** 菜单项，进入已加入用户/组页面。
2. 单击用户或组右侧操作列 **_"修改角色"_** 按钮，弹出修改角色对话框。
3. 修改角色后，单击 **_"确定"_** 按钮，完成操作。

### 移除用户/组

该功能用于将用户或组移出项目。

{{% alert title="说明" %}}
用户既通过用户也通过组加入项目，仅将用户移出项目，该用户仍具有使用该项目的权限，如需彻底将用户移出项目，还需要将用户所在的组也移出项目或将用户移出组。
{{% /alert %}}

**单个移除**

1. 在项目页面，单击项目右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"管理用户/组"_** 菜单项，进入已加入用户/组页面。
2. 单击用户或组右侧操作列 **_"移除"_** 按钮，弹出操作确认对话框。
3. 单击 **_"确定"_** 按钮，将用户或组移出项目。

**批量移除**

1. 在项目页面，单击项目右侧操作列 **_"更多"_** 按钮，选择下拉菜单 **_"管理用户/组"_** 菜单项，进入已加入用户/组页面。
2. 在列表中选一个或多个用户或组，单击列表上方 **_"移除"_** 按钮，弹出操作确认对话框。
3. 单击 **_"确定"_** 按钮，将用户或组移出项目。

## 删除

该功能用于删除项目，支持单个和批量删除项目。当项目中存在资源时，不可以删除。

**单个删除**

1. 在项目页面，单击项目操作列 **_"更多"_** 按钮，选择下拉菜单 **_"删除"_** 菜单项，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。

**批量删除**

1. 在项目列表中选择一个或多个项目，单击列表上方 **_"删除"_** 按钮，弹出操作确认对话框。
2. 单击 **_"确定"_** 按钮，完成操作。

## 查看项目详情

该功能用于查看项目的相关信息。

{{% alert title="说明" %}}
- 资源统计不会实时更新，15分钟更新一次数据。
- 单击刷新按钮，实时刷新资源统计数据。
{{% /alert %}}

1. 在项目页面，单击项目名称项，进入项目详情页面。
2. 详情页面顶部菜单项支持对项目进行管理操作。
3. 查看以下信息：
    - 基本信息：包括项目的云上ID、ID、名称、状态、域、项目、用户标签、组数量、用户数量、创建时间、更新时间、备注。
    - 主机资源统计：用于统计项目下的虚拟机、主机模板、系统镜像、主机镜像、硬盘、快照、主机快照、自动快照策略、安全组、IP子网、弹性公网IP的数量。
    - 负载均衡资源：用于统计项目下的负载均衡实例、访问控制和证书的数量。
    - 其他资源：用于统计项目对应的云上项目（单击超链接可以查看项目对应的云上项目）、存储桶、RDS、Redis的数量。

### 查看操作日志

该功能用于查看项目相关操作的日志信息。

1. 在项目详情页面，单击“操作日志”页签，进入操作日志页面。
    - 加载更多日志：列表默认显示20条操作日志信息，如需查看更多操作日志，请单击 **_"加载更多"_** 按钮，获取更多日志信息。
    - 查看日志详情：单击操作日志右侧操作列 **_"查看"_** 按钮，查看日志的详情信息。支持复制详情内容。
    - 查看指定时间段的日志：如需查看某个时间段的操作日志，在列表右上方的开始日期和结束日期中设置具体的日期，查询指定时间段的日志信息。
    - 导出日志：目前仅支持导出本页显示的日志。单击右上角![](../../../images/system/download.png)图标，在弹出的导出数据对话框中，设置导出数据列，单击 **_"确定"_** 按钮，导出日志。
