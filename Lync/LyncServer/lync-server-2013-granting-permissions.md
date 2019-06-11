---
title: 'Lync Server 2013: предоставление разрешений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="02151-102">Предоставление разрешений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02151-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02151-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="02151-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="02151-104">Для настройки можно предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домене.</span><span class="sxs-lookup"><span data-stu-id="02151-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="02151-105">При предоставлении разрешений на доступ к подразделению предоставляются следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="02151-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="02151-106">Читаются</span><span class="sxs-lookup"><span data-stu-id="02151-106">Read</span></span>

  - <span data-ttu-id="02151-107">Пишу</span><span class="sxs-lookup"><span data-stu-id="02151-107">Write</span></span>

  - <span data-ttu-id="02151-108">Реадспн</span><span class="sxs-lookup"><span data-stu-id="02151-108">ReadSPN</span></span>

  - <span data-ttu-id="02151-109">Вритеспн</span><span class="sxs-lookup"><span data-stu-id="02151-109">WriteSPN</span></span>

<span data-ttu-id="02151-110">Для администрирования вы можете добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные с помощью подготовки леса, могли получать доступ к подразделениям без необходимости входить в группу администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="02151-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="02151-111">Разрешения, добавленные в указанный ОРГАНИЗАЦИОНный элемент, совпадают с разрешениями, которые командлет **Enable-ксаддомаин** добавляет к контейнерам OU Computers и Users.</span><span class="sxs-lookup"><span data-stu-id="02151-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02151-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="02151-112">In This Section</span></span>

  - [<span data-ttu-id="02151-113">Предоставление разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02151-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="02151-114">Предоставление разрешений организационного подразделения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02151-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

