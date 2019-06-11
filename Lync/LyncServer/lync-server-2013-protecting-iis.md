---
title: 'Lync Server 2013: защита IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Защита IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-12-05_

В Microsoft Office Communications Server 2007 и Microsoft Office Communications Server 2007 R2 служба IIS работала под учетной записью обычного пользователя. Это может привести к возникновению проблем: в случае истечения срока действия пароля вы можете потерять веб-службы, проблему, которая часто сложно диагностировать. Чтобы избежать проблем с истекшим сроком действия паролей, Microsoft Lync Server 2013 позволяет создать учетную запись компьютера (на компьютере, который не существует), который может служить субъектом проверки подлинности для всех компьютеров на сайте, на котором запущены службы IIS. Поскольку для этих учетных записей применяется протокол проверки подлинности Kerberos, они называются учетными записями Kerberos, а новый процесс проверки подлинности — веб-проверкой подлинности Kerberos. Таким образом, одна учетная запись обеспечивает управление всеми серверами IIS.

Чтобы выполнить серверы для этого участника проверки подлинности, необходимо сначала создать учетную запись компьютера с помощью командлета New-Кскерберосаккаунт. Эта учетная запись затем назначается для одного или нескольких сайтов. После создания назначения связь между учетной записью и сайтом Lync Server 2013 будет включена путем запуска командлета Enable-Кстопологи. Помимо прочего, в этом случае создается требуемое имя субъекта-службы (SPN) в доменных службах Active Directory (AD DS). Имя SPN предоставляет клиентским службам информацию о расположении конкретной службы. Подробности можно найти в разделе [New-кскерберосаккаунт](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) в документации по эксплуатации.

<div>

## <a name="best-practices"></a>Рекомендации

Для повышения безопасности IIS мы рекомендуем использовать учетную запись Kerberos для IIS. Если вы не реализуете учетную запись Kerberos, службы IIS работают под учетной записью обычного пользователя.

</div>

</div>

<span> </span>

</div>

</div>

</div>

