---
title: 'Lync Server 2013: процесс развертывания для отправки группового звонка'
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
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Процесс развертывания для отправки группового звонка в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-25_

В этом разделе приводятся общие сведения о процедуре развертывания группового звонка. Перед настройкой отправки группового звонка необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью. Компоненты, необходимые для отправки группового звонка, устанавливаются и включаются при развертывании корпоративной голосовой связи.

### <a name="group-call-pickup-deployment-process"></a>Процесс развертывания компонента группового ответа на звонки

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
<th>Необходимые группы и роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Включение средства набора ресурсов Сефаутил в топологии</p></td>
<td><ol>
<li><p>С помощью командлета <strong>New-CsTrustedApplicationPool</strong> создайте новый доверенный пул приложений.</p></li>
<li><p>С помощью командлета<strong>New-CsTrustedApplication</strong> задайте инструмент SEFAUtil в качестве доверенного приложения.</p></li>
<li><p>Выполните командлет <strong>Enable-CsTopology</strong> для включения топологии.</p></li>
<li><p>Установите средства набора ресурсов на сервере переднего плана, который находится в надежном пуле приложений, созданном на этапе 1.</p></li>
<li><p>Убедитесь, что SEFAUtil выполняется правильно, воспользовавшись им для отображения параметров переадресации звонков какого-либо пользователя в развертывании.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройте диапазоны номеров для ответа на звонки в таблице орбит парковки вызовов</p></td>
<td><p>С помощью командлета <strong>New-кскаллпаркорбит</strong> можно создать диапазоны номеров для отправки звонков в таблице "приостановить Звонок", а затем назначить диапазон раскладки для набора грауппиккуп.</p>
<div>

> [!NOTE]  
> Вы должны использовать командную консоль Lync Server для создания, изменения, удаления и просмотра диапазонов номеров отправки групп в таблице "приостановить Звонок". На панели управления Lync Server не доступны диапазоны номеров для отправки групповых звонков.


</div>
<div>

> [!NOTE]  
> Для простой интеграции с существующими абонентскими группами диапазоны номеров обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров диапазона в таблице орбит парковки вызовов не поддерживается.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Настройка номеров групп для отправки звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Назначение абоненту номера для отправки и включения группового приема для пользователей</p></td>
<td><p>Используйте параметр/енаблеграуппиккуп в средстве Сефаутил Resource Kit для включения отправки группового звонка и назначения номера для отправки звонков пользователям.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Включение отправки группового звонка для пользователей в Lync Server 2013 и назначение номера группы</a></p></td>
</tr>
<tr class="even">
<td><p>Уведомление пользователей о назначенном им номере ответа на звонок и любом другом важном номере</p></td>
<td><p>Поскольку любой пользователь может получить звонок пользователю для отправки группового звонка, пользователям может потребоваться мониторинг нескольких групп.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Связь групп раскладки звонков для пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка развертывания для группового приема звонков</p></td>
<td><p>Тестирование размещения и получения звонков для обеспечения работоспособности вашей конфигурации.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Необязательно Проверка развертывания отправки группового звонка в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

