---
title: 'Lync Server 2013: Администрирование пользователей в гибридном развертывании'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd4f53eaa611d130291b1a42c798a8d5589968c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Администрирование пользователей в гибридном развертывании Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-29_

Вы можете управлять параметрами пользователей и политиками для пользователей, перенесенных на Lync Online с помощью функций управления пользователями, доступных на портале Microsoft Office 365 Online. Для выполнения задач администрирования необходимо войти по учетной записи администратора клиента.

<div>

## <a name="moving-users-back-to-on-premises"></a>Перемещение пользователей на локальный сервер

<div class="">


> [!IMPORTANT]  
> Этот раздел относится только к пользователям, которые были созданы и включены в локальной среде Lync, а затем перенесено из локального развертывания в Lync Online. Если вы хотите переместить пользователей, которые были созданы в Lync Online (и не включены для Lync в локальном развертывании), ознакомьтесь с разрешениями: <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальное приложение Lync в Lync Server 2013</A>.



</div>

  - Чтобы переместить пользователя из Lync Online обратно в локальное Lync, выполните следующие командлеты:
    
       ```
        $cred=Get-Credential
       ```
    
       ```
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

В качестве параметра **HostedMigrationOverrideUrl** следует указать URL-адрес пула, где работает служба миграции с размещением, в следующем формате:

Полное\<доменное\>имя пула HTTPS:///хостедмигратион/хостедмигратионсервице.СВК. URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.

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

</div>

<span> </span>

</div>

</div>

</div>

