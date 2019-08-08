---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.
ms.openlocfilehash: 5d506c3b2ff70ae776396e8d3a51e71360cdcc83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241160"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="eb65e-103">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="eb65e-103">Update DNS SRV records</span></span>

<span data-ttu-id="eb65e-104">Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="eb65e-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="eb65e-105">В этой статье описано, как обновить записи DNS после перехода на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb65e-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="eb65e-106">После того как все пользователи будут перемещены в Skype для бизнеса Server 2019, но перед удалением устаревшего пула или режиссера необходимо обновить записи DNS SRV во внутренней службе DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="eb65e-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="eb65e-107">В этой процедуре предполагается, что в вашей внутренней DNS-зоне есть зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="eb65e-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="eb65e-108">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="eb65e-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="eb65e-109">На DNS-сервере нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="eb65e-110">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**, РАЗВЕРНИТЕ домен SIP, в котором установлен Skype для Business Server 2019, и перейдите к параметру " **_tcp** ".</span><span class="sxs-lookup"><span data-stu-id="eb65e-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="eb65e-111">На правой панели щелкните правой кнопкой мыши **_sipinternaltls** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="eb65e-112">В **узле, предлагающем эту службу**, обновите полное доменное имя узла, чтобы оно указывало на пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eb65e-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="eb65e-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="eb65e-114">Проверка возможности разрешения полных доменных имен в пуле или сервере Standard Edition</span><span class="sxs-lookup"><span data-stu-id="eb65e-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="eb65e-115">Войдите в домен на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb65e-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="eb65e-116">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="eb65e-117">В поле **Открыть** введите cmd и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eb65e-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="eb65e-118">В командной строке введите nslookup _ \<FQDN для пула\> переднего плана_ или _ \<полное доменное имя\>сервера Standard Edition_, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="eb65e-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="eb65e-119">Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="eb65e-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

