---
title: Добавление внутреннего IP-адреса пограничного сервера 2010
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: 2f60eef6392b335461a9e0fc427c19d9f1d7b661
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219200"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="5732a-103">Добавление внутреннего IP-адреса пограничного сервера 2010</span><span class="sxs-lookup"><span data-stu-id="5732a-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="5732a-104">Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5732a-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="5732a-105">Указанное полное доменное имя должно совпадать с именем компьютера, настроенным на сервере.</span><span class="sxs-lookup"><span data-stu-id="5732a-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="5732a-106">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="5732a-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="5732a-107">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="5732a-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="5732a-108">Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="5732a-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="5732a-109">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера приведены в разделе [Настройка DNS для поддержки пограничной службы](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span><span class="sxs-lookup"><span data-stu-id="5732a-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span></span>


