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
# <a name="migrate-existing-meetings-and-meeting-content"></a>Перенос существующих собраний и содержимого собраний

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

