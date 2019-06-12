---
title: Проверка того, что все объекты контактов Exchange UM удалены из устаревшего пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="6ca81-102">Проверка того, что все объекты контактов Exchange UM удалены из устаревшего пула</span><span class="sxs-lookup"><span data-stu-id="6ca81-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ca81-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6ca81-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6ca81-104">С помощью средства **оксумутил** или командлета **Get-ксексумконтакт** убедитесь в том, что объекты контактов Exchange UM были удалены из устаревшего пула Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6ca81-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="6ca81-105">**Оксумутил** находится в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="6ca81-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="6ca81-106">% Программных файлов\\% распространенных\\файлов Lync Server\\2013\\support оксумутил. exe</span><span class="sxs-lookup"><span data-stu-id="6ca81-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="6ca81-107">**Оксумутил** необходимо запускать из учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="6ca81-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="6ca81-108">Членство в группе Рткуниверсалсерверадминс и Рткуниверсалусерадминс (которая включает права на чтение параметров единой системы обмена сообщениями Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="6ca81-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="6ca81-109">Права домена на создание объектов контакта в указанном контейнере подразделения</span><span class="sxs-lookup"><span data-stu-id="6ca81-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="6ca81-110">Дополнительные сведения об использовании командлета **Get-ксексумконтакт** можно найти в документации [Get-Ксексумконтакт](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6ca81-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

