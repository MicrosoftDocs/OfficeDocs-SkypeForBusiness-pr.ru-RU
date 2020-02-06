---
title: Добавление внутреннего IP-адреса пограничного компьютера 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: На этой странице вы можете указать внутренний IP-адрес и внутреннее полное доменное имя (FQDN) для пограничного сервера.
ms.openlocfilehash: 1847362f93c1d1ff67c09fb9f552641b0e770bbc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821141"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="0ed87-103">Добавление внутреннего IP-адреса пограничного компьютера 2010</span><span class="sxs-lookup"><span data-stu-id="0ed87-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="0ed87-104">На этой странице вы можете указать внутренний IP-адрес и внутреннее полное доменное имя (FQDN) для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0ed87-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="0ed87-105">В поле **внутренний адрес IPv4**введите IP-адрес пограничного сервера, который вы хотите добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="0ed87-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="0ed87-106">В поле **внутренний доменное имя**введите полное доменное имя (FQDN) пограничного сервера, который вы хотите добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="0ed87-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="0ed87-107">Указанное полное доменное имя должно совпадать с именем компьютера, настроенным на сервере.</span><span class="sxs-lookup"><span data-stu-id="0ed87-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="0ed87-108">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="0ed87-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="0ed87-109">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="0ed87-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="0ed87-110">Поэтому необходимо настроить DNS-суффикс для имени компьютера, который будет развертываться в качестве пограничного сервера, не подключенного к домену.</span><span class="sxs-lookup"><span data-stu-id="0ed87-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0ed87-111">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Настройка поддержки DNS для Microsoft Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ed87-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


