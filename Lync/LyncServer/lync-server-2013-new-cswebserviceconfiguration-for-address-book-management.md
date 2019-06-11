---
title: 'Lync Server 2013: New-Ксвебсервицеконфигуратион для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a973ca1086a9d2ca1ce2d8f19bbb64ba8aae19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="4c2dc-102">New-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c2dc-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c2dc-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4c2dc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4c2dc-104">Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет New-Ксвебсервицеконфигуратион локально: Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="4c2dc-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4c2dc-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="4c2dc-106">Командлет New-Ксвебсервицеконфигуратион определяет новую конфигурацию веб-служб в Организации.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="4c2dc-107">Область конфигурации веб-служб может находиться только на уровне сайта или службы.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="4c2dc-108">Создать новую конфигурацию веб-служб на глобальном уровне нельзя.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="4c2dc-109">В адресную книгу, в частности, интересует атрибут Енаблеграупексансион.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="4c2dc-110">Если установлено значение true, веб-службы могут отвечать на запросы на развертывание групп.</span><span class="sxs-lookup"><span data-stu-id="4c2dc-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="4c2dc-111">Например:</span><span class="sxs-lookup"><span data-stu-id="4c2dc-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="4c2dc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4c2dc-112">See Also</span></span>


[<span data-ttu-id="4c2dc-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c2dc-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

