---
title: 'Lync Server 2013: процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-25_

Для эффективного планирования интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange необходимо учитывать следующее:

  - Необходимые условия для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange

  - обязательные этапы процесса интеграции.

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Необходимые компоненты развертывания для интеграции с размещаемой единой системой обмена сообщениями Exchange

Прежде чем начать процесс интеграции, необходимо предварительно развернуть Lync Server 2013 (как минимум, интерфейсный пул или сервер Standard Edition), пограничный сервер и клиенты Lync 2013 или Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Процесс интеграции

В следующей таблице приведен обзор процесса интеграции единой системы обмена сообщениями Exchange. Сведения о шагах развертывания приведены в статье [предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) в документации по развертыванию.


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
<th>Права и разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка пограничного сервера.</p></td>
<td><ol>
<li><p>Настройка пограничного сервера для федерации.</p></li>
<li><p>Ручное копирование данных на пограничный сервер.</p></li>
<li><p>Настройка поставщика услуг размещения на пограничном сервере.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка политики маршрутизации размещенной голосовой почты.</p></td>
<td><ol>
<li><p>Измените глобальную политику маршрутизации размещенной голосовой почты или создайте новую политику маршрутизации размещенной голосовой почты с областью "сайт" или "на пользователя".</p></li>
<li><p>Для политик с областью "на пользователя" назначьте политику пользователям или группам.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Управление политиками размещенной голосовой почты в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Включение поддержки размещаемой голосовой почты для пользователей.</p></td>
<td><ul>
<li><p>Настройте учетные записи для пользователей, почтовые ящики которых находятся в размещенной службе Exchange.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Предоставление пользователям размещенной голосовой почты в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка размещаемых контактных объектов.</p></td>
<td><ol>
<li><p>Создание контактных объектов для автосекретаря размещаемой единой системы обмена сообщениями Exchange.</p></li>
<li><p>Создание контактных объектов для доступа подписчика размещаемой единой системы обмена сообщениями Exchange.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Чтобы создать, изменить или удалить контактные объекты, пользователь, запускающий командлет New-CsExUmContact, Set-CsExUmContact или Remove-CsExUmContact, должен иметь соответствующее разрешение в подразделении Active Directory, где хранятся новые контактные объекты. Это разрешение можно предоставить, выполнив командлет Grant-CsOUPermission. Дополнительные сведения см. в документации Lync Server Management Shell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

