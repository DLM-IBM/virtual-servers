---

copyright:
  years: 2017, 2019
lastupdated: "2019-09-14"

keywords: public virtual servers, network traffic, virtual server deployment, profile

subcollection: virtual-servers

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tips: .tips}
{:note: .note}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# Profiles
{: #about-virtual-server-profiles}

When you provision {{site.data.keyword.BluVirtServers}}, you can select from supported families of profiles. A profile is a combination of vCPU and RAM that can be instantiated quickly to start a virtual server instance. In the {{site.data.keyword.cloud_notm}} console, you can choose from popular profile configurations or select from a list of profiles that best fit your needs.
{:shortdesc}

The following virtual server instance families are available.

Depending on your instance type, some families might not be available.
{:note}

| Families  | Description                                                                                              |
| ----------------------- | -------------------------------------------------------------------------------------------------------- |
| [Balanced](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#balanced) | Best for common cloud workloads that require a balance of performance and scalability. Uses network-attached storage. |
| [Balanced local storage](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#balanced-local-storage) | Best for large database workloads that require high I/O performance with very low latency. |
| [Variable compute](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#variable-compute)  | Best for workloads that don’t require steady, high-CPU performance. |
| [Compute](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#compute) | Best for moderate to high web traffic workloads.|
| [Memory](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#memory)  | Best for memory caching and real-time analytics workloads. |
| [GPU](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#gpu)  | Best for high-performance workloads. |
{: caption="Table 1. Public virtual server family selections" caption-side="top"}

Some of these families are also available for {{site.data.keyword.vsi_is_full}}. For more information, see [{{site.data.keyword.vsi_is_short}}](/docs/vpc-on-classic-vsi?topic=vpc-on-classic-vsi-getting-started#gettingstartedvsigen).
{:tip}

## Balanced
{: #balanced}

The balanced profiles (with network-attached storage) are ideal for common cloud workloads that require a balance of performance and scale. Network performance ranges from standard to premium.

The offering is available in the following profiles:

| Profile   | vCPU    | RAM     | Storage type |
| --------- | ------- | ------- | ------------ |
| B1.1x2    | 1       | 2 GB    | SAN          |
| B1.1x4    | 1       | 4 GB    | SAN          |
| B1.2x4    | 2       | 4 GB    | SAN          |
| B1.2x8    | 2       | 8 GB    | SAN          |
| B1.4x8    | 4       | 8 GB    | SAN          |
| B1.4x16   | 4       | 16 GB   | SAN          |
| B1.8x16   | 8       | 16 GB   | SAN          |
| B1.8x32   | 8       | 32 GB   | SAN          |
| B1.16x32  | 16      | 32 GB   | SAN          |
| B1.16x64  | 16      | 64 GB   | SAN          |
| B1.32x64  | 32      | 64 GB   | SAN          |
| B1.32x128 | 32      | 128 GB  | SAN          |
| B1.48x192 | 48      | 192 GB  | SAN          |
{: caption="Table 2. Balanced profiles with network-attached storage" caption-side="top"}

### Storage notes
{: #storage-notes-balanced}

* SAN primary boot disk (25 or 100GB) with additional disks available, up to 2 TB each (five total disks allowed).
* Pricing for public virtual servers that use SAN storage includes virtual CPU, memory, and minimum primary boot disk. Extra disk prices depend on the disk size and quantity that you select.  

Balanced profiles (with network-attached storage) are available in all data centers.

All supported operating systems (such as RHEL, CentOS, Windows, Ubuntu, and others), supported  databases, and software add-ons are also available with this offering.

## Balanced local storage
{: #balanced-local-storage}

The balanced local storage profiles are primarily for large database workloads that require high I/O performance with very low latency. Network performance ranges from standard to premium.

The offering is available in various profiles and data centers, with the following local storage options:

* [Local HDD](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#HDD)
* [Local SSD](/docs/virtual-servers?topic=virtual-servers-about-virtual-server-profiles#SSD)

### Local HDD
{: #HDD}

<table>
<CAPTION>Table 3. Balanced local storage profiles using local HDD</CAPTION>
<THEAD>
<TR>
<th>Profile</th>
<th>vCPU</th>
<th>RAM</th>
<th>Secondary disks<sup>(*)</sup></th>
<th>Storage type</th>
</TR>
</THEAD>
<TBODY>
<tr>
<td>BL1.1x2</td>
<td>1</td>
<td>2 GB</td>
<td>25, 100 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.1x4</td>
<td>1</td>
<td>4 GB</td>
<td>25, 100 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.2x4</td>
<td>2</td>
<td>4 GB</td>
<td>100, 200 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.2x8</td>
<td>2</td>
<td>8 GB</td>
<td>100, 200 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.4x8</td>
<td>4</td>
<td>8 GB</td>
<td>150, 300 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.4x16</td>
<td>4</td>
<td>16 GB</td>
<td>150, 300 GB</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.8x16</td>
<td>8</td>
<td>16 GB</td>
<td>250 GB, (2 x 250 GB)</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.8x32</td>
<td>8</td>
<td>32 GB</td>
<td>250 GB, (2 x 250 GB)</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.16x32</td>
<td>16</td>
<td>32 GB</td>
<td>300 GB, (2 x 300 GB)</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.16x64</td>
<td>16</td>
<td>64 GB</td>
<td>300 GB, (2 x 300 GB)</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.32x64</td>
<td>32</td>
<td>64 GB</td>
<td>400 GB, (2 x 400 GB)</td>
<td>Local HDD</td>
</tr>
<tr>
<td>BL1.32x128</td>
<td>32</td>
<td>128 GB</td>
<td>400 GB, (2 x 400 GB)</td>
<td>Local HDD</td>
</tr>
</TBODY>
</table>

#### Storage notes
{: #storage-notes-local-hdd}

* <sup>(*)</sup>Balanced local profiles automatically come with a 100 GB local storage boot disk. Then, you can select a second disk (options shown in Table 3). Any additional local disks are optional. If you require over 500 GB, then two additional disks are required (for example, 8 cores require 2 x 250 GB of local storage).
*	Maximum local storage is limited by cores.
*	Balanced local storage is globally available; however, the type of storage (local SSD or local HDD) depends on the data center location.
*	You can't detach primary or secondary disks.

The following data centers support balanced local storage virtual servers with local HDD:

| Available Data Centers - Local HDD |       |
| ---------------------- | ------- |
| Dallas (DAL01)         | Dallas (DAL05)         |
| Dallas (DAL06)         | Houston (HOU02)        |
| San Jose (SJC01)       | Seattle (SEA01)        |
| Washington, DC (WDC01) |                        |
{: class="simple-tab-table"}
{: caption="Table 4. Available data centers (local HDD) - Americas" caption-side="top"}
{: tab-group="Local-HDD"}
{: #local-hdd1}
{: tab-title="Americas"}

| Available Data Centers - Local HDD |
| ---------------------- |
| Amsterdam (AMS01)      |
{: class="simple-tab-table"}
{: caption="Table 5. Available data centers (local HDD) - Europe" caption-side="top"}
{: tab-group="Local-HDD"}
{: #local-hdd2}
{: tab-title="Europe"}

| Available Data Centers - Local HDD |
| ---------------------- |
| Hong Kong (HKG02)      |
| Singapore (SNG01)      |
{: class="simple-tab-table"}
{: caption="Table 6. Available data centers (local HDD) - Asia-Pacific" caption-side="top"}
{: tab-group="Local-HDD"}
{: #local-hdd3}
{: tab-title="Asia-Pacific"}

All supported operating systems (such as RHEL, CentOS, Windows, Ubuntu, and others), supported  databases, and software add-ons are also available with this offering.  

### Local SSD
{: #SSD}

<table>
<CAPTION>Table 7. Balanced local storage profiles using local SSD</CAPTION>
<THEAD>
<TR>
<th>Profile</th>
<th>vCPU</th>
<th>RAM</th>
<th>Secondary disks<sup>(*)</sup></th>
<th>Storage type</th>
</TR>
</THEAD>
<TBODY>
<tr>
<td>BL2.1x2</td>
<td>1</td>
<td>2 GB</td>
<td>25, 100 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.1x4</td>
<td>1</td>
<td>4 GB</td>
<td>25, 100 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.2x4</td>
<td>2</td>
<td>4 GB</td>
<td>100, 200 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.2x8</td>
<td>2</td>
<td>8 GB</td>
<td>100, 200 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.4x8</td>
<td>4</td>
<td>8 GB</td>
<td>150, 300 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.4x16</td>
<td>4</td>
<td>16 GB</td>
<td>150, 300 GB</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.8x16</td>
<td>8</td>
<td>16 GB</td>
<td>250 GB, (2 x 250 GB)</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.8x32</td>
<td>8</td>
<td>32 GB</td>
<td>250 GB, (2 x 250 GB)</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.16x32</td>
<td>16</td>
<td>32 GB</td>
<td>300 GB, (2 x 300 GB)</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.16x64</td>
<td>16</td>
<td>64 GB</td>
<td>300 GB, (2 x 300 GB)</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.32x64</td>
<td>32</td>
<td>64 GB</td>
<td>400 GB, (2 x 400 GB)</td>
<td>Local SSD</td>
</tr>
<tr>
<td>BL2.32x128</td>
<td>32</td>
<td>128 GB</td>
<td>400 GB, (2 x 400 GB)</td>
<td>Local SSD</td>
</tr>
</TBODY>
</table>

#### Storage notes
{: #storage-notes-local-ssd}

* <sup>(*)</sup>Balanced local profiles automatically come with a 100 GB local storage boot disk. Then, you can select a second disk (options shown in table above). Any additional local disks are optional. If you require over 500 GB, then two additional disks are required (for example, 8 cores require 2 x 250 GB of local storage).
*	Maximum local storage is limited by cores.
*	Balanced local storage is globally available; however, the type of storage (local SSD or local HDD) depends on the data center location.
*	You can't detach primary or secondary disks.

The following data centers support balanced local storage virtual servers with local SSD:

| Available Data Centers - Local SDD |        |
| ---------------------------------- | ------ |
| Dallas (DAL09)                     | Dallas (DAL10)         |
| Dallas (DAL12)                     | Dallas (DAL13)         |
| Queretaro (MEX01)                  | Montreal (MON01)       |
| Sao Paulo (SAO01)                  | San Jose (SJC03)       |
| San Jose (SJC04)                   | Toronto (TOR01)        |
| Washington, DC (WDC04)             | Washington, DC (WDC06) |
| Washington, DC (WDC07)             |                        |
{: class="simple-tab-table"}
{: caption="Table 8. Available data centers (local SDD) - Americas" caption-side="top"}
{: tab-group="Local-SDD"}
{: #local-sdd1}
{: tab-title="Americas"}

| Available Data Centers - Local SDD |       |
| ---------------------------------- | ----- |
| Amsterdam (AMS03)                  | Frankfurt (FRA02) |
| London (LON02)                     | London (LON04)    |
| London (LON06)                     | Milan (MIL01)     |
| Oslo (OSL01)                       | Paris (PAR01)     |
{: class="simple-tab-table"}
{: caption="Table 9. Available data centers (local SDD) - Europe" caption-side="top"}
{: tab-group="Local-SDD"}
{: #local-sdd2}
{: tab-title="Europe"}

| Available Data Centers - Local SDD |       |
| ---------------------------------- | ----- |
| Chennai (CHE01)                    | Melbourne (MEL01) |
| Seoul (SEO01)                      | Sydney (SYD01)    |
| Sydney (SYD04)                     | Tokyo (TOK02)     |
{: class="simple-tab-table"}
{: caption="Table 10. Available data centers (local SDD) - Asia-Pacific" caption-side="top"}
{: tab-group="Local-SDD"}
{: #local-sdd3}
{: tab-title="Asia-Pacific"}

All supported operating systems (such as RHEL, CentOS, Windows, Ubuntu, and others), supported  databases, and software add-ons are also available with this offering.

## Variable compute
{: #variable-compute}

Variable compute profiles are best for workloads that don’t require steady, high-CPU performance. Due to the level of CPU oversubscription allowed on the hosts for variable compute server instances, CPU performance levels might be less than other public profiles with the same number of cores, while RAM and storage remain consistent.  This makes variable compute profiles a lower-cost alternative. For example, you can use this function to test a new feature without incurring the higher cost of a full-performance virtual server instance.

The offering is available in the following profiles:

| Profile      | vCPU     | RAM       | Storage Type |
| ------------ | -------- | --------- | ------------ |
| U1.1x2       | 1        | 2 GB      | SAN          |
| U1.2x4       | 2        | 4 GB      | SAN          |
| U1.4x8       | 4        | 8 GB      | SAN          |
{: caption="Table 11. Variable compute profiles" caption-side="top"}

### Storage notes
{: #storage-notes-variable-compute}

* SAN primary boot disk (25 or 100 GB) with an extra disk available, up to 2 TB. You can add one extra secondary disk to your variable compute instance.
* Pricing for public virtual servers that use SAN storage includes virtual CPU, memory, and minimum primary boot disk. Extra disk prices depend on the disk size and quantity that you select.  

Variable compute profiles are available in all data centers.

Supported operating systems (such as RHEL, CentOS, Ubuntu, and others), supported databases, and software add-ons are also available with this offering.

## Compute
{: #compute}

Compute profiles are best for workloads with intensive CPU demands, such as high web traffic workloads, production batch processing, and front-end web servers.

The offering is available in the following profiles:

| Profile      | vCPU     | RAM       | Storage Type |
| ------------ | -------- | --------- | ------------ |
| C1.1x1       | 1        | 1 GB      | SAN          |
| C1.2x2       | 2        | 2 GB      | SAN          |
| C1.4x4       | 4        | 4 GB      | SAN          |
| C1.8x8       | 8        | 8 GB      | SAN          |
| C1.16x16     | 16       | 16 GB     | SAN          |
| C1.32x32     | 32       | 32 GB     | SAN          |
{: caption="Table 12. Compute profiles" caption-side="top"}

### Storage notes
{: #storage-notes-compute}

* SAN primary boot disk (25 or 100 GB) with additional disks available, up to 2 TB each (five total disks allowed).
* Pricing for public virtual servers that use SAN storage includes virtual CPU, memory, and minimum primary boot disk. Extra disk prices depend on the disk size and quantity that you select.  

Compute profiles are available in all data centers.

All supported operating systems (such as RHEL, CentOS, Windows, Ubuntu, and others), supported  databases, and software add-ons are also available with this offering.

## Memory
{: #memory}

Memory profiles are best for memory intensive workloads, such as large caching workloads, intensive database applications, or in-memory analytics workloads.

The offering is available in the following profiles:

| Profile      | vCPU     | RAM       | Storage Type |
| ------------ | -------- | --------- | ------------ |
| M1.1x8       | 1        | 8 GB      | SAN          |
| M1.2x16      | 2        | 16 GB     | SAN          |
| M1.4x32      | 4        | 32 GB     | SAN          |
| M1.8x64      | 8        | 64 GB     | SAN          |
| M1.16x128    | 16       | 128 GB    | SAN          |
| M1.30x240    | 30       | 240 GB    | SAN          |
| M1.48x384    | 48       | 384 GB    | SAN          |
| M1.56x448    | 56       | 448 GB    | SAN          |
| M1.64x512    | 64       | 512 GB    | SAN          |
{: caption="Table 13. Memory profiles" caption-side="top"}

### Storage notes
{: #storage-notes-memory}

* SAN primary boot disk (25 or 100 GB) with additional disks available, up to 2 TB each (5 total disks allowed).
* Pricing for public virtual servers that use SAN storage includes virtual CPU, memory, and minimum primary boot disk. Additional disk prices depend on the disk size and quantity that you select.  

Memory profiles are available in all data centers.

All supported operating systems (such as RHEL, CentOS, Windows, Ubuntu, and others), supported  databases, and software add-ons are also available with this offering.

## GPU
{: #gpu}

GPU profiles are best for high-performance workloads that require more compute density to reduce resource management and costs. The GPU profiles are ideal for artificial intelligence processes, intense graphic and data applications, or developing new applications that require fast performance.

Powered by NVDIA Tesla GPUs, {{site.data.keyword.cloud_notm}} Accelerated Compute “ac1” and "ac2" profiles both offer block and local SSD storage. The following GPU profiles are available globally for you to choose from:  

<table>
<CAPTION>Table 14. P100 GPU profiles</CAPTION>
<THEAD>
<TR>
<th>Profile</th>
<th>GPU</th>
<th>GPU RAM (GB)</th>
<th>vCPU</th>
<th>vCPU RAM (GB)</th>
<th>Storage Type</th>
<th>Boot Disc (GB)</th>
<th>Secondary Discs (2 and 3) (GB)</th>
</TR>
</THEAD>
<TBODY>
<tr>
<td>ac1.8x60x25</td>
<td>1 P100</td>
<td>16</td>
<td>8</td>
<td>60</td>
<td>Block (SAN)</td>
<td>25</td>
<td>None</td>
</tr>
<tr>
<td>ac1.8x60x100</td>
<td>1 P100</td>
<td>16</td>
<td>8</td>
<td>60</td>
<td>Local SSD or SAN</td>
<td>100</td>
<td>None (SAN)<br>300 (Local)</td>
</tr>
<tr>
<td>ac1.16x120x25</td>
<td>2 P100</td>
<td>32</td>
<td>16</td>
<td>120</td>
<td>Block (SAN)</td>
<td>25</td>
<td>None</td>
</tr>
<tr>
<td>ac1.16x120x100</td>
<td>2 P100</td>
<td>32</td>
<td>16</td>
<td>120</td>
<td>Local SSD or SAN</td>
<td>100</td>
<td>None (SAN)<br>600 (Local)</td></tr>

</TBODY>
</table>

<br>
<br>
The following data centers support P100 GPU profiles:

| Available Data Centers - P100 GPUs |       
| ----------------------  |
| Dallas (DAL13)          |
| Washington , DC (WDC07) |
{: class="simple-tab-table"}
{: caption="Table 15. Available data centers (P100 GPUs) - Americas" caption-side="top"}
{: tab-group="P100 GPUs"}
{: #local-p100_1}
{: tab-title="Americas"}

| Available Data Centers - P100 GPUs |
| ---------------------- |
| Frankfurt (FRA02)      |
| London (LON04)         |
| London (LON06)         |
{: class="simple-tab-table"}
{: caption="Table 16. Available data centers (P100 GPUs) - Europe" caption-side="top"}
{: tab-group="P100 GPUs"}
{: #local-p100_2}
{: tab-title="Europe"}

| Available Data Centers - P100 GPUs |
| ---------------------- |
| Tokyo (TOK02)          |
| Sydney (SYD04)         |
{: class="simple-tab-table"}
{: caption="Table 17. Available data centers (P100 GPUs) - Asia-Pacific" caption-side="top"}
{: tab-group="P100 GPUs"}
{: #local-p100_3}
{: tab-title="Asia-Pacific"}

<br>
<br>

<table>
<CAPTION>Table 18. V100 GPU profiles</CAPTION>
<THEAD>
<TR>
<th>Profile</th>
<th>GPU</th>
<th>GPU RAM (GB)</th>
<th>vCPU</th>
<th>vCPU RAM (GB)</th>
<th>Storage Type</th>
<th>Boot Disc (GB)</th>
<th>Secondary Discs (2 and 3) (GB)</th>
</TR>
</THEAD>
<TBODY>
<tr>
<td>ac2.8x60x25</td>
<td>1 V100</td>
<td>16</td>
<td>8</td>
<td>60</td>
<td>Block (SAN)</td>
<td>25</td>
<td>None</td>
</tr>
<tr>
<td>ac2.8x60x100</td>
<td>1 V100</td>
<td>16</td>
<td>8</td>
<td>60</td>
<td>Local SSD or SAN</td>
<td>100</td>
<td>None (SAN)<br>300 (Local)</td>
</tr>
<tr>
<td>ac2.16x120x25</td>
<td>2 V100</td>
<td>32</td>
<td>16</td>
<td>120</td>
<td>Block (SAN)</td>
<td>25</td>
<td>None</td>
</tr>
<tr>
<td>ac2.16x120x100</td>
<td>2 V100</td>
<td>32</td>
<td>16</td>
<td>120</td>
<td>Local SSD or SAN</td>
<td>100</td>
<td>None (SAN)<br>600 (Local)</td></tr>

</TBODY>
</table>

<br>
<br>

You can also choose V100 GPUs. The following data centers support V100 GPU profiles:

| Available Data Centers - V100 GPUs |       
| ----------------------  |
| Dallas (DAL10)          |
| Dallas (DAL12)          |
| Washington , DC (WDC07) |
{: class="simple-tab-table"}
{: caption="Table 19. Available data centers (V100 GPUs) - Americas" caption-side="top"}
{: tab-group="V100 GPUs"}
{: #local-v100_1}
{: tab-title="Americas"}

| Available Data Centers - V100 GPUs |
| ---------------------- |
| Frankfurt (FRA02)      |  
| London (LON04)         |
{: class="simple-tab-table"}
{: caption="Table 20. Available data centers (V100 GPUs) - Europe" caption-side="top"}
{: tab-group="V100 GPUs"}
{: #local-v100_2}
{: tab-title="Europe"}

| Available Data Centers - V100 GPUs |
| ---------------------- |
| Tokyo (TOK02)          |
| Sydney (SYD04)         |
{: class="simple-tab-table"}
{: caption="Table 21. Available data centers (V100 GPUs) - Asia-Pacific" caption-side="top"}
{: tab-group="V100 GPUs"}
{: #local-v100_3}
{: tab-title="Asia-Pacific"}

<br>
<br>

### GPU prerequisites
{: #gpu-prerequisites}

Review the following GPU prerequisites.

1. GPU profile virtual servers are only available on an operating system that supports Hardware Virtual Machine (HVM) boot mode. See the following list for operating systems that support HVM boot mode.  
  - CentOS 7
  - Debian 8
  - Debian 9
  - RHEL 7
  - Ubuntu 16
  - Ubuntu 18
  - Windows 2012 R2
  - Windows 2016

2. Appropriate NVIDIA drivers and software must be installed. For more information about software and NVIDIA drivers, see [Installing GPU drivers and software packages](/docs/virtual-servers?topic=virtual-servers-installing-gpu-drivers-and-software-packages#installing-gpu-drivers-and-software-packages).  

The software that you install might have prerequisite software and operating system-specific configurations.
{: note}

### Adding or removing GPUs
{: #adding-or-removing-gpus}

You can change the number of GPUs on your virtual server after your initial order. But, that depends on how many GPUs you provisioned. You have one of the following options.

- If one GPU is provisioned, you can add another GPU, or
- If two GPUs are provisioned, you can fallback to one GPU
