---
title: 'Lync Server 2013: Поддерживаемые гибридные конфигурации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b86720e64fdfd071bc5cacb21e4891e3e7758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Поддерживаемые гибридные конфигурации Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-05-10_

Вы можете настроить развертывание Lync Server 2013 для интеграции с Microsoft Exchange Server 2010 и Microsoft Exchange Server 2013 и SharePoint Server, как локально, так и в Интернете. Функции, приведенные в следующей таблице, поддерживаются всеми клиентами, если не указано иное. Дополнительные сведения о поддержке клиентов можно найти в таблице сравнение клиентов с таблицами сравнения клиентов для [Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) и Skype для бизнеса Online на клиентах [Skype для бизнеса Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В таблице ниже перечислены функции, которые поддерживаются в гибридном развертывании при интеграции с Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Локальное подключение к Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Локальный сервер Lync Server 2013</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-im-and-presence.md">в разделе сообщения и сведения о присутствии в Lync Server 2013</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p>
<p>Дополнительные сведения см. в разделе <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a>.</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">в разделе Настройка Microsoft Lync Server 2013 в разных локальных средах</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью веб-приложения Outlook OWA</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собраниям по сети в мобильных клиентах</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-deploying-mobility.md">в разделе Развертывание мобильных устройств на Lync Server 2013</a></p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Список контактов (из единого хранилища контактов)</p>
<p>Дополнительные сведения можно найти в разделе <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Настройка Microsoft Lync Server 2013 для работы с единым хранилищем контактов</a> .</p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.<BR>Требуется клиентское приложение Lync 2013 для настольных компьютеров.


</div></li>
<li><p>Фотография контакта с высоким разрешением в Lync 2013 Client и Lync Web App.</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">в разделе Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-deployment-checklist-for-archiving.md">в разделе Контрольный список развертывания для архивации в Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Поиск заархивированного содержимого</p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Голосовая почта</p>
<p>Дополнительные сведения можно найти в разделе <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">развертывание локальной системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в разделе Настройка интеграции локального сервера Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в OWA</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в разделе Настройка интеграции локального сервера Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование и присоединение к собранию по сети из Outlook Web App</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в разделе Настройка интеграции локального сервера Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Список контактов (из единого хранилища контактов). Дополнительные сведения можно найти в разделе <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Настройка Microsoft Lync Server 2013 для работы с единым хранилищем контактов</a> .</p>
<div>

> [!NOTE]  
> Только для Lync Server 2013. Требуется клиентское приложение Lync 2013 для настольных компьютеров.


</div></li>
<li><p>Фотография контакта с высоким разрешением в Lync 2013 Client и Lync Web App.</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">в разделе Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a>.</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange.</p>
<p>Дополнительные сведения можно найти <a href="lync-server-2013-deployment-checklist-for-archiving.md">в разделе Контрольный список развертывания для архивации в Lync Server 2013</a></p></li>
<li><p>Поиск архивных материалов. Дополнительные сведения можно найти в разделе <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Настройка Exchange для центра обнаружения электронных данных в SharePoint</a></p></li>
<li><p>Голосовая почта. Дополнительные сведения можно найти <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">в разделе Предоставление пользователям Lync Server 2013 голосовой почты в размещенной UM единой системе</a> обмена сообщениями</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Фотография контакта с высоким разрешением в клиенте Lync 2013.</p>
<div>

> [!NOTE]  
> Требуется Microsoft Exchange Server 2013. Это не поддерживается в Lync Web App, если пользователи находятся в Skype для бизнеса Online.


</div></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование собраний по сети и присоединение к ним с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p></li>
<li><p>Планирование и присоединение к собранию по сети из Outlook Web App</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния в соответствии со сведениями о доступности в календаре Outlook</p></li>
<li><p>История пропущенных бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Список контактов (из единого хранилища контактов)</p>
<div>

> [!NOTE]  
> Требуется клиент Lync Server 2013


</div></li>
<li><p>Фотография контакта с высоким разрешением в Lync 2013 Client и Lync Web App</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается, только когда оба пользователя размещены в одном лесу в сети или оба размещены локально.</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p></li>
<li><p>Поиск заархивированного содержимого</p></li>
<li><p>Голосовая почта</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В таблице ниже перечислены функции, которые поддерживаются в гибридной среде Lync Server 2013 при интеграции с SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Локальная среда SharePoint</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Локальный сервер Lync Server 2013</strong></p></td>
<td><ul>
<li><p>Поиск по навыкам</p></li>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Присутствие в SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

