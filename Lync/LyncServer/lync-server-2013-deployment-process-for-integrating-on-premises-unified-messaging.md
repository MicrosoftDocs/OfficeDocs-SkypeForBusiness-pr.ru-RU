---
title: Процесс развертывания для интеграции локальной единой системы обмена сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbef561e7b2c4edd3e38f028bdbdcdfbe246d036
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-17_

Если вы хотите интегрировать единую систему обмена сообщениями Exchange с Lync Server 2013, необходимо выполнить действия, описанные в этой статье. Кроме того, ознакомьтесь с рекомендациями по планированию и развертыванию, описанными в статье [рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). В этом разделе предполагается, что вы развернули Lync Server 2013 с совмещенным сервером-посредником и что вы включили пользователей для Lync Server 2013, но не обязательно выполнили все действия по развертыванию и настройке, чтобы включить корпоративную голосовую связь, как описано в статье Deployment [Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.

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
<li><p>Microsoft Exchange Server 2007 с пакетом обновления 1 (SP2) или последним пакетом обновления</p></li>
<li><p>Microsoft Exchange Server 2010 или последний пакет обновления</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Если вы используете Microsoft Exchange Server 2013, установите следующие роли Exchange Server в том же лесу или в другом лесу, что и Lync Server 2013:</p>
<ul>
<li><p>клиентский доступ;</p></li>
<li><p>Почтовый ящик</p></li>
</ul>
<p>Если Microsoft Exchange Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы он доверял лесу Lync Server 2013.</p>
<p>Если вы используете Exchange 2010, установите следующие роли Exchange Server в том же лесу или в другом лесу, что и Lync Server 2013:</p>
<ul>
<li><p>единая система обмена сообщениями;</p></li>
<li><p>транспортный сервер-концентратор;</p></li>
<li><p>клиентский доступ;</p></li>
<li><p>Почтовый ящик</p></li>
</ul>
<p>Если Lync Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы он доверял лесу Lync Server 2013.</p></td>
<td><p>Администраторы предприятия (если это первый сервер Exchange Server в организации)</p>
<p>-ИЛИ-</p>
<p>Администратор организации Exchange (если это не первый сервер Exchange Server в организации)</p></td>
<td><p>Изучите соответствующую документацию для вашей версии Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Документация по развертыванию Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 на сайте.</p>
</dd>
<dt><span></span></dt>
<dd><p>Документация по развертыванию Exchange Server 2010 или новейшей <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>версии пакета обновления на сайте.</p>
</dd>
<dt><span></span></dt>
<dd><p>Планирование и развертывание Microsoft Exchange Server 2013 на <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>сайте.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Установите сертификаты.</p></td>
<td><p>Скачайте и установите сертификаты для каждого сервера единой системы обмена сообщениями Exchange из доверенного корневого центра сертификации (CA). Сертификаты необходимы для взаимной безопасности на уровне транспорта (MTLS) между серверами, на которых запущены службы единой системы обмена сообщениями Exchange и Lync Server 2013.</p></td>
<td><p>Администраторы</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Создайте и настройте новую абонентскую группу SIP единой системы обмена сообщениями Exchange.</p></td>
<td><p>На сервере единой системы обмена сообщениями Exchange создайте абонентскую группу SIP на основе конкретных требований к развертыванию вашей организации.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p>Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более поздней версии ознакомьтесь со статьей&quot; создание <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>абонентской группы URI SIP единой системы обмена сообщениями в.</p>
<p>&quot; В <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>статье &quot;Создание абонентской группы единой системы обмена сообщениями для Exchange 2010 или более позднего пакета обновления.</p>
<p>Для Exchange 2013: единая система обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</p></td>
</tr>
<tr class="even">
<td><p>Настройте параметры безопасности для абонентской группы SIP единой системы обмена сообщениями Exchange.</p></td>
<td><p>Для шифрования трафика корпоративной голосовой связи настройте параметры безопасности для абонентской группы SIP единой системы обмена сообщениями Exchange в качестве защиты или <strong>защиты</strong> <strong>SIP</strong> . Это особенно важный шаг, если вы развернули или запланируете развертывание устройств Lync Phone Edition в вашей среде. Для работы устройств Lync Phone Edition в среде с интеграцией единой системы обмена сообщениями Exchange параметры шифрования Lync Server должны быть согласованы с параметрами безопасности абонентской группы единой системы обмена сообщениями Exchange. Дополнительные сведения см. в документации по развертыванию.</p></td>
<td><p>Администратор организации Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></p>
<p>Сведения об Exchange 2007 с пакетом обновления 1 (SP1) или более поздней версии см.</p>
<p>&quot;Настройка безопасности для абонентской группы единой системы обмена&quot; сообщениями <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>по адресу.</p>
<p>Для Exchange 2010 или более поздней версии пакета обновления см. также следующие статьи:</p>
<p>&quot;Настройка безопасности VoIP для абонентской группы&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>единой системы обмена сообщениями.</p>
<p>Для Exchange 2013: единая система обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</p></td>
</tr>
<tr class="odd">
<td><p>Добавьте серверы единой системы обмена сообщениями в абонентскую группу SIP единой системы обмена сообщениями Exchange.</p></td>
<td><p>Чтобы добавленный сервер единой системы обмена сообщениями отвечал на входящие звонки и обрабатывал их, необходимо добавить его в абонентскую группу единой системы обмена сообщениями. В этом случае добавьте сервер в абонентскую группу SIP единой системы обмена сообщениями Exchange.</p></td>
<td><p>Администраторы</p>
<p>Администраторы Exchange Server</p></td>
<td><p>В случае с Exchange 2007 с пакетом обновления 1 &quot;(SP1) или более поздней версии Узнайте,&quot; как <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>добавить сервер единой системы обмена сообщениями в абонентскую службу.</p>
<p>Для Exchange 2010 или более поздней версии можно &quot;просмотреть или настроить свойства сервера&quot; единой системы обмена сообщениями <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>на сайте.</p>
<p>Для Exchange 2013: единая система обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</p></td>
</tr>
<tr class="even">
<td><p>Настройте SIP-адреса для почтовых ящиков.</p></td>
<td><p>Назначьте SIP адреса почтовым ящикам пользователей корпоративной голосовой связи, которые будут использовать функции единой системы обмена сообщениями Exchange.</p></td>
<td><p>Lync Server 2013, администратор</p>
<p>Администратор получателей Exchange</p></td>
<td><p>Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более поздней версии Узнайте, как добавить, удалить или изменить SIP адрес для&quot; пользователя <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>с включенной поддержкой единой системы обмена сообщениями.</p>
<p>Для Exchange 2010 или более поздней версии в &quot;разделе изменение SIP SIP Address для пользователя&quot; с включенной поддержкой <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>единой системы обмена сообщениями по адресу.</p>
<p>Для Exchange 2013: единая система обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</p></td>
</tr>
<tr class="odd">
<td><p>Запустите скрипт exchucutil.ps1.</p></td>
<td><p>На сервере, на котором запущены службы единой системы обмена сообщениями, откройте командную консоль Exchange и запустите сценарий сценарий ExchUCUtil. ps1, который выполняет следующие действия:</p>
<ul>
<li><p>Предоставляет Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory единой системы обмена сообщениями Exchange, а именно абонентских групп SIP, созданных в предыдущей задаче.</p></li>
<li><p>Создает объект шлюза IP единой системы обмена сообщениями в Active Directory для каждого пула Lync Server 2013 Enterprise Edition или сервера Standard Edition, на котором размещаются пользователи, для которых включена поддержка корпоративной голосовой связи.</p></li>
<li><p>Создает сервисную группу единой системы обмена сообщениями Exchange для каждого шлюза. Пилотным идентификатором сервисной группы будет имя абонентской группы, связанной с соответствующим шлюзом. Их необходимо сопоставлять 1:1, если абонентских групп несколько.</p></li>
</ul></td>
<td><p>Администратор организации Exchange</p>
<p>Администратор получателей Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка абонентских планов Lync Server 2013.</p></td>
<td><p>При интеграции с Exchange 2007 с пакетом обновления 1 (SP1) или более поздним пакетом обновления или Exchange 2010 создайте новую абонентскую группу для корпоративной голосовой связи с именем, соответствующим полному доменному имени абонентской группы единой системы обмена сообщениями Exchange.</p>



> [!NOTE]
> Это потребуется сделать для каждой абонентской группы единой системы обмена сообщениями.


<p>Если вы интегрируетесь с Exchange 2010 с пакетом обновления 1 (SP1), убедитесь, что настроены соответствующие корпоративные и глобальные абонентские группы на уровне сайта или на уровне пула.</p>



> [!NOTE]
> При интеграции с Exchange 2010 с пакетом обновления 1 (SP1) абонентская группа Lync Server и имена абонентской группы SIP единой системы обмена сообщениями Exchange не должны сопоставляться.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Настройка абонентских планов в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Запустите средство интеграции единой системы обмена сообщениями Exchange.</p></td>
<td><p>На Lync Server 2013 выполните <strong>ocsumutil. exe</strong>, который:</p>
<ul>
<li><p>создает объекты контактов абонентского доступа и автосекретаря;</p></li>
<li><p>Проверка наличия абонентской группы корпоративной голосовой связи с именем, которое соответствует полному доменному имени абонентской группы единой системы обмена сообщениями Exchange. Если вы используете Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии, имена абонентской группы не обязательно должны быть согласованы, и вы можете пропустить предупреждение этого средства.</p></li>
</ul>
<p>Это средство работает, проверяя параметры Active Directory единой системы обмена сообщениями Exchange и позволяя администратору Lync Server 2013 просматривать, создавать и редактировать объекты контактов.</p></td>
<td><p>RTCUniversalServerAdmins <em>и</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Для успешного выполнения ocsumutil.exe пользователь должен принадлежать обеим этим группам.





> [!NOTE]
> Чтобы создать объекты контактов, пользователей, запускающий средство ocsumutil.exe, должен обладать нужными разрешениями для подразделения Active Directory, в котором хранятся новые объекты контактов. Эти разрешения можно получить, выполнив командлет <STRONG>Grant-CsOUPermission</STRONG>. Дополнительные сведения см. в документации Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на сервере Microsoft Exchange</a></p></td>
</tr>
<tr class="even">
<td><p>При необходимости выполните другие действия по настройке корпоративной голосовой связи.</p></td>
<td><p>Если вы еще не настроили параметры корпоративной голосовой связи на серверах или пользователях, выполните одно или несколько из следующих действий:</p>
<ul>
<li><p>разверните и настройте</p>
<p>шлюзы и серверы-посредники телефонной сети общего пользования (ТСОП);</p></li>
<li><p>определите политики голосовой связи, записи использования ТСОП и маршруты исходящих вызовов;</p></li>
<li><p>активируйте пользователей для применения Enterprise Voice;</p></li>
<li><p>при необходимости настройте абонентские группы для определенных пользователей.</p></li>
</ul>
<p>В зависимости от включенных функций корпоративной голосовой связи может потребоваться выполнить другие действия по настройке.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>См. следующие разделы:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Включение пользователей корпоративной голосовой связи для единой системы обмена сообщениями Exchange.</p></td>
<td><p>На сервере единой системы обмена сообщениями Exchange убедитесь, что создана политика почтовых ящиков единой системы обмена сообщениями и у каждого пользователя есть уникальное назначение добавочного номера, а затем включите для пользователя единую систему обмена сообщениями.</p></td>
<td><p>Администратор получателей Exchange</p></td>
<td><p>Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>поздней версии Узнайте,&quot; как включить для пользователя поддержку единой системы обмена сообщениями.</p>
<p>Для сервера Exchange 2010 или более поздней версии &quot;в разделе Включение поддержки единой системы&quot; обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>сообщениями в Exchange или более поздней версии.</p>
<p>Для Exchange 2013: единая система обмена <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

