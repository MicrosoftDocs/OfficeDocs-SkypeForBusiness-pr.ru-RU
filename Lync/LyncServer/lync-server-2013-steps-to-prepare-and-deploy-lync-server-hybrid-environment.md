---
title: 'Lync Server 2013: действия по подготовке и развертыванию гибридной среды Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Действия по подготовке и развертыванию гибридной среды Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-12-08_

В следующей таблице перечислены шаги, необходимые для подготовки среды для гибридного развертывания в Skype для бизнеса Online и Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Выполнение</th>
<th>Шаг</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Создание учетной записи клиента для Office 365 и включение Lync Online</p></td>
<td><p>Узнайте о Office 365 и Lync Online в <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Чтобы убедиться в том, что ваша среда готова к работе с Office 365, ознакомьтесь с <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">требованиями к системе</a>.</p>
<p>Подробные сведения о настройке Office 365 можно найти <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">в разделе Начало работы с office 365</a> и <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Настройка Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Добавление домена и проверка прав на владение доменом</p></td>
<td><p>Данный домен иногда называют <em>именным доменом</em>. Необходимо добавить домен к клиенту Office 365 и затем подтвердить права владения им в Office 365, выполнив следующие действия.</p>
<p>Чтобы добавить домен в клиент Office 365, выполните действия, описанные в разделе <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Добавление домена в office 365</a>.</p>
<p>Выполните все действия, описанные в каждом разделе раздела, в том &quot;числе изменить записи DNS для служб Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Проверка готовности среды</p></td>
<td><p>Вы можете использовать помощник по установке Office 365, который поможет вам развернуть Office 365. Дополнительные сведения можно найти <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">в разделе Использование помощника по настройке, чтобы определить готовность Office 365</a>.</p>
<p>Подробнее об использовании этого средства и развертывании Office 365 можно найти в <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">руководстве по развертыванию office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Подготовка к синхронизации Active Directory</p></td>
<td><p>Синхронизация службы каталогов Active Directory позволяет постоянно синхронизировать локальную службу Active Directory с Office 365. Это позволяет создавать синхронизированные версии каждой учетной записи пользователя и группы, а также выполнять синхронизацию глобального списка адресов (GAL) из локальной среды Microsoft Exchange Server с Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Вы должны синхронизировать учетные записи для всех пользователей Lync в вашей организации между локальными и Интернет-развертываниями Lync, даже если пользователи не перемещаются в Lync Online. Если не все пользователи синхронизированы, связь между локальными и сетевыми пользователи в организации может функционировать неправильно.


</div>
<p>Чтобы подготовить среду для синхронизации Active Directory, выполните действия, описанные в разделе <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">схема синхронизации службы каталогов</a>, в том числе Настройка единого входа.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Создание сертификатов для служб федерации Active Directory (AD FS)</p></td>
<td><p>Вам потребуется создать сертификаты, которые будут использоваться для федерации удостоверений с Office 365. Дополнительные сведения можно найти в разделе "сертификаты сервера федерации" плана и развертывания AD FS для использования с одним разделом для единого входа в <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">контрольном списке: использование служб ADFS для реализации единого входа и управления ими</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Назначение сертификатов для AD FS</p></td>
<td><p>После создания сертификатов, используемых для федерации удостоверений с Office 365, необходимо установить и назначить их.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Перемещение пилотных пользователей в Skype для бизнеса Online</p></td>
<td><p>После того как вы закончите процедуру подготовки и настройки среды для Skype для бизнеса Online, вы сможете переместить пилотных пользователей в Lync Online.</p>
<p>Дополнительные сведения <a href="lync-server-2013-move-users-to-lync-online.md">можно найти в разделе Перемещение пользователей в Lync Online в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Администрирование пользователей в гибридном развертывании</p></td>
<td><p>Подробнее об администрировании пользователей в гибридном развертывании можно узнать в разделе <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Администрирование пользователей в гибридном развертывании Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

