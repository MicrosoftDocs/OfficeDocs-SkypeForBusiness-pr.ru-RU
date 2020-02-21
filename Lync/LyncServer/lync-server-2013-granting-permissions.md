---
title: 'Lync Server 2013: предоставление разрешений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Предоставление разрешений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-15_

Для программы установки можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в указанном домене. При этом выдаются следующие разрешения:

  - Чтение

  - Запись

  - реадспн

  - вритеспн

Для администрирования можно добавить разрешения в указанные подразделения, чтобы члены универсальных групп RTC, созданных в ходе подготовки леса, могли получить доступ к подразделениям, не являясь членами группы администраторов домена. Разрешения, добавляемые к указанному подразделению — это те же разрешения, которые командлет **Enable-CsAdDomain** добавляет для компьютеров и контейнеров пользователей подразделения.

<div>

## <a name="in-this-section"></a>Содержание

  - [Предоставление разрешений на установку в Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Предоставление разрешений организационных подразделений в Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

