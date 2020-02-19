---
title: 'Lync Server 2013: Просмотр параметров пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eb804329bd0e8ce5c502c44d1ef1071e19f65c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="3516a-102">Просмотр параметров пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3516a-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3516a-103">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="3516a-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="3516a-104">Общие конфигурации пограничных серверов следует проверить на соответствие данным в базе данных управления конфигурацией, чтобы обеспечить документирование всех изменений в соответствии с определенными процедурами управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="3516a-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="3516a-105">Дополнительные проверки могут включать в себя те, что описаны в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3516a-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="3516a-106">Проверка списков разрешенных и заблокированных списков</span><span class="sxs-lookup"><span data-stu-id="3516a-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="3516a-107">Проверьте списки URI SIP "Allow" и "Block" для федеративных доменов, чтобы определить, являются ли указанные пространства имен действительными.</span><span class="sxs-lookup"><span data-stu-id="3516a-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="3516a-108">Вы можете использовать Windows PowerShell для просмотра разрешенных и заблокированных списков.</span><span class="sxs-lookup"><span data-stu-id="3516a-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="3516a-109">Чтобы просмотреть домены в списке разрешенных доменов, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3516a-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="3516a-110">Эта команда возвращает сведения, аналогичные приведенным ниже, для доменов в списке разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="3516a-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="3516a-111">Identity: contoso.com</span><span class="sxs-lookup"><span data-stu-id="3516a-111">Identity : contoso.com</span></span>

<span data-ttu-id="3516a-112">Домен: contoso.com</span><span class="sxs-lookup"><span data-stu-id="3516a-112">Domain : contoso.com</span></span>

<span data-ttu-id="3516a-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="3516a-113">ProxyFqdn :</span></span>

<span data-ttu-id="3516a-114">Комментарий</span><span class="sxs-lookup"><span data-stu-id="3516a-114">Comment :</span></span>

<span data-ttu-id="3516a-115">Маркформониторинг: false</span><span class="sxs-lookup"><span data-stu-id="3516a-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="3516a-116">Комментарий</span><span class="sxs-lookup"><span data-stu-id="3516a-116">Comment :</span></span>

<span data-ttu-id="3516a-117">Чтобы просмотреть домены в списке блокируемых доменов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3516a-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="3516a-118">В свою очередь вы получите такие сведения, как, например, для каждого заблокированного домена:</span><span class="sxs-lookup"><span data-stu-id="3516a-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="3516a-119">Identity: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="3516a-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="3516a-120">Домен: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="3516a-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="3516a-121">Кроме того, Windows PowerShell позволяет убедиться, что вы можете подключиться к доменам в списке разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="3516a-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="3516a-122">Например, эта команда проверяет подключение между пограничным сервером (TargetFqdn) и contoso.com федеративного домена:</span><span class="sxs-lookup"><span data-stu-id="3516a-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="3516a-123">Эта команда проверяет подключение между пограничным сервером и всеми доменами, найденными в списке разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="3516a-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="3516a-124">Проверка того, что несколько пограничных серверов идентичны</span><span class="sxs-lookup"><span data-stu-id="3516a-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="3516a-125">Если в массиве с балансировкой нагрузки развернуты несколько пограничных серверов, рекомендуется проверить, что все пограничные серверы в массиве настроены одинаковым образом.</span><span class="sxs-lookup"><span data-stu-id="3516a-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="3516a-126">Параметры для пограничных серверов можно просмотреть в области сведений расширения Lync Server 2013 для оснастки "Управление компьютером".</span><span class="sxs-lookup"><span data-stu-id="3516a-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3516a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3516a-127">See Also</span></span>


[<span data-ttu-id="3516a-128">Get — CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="3516a-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="3516a-129">Get — CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="3516a-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="3516a-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="3516a-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

