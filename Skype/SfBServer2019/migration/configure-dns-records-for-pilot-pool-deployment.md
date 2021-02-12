---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Перед развертыванием пилотного пула необходимо обновить записи DNS Host A для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754059"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="eeef3-104">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="eeef3-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="eeef3-105">Перед развертыванием пилотного пула необходимо обновить записи DNS Host A для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="eeef3-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="eeef3-106">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="eeef3-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="eeef3-107">Настройка записей A узла DNS</span><span class="sxs-lookup"><span data-stu-id="eeef3-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="eeef3-108">На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="eeef3-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="eeef3-109">В дереве консоли домена разйдите зоны прямого подсмотра **и** щелкните правой кнопкой мыши домен, в котором будет установлен Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eeef3-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="eeef3-110">Выберите команду **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="eeef3-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="eeef3-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span><span class="sxs-lookup"><span data-stu-id="eeef3-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="eeef3-112">Щелкните **IP-адрес** и введите IP-адрес для пула переднего входа.</span><span class="sxs-lookup"><span data-stu-id="eeef3-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="eeef3-113">Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eeef3-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="eeef3-114">По завершении нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="eeef3-114">When you are finished, click **Done**.</span></span>
    

