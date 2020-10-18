---
title: 'Lync Server 2013: подготовка среды к VDI'
description: 'Lync Server 2013: подготовка среды для VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e90b9e0f09d3082a28406f1a1dc715285ee4d7e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579915"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Подготовка среды Lync Server 2013 для VDI

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Чтобы подготовить среду для подключаемого модуля Lync VDI, администратор должен выполнить указанные ниже действия.

1.  В Lync Server 2013 убедитесь, что для EnableMediaRedirection задано значение TRUE для всех пользователей VDI. Дополнительные сведения можно найти в разделах справки для командлета [New – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и командлета [Set – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  На компьютере центра обработки данных установите клиент Lync 2013 на всех виртуальных машинах.

3.  На локальных компьютерах установите подключаемый модуль VDI для Lync.

</div>

<span> </span>

</div>

</div>

</div>

