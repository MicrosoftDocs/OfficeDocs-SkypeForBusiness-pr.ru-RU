---
title: 'Lync Server 2013: интеграция с Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dccf60dba1b729b1ffa808694fffcacc14e460ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Интеграция Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-07-09_

Exchange и Lync Server имеют длительную историю интеграции и совместимости. Эта интеграция наиболее заметна в соответствующем клиентском приложении. Например, сведения о присутствии Lync можно указать в Microsoft Outlook; Аналогично, Lync может использовать календарь Outlook для автоматического обновления сведений о присутствии. (Например, Lync может изменить свое состояние на "занято" в любое время, когда в календаре отображается запланированное собрание.) Несмотря на то, что для работы с Lync Server (или наоборот) не требуется запускать Exchange, существует небольшое мнение о том, что использование двух продуктов совместно епитомизес очень важное значение термина "более эффективная совместная работа".

Это особенно относится к выпуску Microsoft Lync Server 2013 и Microsoft Exchange Server 2013. Помимо функций, таких как единая система обмена сообщениями и обмен мгновенными сообщениями и сведениями о присутствии, которые находятся в Microsoft Exchange Server 2010 и Microsoft Lync Server 2010, выпуски серверных продуктов с 2013 для имеют ряд новых возможностей. Эти возможности включают в себя следующие моменты:

  - **Интеграция архивации Lync**. В Lync Server 2013 администраторы по-прежнему имеют возможность сохранять записи о мгновенных сообщениях и веб-конференциях в SQL Server (аналогично тому, как эти записи были архивированы в Lync Server 2010). Кроме того, администраторы могут использовать записи архивов в Exchange 2013, сохраняя эти записи в почтовых ящиках отдельных пользователей точно так же, как и для обмена сообщениями в архиве Exchange. Это означает, что вы можете использовать один репозиторий для всех электронных коммуникаций (от Exchange и Lync Server), что значительно упрощает поиск и извлечение таких архивных данных, которые должны возникать.

  - **Единое хранилище контактов**. В Lync Server 2010 пользователям приходится поддерживать отдельные списки контактов в Outlook и Lync; на самом деле, чтобы обеспечить наличие одних и тех же контактов в обоих продуктах, для которых необходимо поддерживать повторяющиеся списки контактов, один для Outlook и один для Lync. Однако при использовании Lync Server 2013 контакты пользователей могут храниться в Exchange 2013 и в едином хранилище контактов. Использование одного хранилища контактов позволяет пользователям хранить только один набор контактов с тем же набором контактов, который доступен в Lync 2013, Outlook 2013 и Outlook Web Access 2013.

  - **Планирование собраний Lync из OWA**. С помощью Lync Server 2013 и интеграции с Exchange 2013 пользователи могут планировать собрания Lync из Outlook Web Access 2013.

  - **Фотографии с высоким разрешением**. Lync 2010 может отображать только небольшие фотографии контактов. Это вызвано тем, что эти фотографии хранились в Active Directory, а Active Directory накладывает ограничение размера 48 на 48 пикселя для сохраненных фотографий. Тем не менее, в Lync Server 2013 фотографии могут храниться в Microsoft Exchange. Это позволяет использовать фотографии высокого разрешения в размере 648 x 648 пикселей. Как можно было ожидать, Lync 2013 был обновлен, чтобы иметь возможность отображать фотографии с высоким разрешением.

Помните, что для этих новых функций требуется использование Lync Server 2013 и Exchange 2013. Кроме того, пользователи, которые пожелают использовать все преимущества этих новых возможностей, должны иметь учетные записи на Lync Server 2013 и Exchange 2013, а также должны использовать последние версии клиентского программного обеспечения (например, Lync 2013). Например, единое хранилище контактов недоступно для пользователей, размещенных в Lync Server 2010; Аналогично, фотографии с высоким разрешением не могут отображаться в Lync 2010.

В этой документации представлены сведения о интеграции Lync Server 2013 и Exchange 2013. включает пошаговые инструкции по включению новых функций, таких как интеграция архивации и единое хранилище контактов. В этой документации не рассматриваются первоначальная установка и настройка этих двух продуктов. Дополнительные сведения о развертывании Lync Server 2013 см. в статье Lync Server 2013 [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)Tech Center по адресу. Для получения дополнительных сведений о развертывании Exchange 2013 посетите центр технической поддержки [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)Exchange 2013 по адресу.

<div>

## <a name="in-this-section"></a>Содержание

[Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Настройка Microsoft Lync Server 2013 для использования архивации Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Настройка Microsoft SharePoint Server 2013 для поиска архивных данных Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

