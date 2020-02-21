---
title: 'Lync Server 2013: взаимодействие клиентов в Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 437051279393b9dedc7c4def0c75cd119cded914
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Взаимодействие клиентов в Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-03-04_

В этом разделе рассказывается о возможности совместного использования клиентами Microsoft Lync Server 2013 и взаимодействии с клиентами из более ранних версий Lync Server и Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Совместимость серверов и клиентов

В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов. В этой таблице показано, поддерживается ли вход, когда клиент пытается подключиться к указанному серверу. Lync Server 2013 поддерживает предыдущую версию клиента. Кроме того, в отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013. Это позволяет организациям, которые обновляются с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Supported5</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Group Chat</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Неприменимо</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Не Supported3</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Помощник Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Приложение Lync для Магазина Windows</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
</tbody>
</table>


1For Details: [Migration from Lync server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat to Lync server 2013, сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, доступны функции группового чата с сервером группового чата, доверенным сторонним приложением для Lync Server 2010. Клиенты Lync 2013 несовместимы с Lync Server 2010, группового чата.

3Lync Web App 2013 теперь предоставляет полный интерфейс для собраний, включая аудио-и видеоданные, и считается заменой участнику Lync 2010. Lync 2010 участник будет подключаться к Lync Server 2013 только при использовании неподдерживаемого браузера (Internet Explorer 6 или Internet Explorer 7) и Windows XP.

4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются. Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.

5 для получения ограничений обратитесь к разделу "Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний" Далее в этом разделе.

</div>

<div>

## <a name="interoperability-among-clients"></a>Взаимодействие между клиентами

В выпуске Lync Server 2013 различные клиентские версии могут беспрепятственно взаимодействовать как в одноранговых, так и в сценариях конференц-связи. В этом разделе описывается доступность функций, когда пользователи взаимодействуют с другими пользователями, использующими разные версии клиентов и серверов.

<div>

## <a name="peer-to-peer-feature-support"></a>Поддержка одноранговых функций

Одноранговые функции поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные версии клиентов. Функции конечного пользователя и доступные функции соответствуют возможностям клиента пользователя и версии сервера, на котором выполнен вход пользователя. Другими словами:

  - Если пользователь вошел в Lync Server 2013 с более старым клиентом, он будет иметь такой же интерфейс, что и для пользователя. Никакие новые функции, введенные в Lync Server 2013, будут недоступны до тех пор, пока клиент пользователя не будет обновлен. Примеры включают представление "Коллекция видео", видео в формате HD, обновленный общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания. Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Если пользователь вошел в Lync Server 2010 с клиентом Lync 2013, все новые функции, не поддерживаемые в Lync Server 2010, будут недоступны до тех пор, пока пользователь не будет перемещен в Lync Server 2013.

В следующей таблице сравнивается доступность функций в одноранговых сеансах, где клиент входит в состав Lync Server 2013 или Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App и Lync 2010 участник являются клиентами только для собраний и не включены в эту таблицу.



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Обмен мгновенными сообщениями</th>
<th>Присутствие</th>
<th>Голос</th>
<th>Видео</th>
<th>Совместное использование приложений</th>
<th>Передача файлов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Yes1</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Общедоступная служба обмена мгновенными сообщениями (AOL, Yahoo!)</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Общедоступная служба обмена мгновенными сообщениями (MSN, Windows Live Messenger)</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров. Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo! Messenger до даты завершения работы службы. Дата окончания срока жизни 2014 для AOL и Yahoo! объявлено. Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>..</P>
> <LI>
> <P>УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo! Messenger. Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</P>
> <LI>
> <P>Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL. В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</P></LI></UL>



</div>

1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).

<div>


> [!NOTE]  
> Общий доступ к рабочему столу Office Communicator 2007 R2 и Skype для бизнеса 2015 невозможно инициировать из нового клиента, когда применяется пользовательский интерфейс клиента Skype для бизнеса 2015.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Поддержка функций конференц-связи для клиентов Lync 2013 в Lync Server 2010 для собраний

Когда пользователи присоединяются к Lync Server 2010 meetings с клиентом Lync 2013, у них есть доступ к клиентским функциям Lync 2013 со следующими исключениями:

  - В параметрах управления **участниками** , доступ к которым осуществляется путем указания значка "люди" в окне собрания, параметр "не вести **мгновенный обмен мгновенными сообщениями** " не работает.

  - Представление галереи не работает в видеоконференциях. Пользователю развидится только активный динамик, а не все динамики. В списке выберите параметры **макета** недоступно **представление "коллекция** "

  - Список участников по умолчанию отображается в видеоконференциях.

  - Когда вы щелкаете правой кнопкой мыши пользователя в списке участников, вы не сможете получить доступ к параметрам управления участниками **коллекции и закрепить** **его** в коллекции.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Поддержка функций конференц-связи в Lync Server 2013 meetings

Lync Server 2013 предоставляет новые функции конференц-связи, которые становятся доступными пользователям после перемещения их учетных записей в Lync Server 2013 и входе в систему с помощью клиента Lync 2013. К примерам относится представление "Коллекция видео", видео высокой четкости, общий доступ к PowerPoint и возможность отключения звука и видео участников при вводе собрания. Новые возможности, описанные в разделе [новые функции конференц-связи в Lync server 2013](lync-server-2013-new-conferencing-features.md) , а также новые возможности [для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

В Lync Server 2013 для собраний некоторые функции конференций поддерживаются для пользователей, размещенных в различных версиях сервера и использующих разные клиенты и клиентские версии. Когда клиенты присоединяются к собранию Lync Server 2013, у пользователей есть доступ к функциям и функциям, представленным в этой таблице.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Обмен мгновенными сообщениями в одноранговой сети</th>
<th>Голос</th>
<th>Видео</th>
<th>Совместное использование приложений</th>
<th>PowerPoint</th>
<th>Передача файлов</th>
<th>Доска</th>
<th>Опрос</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да2</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Yes3</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Да</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 в Office Communicator 2007 R2 доступен только общий доступ к рабочему столу (а не к совместному использованию программ).

2 Lync Server 2013 использует обновленный механизм для отправки файлов PowerPoint. Пользователи Lync Web App, присоединяющиеся к собранию, изначально запланированному на Lync Server 2010, могут просматривать презентации PowerPoint и перемещаться по ним, но не могут отправлять файлы PowerPoint.

3 Если собрание было запланировано на Lync Server 2013, а слайды PowerPoint были отправлены клиентом Lync 2013, пользователи Lync 2010 имеют доступ к слайдам только для просмотра. И наоборот, если слайды PowerPoint были отправлены пользователем Lync 2010, пользователи Lync Server 2013 смогут просматривать и просматривать слайды и, если сервер Office Web Apps настроен, получать доступ к новым возможностям, таким как более высокое разрешение, анимацию, переходы слайдов и внедренный видеоролик. Дополнительную информацию можно узнать в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются. Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Планирование поддержки надстроек

Серверная поддержка различных надстроек планирования согласуется с совместимостью версий сервера и клиентов. Как правило, в Lync Server 2013 поддерживаются следующие надстройки планирования. Однако предыдущие версии надстроек не предоставляют новые функции надстройки Lync 2013, такие как возможность отключения всех звуков и видео участников при вводе собрания.

  - **Надстройка "собрание по сети" для Lync 2013**   предоставляет те же функции, что и надстройка "собрание по сети" для Lync 2010 с добавлением элементов управления для участников собрания, которые позволяют организаторов по умолчанию планировать конференции, для которых по умолчанию отключен звук участника и видео. Кроме того, администраторы могут настроить приглашения на собрание Организации, добавив настраиваемую эмблему, URL-адрес, юридический URL-адрес или текст нижнего колонтитула.

  - **Надстройка "собрание по сети" для Lync 2010**   предоставляет планирование для собраний Lync и удаляет возможность планирования конференций Office Live Meeting.

  - **Надстройка конференц-связи Office Communicator 2007 R2**   предоставляет планирование для конференций Office Live Meeting и конференций Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> В Lync Server 2013 невозможно планировать конференции Live Meeting.



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
<th>Планирование клиента</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Надстройка "собрание по сети" для Lync 2013 (может использоваться с Office 2013, Outlook 2010 и Outlook 2007)</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается (новые функции надстроек недоступны)</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Веб-планировщик Lync 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Надстройка "собрание по сети" для Lync 2010</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Надстройка конференц-связи Office Communicator 2007 R2</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Поддержка присоединения к собраниям

Все клиенты, поддерживаемые Lync Server 2013, могут присоединяться к собраниям Lync 2013. Так как Lync Web App является веб-компонентом сервера, то в тех случаях, когда Lync Web App используется для присоединения к собранию Lync Server 2013, всегда используется более новая версия Lync Web App.

Пользователи Lync 2013 могут присоединяться к собраниям, размещенным на Lync 2010 и Office Communications Server 2007 R2, с возможностью масштабирования. Функции для собраний ограничены версией сервера, на котором размещается собрание.

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к приложению для Магазина Windows Lync для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Новые возможности конференц-связи в Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Новые возможности для клиентов в Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

