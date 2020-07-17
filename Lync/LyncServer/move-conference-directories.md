---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="83d54-102">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="83d54-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d54-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="83d54-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="83d54-104">Перед списанием пула необходимо выполнить следующую процедуру для каждого каталога конференций в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="83d54-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="83d54-105">Перемещение каталога конференций на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83d54-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="83d54-106">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83d54-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="83d54-107">Чтобы получить идентификатор каталогов конференций в организации, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="83d54-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="83d54-p101">Так как этот командлет возвращает все каталоги конференций в организации, вы можете ограничить результаты только для ликвидируемого пула. Например, если вы хотите ликвидировать пул с полным доменным именем pool01.contoso.net, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="83d54-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="83d54-110">Этот командлет возвращает все каталоги конференций, для которых идентификатор службы содержит полное доменное имя pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="83d54-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="83d54-111">Для перемещения каталогов конференций выполните следующую команду для каждого каталога конференции в пуле:</span><span class="sxs-lookup"><span data-stu-id="83d54-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="83d54-112">Например:</span><span class="sxs-lookup"><span data-stu-id="83d54-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="83d54-113">Вы можете столкнуться с ошибкой, показанной ниже, которая связана с тем, что командная консоль Lync Server запрашивает обновленный набор разрешений из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="83d54-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="83d54-114">Чтобы устранить эту ошибку, закрыло текущее окно и откройте новую командную консоль Lync Server, а затем снова запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="83d54-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="83d54-115">![Вывод ошибок Move – CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Вывод ошибок Move – CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="83d54-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

