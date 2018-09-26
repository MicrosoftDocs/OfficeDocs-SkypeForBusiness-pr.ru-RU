---
title: Настройка DNS-записей для развертывания пилотного пула
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед развертыванием пилотного пула, необходимо обновить записи узла DNS A для пилотного пула. Чтобы успешно выполнить данную процедуру, необходимо войти в систему на сервере или в домене, что и должна быть членом группы администраторов домена или член группы DnsAdmins.
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029897"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="8952a-104">Настройка DNS-записей для развертывания пилотного пула</span><span class="sxs-lookup"><span data-stu-id="8952a-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="8952a-105">Перед развертыванием пилотного пула, необходимо обновить записи узла DNS A для пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="8952a-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="8952a-106">Чтобы успешно выполнить данную процедуру, необходимо войти в систему на сервере или в домене, что и должна быть членом группы администраторов домена или член группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8952a-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="8952a-107">Настройка записей A узла DNS</span><span class="sxs-lookup"><span data-stu-id="8952a-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="8952a-108">На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**и затем щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8952a-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="8952a-109">В дереве консоли для своего домена разверните узел **Зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8952a-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="8952a-110">Щелкните **Создать узел (A или AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="8952a-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="8952a-111">Выберите **имя**, введите имя узла для Скайп для пула Business Server 2019 (доменное имя берется из зоны, определенные в эту запись и не нужно вводить как часть записи A узла).</span><span class="sxs-lookup"><span data-stu-id="8952a-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="8952a-112">Выберите **IP-адрес**и введите IP-адрес для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8952a-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="8952a-113">Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8952a-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="8952a-114">Завершив настройку, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8952a-114">When you are finished, click **Done**.</span></span>
    

