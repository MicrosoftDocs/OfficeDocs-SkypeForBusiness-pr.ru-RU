---
title: 'Lync Server 2013: предоставление разрешений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="8d874-102">Предоставление разрешений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d874-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d874-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="8d874-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="8d874-104">Для программы установки можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="8d874-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="8d874-105">При этом выдаются следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="8d874-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="8d874-106">Чтение</span><span class="sxs-lookup"><span data-stu-id="8d874-106">Read</span></span>

  - <span data-ttu-id="8d874-107">Запись</span><span class="sxs-lookup"><span data-stu-id="8d874-107">Write</span></span>

  - <span data-ttu-id="8d874-108">реадспн</span><span class="sxs-lookup"><span data-stu-id="8d874-108">ReadSPN</span></span>

  - <span data-ttu-id="8d874-109">вритеспн</span><span class="sxs-lookup"><span data-stu-id="8d874-109">WriteSPN</span></span>

<span data-ttu-id="8d874-110">Для администрирования можно добавить разрешения в указанные подразделения, чтобы члены универсальных групп RTC, созданных в ходе подготовки леса, могли получить доступ к подразделениям, не являясь членами группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="8d874-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="8d874-111">Разрешения, добавляемые к указанному подразделению — это те же разрешения, которые командлет **Enable-CsAdDomain** добавляет для компьютеров и контейнеров пользователей подразделения.</span><span class="sxs-lookup"><span data-stu-id="8d874-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d874-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="8d874-112">In This Section</span></span>

  - [<span data-ttu-id="8d874-113">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d874-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="8d874-114">Предоставление разрешений организационных подразделений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d874-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

