---
title: Обновление записей DNS SRV
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Чтобы успешно выполнить данную процедуру, необходимо войти в систему на сервере или в домене, что и должна быть членом группы администраторов домена или член группы DnsAdmins.
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027230"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="a525c-103">Обновление записей DNS SRV</span><span class="sxs-lookup"><span data-stu-id="a525c-103">Update DNS SRV records</span></span>

<span data-ttu-id="a525c-104">Чтобы успешно выполнить данную процедуру, необходимо войти в систему на сервере или в домене, что и должна быть членом группы администраторов домена или член группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="a525c-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="a525c-105">В этом разделе описывается, как обновить записи доменных имен (DNS) после миграции на Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a525c-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="a525c-106">После перемещения всех пользователей к Скайп для Business Server 2019, но перед ликвидацией устаревшего пула и директора, необходимо обновить DNS SRV-записи во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="a525c-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="a525c-107">Эта процедура предполагается, что внутренний DNS-сервера содержит зон для своих доменов SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="a525c-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="a525c-108">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="a525c-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="a525c-109">На DNS-сервере нажмите кнопку **Пуск**, выберите пункт **Администрирование**и затем щелкните **DNS**.</span><span class="sxs-lookup"><span data-stu-id="a525c-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="a525c-110">В дереве консоли для вашего домена SIP разверните узел **Зоны прямого просмотра**, разверните SIP-домена, в котором Скайп for Business Server 2019 установлен и перейдите к параметру **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="a525c-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="a525c-111">В правой области щелкните правой кнопкой мыши **_sipinternaltls** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a525c-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="a525c-112">В **узел этой службы**обновите полное доменное имя для указания на Скайп для пула Business Server 2019 узла.</span><span class="sxs-lookup"><span data-stu-id="a525c-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="a525c-113">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a525c-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="a525c-114">Чтобы убедиться, что можно разрешить полное доменное имя пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a525c-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="a525c-115">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="a525c-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="a525c-116">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a525c-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="a525c-117">В поле **Открыть** введите cmd и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a525c-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="a525c-118">В командной строке введите nslookup _ \<полное доменное имя пула переднего плана\> _ или _ \<полное доменное имя сервера Standard Edition\>_, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a525c-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="a525c-119">Убедитесь в том, что вы получили ответ, которая разрешается в нужный IP-адрес для полного доменного ИМЕНИ.</span><span class="sxs-lookup"><span data-stu-id="a525c-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

