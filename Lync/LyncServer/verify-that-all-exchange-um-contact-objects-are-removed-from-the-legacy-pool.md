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

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Проверка того, что все объекты контактов Exchange UM удалены из устаревшего пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-26_

С помощью средства **оксумутил** или командлета **Get-ксексумконтакт** убедитесь в том, что объекты контактов Exchange UM были удалены из устаревшего пула Office Communications Server 2007 R2. **Оксумутил** находится в следующей папке:

% Программных файлов\\% распространенных\\файлов Lync Server\\2013\\support оксумутил. exe

**Оксумутил** необходимо запускать из учетной записи пользователя:

  - Членство в группе Рткуниверсалсерверадминс и Рткуниверсалусерадминс (которая включает права на чтение параметров единой системы обмена сообщениями Exchange Server)

  - Права домена на создание объектов контакта в указанном контейнере подразделения

Дополнительные сведения об использовании командлета **Get-ксексумконтакт** можно найти в документации [Get-Ксексумконтакт](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в командной консоли Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

