---
title: 'Lync Server 2013: Настройка диапазонов номеров для отправки групповых звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbcbf05fbb73e2023b48bdb1f7e74ecdee6a36bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a>Настройка диапазонов номеров для группового приема звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Отправка группового звонка осуществляется на основе заявления на приостановку звонков. При развертывании группового приема звонков настраивается таблица на приостановку соединения с диапазонами номеров телефонов, которые обозначены как номера групп для отправки звонков. These group numbers are the numbers that users dial to pick up calls that are ringing for another user.

Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them. У каждого пула переднего плана, в котором вы развертываете раскладки группового звонка, может быть один или несколько диапазонов номеров групп для раскладки звонков. Диапазоны номеров групп должны быть глобально уникальными в рамках развертывания Lync Server.

<div>

## <a name="in-this-section"></a>Содержание

  - [Create or modify a Group Call Pickup number range in Lync Server 2013](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [Удаление диапазона номеров для отправки группового звонка в Lync Server 2013](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

