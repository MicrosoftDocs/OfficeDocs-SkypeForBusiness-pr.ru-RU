---
title: Перенос существующих собраний и содержимого собраний
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="9c9c3-102">Перенос существующих собраний и содержимого собраний</span><span class="sxs-lookup"><span data-stu-id="9c9c3-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c9c3-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9c9c3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9c9c3-104">При перемещении учетной записи пользователя из Lync Server 2010 на сервер Lync Server 2013 переносятся следующие данные с учетной записью пользователя:</span><span class="sxs-lookup"><span data-stu-id="9c9c3-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="9c9c3-105">**Собрания, уже запланированные пользователем**.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="9c9c3-106">Сюда входит перемещение каталогов конференций и данных конференций.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="9c9c3-107">**Персональный идентификационный номер пользователя (ПИН-код)**.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="9c9c3-108">Текущий ПИН-код пользователя продолжает работать, пока не истечет срок действия или пользователь запросит новый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="9c9c3-109">Указанные ниже сведения об учетной записи пользователя не перемещаются на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="9c9c3-110">**Содержимое собрания**.</span><span class="sxs-lookup"><span data-stu-id="9c9c3-110">**Meeting content**.</span></span> <span data-ttu-id="9c9c3-111">Чтобы переместить содержимое, совместно используемое во время собрания, например PowerPoint, доска, вложения или данные опроса, используйте параметр **-мовеконференцедата** в составе командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="9c9c3-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

