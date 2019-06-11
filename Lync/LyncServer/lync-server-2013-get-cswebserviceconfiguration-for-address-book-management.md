---
title: 'Lync Server 2013: Get-Ксвебсервицеконфигуратион для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e88d13a910a7883f88ceadc28225cbaa85bb17b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c49c9-102">Get-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c49c9-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c49c9-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c49c9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c49c9-104">Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Get-Ксвебсервицеконфигуратион локально: Рткуниверсалусерадминс, Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="c49c9-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="c49c9-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c49c9-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="c49c9-106">Get-Ксвебсервицеконфигуратион возвращает сведения о конфигурации веб-служб, которые в настоящее время используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c49c9-106">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization.</span></span> <span data-ttu-id="c49c9-107">% Поинтересуются службами адресных книг — это состояние функции расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="c49c9-107">Of interest to the Address Book Services is the status of Distribution List Expansion function.</span></span> <span data-ttu-id="c49c9-108">Если атрибут Енаблеграупекспансион имеет значение true, ваша организация в настоящее время допускает развертывание групп.</span><span class="sxs-lookup"><span data-stu-id="c49c9-108">If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="c49c9-109">Например:</span><span class="sxs-lookup"><span data-stu-id="c49c9-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="c49c9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c49c9-110">See Also</span></span>


[<span data-ttu-id="c49c9-111">Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c49c9-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

