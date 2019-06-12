---
title: Перемещение каталогов конференций
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="a2084-102">Перемещение каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="a2084-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2084-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a2084-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a2084-104">Перед списанием пула вам потребуется выполнить описанные ниже действия для каждой из каталогов конференций в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a2084-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="a2084-105">Перемещение каталога конференций на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2084-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="a2084-106">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a2084-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a2084-107">Чтобы получить удостоверение каталогов конференции в Организации, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="a2084-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="a2084-108">Поскольку этот командлет возвращает все каталоги конференций в Организации, может потребоваться ограничить результаты только тем пулом, для которого вы хотите списать.</span><span class="sxs-lookup"><span data-stu-id="a2084-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="a2084-109">Например, если вы хотите списать пул с полным доменным именем (FQDN) pool01.contoso.net, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a2084-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="a2084-110">Этот командлет возвращает все каталоги конференций, в которых служба Service ID имеет полное доменное имя (FQDN) pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="a2084-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="a2084-111">Чтобы переместить каталоги конференций, выполните указанные ниже действия для каждой из каталогов конференций в пуле.</span><span class="sxs-lookup"><span data-stu-id="a2084-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="a2084-112">Например:</span><span class="sxs-lookup"><span data-stu-id="a2084-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="a2084-113">Вы можете столкнуться с ошибкой, описанной ниже, которая связана с тем, что в командной консоли Lync Server, требующей обновленный набор разрешений из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a2084-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="a2084-114">Чтобы устранить эту ошибку, закройте текущее окно и откройте новую консоль управления Lync Server, а затем выполните команду еще раз.</span><span class="sxs-lookup"><span data-stu-id="a2084-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="a2084-115">![Вывод ошибок Move-ксконференцедиректори] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Вывод ошибок Move-ксконференцедиректори")</span><span class="sxs-lookup"><span data-stu-id="a2084-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

