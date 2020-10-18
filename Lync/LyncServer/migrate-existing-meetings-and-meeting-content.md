---
title: Перенос существующих собраний и содержимого собраний
description: Перенос существующих собраний и содержимого собраний.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94dd35063a121a057a218c27fdb36e42a155b77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579315"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="434f0-103">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="434f0-103">Migrate existing meetings and meeting content</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="434f0-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="434f0-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="434f0-105">Когда учетная запись пользователя перемещается из Lync Server 2010 на сервер Lync Server 2013, следующая информация перемещается вместе с этой учетной записью пользователя:</span><span class="sxs-lookup"><span data-stu-id="434f0-105">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="434f0-p101">**Собрания, уже запланированные этим пользователем**. В том числе, перемещаются каталоги конференций и данные конференций.</span><span class="sxs-lookup"><span data-stu-id="434f0-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="434f0-p102">**Персональный идентификационный номер (ПИН-код) пользователя**. Текущий ПИН-код пользователя будет действовать, пока его срок действия не истечет или пока пользователь не запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="434f0-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="434f0-110">На новый сервер не перемещаются следующие сведения об учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="434f0-110">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="434f0-p103">**Содержимое собрания**. Для перемещения содержимого, которое совместно использовалось во время собрания, например файлов PowerPoint, доски, сложений или данных опросов, используйте параметр **-MoveConferenceData** в командлете **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="434f0-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

