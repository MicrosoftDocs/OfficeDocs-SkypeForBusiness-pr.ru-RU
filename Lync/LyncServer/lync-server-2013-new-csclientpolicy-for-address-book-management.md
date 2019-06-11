---
title: 'Lync Server 2013: New-CsClientPolicy для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a7cc6-102">New-CsClientPolicy для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7cc6-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7cc6-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a7cc6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a7cc6-104">Кто может запустить этот командлет: по умолчанию членам указанных ниже групп разрешено выполнять командлет New-CsClientPolicy: Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a7cc6-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a7cc6-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="a7cc6-106">Командлет New-CsClientPolicy определяет большое количество параметров для подготовки клиентов к функциям, которые доступны в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="a7cc6-107">Для службы адресной книги Аддрессбукаваилабилити параметра.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="a7cc6-108">Этот параметр, непосредственно влияющий на доступные клиентам варианты, имеет три возможных параметра:</span><span class="sxs-lookup"><span data-stu-id="a7cc6-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="a7cc6-109">Вебсеарчандфиледовнлоад</span><span class="sxs-lookup"><span data-stu-id="a7cc6-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="a7cc6-110">Вебсеарчонли</span><span class="sxs-lookup"><span data-stu-id="a7cc6-110">WebSearchOnly</span></span>

  - <span data-ttu-id="a7cc6-111">Филедовнлоадонли</span><span class="sxs-lookup"><span data-stu-id="a7cc6-111">FileDownloadOnly</span></span>

<span data-ttu-id="a7cc6-112">При определении определяет способ доступа к адресной книге клиентам.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="a7cc6-113">Если вы определяете этот параметр, необходимо задать один из вариантов.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="a7cc6-114">Если вы не измените этот параметр, Вебсеарчандфиледовнлоад по умолчанию остается в силе.</span><span class="sxs-lookup"><span data-stu-id="a7cc6-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="a7cc6-115">Например:</span><span class="sxs-lookup"><span data-stu-id="a7cc6-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="a7cc6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a7cc6-116">See Also</span></span>


[<span data-ttu-id="a7cc6-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a7cc6-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

