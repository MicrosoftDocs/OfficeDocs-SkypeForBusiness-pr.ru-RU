---
title: Добавление IP-адреса NAT пограничного сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: Общедоступный IP-адрес — это IP-адрес, используемый преобразование сетевых адресов (NAT). IP-адрес должен быть открыто маршрутизируемыми. Это необходимо, потому что вы выбрали внешний IP-адрес этого пограничного пула преобразуется параметром преобразования сетевых адресов на странице "Выбор компонентов" мастера.
ms.openlocfilehash: 4f27af53c8075db48d0774ea67c389802ee56e24
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889040"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="aae72-105">Добавление IP-адреса NAT пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="aae72-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="aae72-106">Общедоступный IP-адрес — это IP-адрес, используемый преобразование сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="aae72-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="aae72-107">IP-адрес должен быть открыто маршрутизируемыми.</span><span class="sxs-lookup"><span data-stu-id="aae72-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="aae72-108">Это необходимо, так как выбрано **внешний IP-адрес этого пограничного пула преобразовываются NAT** на странице **Выбор компонентов** из этого мастера.</span><span class="sxs-lookup"><span data-stu-id="aae72-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="aae72-109">Преобразование сетевых адресов (NAT) позволяет клиентов или серверов в частной сети (например, 192.168.0.0 диапазон) для взаимодействия с системами для удаленных сетей через общедоступную сеть Интернет.</span><span class="sxs-lookup"><span data-stu-id="aae72-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="aae72-110">Преобразование сетевых адресов работает с помощью один общедоступный IP-адрес для внешнего интерфейса, связь с один общий IP-адрес внутреннего IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="aae72-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="aae72-111">Сопоставление NAT сопоставляет внешний общедоступный IP-адрес внутреннего адреса.</span><span class="sxs-lookup"><span data-stu-id="aae72-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="aae72-112">Удаленная система видит только общий адрес источника.</span><span class="sxs-lookup"><span data-stu-id="aae72-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="aae72-113">Удаленная система отвечает на источник, а источник ссылается на NAT сопоставить определить, какие внутреннего IP-адреса ответа должны быть возвращены для.</span><span class="sxs-lookup"><span data-stu-id="aae72-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="aae72-p104">Поддержку внешнего доступа пользователей можно настроить при развертывании начальной топологии или позднее. Дополнительные сведения о добавлении пограничных серверов к существующей топологии см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) документации по развертыванию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="aae72-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


