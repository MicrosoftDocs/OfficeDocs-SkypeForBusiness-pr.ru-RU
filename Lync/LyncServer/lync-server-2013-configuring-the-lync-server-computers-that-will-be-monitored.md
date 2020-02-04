---
title: 'Lync Server 2013: Настройка компьютеров с Lync Server, которые будут отслеживаться'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68dccef2e9451e4c077f5292398bb663f1acb514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a>Настройка компьютеров с Lync Server, которые будут отслеживаться в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Поскольку Lync Server 2013 не использует процесс центрального обнаружения, используемый в Microsoft Lync Server 2010, каждый сервер Lync Server 2013, на котором вы хотите наблюдать, должен иметь возможность самостоятельно сообщать о существовании сервера управления. Чтобы сделать это возможным, необходимо установить файлы агента Operations Manager на каждом из компьютеров, которые нужно отслеживать. После установки файлов агента необходимо настроить компьютер так, чтобы он действовал как прокси System Center. Обратите внимание на то, что эти процедуры должны выполняться после установки и настройки сервера Lync Server на этих компьютерах.

</div>

<span> </span>

</div>

</div>

</div>

