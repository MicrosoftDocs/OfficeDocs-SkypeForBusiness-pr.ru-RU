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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="7ea3d-102">Предоставление разрешений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea3d-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ea3d-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="7ea3d-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="7ea3d-104">Для настройки можно предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="7ea3d-105">При предоставлении разрешений на доступ к подразделению предоставляются следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="7ea3d-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="7ea3d-106">Читаются</span><span class="sxs-lookup"><span data-stu-id="7ea3d-106">Read</span></span>

  - <span data-ttu-id="7ea3d-107">Пишу</span><span class="sxs-lookup"><span data-stu-id="7ea3d-107">Write</span></span>

  - <span data-ttu-id="7ea3d-108">реадспн</span><span class="sxs-lookup"><span data-stu-id="7ea3d-108">ReadSPN</span></span>

  - <span data-ttu-id="7ea3d-109">вритеспн</span><span class="sxs-lookup"><span data-stu-id="7ea3d-109">WriteSPN</span></span>

<span data-ttu-id="7ea3d-110">Для администрирования вы можете добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные с помощью подготовки леса, могли получать доступ к подразделениям без необходимости входить в группу администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="7ea3d-111">Разрешения, добавленные в указанный ОРГАНИЗАЦИОНный элемент, совпадают с разрешениями, которые командлет **Enable-ксаддомаин** добавляет к контейнерам OU Computers и Users.</span><span class="sxs-lookup"><span data-stu-id="7ea3d-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ea3d-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="7ea3d-112">In This Section</span></span>

  - [<span data-ttu-id="7ea3d-113">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea3d-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="7ea3d-114">Предоставление разрешений организационного подразделения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ea3d-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

