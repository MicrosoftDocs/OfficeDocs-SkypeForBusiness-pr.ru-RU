---
title: Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула
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
ms.openlocfilehash: 6e638dc7e0172c3187859797776f8e64372c81d5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="43cd9-102">Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула</span><span class="sxs-lookup"><span data-stu-id="43cd9-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43cd9-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="43cd9-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="43cd9-104">С помощью средства **OCSUmUtil** или командлета **Get – CsExumContact** убедитесь, что объекты контакта единой системы обмена сообщениями Exchange удалены из пула Office Communications Server 2007 R2 прежних версий.</span><span class="sxs-lookup"><span data-stu-id="43cd9-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="43cd9-105">Средство **OCSUmUtil** содержится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="43cd9-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="43cd9-106">% Program Files% \\ Common Files \\ Lync Server 2013 \\ support \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="43cd9-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="43cd9-107">Средство **OCSUmUtil** должно быть запущено от имени учетной записи, которая характеризуется следующим:</span><span class="sxs-lookup"><span data-stu-id="43cd9-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="43cd9-108">наличие членства в группах RTCUniversalServerAdmins и RTCUniversalUserAdmins group (что подразумевает права на чтение параметров единой системы обмена сообщениями Exchange);</span><span class="sxs-lookup"><span data-stu-id="43cd9-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="43cd9-109">доменные права на создание контактных объектов в указанном контейнере подразделения (OU).</span><span class="sxs-lookup"><span data-stu-id="43cd9-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="43cd9-110">Дополнительные сведения об использовании командлета **Get – CsExumContact** можно найти в статье [Get – CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43cd9-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

