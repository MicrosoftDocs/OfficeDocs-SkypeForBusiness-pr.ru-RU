---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 410fd1fe521bd8d4750b290a54db26adb630a8be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Перемещение пользователей в Lync Online в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-29_

Прежде чем приступить к переносу пользователей на Lync Online, необходимо создать резервную копию данных пользователя, связанных с учетными записями, которые нужно переместить. Вместе с учетной записью перемещаются не все данные пользователя. Дополнительные сведения можно найти [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Перенос параметров пользователя в Lync Online

Параметры пользователя перемещаются вместе с учетной записью пользователя. Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Перемещение пилотных пользователей в Lync Online

Прежде чем приступить к перемещению пользователей на Lync Online, вам может потребоваться переместить нескольких пилотных пользователей, чтобы убедиться, что ваша среда настроена правильно. Вы можете проверить, что функции и службы Lync будут работать должным образом, прежде чем переходить к перемещению других пользователей.

Чтобы переместить локального пользователя в клиент Lync Online, выполните в командной консоли Lync Server следующие командлеты с помощью учетных данных администратора для вашего клиента Microsoft Office 365. Замените "username@contoso.com" на информацию о перемещаемом пользователе.

   ```
    $creds=Get-Credential
   ```

   ```
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, на котором запущена служба размещенной миграции, в следующем формате:\<HTTPS://FQDN\>Pool/хостедмигратион/ Хостедмигратионсервице. svc.

URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.

**Определение URL-адреса размещенной службы миграции для своего клиента Office 365**

1.  Выполните вход в свое клиентское приложение Office 365 как администратор.

2.  Откройте **центр администрирования Lync**.

3.  В **центре администрирования Lync** выберите и скопируйте URL-адрес в адресной строке на **Lync.com**. Ниже показан возможны пример URL-адреса
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  После замены фрагмента **webdir** в URL-адресе фрагментом **admin** получается следующий результат:
    
    `https://admin0a.online.lync.com`

5.  Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.
    
    Итоговый URL-адрес, который служит значением параметра **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Перемещение пользователей в Lync Online

Вы можете переместить нескольких пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) с параметром – Filter, чтобы выбрать пользователей с определенным свойством, назначенным учетным записям пользователей, например регистрарпул. Затем можно передать возвращенные пользователи в командлет [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , как показано в следующем примере.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Вы также можете использовать параметр –OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Проверка параметров и функций пользователей Lync Online

Можно проверить успешность перемещения пользователя следующими способами:

  - Просмотр состояния пользователя на панели управления Lync Online. Визуальный индикатор для локальных пользователей и пользователей в сети отличается.

  - Выполнить следующий командлет:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

