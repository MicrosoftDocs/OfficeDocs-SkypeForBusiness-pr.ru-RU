---
title: 'Lync Server 2013: процесс развертывания для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54335e8f70753a77f937819f896135ec1fe67b93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526896"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Процесс развертывания для группы ответа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-27_

В этом разделе представлен обзор этапов и действий, необходимых при развертывании приложения группы ответа.

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
<th>Действия</th>
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
<td><p>Командлеты Lync Server, панель управления Lync Server, средство настройки группы ответа, агенты входа и выхода, а также клиентская веб-служба "группа ответа" устанавливается в составе веб-служб. Веб-службы устанавливаются при развертывании пула Enterprise Edition или сервера Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Включение пользователей для Lync 2013 и корпоративной голосовой связи</p></td>
<td><p>Включите пользователей, которые будут агентами для Lync Server и корпоративной голосовой связи. Пользователей необходимо включить до того, как их можно будет добавлять в группы агентов. Как правило, для пользователей включена поддержка Lync Server во время развертывания Enterprise Edition или Standard Edition Server. Для пользователей включена поддержка корпоративной голосовой связи во время развертывания корпоративной голосовой связи.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Создание и настройка групп ответа, которые состоят из групп агентов, очередей и рабочих процессов</p></td>
<td><ol>
<li><p>Используйте панель управления Lync Server или Командная консоль Lync Server, чтобы выполнить следующие задачи:</p>
<ol>
<li><p>Создайте и настройте группы агентов.</p></li>
<li><p>Создайте и настройте очереди.</p></li>
</ol></li>
<li><p>Кроме того, можно использовать командную консоль Lync Server для создания предопределенных рабочих часов и праздников для группы ответа.</p></li>
<li><p>С помощью средства настройки группы ответа или командной консоли Lync Server можно создавать рабочие процессы (сервисные группы или потоки вызовов интерактивного речевого ответа (IVR)), в том числе настраиваемые рабочие часы и праздники для группы ответа.</p>
<div>

> [!NOTE]  
> Вы можете получить доступ к средству настройки группы ответа с помощью панели управления Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>ксреспонсеграупадминистратор</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Создание групп агентов группы ответа Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Создание очередей группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Создание или изменение рабочего процесса в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Необязательно) Задание настроек на уровне приложения</p></td>
<td><p>Используйте командную консоль Lync Server, чтобы настроить используемую по умолчанию конфигурацию хранения музыки, а также звуковой файл по умолчанию для хранения музыки, период отсрочки агента удерживаемого абонента и конфигурацию контекста вызовов.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>ксреспонсеграупадминистратор</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Управление параметрами группы ответа уровня приложения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Необязательно) Делегирование управления группами реагирования</p></td>
<td><p>Назначьте пользователям роль CsResponseGroupManager для делегирования настройки групп ответа. После этого менеджеры группы ответа могут настраивать назначенные им группы ответа.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>ксреспонсеграупадминистратор</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</a></p></td>
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

