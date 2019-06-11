---
title: 'Lync Server 2013: процесс развертывания для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Процесс развертывания группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-27_

В этом разделе приводятся общие этапы и инструкции по развертыванию приложения группы ответа.

### <a name="response-group-deployment-process"></a>Процедура развертывания группы ответа

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Установка приложения группы ответа</p></td>
<td><p>Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Установка компонентов для группы ответа</p></td>
<td><p>Командлеты Lync Server, панель управления Lync Server, средство настройки группы ответа, агент "вход и выход из консоли" и клиентская веб-служба "группа ответа" устанавливается как часть веб-служб. Веб-службы устанавливаются при развертывании пула Enterprise Edition или стандартного сервера выпусков.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Включение пользователей для Lync 2013 и для корпоративного голосовой связи</p></td>
<td><p>Включите пользователей, которые будут агентами для Lync Server и корпоративной голосовой связи. Пользователей необходимо включить до того, как их можно будет добавлять в группы агентов. Как правило, пользователи работают с Lync Server во время развертывания Enterprise Edition или Standard Edition Server. Для пользователей, использующих корпоративную голосовую раскладку, включены пользователи.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение и повторное включение учетной записи пользователя для Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Включение пользователей корпоративной голосовой связи в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Создание и настройка групп ответа, которые состоят из групп агентов, очередей и рабочих процессов</p></td>
<td><ol>
<li><p>С помощью панели управления Lync Server или командной консоли Lync Server вы можете сделать следующее:</p>
<ol>
<li><p>Создайте и настройте группы агентов.</p></li>
<li><p>Создайте и настройте очереди.</p></li>
</ol></li>
<li><p>Кроме того, можно использовать командную консоль Lync Server для создания стандартных рабочих часов и праздников для группы ответа.</p></li>
<li><p>С помощью средства настройки группы ответа или командной консоли Lync Server вы можете создавать рабочие процессы (группы слежения или потоки звонков для голосовой связи), в том числе пользовательские группы ответов и рабочие часы и праздники.</p>
<div>

> [!NOTE]  
> Вы можете получить доступ к средству настройки группы ответа с помощью панели управления Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Создание групп агента группы ответа Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Создание очередей группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Необязательно Определение группы ответа в рабочее время в Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Создание или изменение рабочего процесса в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Необязательно) Задание настроек на уровне приложения</p></td>
<td><p>Используйте командную консоль Lync Server для настройки стандартной конфигурации сохранения музыки, используемого по умолчанию звукового файла для сохранения музыки, периода отсрочки агента рингбакк и контекстной конфигурации вызова.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Управление параметрами группы ответа уровня приложения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Необязательно) Делегирование управления группами реагирования</p></td>
<td><p>Назначьте пользователям роль Ксреспонсеграупманажер для делегирования конфигурации групп ответов. После этого диспетчер групп ответов может настроить назначенные им группы ответа.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование контроля доступа на основе ролей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка развертывания группы ответа</p></td>
<td><p>Протестируйте ответ на звонки в сервисную группу и рабочие процессы IVR, чтобы гарантировать правильную работу конфигурации.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

