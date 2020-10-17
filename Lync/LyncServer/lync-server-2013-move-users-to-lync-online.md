---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 189bf46da6c6bdaa6749f899d2a672967680cc45
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500576"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Перемещение пользователей в Lync Online в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-29_

Прежде чем приступить к переносу пользователей на Lync Online, необходимо создать резервную копию пользовательских данных, связанных с перемещаемыми учетными записями. Не все данные пользователя перемещаются вместе с учетной записью пользователя. Дополнительные сведения приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Перенос параметров пользователя в Lync Online

Параметры пользователя перемещаются вместе с учетной записью пользователя. Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Перемещение пилотных пользователей в Lync Online

Прежде чем приступить к перемещению пользователей в Lync Online, вам может потребоваться переместить несколько пилотных пользователей, чтобы убедиться, что среда настроена правильно. После этого вы можете проверить, что функции и службы Lync работают должным образом, прежде чем пытаться переместить дополнительных пользователей.

Чтобы переместить локального пользователя в клиент Lync Online, выполните следующие командлеты в командной консоли Lync Server, используя учетные данные администратора для своей организации Microsoft 365 или Office 365. Замените "username@contoso.com" информацией для пользователя, которого требуется переместить.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.

Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Microsoft 365 или Office 365.

**Определение URL-адреса размещенной службы миграции для Организации**

1.  Войдите в организацию Microsoft 365 или Office 365 с правами администратора.

2.  Откройте **центр администрирования Lync**.

3.  При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**. Пример URL-адреса выглядит примерно следующим образом:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:
    
    `https://admin0a.online.lync.com`

5.  Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.
    
    Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Перемещение пользователей в Lync Online

Можно переместить несколько пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) с параметром – Filter, чтобы выбрать пользователей с определенным свойством, назначенным учетным записям пользователей, например RegistrarPool. Затем можно передать возвращенных пользователей в командлет [Move – CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , как показано в следующем примере.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Вы также можете использовать параметр – OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Проверка пользовательских параметров и функций Lync Online

Можно проверить успешность перемещения пользователя следующими способами:

  - просмотреть состояние пользователя в панели управления Lync Online: визуальные индикаторы для локальных и сетевых пользователей различаются;

  - выполнить следующий командлет:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

