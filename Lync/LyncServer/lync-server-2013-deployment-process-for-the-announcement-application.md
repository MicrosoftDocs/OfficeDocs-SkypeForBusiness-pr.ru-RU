---
title: 'Lync Server 2013: процесс развертывания для приложения "оповещение"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d38db71daed7a7946b62593a29f7f685c96c647
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526856"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Процесс развертывания приложения "объявление" в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

В этом разделе представлен обзор действий, необходимых при развертывании приложения извещения. Перед настройкой объявлений необходимо развернуть корпоративную голосовую связь. Компоненты, необходимые для приложения извещения, устанавливаются и включаются при развертывании корпоративной голосовой связи.

### <a name="announcement-deployment-process"></a>Процесс развертывания объявлений

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
<th>Роли</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка параметров объявлений</p></td>
<td><ul>
<li><p>Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</p></li>
<li><p>Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Создание извещения в Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Настройка таблицы неназначенных номеров в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания объявления</p></td>
<td><p>Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Необязательно Проверка развертывания объявлений в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

