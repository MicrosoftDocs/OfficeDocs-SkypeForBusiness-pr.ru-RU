---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd35ed2d153bb33f93f6533e9eacb0ffab7788f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Проверка параметров настройки

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-06_

Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Lync Server 2013 **Get-ксманажементсторерепликатионстатус** на внутреннем компьютере, на котором находится хранилище Центрального управления, или в любом домене. подключенный компьютер, на котором установлен компонент Lync Server 2013 Core (Окскоре. msi).

Начальные результаты могут содержать состояние "false", а не "истина" для репликации. Если это так, запустите командлет **Invoke-ксманажементсторерепликатион** и разрешите время завершения репликации, прежде чем запускать командлет **Get-ксманажементсторерепликатионстатус** еще раз.

</div>

<span> </span>

</div>

</div>

</div>

