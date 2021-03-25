---
title: Добавление внутреннего IP-адреса пограничного компьютера
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
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: 291c5cbd576d9a4cc03bf90caf41d167014a4ac4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120960"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="1a6a0-103">Добавление внутреннего IP-адреса пограничного компьютера</span><span class="sxs-lookup"><span data-stu-id="1a6a0-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="1a6a0-104">Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="1a6a0-105">Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="1a6a0-106">По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="1a6a0-107">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="1a6a0-108">Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену.</span><span class="sxs-lookup"><span data-stu-id="1a6a0-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1a6a0-109">Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span><span class="sxs-lookup"><span data-stu-id="1a6a0-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>