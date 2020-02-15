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
ms.openlocfilehash: 31a6036421dd84f466df0f2353b6d5264e0680c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>Перенос существующих собраний и содержимого собраний

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Когда учетная запись пользователя перемещается из Lync Server 2010 на сервер Lync Server 2013, следующая информация перемещается вместе с этой учетной записью пользователя:

  - **Собрания, уже запланированные этим пользователем**. В том числе, перемещаются каталоги конференций и данные конференций.

  - **Персональный идентификационный номер (ПИН-код) пользователя**. Текущий ПИН-код пользователя будет действовать, пока его срок действия не истечет или пока пользователь не запросит новый ПИН-код.

На новый сервер не перемещаются следующие сведения об учетной записи пользователя.

  - **Содержимое собрания**. Для перемещения содержимого, которое совместно использовалось во время собрания, например файлов PowerPoint, доски, сложений или данных опросов, используйте параметр **-MoveConferenceData** в командлете **Move-CsUser**.

</div>

<span> </span>

</div>

</div>

</div>

