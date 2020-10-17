---
title: 'Lync Server 2013: совместимость с Lync 2013'
description: 'Lync Server 2013: совместимость с Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b905d5aa43ea2a73f8b08721e39c95a30b3baa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570545"
---
# <a name="lync-2013-compatibility"></a>Совместимость с Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-10-07_

В этом разделе описывается совместимость Lync 2013 с различными версиями пакетов Microsoft Office, Microsoft Exchange Server, операционными системами Windows и выбранными клиентами общедоступных мгновенных сообщений (IM).

<div>

## <a name="office-and-lync-2013"></a>Office и Lync 2013

В следующей таблице описаны функции Lync 2013, которые поддерживаются различными версиями Office.

### <a name="lync-2013-and-microsoft-office-compatibility"></a>Lync 2013 и совместимость с Microsoft Office

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Microsoft Office 2003 с пакетом обновления 3 (SP3) (обязательно) или последним пакетом обновления (рекомендуется)</th>
<th>Microsoft Office 2007;</th>
<th>Microsoft Office 2010;</th>
<th>Microsoft Office 2013;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Настройка приглашений на собрания в Outlook (Добавление логотипа, URL-адреса справки, заявления об отказе, текста нижнего колонтитула)</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>В Outlook настройте параметр собрания, чтобы он отключил аудио и видео участников по умолчанию.</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Единое хранилище контактов для управления списками контактов в Office и Lync</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да (требуется Exchange 2013) 1</p></td>
</tr>
<tr class="even">
<td><p>Изображения с высоким разрешением</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да (требуется Exchange 2013) 1</p></td>
</tr>
<tr class="odd">
<td><p>Интегрированная программа установки Lync 2013 в программу установки Office</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Общие заметки OneNote</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Содержимое презентации PowerPoint</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Состояние присутствия в полях "Кому" и "копия" в Microsoft Outlook</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Ответ с Конференц-вызовом из меню доступности</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да (с карточки контакта)</p></td>
<td><p>Да (с карточки контакта)</p></td>
</tr>
<tr class="even">
<td><p>Состояние присутствия в приглашении на собрание на вкладке помощник по планированию</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Ответ с помощью IM или вызов из панели инструментов или ленты в полученном сообщении электронной почты</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Состояние присутствия в поле Outlook от</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Ответ в меню доступности для обмена мгновенными сообщениями или голосовой связью</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да (с карточки контакта)</p></td>
<td><p>Да (с карточки контакта)</p></td>
</tr>
<tr class="even">
<td><p>Мгновенные сообщения и сведения о присутствии в Microsoft Word и Microsoft Excel Files (смарт-теги включены)</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Только Microsoft Word</p></td>
<td><p>Только Microsoft Word</p></td>
</tr>
<tr class="odd">
<td><p>Мгновенные сообщения и сведения о присутствии на сайтах Microsoft SharePoint (необходимо установить Outlook)</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
</tbody>
</table>


1 Дополнительные сведения приведены в [статье интеграция Microsoft Lync server 2013 и Microsoft Exchange server 2013](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md) в документации по планированию.

Следующие функции доступны только в Office 2010 или Office 2013:

  - Карточка контакта с расширенными возможностями, такими как видеовызовы и общий доступ к рабочему столу

  - Быстрый поиск из поля "найти контакт" в Outlook

  - Ответ с помощью мгновенного сообщения или вызова из домашней ленты Outlook в папках почта, календарь, контакты и задачи

  - Список контактов Lync в панели Outlook To-Do

  - Состояние присутствия, общий доступ к программе и передача файлов в Office Backstage (вкладка "файл")

  - Меню присутствия в Microsoft Office SharePoint Workspace 2010 (ранее Microsoft Office Groove 2007)

  - Расширяемость меню присутствия

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server и Lync 2013

В следующей таблице описывается поддержка Lync 2013 для различных версий Exchange Server. Для обработки расширенных вызовов MAPI необходимо установить Outlook на клиентском компьютере, а для некоторых функций требуется использование веб-служб Exchange (EWS).

### <a name="lync-2013-and-exchange-server-compatibility"></a>Совместимость с Lync 2013 и Exchange Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Версия Exchange Server</th>
<th>Поддержка Lync 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>Аналогично поддержке Exchange Server 2010, с добавлением единого хранилища контактов, изображений с высоким разрешением и интеграции архивации.</p>
<div>

> [!NOTE]  
> Дополнительные сведения см. в <A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">статье интеграция Microsoft Lync server 2013 и Microsoft Exchange server 2013</A>.


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>То же, что и поддержка Exchange Server 2007 с добавлением синхронизации контактов Exchange.</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 с пакетом обновления 1 (SP1) (обязательно) или последним пакетом обновления (рекомендуется)</p></td>
<td><p>Следующие функции доступны только в службах EWS:</p>
<ul>
<li><p>Чтение или удаление элементов в папке "Журнал бесед"</p></li>
<li><p>Чтение или удаление элементов голосовой почты</p></li>
<li><p>Отображение расширенных сведений о доступности, темы и местонахождения собрания</p></li>
</ul>
<p>Общедоступные папки являются необязательными в Exchange Server 2007 с пакетом обновления 1 (SP1) или последним пакетом обновления или выпуском (рекомендуется).</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>Только MAPI для Outlook. Функции, доступные только для EWS, недоступны (см. предыдущую строку).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows и Lync 2013

Сведения о поддержке Lync 2013 и Windows можно найти в разделе [Поддержка клиентского программного обеспечения Lync в Lync Server 2013](lync-server-2013-lync-client-software-support.md) в документации по планированию.

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh и Lync 2013

Lync Server 2013 поддерживает определенные клиенты на компьютерах с операционными системами Macintosh. Для получения дополнительных сведений обратитесь к разделу [Поддержка клиентского программного обеспечения Lync в Lync Server 2013](lync-server-2013-lync-client-software-support.md) в документации по планированию.

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>Общедоступные клиенты обмена мгновенными сообщениями и Lync 2013

Если вы настроили сервер для общедоступной службы обмена мгновенными сообщениями, Lync поддерживает следующие возможности в общедоступных сетях обмена мгновенными сообщениями. Состояние присутствия фильтруется по этим состояниям присутствия, поддерживаемым клиентом общедоступной системы обмена мгновенными сообщениями. Дополнительные сведения приведены в статье [Планирование подключений к общедоступным службам обмена мгновенными сообщениями в Lync server 2013](lync-server-2013-planning-for-public-instant-messaging-connectivity.md) в документации по планированию и [Управление политикой внешнего доступа в Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md) в документации по операциям.

Кроме того, функция интеграции XMPP в Lync Server 2013 позволяет пользователям обмениваться мгновенными сообщениями и сведениями о присутствии с пользователями общедоступных служб обмена мгновенными сообщениями, которые используют протокол расширенной службы обмена сообщениями и присутствия, например Google говорите. Дополнительные сведения приведены в статье [планирование Федерации для Федерации XMPP в Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md) в документации по планированию.

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Совместимость клиентов Lync 2013 и общедоступных мгновенных сообщений

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Клиент</th>
<th>Поддерживаемые возможности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>Обмен мгновенными сообщениями, основное присутствие, аудио/видео (A/V) *</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>Обмен мгновенными сообщениями, базовое присутствие, аудио</p></td>
</tr>
<tr class="odd">
<td><p>ПРОГРАММУ</p></td>
<td><p>Мгновенные сообщения и основные сведения о присутствии</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Мгновенные сообщения и основные сведения о присутствии</p></td>
</tr>
<tr class="odd">
<td><p>Google говорите</p></td>
<td><p>Мгновенные сообщения и основные сведения о присутствии</p></td>
</tr>
</tbody>
</table>


\*A/V поддерживается последней версией Windows Live Messenger. Если вы реализуете Федерацию аудио-и видеоданных (A/V) с помощью Windows Live Messenger, необходимо также изменить уровень шифрования сервера. По умолчанию уровень шифрования обязателен. Этот параметр необходимо изменить для поддержки с помощью командной консоли Lync Server.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров. Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo! Messenger до даты завершения работы службы. Дата окончания срока жизни 2014 для AOL и Yahoo! объявлено. Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</P>
> <LI>
> <P>УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo! Messenger. Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</P>
> <LI>
> <P>Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Взаимодействие клиентов в Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Поддержка клиентского программного обеспечения Lync в Lync Server 2013](lync-server-2013-lync-client-software-support.md)  
[Платформы, поддерживаемые в Lync Web App для Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
[Требования к приложению для Магазина Windows Lync для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  


[Требования к клиентской системе для Lync Server 2013](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

