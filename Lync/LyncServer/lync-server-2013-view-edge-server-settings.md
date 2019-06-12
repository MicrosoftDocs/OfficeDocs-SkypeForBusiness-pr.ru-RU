---
title: 'Lync Server 2013: Просмотр параметров пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="9de69-102">Просмотр параметров пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9de69-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9de69-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9de69-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="9de69-104">Общие конфигурации пограничного сервера следует проверять на основе данных в базе данных управления конфигурацией, чтобы гарантировать, что все изменения будут документированы в соответствии с определенными процедурами управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="9de69-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="9de69-105">Дополнительные проверки могут включать в себя те, которые описаны в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9de69-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="9de69-106">Проверка списка разрешенных и заблокированных списков</span><span class="sxs-lookup"><span data-stu-id="9de69-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="9de69-107">Убедитесь, что указанные пространства имен по-прежнему являются допустимыми списками URI SIP "Allow" и "Block" для федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="9de69-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="9de69-108">Вы можете использовать Windows PowerShell для просмотра списка разрешенных и заблокированных списков.</span><span class="sxs-lookup"><span data-stu-id="9de69-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="9de69-109">Чтобы просмотреть домены в списке разрешенные домены, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9de69-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="9de69-110">Эта команда возвращает сведения о доменах в списке разрешенные домены, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9de69-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="9de69-111">Identity: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9de69-111">Identity : contoso.com</span></span>

<span data-ttu-id="9de69-112">Domain (домен): contoso.com</span><span class="sxs-lookup"><span data-stu-id="9de69-112">Domain : contoso.com</span></span>

<span data-ttu-id="9de69-113">Проксифкдн:</span><span class="sxs-lookup"><span data-stu-id="9de69-113">ProxyFqdn :</span></span>

<span data-ttu-id="9de69-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9de69-114">Comment :</span></span>

<span data-ttu-id="9de69-115">Маркформониторинг: false</span><span class="sxs-lookup"><span data-stu-id="9de69-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="9de69-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="9de69-116">Comment :</span></span>

<span data-ttu-id="9de69-117">Чтобы просмотреть домены в списке блокируемых доменов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9de69-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="9de69-118">В свою очередь, вы получите такие сведения, как, например, для всех блокируемых доменов.</span><span class="sxs-lookup"><span data-stu-id="9de69-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="9de69-119">Identity: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="9de69-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="9de69-120">Domain (домен): tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="9de69-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="9de69-121">Кроме того, Windows PowerShell позволяет убедиться, что вы можете подключиться к доменам в списке разрешенные домены.</span><span class="sxs-lookup"><span data-stu-id="9de69-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="9de69-122">Например, эта команда проверяет соединение между пограничным сервером (Таржетфкдн) и федеративным доменом contoso.com:</span><span class="sxs-lookup"><span data-stu-id="9de69-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="9de69-123">Эта команда проверяет подключение между пограничным сервером и всеми доменами, которые находятся в списке разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="9de69-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="9de69-124">Проверка того, что несколько пограничных серверов идентичны</span><span class="sxs-lookup"><span data-stu-id="9de69-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="9de69-125">Если в массиве с балансировкой нагрузки развернут несколько пограничных серверов, мы рекомендуем проверить, настроены ли все пограничные серверы в массиве одинаковым образом.</span><span class="sxs-lookup"><span data-stu-id="9de69-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="9de69-126">Параметры для пограничных серверов можно просмотреть в области сведений в расширении Lync Server 2013 для оснастки управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="9de69-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9de69-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9de69-127">See Also</span></span>


[<span data-ttu-id="9de69-128">Get-Ксалловеддомаин</span><span class="sxs-lookup"><span data-stu-id="9de69-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="9de69-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="9de69-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="9de69-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="9de69-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

