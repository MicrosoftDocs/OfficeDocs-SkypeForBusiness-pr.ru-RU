---
title: Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79183039cedc058d479d52fa80ce09a70ffd73b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

С помощью средства **OCSUmUtil** или командлета **Get – CsExumContact** убедитесь, что объекты контакта единой системы обмена сообщениями Exchange удалены из пула Office Communications Server 2007 R2 прежних версий. Средство **OCSUmUtil** содержится в следующей папке:

% Program Files\\% Common\\files Lync\\Server\\2013 support OcsUMUtil. exe

Средство **OCSUmUtil** должно быть запущено от имени учетной записи, которая характеризуется следующим:

  - наличие членства в группах RTCUniversalServerAdmins и RTCUniversalUserAdmins group (что подразумевает права на чтение параметров единой системы обмена сообщениями Exchange);

  - доменные права на создание контактных объектов в указанном контейнере подразделения (OU).

Дополнительные сведения об использовании командлета **Get – CsExumContact** можно найти в статье [Get – CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в документации по консоли управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

