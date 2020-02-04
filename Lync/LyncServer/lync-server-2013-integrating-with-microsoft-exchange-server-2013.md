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
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Интеграция Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-07-09_

В Exchange и Lync Server есть продолжительная история интеграции и совместимости. Эта интеграция особенно заметна в соответствующем клиентском приложении. Например, информацию о присутствии Lync можно сообщить в Microsoft Outlook; Аналогичным образом Lync может автоматически обновлять сведения о присутствии с помощью календаря Outlook. (Например, Lync может изменить свое состояние на "занят" в любое время, когда в календаре отображается запланированное собрание.) Несмотря на то, что вам не нужно запускать Exchange для работы с Lync Server (или наоборот), у вас есть сомнения в том, что использование двух продуктов вместе епитомизес в определении термина "лучше вместе".

Это особенно актуально при выпуске Microsoft Lync Server 2013 и Microsoft Exchange Server 2013. Помимо функций, таких как единая система обмена сообщениями и обмен сообщениями и присутствие, которые находятся в Microsoft Exchange Server 2010 и Microsoft Lync Server 2010, выпуски 2013 из серверных продуктов включают ряд новых возможностей. Эти возможности включают в себя следующие моменты:

  - **Интеграция с архивацией Lync**. В Lync Server 2013 администраторы по-прежнему могут получать мгновенные сообщения и записи для веб-конференций, архивированные в SQL Server (аналогично тому, как они были архивированы в Lync Server 2010). Кроме того, администраторы могут выбрать, что вы заархивированы в Exchange 2013, сохранив эти записи в почтовых ящиках отдельных пользователей точно так же, как и при обмене сообщениями в архиве Exchange. Это означает единое хранилище для всех электронных коммуникаций (из Exchange и Lync Server), что значительно упрощает поиск и получение архивных данных, которые могут возникнуть.

  - **Единое хранилище контактов**. В Lync Server 2010 пользователям пришлось поддерживать отдельные списки контактов в Outlook и Lync; на самом деле, чтобы убедиться в том, что у вас есть одинаковые контакты в обоих продуктах, вы должны поддерживать дубликаты списков контактов, для Outlook и для Lync. Однако при использовании Lync Server 2013 контакты пользователей могут храниться в Exchange 2013 и едином банке контактов. С помощью одного магазина контактов пользователи смогут поддерживать только один набор контактов, с тем же набором контактов, который доступен в Lync 2013, Outlook 2013 и Outlook Web Access 2013.

  - **Планирование собраний Lync из Outlook Web**App. С помощью Lync Server 2013 и Exchange 2013 интеграция пользователи могут планировать собрания Lync из Outlook Web Access 2013.

  - **Фотографии высокого разрешения**. Lync 2010 может показывать только небольшие фотографии контактов; Это объясняется тем, что эти фотографии хранились в службе каталогов Active Directory, а служба каталогов Active Directory накладывает на 48 точку 48 с ограничением размера в пикселях для сохраненных фотографий. Однако в Lync Server 2013 фотографии могут храниться в Microsoft Exchange; Это позволяет создавать фотографии высокого разрешения размером в 648 пикселей на 648 пикселей. Как вы можете ожидать, Lync 2013 был обновлен таким образом, чтобы иметь возможность отображать фотографии высокого разрешения.

Имейте в виду, что для этих новых функций требуется использование как Lync Server 2013, так и Exchange 2013. Кроме того, пользователи, которые хотят воспользоваться всеми преимуществами этих новых возможностей, должны иметь учетные записи на Lync Server 2013 и Exchange 2013 и должны использовать последние версии клиентского программного обеспечения (например, Lync 2013). Например, единое хранилище контактов недоступно для пользователей, которые были размещены на сервере Lync Server 2010; Кроме того, в Lync 2010 не отображаются фотографии высокого разрешения.

В этой документации содержатся сведения о том, как интегрировать Lync Server 2013 и Exchange 2013. включая пошаговые инструкции по включению новых функций, таких как интеграция архивирования и единое хранилище контактов. Это не относится к рассмотрению первоначальной настройки и конфигурации этих двух продуктов. Подробнее о том, как развертывать Lync Server 2013, можно найти в разделе [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)lync Server 2013 Tech Center по адресу. Подробнее о том, как развертывать Exchange 2013, можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)центре Exchange 2013 Tech Center по адресу.

<div>

## <a name="in-this-section"></a>Содержание

[Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Настройка Microsoft Lync Server 2013 для использования архивации Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Настройка Microsoft Lync Server 2013 для работы с единым хранилищем контактов](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Microsoft Lync Server 2013 для голосовой почты](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

