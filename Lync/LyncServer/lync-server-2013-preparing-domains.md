---
title: 'Lync Server 2013: подготовка доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Подготовка доменов для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-29_

Подготовка домена — это заключительный этап подготовки доменных служб Active Directory для Lync Server 2013. На этапе подготовки домена в универсальные группы добавляются необходимые записи управления доступом (ACE), которые предоставляют разрешения для размещения и управления пользователями в домене. При подготовке домена создаются записи ACE в корне домена и три встроенных контейнера: пользователи, компьютеры и контроллеры домена.

Вы можете выполнить подготовку домена на любом компьютере домена, на котором вы развертываете Lync Server. Необходимо подготовить каждый домен, на котором будет размещен сервер Lync Server или пользователи.

Если в вашей организации отключены разрешения на наследование разрешений или аутентификация пользователей, прошедших проверку подлинности, необходимо выполнить дополнительные действия в процессе подготовки домена. Дополнительные сведения можно найти [в разделе Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Если в вашей организации используются организационные подразделения (OU), а не три встроенных контейнера (например, пользователи, компьютеры и контроллеры домена), необходимо предоставить доступ на чтение к подразделениям для группы пользователей, прошедших проверку подлинности. Для подготовки домена требуется доступ на чтение к контейнерам. Если у группы пользователей, прошедших проверку подлинности, нет доступа на чтение к OU, выполните командлет **Grant-ксаупермиссион** , как показано в приведенных ниже примерах кода, чтобы предоставить разрешения на чтение для каждого подразделения.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Дополнительные сведения о командлете **Grant-ксаупермиссион** можно найти в документации по оболочке Lync Server Management Shell.

<div class="">


> [!TIP]  
> Подробнее об ACE, созданных в корне домена и в контейнерах пользователей, компьютеров и контроллеров домена, можно узнать <A href="lync-server-2013-changes-made-by-domain-preparation.md">в статьях изменения подготовки домена в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Проведение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Использование командлетов для отмены подготовки доменов для Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

