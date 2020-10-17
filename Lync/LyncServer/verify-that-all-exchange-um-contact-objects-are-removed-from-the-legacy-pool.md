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
ms.openlocfilehash: eae8f82016f8dd78c3ecd568e34c3cc408a204ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515956"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Проверка того, что все объекты контактов Exchange единой системы обмена сообщениями удалены из устаревшего пула

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

С помощью средства **OCSUmUtil** или командлета **Get – CsExumContact** убедитесь, что объекты контакта единой системы обмена сообщениями Exchange удалены из пула Office Communications Server 2007 R2 прежних версий. Средство **OCSUmUtil** содержится в следующей папке:

% Program Files% \\ Common Files \\ Lync Server 2013 \\ support \\OcsUMUtil.exe

Средство **OCSUmUtil** должно быть запущено от имени учетной записи, которая характеризуется следующим:

  - наличие членства в группах RTCUniversalServerAdmins и RTCUniversalUserAdmins group (что подразумевает права на чтение параметров единой системы обмена сообщениями Exchange);

  - доменные права на создание контактных объектов в указанном контейнере подразделения (OU).

Дополнительные сведения об использовании командлета **Get – CsExumContact** можно найти в статье [Get – CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) в документации по консоли управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

