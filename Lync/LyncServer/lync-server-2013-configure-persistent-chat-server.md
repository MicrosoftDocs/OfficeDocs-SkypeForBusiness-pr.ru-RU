---
title: 'Lync Server 2013: Настройка сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97797500bab9b6c0ed7dc2c79e603d84e819df5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a>Настройка сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Создание новой конфигурации сохраняемого чата

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Получение конфигурации сохраняемого чата

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

Удаление конфигурации сохраняемого чата

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

Настройка конфигурации сохраняемого чата

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Для Lync Server 2013 весь трафик веб-службы поддерживается на сервере Lync Server 2013, на серверах переднего плана. Поэтому адрес gcweb01 на сервере сохраняемого чата не требуется. Мы продолжаем поддерживать внутренний доступ веб-службы, поскольку предоставляем веб-службу отправки и загрузки файлов только на *внутренний* веб-сайт (не на *внешний* веб-сайт для удаленных пользователей).

</div>

<span> </span>

</div>

</div>

</div>

