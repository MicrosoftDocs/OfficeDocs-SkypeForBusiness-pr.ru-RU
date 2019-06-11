---
title: 'Lync Server 2013: контрольный список развертывания для контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Контрольный список развертывания для контроля допуска звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-08_

Чтобы эффективно спланировать управление допуском звонков (CAC), необходимо принять во все указанные ниже действия.

  - Необходимые условия для развертывания CAC.

  - Информация, необходимая для решений CAC и конфигурации, которые необходимо выполнить перед развертыванием.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Предварительные требования к развертыванию для управления допуском звонков

Прежде чем развертывать управление допуском звонков, необходимо предварительно развернуть внутренние серверы Lync Server 2013, в том числе либо интерфейсный пул, либо сервер Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Требования к сведениям для управления допуском звонков

В таблице ниже приведены сведения, необходимые для развертывания управления допуском звонков.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Требования к сведениям для развертывания управления допуском звонков

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Информация</th>
<th>Сводка данных, необходимых</th>
<th>Документация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Возможности Lync Server, необходимые для Организации</p></td>
<td><ul>
<li><p>Возможности, которые должны поддерживаться вашей организацией</p></li>
<li><p>Возможности, которые должны быть включены для отдельных пользователей</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Топологии и компоненты, которые нужно развернуть</p></td>
<td><ul>
<li><p>Компоненты, связанные с CAC, автоматически устанавливаются в составе Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение своих требований для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Требования к системе</p></td>
<td><ul>
<li><p>Требования к оборудованию</p></li>
<li><p>Требования к программному обеспечению </p></li>
<li><p>Требования к выровнению</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Требования к инфраструктуре</p></td>
<td><ul>
<li><p>Для CAC не требуются особые требования к инфраструктуре</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Требования к инфраструктуре для контроля допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Требования к сетевому интерфейсу</p></td>
<td><ul>
<li><p>Сведения о внутреннем и внешнем интерфейсе</p></li>
<li><p>Сведения о маршрутизации (в том числе сведения в блоге <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>на странице Microsoft Lync Server Teams в канале ответа клиента)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Развертывание доступа внешних пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Стратегия развертывания</p></td>
<td><ul>
<li><p>Последовательность развертывания</p></li>
<li><p>Рабочая группа или домен</p></li>
<li><p>Безопасность</p></li>
<li><p>Мониторинг и аудит</p></li>
<li><p>Рекомендации по оборудованию</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Рекомендации по контролю допуска звонков в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Процесс развертывания</p></td>
<td><ul>
<li><p>Необходимые компоненты</p></li>
<li><p>Требования к информации</p></li>
<li><p>Процесс и процедуры</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Настройка управления допуском звонков в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

