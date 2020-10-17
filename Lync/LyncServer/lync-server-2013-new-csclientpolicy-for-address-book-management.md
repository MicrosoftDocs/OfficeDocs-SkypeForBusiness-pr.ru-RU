---
title: 'Lync Server 2013: New-CsClientPolicy для управления адресной книгой'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a253fb46dfdfe63957efa97ffa68d97ead65ed87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508826"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="88da4-102">New-CsClientPolicy для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88da4-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88da4-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="88da4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="88da4-104">По умолчанию право на локальный запуск командлета New-CsClientPolicy имеют члены группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="88da4-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="88da4-105">Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="88da4-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="88da4-106">Командлет New-CsClientPolicy определяет большое количество параметров для подготовки клиентов к функциям, доступным в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88da4-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="88da4-107">Для службы адресной книги представляет интерес параметр AddressBookAvailability.</span><span class="sxs-lookup"><span data-stu-id="88da4-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="88da4-108">Он напрямую влияет на возможности, доступные клиенту, и предоставляет три параметра:</span><span class="sxs-lookup"><span data-stu-id="88da4-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="88da4-109">вебсеарчандфиледовнлоад</span><span class="sxs-lookup"><span data-stu-id="88da4-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="88da4-110">вебсеарчонли</span><span class="sxs-lookup"><span data-stu-id="88da4-110">WebSearchOnly</span></span>

  - <span data-ttu-id="88da4-111">филедовнлоадонли</span><span class="sxs-lookup"><span data-stu-id="88da4-111">FileDownloadOnly</span></span>

<span data-ttu-id="88da4-p103">Этот параметр определяет, как клиенты получают доступ к адресной книге. Если вы задали этот параметр, вы должны указать одну из его настроек. Если не изменить этот параметр, WebSearchAndFileDownload продолжает действовать.</span><span class="sxs-lookup"><span data-stu-id="88da4-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="88da4-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="88da4-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="88da4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="88da4-116">See Also</span></span>


[<span data-ttu-id="88da4-117">New — CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="88da4-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

