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
ms.openlocfilehash: 3326db7ce62279c4295bc13ec262a5a553ca5e62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Действия по подготовке и развертыванию гибридной среды Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-12-08_

В следующей таблице приведены действия, необходимые для подготовки среды к гибридному развертыванию со Skype для бизнеса Online и Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Выполнено?</th>
<th>Шаг</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Создание учетной записи клиента для Office 365 и включение Lync Online</p></td>
<td><p>Узнайте о Office 365 и Lync Online в <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Чтобы убедиться, что ваша среда готова к работе с Office 365, ознакомьтесь с <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">требованиями к системе</a>.</p>
<p>Подробнее о настройке Office 365 вы найдете в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Начало работы с office 365</a> и <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Настройка Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Добавление домена и проверка прав на владение доменом</p></td>
<td><p>Домен иногда также называется <em>доменом запоминающийся</em>. Вам необходимо добавить домен в клиент Office 365 и затем проверить домен в Office 365. Эти действия предназначены для проверки прав владения доменом.</p>
<p>Чтобы добавить свой домен в клиент Office 365, выполните действия, описанные в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Добавление домена в office 365</a>.</p>
<p>Выполните все действия, описанные в разделах этой статьи, в том &quot;числе изменение записей DNS для служб Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Проверка готовности среды</p></td>
<td><p>С помощью помощника по установке Office 365 вы можете развернуть Office 365. Дополнительные сведения см. <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">в статье Использование помощника по настройке для определения готовности Office 365</a>.</p>
<p>Дополнительные сведения об использовании этого средства и развертывании Office 365 содержатся в <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">руководстве по развертыванию office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Подготовка к синхронизации Active Directory</p></td>
<td><p>Синхронизация Active Directory обеспечивает непрерывную синхронизацию локальной службы каталогов Active Directory и Office 365. Это позволяет создавать синхронизированные версии каждой учетной записи пользователя и группы, а также выполнять синхронизацию глобального списка адресов (GAL) из локальной среды Microsoft Exchange Server в Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Необходимо синхронизировать учетные записи AD для всех пользователей Lync в Организации между локальными и подключенными развертываниями Lync, даже если пользователи не перемещены в Lync Online. Если вы не синхронизируете всех пользователей, связь между локальными и сетевыми пользователями в Организации может работать неправильно.


</div>
<p>Чтобы подготовить среду к синхронизации Active Directory, выполните действия, описанные в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">схема синхронизации службы каталогов</a>, в том числе Настройка единого входа.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Создание сертификатов для служб федерации Active Directory (AD FS)</p></td>
<td><p>Вам потребуется создать сертификаты, используемые для федерации удостоверений Office 365. Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входным разделом в разделе <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Контрольный список: использование AD FS для реализации единого входа и управления им</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Назначение сертификатов Active Directory</p></td>
<td><p>После создания сертификатов, используемых для федерации удостоверений с Office 365, необходимо установить и назначить их.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Перемещение пилотных пользователей в Skype для бизнеса Online</p></td>
<td><p>После выполнения действий по подготовке и настройке среды для Skype для бизнеса Online можно начать перемещение пилотных пользователей в Lync Online.</p>
<p>Ознакомьтесь <a href="lync-server-2013-move-users-to-lync-online.md">со статьей перемещение пользователей в Lync Online в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Администрирование пользователей в гибридном развертывании</p></td>
<td><p>Сведения о том, как администрировать пользователей в гибридном развертывании, приведены <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">в разделе Администрирование пользователей в гибридном развертывании Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

