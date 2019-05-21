---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед развертыванием пилотного пула необходимо обновить записи узла DNS для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289625"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="2b8d1-104">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="2b8d1-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="2b8d1-105">Перед развертыванием пилотного пула необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="2b8d1-106">Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="2b8d1-107">Настройка записей узла DNS</span><span class="sxs-lookup"><span data-stu-id="2b8d1-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="2b8d1-108">На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="2b8d1-109">В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="2b8d1-110">Выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="2b8d1-111">Щелкните **Name (имя**), введите имя узла для пула Skype для бизнеса Server 2019 (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="2b8d1-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="2b8d1-112">Щелкните **IP-адрес**, а затем введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="2b8d1-113">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="2b8d1-114">Когда все будет готово, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2b8d1-114">When you are finished, click **Done**.</span></span>
    

