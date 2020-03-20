---

copyright:
  years: 2018, 2019
lastupdated: "2019-06-04"

subcollection: virtual-servers

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:table: .aria-labeledby="caption"}

# Assigning server IP addresses
{: #assigning-server-ip-addresses}

{{site.data.keyword.cloud}} configures virtual server instances with an IPv4 address on the private network, and if requested, a public (internet-facing) IPv4 address. Additionally, you can request an IPv6 address on the public network. All of these IP addresses are collectively referred to as _Primary IP Addresses_.
{:shortdesc}

Additional IP addresses can be bound to virtual server instances after purchasing secondary subnets through the {{site.data.keyword.cloud_notm}} console. IP addresses purchased in this way and managed by you are referred to as _Secondary IP Addresses_.

For more information about options available for acquiring IP addresses, see [Subnets and IPs](/docs/subnets?topic=subnets-about-subnets-and-ips).

## Binding secondary IP addresses
{: #binding-secondary-ip-addresses}

After a secondary subnet is purchased and routed, you must configure the operating system to use one or more of the newly available IP addresses. The configuration steps for the new IP addresses are different for each operating system, but the setup is typically referred to as setting up "interface aliases." See your operating system documentation for additional configuration details.
