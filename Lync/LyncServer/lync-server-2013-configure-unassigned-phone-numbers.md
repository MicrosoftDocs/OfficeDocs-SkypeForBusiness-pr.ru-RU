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
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Настройка неназначенных номеров телефонов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Lync Server позволяет настроить действия, которые будут происходить на входящие звонки на номера телефонов, которые действительны для вашей организации, но не назначены пользователю или телефону. Для настройки обработки таких звонков вы настроили таблицу неназначенных номеров. Вы можете использовать таблицу для маршрутизации вызовов в приложение объявлений или на сервер Exchange UM.

Настройка таблицы неназначенных номеров зависит от способа ее использования. В эту таблицу можно добавить все добавочные номера, используемые в организации, добавить только неназначенные добавочные номера или добавить номера обоих типов. Таблица неназначенных номеров может содержать назначенные и неназначенные номера, но вызывается только в том случае, если звонящий набирает номер, который в настоящее время не назначен. Если вы добавили в таблицу неназначенных номеров все допустимые добавочные номера, то вы можете указать действие, выполняемое при выходе сотрудника в отпуск без необходимости дополнительной настройки таблицы. Если вы добавили в таблицу неназначенные добавочные номера, то вы можете указать действие, выполняемое для определенных номеров. Например, при изменении добавочного номера службы поддержки клиентов вы можете добавить в таблицу старый номер службы поддержки и назначить ему оповещение, которое сообщает новый номер.

<div>


> [!IMPORTANT]  
> Перед настройкой таблицы неназначенные номера необходимо, чтобы в ней уже было определено одно или несколько объявлений либо настроен автоматический секретарь UM Exchange. Подробнее о создании извещений можно узнать <A href="lync-server-2013-create-an-announcement.md">в статьях создание объявления в Lync Server 2013</A>. Чтобы узнать, настроены ли параметры Exchange UM, запустите командлет <STRONG>Get-ксексумконтакт</STRONG> . Подробности можно найти в <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">статьях Get-ксексумконтакт</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание и изменение неназначенного диапазона номеров в Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Удаление неназначенного диапазона номеров в Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

