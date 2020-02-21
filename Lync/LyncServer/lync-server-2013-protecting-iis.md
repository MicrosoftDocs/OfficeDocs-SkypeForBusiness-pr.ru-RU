---
title: 'Lync Server 2013: защита IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Защита служб IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-12-05_

В Microsoft Office Communications Server 2007 и Microsoft Office Communications Server 2007 R2 службы IIS выполнялись от имени стандартной учетной записи пользователя. Это может привести к возникновению проблем: в случае истечения срока действия пароля можно потерять веб-службы, что часто трудно диагностировать. Чтобы избежать проблем с истекшим сроком действия паролей, Microsoft Lync Server 2013 позволяет создать учетную запись компьютера (для компьютера, который не существует), который может выступать в качестве субъекта проверки подлинности для всех компьютеров сайта, на котором запущены службы IIS. Так как эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи называются учетными записями Kerberos, а новый процесс проверки подлинности называется проверкой подлинности Kerberos. Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.

Чтобы запустить серверы для этого участника проверки подлинности, необходимо сначала создать учетную запись компьютера с помощью командлета New – CsKerberosAccount; Затем эта учетная запись назначается одному или нескольким сайтам. После выполнения назначения связь между учетной записью и сайтом Lync Server 2013 включается с помощью командлета Enable-CsTopology. Помимо прочего, при этом создается имя участника-службы (SPN) в доменных службах Active Directory (AD DS). Имена субъектов-служб предоставляют клиентским приложениям способ для обнаружения конкретной службы. Дополнительные сведения см. в статье [New – CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) в документации по операциям.

<div>

## <a name="best-practices"></a>Рекомендации

Для повышения безопасности IIS рекомендуется реализовать учетную запись Kerberos для служб IIS. Если вы не реализуете учетную запись Kerberos, службы IIS выполняются с использованием стандартной учетной записи пользователя.

</div>

</div>

<span> </span>

</div>

</div>

</div>

