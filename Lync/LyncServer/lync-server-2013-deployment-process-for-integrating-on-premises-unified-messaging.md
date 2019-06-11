---
title: Процесс развертывания для интеграции локальной системы обработки сообщений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-17_

Если вы хотите интегрировать единую систему обмена сообщениями Exchange с Lync Server 2013, необходимо выполнить задачи, описанные в этой статье. Также убедитесь в том, что вы просматриваете рекомендации по планированию и развертыванию, описанные в [руководстве по интеграции локальной системы обработки сообщений и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). В этой статье предполагается, что вы развернули сервер Lync Server 2013 с размещенным сервером исправлений, и что вы включили пользователей для Lync Server 2013, но не обязательно выполнять все действия по развертыванию и настройке для включения корпоративной голосовой связи. описано в разделе [Развертывание корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.

<div>

## <a name="unified-messaging-integration-process"></a>Процесс интеграции единой системы обмена сообщениями

<div>


> [!IMPORTANT]
> Важно скоординировать администраторов Exchange вашей организации, чтобы подтвердить задачи, которые они будут выполнять для обеспечения успешной интеграции.



</div>


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
<td><p>Выполните развертывание одного из следующих компонентов:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 с пакетом обновления 1 (SP2) или последний пакет обновления</p></li>
<li><p>Microsoft Exchange Server 2010 или последний пакет обновления</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Если вы используете Microsoft Exchange Server 2013, установите следующие роли Exchange Server в одном лесу или другом лесе в качестве Lync Server 2013:</p>
<ul>
<li><p>клиентский доступ;</p></li>
<li><p>почтовый ящик.</p></li>
</ul>
<p>Если Microsoft Exchange Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange таким образом, чтобы он доверял лесу Lync Server 2013.</p>
<p>Если вы используете Exchange 2010, установите следующие роли Exchange Server либо в том же лесе, либо в другом лесе в составе Lync Server 2013:</p>
<ul>
<li><p>единая система обмена сообщениями;</p></li>
<li><p>транспортный сервер-концентратор;</p></li>
<li><p>клиентский доступ;</p></li>
<li><p>почтовый ящик.</p></li>
</ul>
<p>Если в разных лесах установлено приложение Lync Server 2013 и единая система обмена сообщениями Exchange (UM), настройте каждый лес Exchange таким образом, чтобы он доверял лесу Lync Server 2013.</p></td>
<td><p>Администраторы предприятия (если это первый сервер Exchange Server в организации)</p>
<p>-ИЛИ-</p>
<p>Администратор организации Exchange (если это не первый сервер Exchange Server в организации)</p></td>
<td><p>Изучите соответствующую документацию для своей версии Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Документация по развертыванию Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 по адресу.</p>
</dd>
<dt><span></span></dt>
<dd><p>Документация по развертыванию пакета обновления для Exchange Server 2010 <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>или последней версии.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>: планирование и развертывание.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Установите сертификаты.</p></td>
<td><p>Скачайте и установите сертификаты для каждого сервера UM Exchange в доверенном корневом центре сертификации (ЦС). Сертификаты необходимы для взаимной защиты на уровне транспорта (MTLS) между серверами, на которых запущены службы Exchange UM и Lync Server 2013.</p></td>
<td><p>Администраторы</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Создайте и настройте новую абонентскую группу Exchange UM.</p></td>
<td><p>На сервере Exchange UM Создайте абонентскую группу SIP, основываясь на конкретных требованиях к развертыванию вашей организации.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p>Для Exchange 2007 SP1 или новейшего пакета обновления ознакомьтесь &quot;со сведениями о том, как создать универсальный код&quot; ресурса <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>(URI) для единой системы обмена сообщениями в.</p>
<p>2010 или более поздней версии пакета обновления можно &quot;найти&quot; в <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>разделе Создание абонентской группы единой системы обмена сообщениями.</p>
<p>Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</p></td>
</tr>
<tr class="even">
<td><p>Настройте параметры безопасности для абонентской группы Exchange UM.</p></td>
<td><p>Чтобы зашифровать голосовой трафик для предприятия, настройте параметры безопасности в абонентской группе Exchange UM с помощью <strong>SIP Secure</strong> или <strong>Secure</strong>. Это особенно важный шаг, если вы развернули или планируете развертывание устройств Lync Phone Edition в своей среде. Для функционирования устройств Lync Phone Edition в среде с интегрированной функцией интегрированной системы обмена сообщениями, параметры шифрования Lync Server должны быть согласованы с параметрами безопасности для абонентской группы Exchange. For details, refer to the Deployment documentation.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></p>
<p>2007 и более поздних версий пакета обновления можно найти в статье:</p>
<p>&quot;Настройка безопасности для абонентской группы единой системы обмена&quot; сообщениями <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>по адресу.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновления см. также следующие статьи:</p>
<p>&quot;Настройте безопасность VoIP для абонентской группы&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>единой системы обмена сообщениями.</p>
<p>Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</p></td>
</tr>
<tr class="odd">
<td><p>Добавьте серверы единой системы обмена сообщениями в абонентскую группу Exchange UM.</p></td>
<td><p>To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan. В этом случае добавьте сервер в абонентскую группу Exchange UM.</p></td>
<td><p>Администраторы</p>
<p>Администраторы Exchange Server</p></td>
<td><p>Инструкции по добавлению сервера единой системы обмена сообщениями &quot;в телефонную группу&quot; для Exchange 2007 SP1 или новейшего <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>пакета обновления.</p>
<p>Для Exchange 2010 или новейшего пакета обновления ознакомьтесь &quot;со сведениями Просмотр и Настройка свойств сервера&quot; UM. <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a></p>
<p>Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</p></td>
</tr>
<tr class="even">
<td><p>Настройте SIP-адреса для почтовых ящиков.</p></td>
<td><p>Назначьте адреса SIP почтовым ящикам пользователей корпоративной голосовой связи, которые будут использовать возможности Exchange UM.</p></td>
<td><p>Администратор Lync Server 2013</p>
<p>Администратор получателей Exchange</p></td>
<td><p>В <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>Exchange 2007 с пакетом обновления 1 (SP1 &quot;или более поздней версии) Узнайте, как добавить, удалить или изменить адрес SIP для&quot; пользователя с поддержкой UM.</p>
<p>Для Exchange 2010 или новейшего пакета обновления ознакомьтесь &quot;со сведениями в <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>разделе Изменение адреса SIP для пользователя&quot; с поддержкой UM.</p>
<p>Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</p></td>
</tr>
<tr class="odd">
<td><p>Запустите скрипт exchucutil.ps1.</p></td>
<td><p>На сервере с запущенными службами Exchange UM откройте командную консоль Exchange и запустите сценарий ексчукутил. ps1, который выполняет следующие действия:</p>
<ul>
<li><p>Предоставляет Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory для Exchange UM, а именно, абонентские группы SIP, созданные в предыдущей задаче.</p></li>
<li><p>Создает объект шлюза для единой системы обмена сообщениями в службе каталогов Active Directory для каждого пула Lync Server 2013 Enterprise Edition или Standard Edition Server, на котором размещаются пользователи, поддерживающие корпоративную голосовую почту.</p></li>
<li><p>Создает группу слежения UM для каждого шлюза. The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway. These need to be mapped 1:1 if there is more than one dial plan.</p></li>
</ul></td>
<td><p>Администратор организации Exchange</p>
<p>Администратор получателей Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройте абонентские группы Lync Server 2013.</p></td>
<td><p>Если вы интегрируется с Exchange 2007 с пакетом обновления 1 (SP1) или более поздним пакетом обновления или Exchange 2010, создайте новый план голосовой коммутируемой телефонной связи с именем, совпадающим с полным доменным именем Exchange для абонентского плана.</p>



> [!NOTE]
> Это потребуется сделать для каждой абонентской группы единой системы обмена сообщениями.


<p>Если вы интегрируется с Exchange 2010 с пакетом обновления 1 (SP1), убедитесь в том, что настроены подходящие планы глобальных абонентов или уровней сайтов или пулов.</p>



> [!NOTE]
> При интеграции с Exchange 2010 с пакетом обновления 1 (SP1) абонентская группа Lync Server и имена абонентских групп UM Exchange не должны совпадать.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Настройка абонентских групп в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Запустите средство интеграции единой системы обмена сообщениями.</p></td>
<td><p>На Lync Server 2013 запустите <strong>оксумутил. exe</strong>, который:</p>
<ul>
<li><p>создает объекты контактов абонентского доступа и автосекретаря;</p></li>
<li><p>Проверка наличия корпоративной телефонной группы с именем, совпадающим с полным доменным планом Exchange UM. Если вы используете Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии, имена абонентской группы не должны совпадать, и вы можете пропустить предупреждение этого средства.</p></li>
</ul>
<p>Это средство работает, проверяя параметры службы единой системы обмена сообщениями в Active Directory и разрешая администратору Lync Server 2013 просматривать, создавать и редактировать объекты контактов.</p></td>
<td><p>RTCUniversalServerAdmins <em>и</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Для успешного выполнения ocsumutil.exe пользователь должен принадлежать обеим этим группам.





> [!NOTE]
> To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored. This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet. Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>При необходимости выполните другие действия по настройке голосовой связи.</p></td>
<td><p>Если вы еще не настроили параметры корпоративной голосовой связи на серверах или пользователях, выполните одно или несколько из указанных ниже действий.</p>
<ul>
<li><p>разверните и настройте</p>
<p>шлюзы и серверы-посредники телефонной сети общего пользования (ТСОП);</p></li>
<li><p>определите политики голосовой связи, записи использования ТСОП и маршруты исходящих вызовов;</p></li>
<li><p>активируйте корпоративную голосовую связь для пользователей;</p></li>
<li><p>при необходимости настройте абонентские группы для определенных пользователей.</p></li>
</ul>
<p>В зависимости от того, какие возможности поддерживаются корпоративными голосовыми функциями, могут потребоваться другие этапы настройки.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>См. следующие разделы:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Включите пользователей корпоративной голосовой почты для Exchange UM.</p></td>
<td><p>На сервере Exchange UM убедитесь, что политика почтового ящика единой системы обмена сообщениями создана и у каждого пользователя есть уникальное назначение добавочного номера, а затем включите ее для единой системы обмена сообщениями.</p></td>
<td><p>Администратор получателей Exchange</p></td>
<td><p>Для Exchange 2007 SP1 или более поздней версии ознакомьтесь &quot;со сведениями о том, как разрешить&quot; пользователям <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>единую систему обмена сообщениями на веб-странице.</p>
<p>2010 или более поздней версии пакета обновления можно &quot;узнать в <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>разделе Включение поддержки единой&quot; системы обмена сообщениями для пользователей Exchange.</p>
<p>Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

