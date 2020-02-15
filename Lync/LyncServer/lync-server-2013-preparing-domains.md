---
title: 'Lync Server 2013: подготовка доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173b1293fb4bf0353b4e6d9038d05c1480697d17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Подготовка доменов для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-29_

Подготовка домена — это завершающий этап подготовки доменных служб Active Directory для Lync Server 2013. На этапе подготовки домена необходимые элементы управления доступом (ACE) добавляются в универсальные группы, которые предоставляют разрешения для размещения пользователей в домене и управления ими. При подготовке домена создаются элементы управления доступом в корне домена и три встроенных контейнера: пользователей, компьютеров и контроллеров домена.

Подготовка домена может выполняться на любом компьютере в домене, где выполняется развертывание Lync Server. Необходимо подготовить каждый домен, на котором будут размещаться сервер Lync Server или пользователи.

Если в организации отключено наследование разрешений, или отключены разрешения авторизованных пользователей, то во время подготовки домена необходимо выполнить дополнительные действия. Дополнительные сведения см [в статье Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Если в организации вместо трех встроенных контейнеров (пользователей, компьютеров и контроллеров доменов) используются подразделения, то группе авторизованных пользователей необходимо предоставить доступ на чтение в этих подразделениях. Доступ на чтение в контейнерах необходим для подготовки домена. Если группа авторизованных пользователей не имеет доступа на чтение в подразделении, выполните командлет **Grant-CsOuPermission**, как показано в следующих примерах кода, чтобы предоставить разрешения на чтение в каждом подразделении.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Сведения о командлете **Grant – CsOuPermission** можно найти в документации по командной консоли Lync Server.

<div class="">


> [!TIP]  
> Сведения об элементах управления доступом (ACE), созданных в контейнере "Пользователи", "компьютеры" и "контроллеры домена", приведены в статье <A href="lync-server-2013-changes-made-by-domain-preparation.md">изменения, внесенные в ходе подготовки домена в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Выполнение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Использование командлетов для обратной подготовки домена для Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

