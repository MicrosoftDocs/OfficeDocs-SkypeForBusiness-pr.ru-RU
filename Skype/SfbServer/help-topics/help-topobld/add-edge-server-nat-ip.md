---
title: Добавление IP-адреса NAT пограничного сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: Общедоступный IP-адрес — это IP-адрес, который используется при преобразовании сетевых адресов (NAT). Такой IP-адрес должен обеспечивать общедоступную маршрутизацию. Это требуется из-за того, что вы выбрали параметр Внешний IP-адрес данного пограничного пула преобразуется системой NAT на странице Выбрать функции данного матера.
ms.openlocfilehash: 12749d3bcaec2478481fc1a4bc5597fb9693c5c4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216550"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="2e403-105">Добавление IP-адреса NAT пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2e403-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="2e403-p102">Общедоступный IP-адрес — это IP-адрес, который используется при преобразовании сетевых адресов (NAT). Такой IP-адрес должен обеспечивать общедоступную маршрутизацию. Это требуется из-за того, что вы выбрали параметр **Внешний IP-адрес данного пограничного пула преобразуется системой NAT** на странице **Выбрать функции** данного матера.</span><span class="sxs-lookup"><span data-stu-id="2e403-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="2e403-p103">Преобразование сетевых адресов (NAT) позволяет клиентам или серверам из частной сети (например, в диапазоне 192.168.0.0) взаимодействовать с системами в удаленных сетях через общедоступную сеть Интернет. Преобразование сетевых адресов использует отдельный общедоступный IP-адрес во внешнем интерфейсе и сопоставляет с этим адресом внутренние IP-адреса. NAT сопоставляет внутренний адрес с внешним общедоступным IP-адресом. В результате удаленная система видит только общедоступный адрес источника. Удаленная система отвечает источнику, который ссылается на сопоставление NAT, чтобы определить, на какой внутренний IP-адрес следует возвратить этот ответ.</span><span class="sxs-lookup"><span data-stu-id="2e403-p103">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks. NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address. NAT mapping maps an internal address to the external public IP address. The remote system sees only the public address of the source. The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="2e403-114">Поддержку внешнего доступа пользователей можно добавить при развертывании начальной топологии или позднее.</span><span class="sxs-lookup"><span data-stu-id="2e403-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="2e403-115">Дополнительные сведения о добавлении пограничных серверов в существующую топологию см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) документации по развертыванию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2e403-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


