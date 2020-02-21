---
title: Проверка репликации параметров конфигурации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b238b0431c266204daa9ecdfc6cf72986fd9e40b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>Проверка репликации параметров конфигурации

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Можно проверить репликацию сведений о конфигурации на пограничный сервер, выполнив командлет Lync Server 2013 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположено центральное хранилище управления, или на любом компьютере, присоединенном к домену, на котором установлены основные компоненты Lync Server 2013.

В начальных результатах для репликации может быть указано состояние "False" вместо "True". В этом случае выполните командлет **Invoke-CsManagementStoreReplication** и дождитесь завершения репликации, после чего еще раз выполните командлет **Get-CsManagementStoreReplicationStatus**.

</div>

<span> </span>

</div>

</div>

</div>

