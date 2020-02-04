---
title: Добавление внутреннего IP-адреса пограничного компьютера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
description: На этой странице вы можете указать внутренний IP-адрес и внутреннее полное доменное имя (FQDN) для пограничного сервера.
ms.openlocfilehash: b26e86391dca65665c368ab5ce7f0f9eb36d4940
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698514"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="238f9-103">Добавление внутреннего IP-адреса пограничного компьютера</span><span class="sxs-lookup"><span data-stu-id="238f9-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="238f9-104">На этой странице вы можете указать внутренний IP-адрес и внутреннее полное доменное имя (FQDN) для пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="238f9-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="238f9-105">Указанное полное доменное имя должно совпадать с именем компьютера, настроенным на сервере.</span><span class="sxs-lookup"><span data-stu-id="238f9-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="238f9-106">По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="238f9-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="238f9-107">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="238f9-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="238f9-108">Поэтому необходимо настроить DNS-суффикс для имени компьютера, который будет развертываться в качестве пограничного сервера, не подключенного к домену.</span><span class="sxs-lookup"><span data-stu-id="238f9-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="238f9-109">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Настройка поддержки DNS для Microsoft Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="238f9-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


