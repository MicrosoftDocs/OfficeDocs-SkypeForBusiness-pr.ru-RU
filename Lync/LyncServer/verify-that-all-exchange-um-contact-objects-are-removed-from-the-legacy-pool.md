---
title: Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула
description: Убедитесь, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555515"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="87fc7-103">Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула</span><span class="sxs-lookup"><span data-stu-id="87fc7-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87fc7-104">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="87fc7-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="87fc7-105">С помощью средства **OCSUmUtil** или командлета **Get – CsExumContact** убедитесь, что объекты контакта единой системы обмена сообщениями Exchange удалены из пула Office Communications Server 2007 R2 прежних версий.</span><span class="sxs-lookup"><span data-stu-id="87fc7-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="87fc7-106">Средство **OCSUmUtil** содержится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="87fc7-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="87fc7-107">% Program Files% \\ Common Files \\ Lync Server 2013 \\ support \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="87fc7-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="87fc7-108">Средство **OCSUmUtil** должно быть запущено от имени учетной записи, которая характеризуется следующим:</span><span class="sxs-lookup"><span data-stu-id="87fc7-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="87fc7-109">наличие членства в группах RTCUniversalServerAdmins и RTCUniversalUserAdmins group (что подразумевает права на чтение параметров единой системы обмена сообщениями Exchange);</span><span class="sxs-lookup"><span data-stu-id="87fc7-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="87fc7-110">доменные права на создание контактных объектов в указанном контейнере подразделения (OU).</span><span class="sxs-lookup"><span data-stu-id="87fc7-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="87fc7-111">Дополнительные сведения об использовании командлета **Get – CsExumContact** можно найти в статье [Get – CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87fc7-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

