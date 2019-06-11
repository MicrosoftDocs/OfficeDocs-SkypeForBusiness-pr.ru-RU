---
title: 'Lync Server 2013: состояние репликации центрального хранилища управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce46b403e27d0a2b69f705b5bada026882eec7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Состояние репликации центрального хранилища управления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2015-01-26_

Если администратор вносит изменения в сервер Lync Server (например, при создании администратором новой политики голосовой почты или изменении параметров конфигурации сервера адресной книги), то изменения записываются в хранилище Центрального управления. После этого изменения должны быть реплицированы на все компьютеры, на которых запущены службы или роли сервера Lync Server.

Для репликации данных основная служба репликации (запущенная на центральном сервере управления) создает снимок измененных данных конфигурации. Затем на каждый компьютер, на котором выполняются службы Lync Server или серверные роли, отправляется копия этого снимка. На этих компьютерах агент репликации получает снимок и загружает измененные данные. После этого агент отправляет основной службе репликации сообщение о последнем состоянии репликации.

Командлет Get-Ксманажементсторерепликатионстатус позволяет проверить состояние репликации для всех (или всех) компьютеров Lync Server в Организации.

Кто может выполнить этот командлет? По умолчанию право на локальное выполнение командлета Get-CsManagementStoreReplicationStatus имеют участники следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные вами), выполните в командной строке Windows PowerShell следующую команду:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>См. также


[Get-Ксманажементсторерепликатионстатус](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

