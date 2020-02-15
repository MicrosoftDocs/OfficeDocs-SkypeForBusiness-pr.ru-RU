---
title: 'Lync Server 2013: New – CsClientPolicy для управления адресной книгой'
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
ms.openlocfilehash: f84ef03f782263ed9f82b1667418c907087f5d5c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2b106-102">New – CsClientPolicy для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b106-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b106-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b106-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2b106-104">По умолчанию право на локальный запуск командлета New-CsClientPolicy имеют члены группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b106-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="2b106-105">Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2b106-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="2b106-106">Командлет New – CsClientPolicy определяет большое количество параметров для подготовки клиентов к функциям, доступным в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b106-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="2b106-107">Для службы адресной книги представляет интерес параметр AddressBookAvailability.</span><span class="sxs-lookup"><span data-stu-id="2b106-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="2b106-108">Он напрямую влияет на возможности, доступные клиенту, и предоставляет три параметра:</span><span class="sxs-lookup"><span data-stu-id="2b106-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="2b106-109">вебсеарчандфиледовнлоад</span><span class="sxs-lookup"><span data-stu-id="2b106-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="2b106-110">вебсеарчонли</span><span class="sxs-lookup"><span data-stu-id="2b106-110">WebSearchOnly</span></span>

  - <span data-ttu-id="2b106-111">филедовнлоадонли</span><span class="sxs-lookup"><span data-stu-id="2b106-111">FileDownloadOnly</span></span>

<span data-ttu-id="2b106-p103">Этот параметр определяет, как клиенты получают доступ к адресной книге. Если вы задали этот параметр, вы должны указать одну из его настроек. Если не изменить этот параметр, WebSearchAndFileDownload продолжает действовать.</span><span class="sxs-lookup"><span data-stu-id="2b106-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="2b106-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="2b106-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="2b106-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2b106-116">See Also</span></span>


[<span data-ttu-id="2b106-117">New — CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2b106-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

