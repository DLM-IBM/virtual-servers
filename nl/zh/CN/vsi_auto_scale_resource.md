---

copyright:
  years: 2014, 2019
lastupdated: "2019-06-07"

keywords:

subcollection: virtual-servers

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 使用基于资源的自动缩放管理流量峰值
{: #managing-resourced-based-auto-scaling}

推出新产品或降价销售现有产品可能会导致 Web 站点上出现流量峰值。流量峰值可能会影响响应时间，进而影响到客户对 Web 站点的体验。通过 {{site.data.keyword.cloud}} 自动缩放，可以自动响应流量峰值。您可以使用基于资源的自动缩放来控制这些流量峰值。
{:shortdesc}

## 开始之前
首先，导航至设备菜单，并确保您具有完成任务的正确帐户许可权。

* 导航至控制台的设备菜单。有关更多信息，请参阅[导航至设备](/docs/vsi?topic=virtual-servers-navigating-devices)。
* 确保您具有任何必需的帐户许可权和设备访问权。如果您不是帐户管理员，那么您的用户帐户必须包含使用自动缩放的许可权。 有关更新许可权以使用自动缩放的更多信息，请参阅[设置自动缩放的用户许可权](/docs/vsi?topic=virtual-servers-user-permissions-required-to-use-auto-scale)。只有帐户所有者或具有**管理用户**经典基础架构许可权的用户才能调整许可权。 

有关许可权的更多信息，请参阅[经典基础架构许可权](/docs/iam?topic=iam-infrapermission#infrapermission)和[管理设备访问权](/docs/vsi?topic=virtual-servers-managing-device-access)。

## 添加自动缩放组
{: #adding-auto-scale-group}

例如，一家位于得克萨斯州达拉斯的电子商务 Web 站点需要三个虚拟服务器始终处于联机状态。该公司在每个工作日的上午 9:00 到下午 5:00 进行线上折扣促销，因此这一时段为业务峰值。为了帮助维持 Web 站点的响应时间，在这一时段内还需要额外的三个虚拟服务器。此外，当所有虚拟服务器上的公共入站流量平均值超过 5 MB/秒并持续 10 分钟时，还应该额外供应两个虚拟服务器。当流量低于 5 MB/秒时，应该取消并除去这些额外的虚拟服务器。目标是用于处理流量激增的虚拟服务器不超过五个，这将使工作日虚拟服务器不会受到额外的工作日流量的影响。以下步骤将引导您逐步设置自动缩放以支持基于资源的缩放。

1. 从**设备**菜单中，选择**自动缩放**。
2. 选择**添加自动缩放组**。
3. 通过首先输入**组名**（例如，Weekend Scale Up 组）来设置自动缩放组，然后选择数据中心。
4. 选择服务器终止策略。例如，如果选择**最旧**，那么在缩减时会选择供应日期最早的服务器。
5. 指示组是否为多 VLAN 缩放组，以及如何在已配置的 VLAN 对中均衡缩减。
6. 选择要在其中供应服务器的公用和专用 VLAN。如果要从公用因特网访问服务器（如果 VLAN 正在运行 Web 服务器），请使**仅专用网络**保留为未选中状态。
7. 将**最小成员计数**设置为 3，将**最大成员计数**设置为 6。将**冷却时间段**设置为 0。因为这是基于安排的缩放，所以没有收集任何统计信息来触发缩放操作。

## 为组定义成员配置
{: #defining-member-configuration}

1. 找到**成员配置**，然后输入缩放服务器的**主机名**和**域**。添加到该组的后续服务器会在主机名后附加唯一后缀。
2. 指定计算实例的硬件配置（核心数、RAM 等）。
3. 如果要安装最简操作系统，请选择操作系统。还可以使用**公共映像**或**专用映像**来供应实例。
4. 如果实例需要额外的步骤来安装其他软件，请指定**安装后脚本**的 URL 以安装该软件。（如果对该组使用负载均衡器，那么会先运行安装后脚本，然后将成员置于负载均衡器后面。）

## 设置策略
{: #setting-up-policies}

在此场景中，该电子商务 Web 站点使用的是基于资源的缩放。因此，需要两个策略：一个策略用于在所需时间范围内执行相对缩放操作 +3，另一个策略用于在峰值结束后执行解除操作 3。第一个策略是添加资源。

1. 向下滚动到**策略**，然后单击**添加策略**。输入**策略名称** (Weekday Scale Up)。
2. 对于**冷却时间段**，选择组冷却时间段选项。
3. 单击**添加触发器**，然后通过在第一个下拉菜单中选择**频率**来指定重复触发器，然后突出显示后续下拉框中的**周一、周二、周三、周四**和**周五**以及**下午 2:00**\*。（**高级编辑**复选框允许您以类似 crontab 的表示法输入触发器频率。）
4. 单击**操作**下的**缩放方式**下拉框，然后选择**精确**。在**成员**字段中输入 3。
5. 再次单击**添加策略**以指定第二个策略，此策略用于每天下午除去服务器。冷却时间段与组的冷却时间段相同。触发器是每个周一、周二、周三、周四和周五晚上 10:00\* 触发，精确缩放操作为 3。在**触发器**字段中输入的时间是基于 UTC 时间的，因此您需要选择下午 2:00（相当于中部夏令时上午 9:00）和晚上 10:00（相当于中部夏令时下午 5:00）。对于中部标准时间，这两个时间将分别为下午 1:00 和晚上 9:00，因为 UTC/GMT 不接受夏令时。请参阅[世界时间服务器 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://www.worldtimeserver.com/current_time_in_UTC.aspx){: new_window} 站点以获取时间转换器。
6. 设置另一个组（例如，名为 Traffic Burst 组），其中“冷却时间段”为 0，“最小成员计数”为 0，“最大成员计数”为 5。使用与 Weekday Scale Up 组相同的组和成员配置设置，但组名除外。
7. 单击**添加策略**以添加第二个策略，此策略用于控制当所有虚拟服务器上的公共入站流量在 10 分钟内平均值超过 5 MB/秒时增加两个额外服务器。
8. 输入**策略名称**，例如 Traffic Burst 组。
9. 对于**冷却时间段**，选择组冷却时间段选项。
10. 单击**添加触发器**。保留第一个框中的缺省值**如果我的**，然后为第二个框选择**公用网络入局 Mbps**。保留第三个框中的缺省 > 符号。在第四个框中，输入 **5** (5 MB)，在第五个框中输入 **600**，然后在最后一个框中选择**秒**以表示 10 分钟。
11. 单击**操作**下的**缩放方式**下拉框，然后选择**相对**。在**成员**字段中输入 2。
12. 再次单击**添加策略**以指定第二个策略，此策略用于在流量减少至低于 5 Mbps\* 时除去服务器。冷却时间段将与组的冷却时间段相同。当我的公用网络入局 Mbps 在 600 秒（10 分钟）的时间段内小于 5 (5 Mbps) 时，将触发触发器。

创建这两个组后，Weekday Scale Up 组会创建三个服务器（最小值）。在工作日，中部时间上午 9:00 会再添加三个服务器，在中部时间下午 5:00 会除去这三个服务器。没有其他方法可在该组中添加或除去成员。在完全独立的 Traffic Burst 组中，每 10 分钟内所有成员的入站公共流量平均值达到 5 MB/秒时，就会添加两个服务器，直到达到组的最大值 5。入站公共流量在 10 分钟内保持低于该量之后，将除去此组中的所有服务器。
