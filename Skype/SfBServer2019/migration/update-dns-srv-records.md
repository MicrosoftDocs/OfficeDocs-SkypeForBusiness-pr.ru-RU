---
title: Обновление записей DNS SRV
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
description: Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753271"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="6d0db-103">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="6d0db-103">Update DNS SRV records</span></span>

<span data-ttu-id="6d0db-104">Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="6d0db-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="6d0db-105">В этом разделе описывается, как обновить записи службы доменных имен (DNS) после перехода на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d0db-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="6d0db-106">После того как все пользователи будут перемещены в Skype для бизнеса Server 2019, но до списания устаревшего пула или директора, необходимо обновить записи DNS SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="6d0db-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="6d0db-107">В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="6d0db-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="6d0db-108">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="6d0db-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="6d0db-109">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="6d0db-110">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**, РАЗВЕРНИТЕ домен SIP, в котором установлен Skype для бизнеса Server 2019, и перейдите к параметру **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="6d0db-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="6d0db-111">В правой области щелкните правой кнопкой мыши элемент **_sipinternaltls** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="6d0db-112">В **узле, на котором размещена эта служба**, обновите полное доменное имя узла, чтобы оно ссылалось на пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d0db-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="6d0db-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="6d0db-114">Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6d0db-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="6d0db-115">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="6d0db-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="6d0db-116">Нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="6d0db-117">В поле **Открыть** введите cmd, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="6d0db-118">В командной строки введите nslookup _\<FQDN of the Front End pool\>_ или и нажмите _\<FQDN of the Standard Edition server\>_ клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="6d0db-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="6d0db-119">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="6d0db-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

