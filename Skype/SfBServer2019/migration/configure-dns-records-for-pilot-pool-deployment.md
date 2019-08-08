---
title: Настройка DNS-записей для развертывания пилотного пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед развертыванием пилотного пула необходимо обновить записи узла DNS для пилотного пула. Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.
ms.openlocfilehash: 0de8e144ea8d77e7ffa86562c120a54e3ec61ae0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239443"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="973dc-104">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="973dc-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="973dc-105">Перед развертыванием пилотного пула необходимо обновить записи узла DNS для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="973dc-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="973dc-106">Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="973dc-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="973dc-107">Настройка записей узла DNS</span><span class="sxs-lookup"><span data-stu-id="973dc-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="973dc-108">На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="973dc-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="973dc-109">В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="973dc-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="973dc-110">Выберите команду **создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="973dc-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="973dc-111">Щелкните **Name (имя**), введите имя узла для пула Skype для бизнеса Server 2019 (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).</span><span class="sxs-lookup"><span data-stu-id="973dc-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="973dc-112">Щелкните **IP-адрес**, а затем введите IP-адрес пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="973dc-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="973dc-113">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="973dc-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="973dc-114">Когда все будет готово, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="973dc-114">When you are finished, click **Done**.</span></span>
    

