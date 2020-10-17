---
title: Проверка подключения между внутренними и пограничными серверами
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a170ac21c89bd405ad0406830c00feabbde5434
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518656"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Проверка подключения между внутренними и пограничными серверами в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

В Lync Server 2013 был доступен отдельный мастер проверки для проверки связи между пограничными серверами и внутренними серверами. При установке пограничных серверов в Lync Server 2013 проверка подключения выполняется автоматически.

Можно проверить репликацию сведений о конфигурации на пограничный сервер, выполнив командлет Windows PowerShell **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления (или на любом присоединенном к домену компьютере, на котором установлен компонент Lync Server 2013 Core Components (OcsCore.msi). В начальных результатах для репликации может быть указано состояние "False" вместо "True". В этом случае выполните командлет **Invoke-CsManagementStoreReplication** и дождитесь завершения репликации перед повторным выполнением **Get-CsManagementStoreReplicationStatus**.

Можно проверить подключение внешних пользователей отдельно, в том числе с помощью анализатора удаленных подключений Office Communications Server. Дополнительные сведения см. [в статье Проверка подключения для внешних пользователей в Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

</div>

<span> </span>

</div>

</div>

</div>

