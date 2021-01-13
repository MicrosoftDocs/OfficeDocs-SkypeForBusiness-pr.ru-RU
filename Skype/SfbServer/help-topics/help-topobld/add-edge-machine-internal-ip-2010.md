---
title: Добавление внутреннего IP-адреса пограничного сервера 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: eb5d2d8aa7dd0d7827e13089f7588f5090b6744a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828789"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="f9578-103">Добавление внутреннего IP-адреса пограничного сервера 2010</span><span class="sxs-lookup"><span data-stu-id="f9578-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="f9578-104">Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f9578-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="f9578-105">Во **внутреннем IPv4-адресе** введите IP-адрес сервера, который нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="f9578-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="f9578-106">Во **внутреннем полном доменном имени** введите полное доменное имя (FQDN) сервера, который нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="f9578-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="f9578-107">Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="f9578-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="f9578-108">По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="f9578-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="f9578-109">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="f9578-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="f9578-110">Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="f9578-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="f9578-111">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="f9578-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


