---
title: 'Lync Server 2013: Администрирование пользователей в гибридном развертывании'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15585b5df4a2c38c4d72733b8c999556e6cb8467
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521246"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Администрирование пользователей в гибридном развертывании Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-29_

Вы можете управлять параметрами пользователей и политиками для пользователей, перенесенных в Lync Online, используя функции управления пользователями, доступные в центре администрирования Microsoft 365. Для выполнения задач администрирования необходимо войти в систему с помощью учетной записи администратора клиента.

<div>

## <a name="moving-users-back-to-on-premises"></a>Возврат пользователей в локальную среду

<div class="">


> [!IMPORTANT]  
> Этот раздел относится только к пользователям, созданным и включенным в локальной среде Lync, а затем перемещению из локального развертывания в Lync Online. Если вы хотите переместить пользователей, созданных в Lync Online (и не включенных для Lync в локальном развертывании), ознакомьтесь со статьей <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальную среду Lync в Lync Server 2013</A>.



</div>

  - Выполните следующие командлеты, чтобы переместить пользователя из Lync Online обратно в локальную среду Lync:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Формат URL-адреса, указанный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, в котором запущена служба переноса, в следующем формате:

Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc. Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Microsoft 365 или Office 365.

**Определение URL-адреса размещенной службы миграции для организации Microsoft 365 или Office 365**

1.  Войдите в свою организацию с учетной записью администратора.

2.  Откройте **центр администрирования Lync**.

3.  При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**. Пример URL-адреса выглядит примерно следующим образом:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:
    
    `https://admin0a.online.lync.com`

5.  Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.
    
    Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

