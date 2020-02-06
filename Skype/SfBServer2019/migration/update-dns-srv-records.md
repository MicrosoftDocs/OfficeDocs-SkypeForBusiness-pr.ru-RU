---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812777"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="a0819-103">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="a0819-103">Update DNS SRV records</span></span>

<span data-ttu-id="a0819-104">Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="a0819-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="a0819-105">В этой статье описано, как обновить записи DNS после перехода на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a0819-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="a0819-106">После того как все пользователи будут перемещены в Skype для бизнеса Server 2019, но перед удалением устаревшего пула или режиссера необходимо обновить записи DNS SRV во внутренней службе DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="a0819-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="a0819-107">В этой процедуре предполагается, что в вашей внутренней DNS-зоне есть зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="a0819-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="a0819-108">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="a0819-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="a0819-109">На DNS-сервере нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="a0819-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="a0819-110">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**, РАЗВЕРНИТЕ домен SIP, в котором установлен Skype для Business Server 2019, и перейдите к параметру **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="a0819-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="a0819-111">На правой панели щелкните правой кнопкой мыши **_sipinternaltls** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="a0819-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="a0819-112">В **узле, предлагающем эту службу**, обновите полное доменное имя узла, чтобы оно указывало на пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a0819-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="a0819-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0819-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="a0819-114">Проверка возможности разрешения полных доменных имен в пуле или сервере Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a0819-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="a0819-115">Войдите в домен на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0819-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="a0819-116">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a0819-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="a0819-117">В поле **Открыть** введите cmd и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0819-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="a0819-118">В командной строке введите nslookup _ \<FQDN для пула\> переднего плана_ или _ \<полное доменное имя сервера\>Standard Edition_, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a0819-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="a0819-119">Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="a0819-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

