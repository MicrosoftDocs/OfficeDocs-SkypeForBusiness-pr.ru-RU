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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219382"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="66727-103">Добавление внутреннего IP-адреса пограничного сервера 2010</span><span class="sxs-lookup"><span data-stu-id="66727-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="66727-104">Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="66727-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="66727-105">В поле **Внутренний IPv4-адрес**введите IP-адрес пограничного сервера, который требуется добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="66727-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="66727-106">В поле **внутреннее полное**доменное имя введите полное доменное имя (FQDN) пограничного сервера, который требуется добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="66727-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="66727-107">Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="66727-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="66727-108">По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="66727-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="66727-109">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="66727-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="66727-110">Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="66727-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="66727-111">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="66727-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


