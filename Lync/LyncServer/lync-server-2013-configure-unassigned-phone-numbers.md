---
title: 'Lync Server 2013: Настройка неназначенных телефонных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d7fdbbca81ecd0dd42a9b5198f266b9a63d793e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Настройка неназначенных телефонных номеров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Lync Server позволяет настраивать действия, выполняемые для входящих вызовов на номера телефонов, действительные для вашей организации, но не назначенные пользователю или телефону. Чтобы настроить обработку таких вызовов, следует задать таблицу неназначенных номеров. Вы можете использовать таблицу для маршрутизации вызовов в приложение извещения или на сервер единой системы обмена сообщениями Exchange.

Способ настройки таблицы неназначенных номеров зависит от того, как вы хотите ее использовать. Вы можете настроить таблицу с учетом всех допустимых добавочных номеров для своей организации, только неназначенных добавочных номеров или сочетания обоих типов номеров. Таблица неназначенных номеров может включать в себя как назначенные, так и неназначенные номера, но она вызывается только в том случае, когда звонящий набирает номер, который в данный момент не назначен. Если вы включаете в таблицу неназначенных номеров все допустимые добавочные номера, то можете указать действие, которое выполняется при увольнении человека из организации, благодаря чему вам не требуется изменять настройку данной таблицы. Если вы включаете в таблицу неназначенные добавочные номера, то можете настроить действие, выполняемое для отдельных номеров. Например, если вы изменяете добавочный номер для своего отдела обслуживания клиентов, то можете включить таблицу старый номер этого отдела и назначить ему извещение, содержащее новый номер.

<div>


> [!IMPORTANT]  
> Перед настройкой таблицы неназначенных номеров необходимо, чтобы уже было определено одно или несколько объявлений или настроен автосекретарь единой системы обмена сообщениями Exchange. Более подробную информацию о создании <A href="lync-server-2013-create-an-announcement.md">оповещений можно узнать в статье Create a извещения в Lync Server 2013</A>. Чтобы проверить, настроены ли параметры единой системы обмена сообщениями Exchange, выполните командлет <STRONG>Get – CsExUmContact</STRONG> . Дополнительные сведения см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание или изменение диапазона неназначенных номеров в Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Удаление диапазона неназначенных номеров в Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

