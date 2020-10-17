---
title: 'Lync Server 2013: состояние репликации центрального хранилища управления'
description: 'Lync Server 2013: состояние репликации центрального хранилища управления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f1f9008a966040cf34ac0499c023f9dbe53a541
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544365"
---
# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Состояние репликации центрального хранилища управления в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-01-26_

Когда администратор вносит изменения в Lync Server (например, когда администратор создает новую политику голосовой связи или изменяет параметры конфигурации сервера адресной книги), она записывается в хранилище центрального хранилища управления. В свою очередь, это изменение необходимо реплицировать на все компьютеры, на которых выполняются службы или роли сервера Lync Server.

Для репликации данных главный репликатор (работающий на центральном сервере управления) создает моментальный снимок измененных данных конфигурации. Затем копия этого снимка отправляется на каждый компьютер, на котором выполняются службы или роли сервера Lync Server. На этих компьютерах агент репликации получает моментальный снимок и передает измененные данные. Затем агент отправляет главный репликатор сообщение, сообщающее о последнем состоянии репликации.

Командлет Get-CsManagementStoreReplicationStatus позволяет проверить состояние репликации для всех (или всех) компьютеров Lync Server в Организации.

Кто может выполнить этот командлет? По умолчанию члены следующих групп авторизованы для локального запуска командлета Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>См. также


[Get — CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

