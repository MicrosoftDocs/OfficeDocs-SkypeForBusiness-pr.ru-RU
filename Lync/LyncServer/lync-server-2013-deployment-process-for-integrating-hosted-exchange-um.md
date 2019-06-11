---
title: 'Lync Server 2013: процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-25_

Для эффективного планирования интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange необходимо учитывать следующее:

  - Предварительные требования для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями

  - Шаги, необходимые для процесса интеграции

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Требования к развертыванию для интеграции с размещенной единой системой обмена сообщениями Exchange

Прежде чем начать процесс интеграции, необходимо предварительно развернуть Lync Server 2013 (как минимум, пул переднего плана или сервер Standard Edition), пограничный сервер, а также клиенты Lync 2013 или Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Процесс интеграции

В следующей таблице представлены общие сведения о размещенном процессе интеграции Exchange UM. Дополнительные сведения о действиях по развертыванию можно найти в статье [предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) в документации по развертыванию.


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
<td><p>Настройте пограничный сервер.</p></td>
<td><ol>
<li><p>Настроить пограничный сервер для федерации.</p></li>
<li><p>Ручная репликация данных на пограничный сервер.</p></li>
<li><p>Настройте поставщика услуг размещения на пограничном сервере.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка политики размещенной голосовой почты.</p></td>
<td><ol>
<li><p>Либо измените политику глобальной размещенной голосовой почты, либо создайте новую политику размещенной голосовой почты с помощью сайта или области "на пользователя".</p></li>
<li><p>Для политик с областью "на пользователя" назначьте политику пользователям или группам.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Управление политиками размещенной голосовой почты в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Включите пользователей для размещенной голосовой почты.</p></td>
<td><ul>
<li><p>Настройте учетные записи пользователей, чьи почтовые ящики находятся в размещенной службе Exchange.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Включение поддержки размещаемой голосовой почты для пользователей в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка объектов размещенных контактов.</p></td>
<td><ol>
<li><p>Создание объектов контактов для автоматического ассистента для размещенной единой системы обмена сообщениями.</p></li>
<li><p>Создание объектов контактов для доступа абонента для размещенной единой системы обмена сообщениями.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Для создания, изменения и удаления объектов контакта пользователь, который запускает командлет New-Ксексумконтакт, Set-Ксексумконтакт или Remove-Ксексумконтакт, должен иметь соответствующее разрешение на доступ к организационному подразделению Active Directory, в котором хранятся новые объекты контакта. This permission can be granted by running the Grant-CsOUPermission cmdlet. Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.


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

