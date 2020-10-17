---
title: 'Lync Server 2013: процесс развертывания для групповой отправки звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522616"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Процесс развертывания для группового ответа на звонки в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-25_

В этом разделе представлен обзор действий, необходимых для развертывания групповой отправки вызовов. Перед настройкой групповой отправки звонков необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью. Компоненты, необходимые для групповой отправки звонков, устанавливаются и включаются при развертывании корпоративной голосовой связи.

### <a name="group-call-pickup-deployment-process"></a>Процесс развертывания группового ответа на звонки

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
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Включение средства SEFAUtil Resource Kit в топологии</p></td>
<td><ol>
<li><p>Используйте командлет <strong>New – кструстедаппликатионпул</strong> для создания нового пула доверенных приложений.</p></li>
<li><p>Используйте командлет <strong>New – кструстедаппликатион</strong> , чтобы указать средство SEFAUtil в качестве доверенного приложения.</p></li>
<li><p>Выполните командлет <strong>Enable – CsTopology</strong> , чтобы включить топологию.</p></li>
<li><p>Установите средства набора ресурсов на сервер переднего плана, который находится в пуле доверенных приложений, созданном на этапе 1.</p></li>
<li><p>Убедитесь, что SEFAUtil работает правильно, выполнив его, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Развертывание средства SEFAUtil в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка диапазонов номеров для ответа на звонки в таблице орбит парковки вызовов</p></td>
<td><p>Используйте командлет <strong>New – CSCallParkOrbit</strong> для создания диапазонов номеров для ответа на звонки в таблице орбит парковки вызовов и назначения диапазона ответа на звонки типу грауппиккуп.</p>
<div>

> [!NOTE]  
> Для создания, изменения, удаления и просмотра групп номеров для ответа на звонки в таблице орбит парковки вызовов необходимо использовать командную консоль Lync Server. Диапазоны номеров для группового ответа на звонки недоступны в панели управления Lync Server.


</div>
<div>

> [!NOTE]  
> Для тесной интеграции с существующими абонентами, диапазоны номеров обычно настраиваются как блок виртуальных расширений. Назначение непосредственных номеров (выполненных) в качестве номеров диапазонов в таблице орбит парковки вызовов не поддерживается.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Настройка номеров групп для ответа на звонки в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Назначение номера для ответа пользователям и включение групповой отправки звонков для пользователей</p></td>
<td><p>Используйте параметр/енаблеграуппиккуп в средстве SEFAUtil Resource Kit, чтобы включить отправке группового ответа и назначить для пользователей номер для ответа на звонки.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы</a></p></td>
</tr>
<tr class="even">
<td><p>Уведомлять пользователей о назначенном им номере для ответа и любое другое количество интересов</p></td>
<td><p>Так как любой пользователь может получить вызов, выполненный для группы пользователя ответа на звонок, пользователям может понадобиться мониторинг нескольких групп.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Обмен назначениями группового ответа на звонки пользователям в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка развертывания группового приема звонков</p></td>
<td><p>Тестирование размещения и извлечения вызовов убедитесь, что конфигурация работает должным образом.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Необязательно Проверка развертывания группового ответа на звонки в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

