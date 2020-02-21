---
title: 'Lync Server 2013: Поддерживаемые гибридные конфигурации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34a73d343375f53acf7f1b7383efb05dd63b9a64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Поддерживаемые гибридные конфигурации Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-05-10_

Вы можете настроить развертывание Lync Server 2013 для интеграции с Microsoft Exchange Server 2010 и Microsoft Exchange Server 2013 и SharePoint Server, как в локальной среде, так и в сети. Функции, перечисленные в следующей таблице, поддерживаются для всех клиентов, если не указано иное. Дополнительные сведения о поддержке клиентов приведены в [таблицах сравнения клиентов для таблиц сравнения клиентов Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) и Skype для бизнеса Online на клиентах [Skype для бизнеса Online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Интеграция с Exchange Server

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании при интеграции с Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Локальная среда Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 в локальной среде</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-im-and-presence.md">в статье обмен мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</a></p></li>
<li><p>Планирование и присоединение к собраниям по сети с помощью Outlook</p>
<p>Дополнительные сведения см в <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">статье интеграция Microsoft Lync server 2013 и Microsoft Exchange server 2013</a></p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p>
<p>Дополнительные сведения см в разделе <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Настройка Microsoft Lync Server 2013 в</a> распределенной среде</p></li>
<li><p>Планирование и присоединение к собраниям по сети с помощью Outlook Web App</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собраниям по сети в мобильных клиентах</p>
<p>Дополнительные сведения см в статье <a href="lync-server-2013-deploying-mobility.md">deploy Mobility in Lync Server 2013</a></p></li>
<li><p>Публикация состояния на основе сведений о доступности в календаре Outlook</p></li>
<li><p>Список контактов (через единое хранилище контактов)</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">в статье Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов</a></p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.<BR>Необходимо указать клиент Lync 2013 для настольных ПК.


</div></li>
<li><p>Фото контакта с высоким разрешением в клиенте Lync 2013 и Lync Web App.</p>
<p>Дополнительные сведения см в разделе <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается только в том случае, если оба пользователя размещены в сети в одном лесу или оба размещены в локальной среде.</p></li>
<li><p>Журнал бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-deployment-checklist-for-archiving.md">в разделе Контрольный список развертывания для архивации в Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Поиск в архивном контенте</p>
<div>

> [!NOTE]  
> Требуется Exchange 2013.


</div></li>
<li><p>Голосовая почта</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">в статье Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в статье Настройка локальной интеграции Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование и присоединение к собранию по сети через Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в OWA</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в статье Настройка локальной интеграции Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Планирование и присоединение к собранию по сети из Outlook Web App</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">в статье Настройка локальной интеграции Lync Server 2013 с Exchange Online</a></p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния на основе сведений о доступности в календаре Outlook</p></li>
<li><p>Список контактов (через единое хранилище контактов). Дополнительные сведения см. <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">в статье Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов</a></p>
<div>

> [!NOTE]  
> Только Lync Server 2013. Необходимо указать клиент Lync 2013 для настольных ПК.


</div></li>
<li><p>Фото контакта с высоким разрешением в клиенте Lync 2013 и Lync Web App.</p>
<p>Дополнительные сведения см в разделе <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</a>.</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается только в том случае, если оба пользователя размещены в сети в одном лесу или оба размещены в локальной среде.</p></li>
<li><p>Журнал бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange.</p>
<p>Дополнительные сведения см. <a href="lync-server-2013-deployment-checklist-for-archiving.md">в разделе Контрольный список развертывания для архивации в Lync Server 2013</a></p></li>
<li><p>Поиск архивированного контента. Дополнительные сведения см в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Настройка Exchange для обнаружения электронных данных SharePoint</a></p></li>
<li><p>Голосовая почта. Дополнительные сведения приведены в статье <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование и присоединение к собраниям по сети с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Журнал бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Фото контакта с высоким разрешением в клиенте Lync 2013.</p>
<div>

> [!NOTE]  
> Требуется Microsoft Exchange Server 2013. Эта возможность не поддерживается в Lync Web App, когда пользователи размещены в Skype для бизнеса Online.


</div></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния на основе сведений о доступности в календаре Outlook</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается только в том случае, если оба пользователя размещены в сети в одном лесу или оба размещены в локальной среде.</p></li>
</ul></td>
<td><ul>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook</p></li>
<li><p>Планирование и присоединение к собраниям по сети с помощью Outlook</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в Outlook Web App</p></li>
<li><p>Планирование и присоединение к собранию по сети из Outlook Web App</p></li>
<li><p>Обмен мгновенными сообщениями и присутствие в мобильных клиентах</p></li>
<li><p>Присоединение к собранию по сети в мобильных клиентах</p></li>
<li><p>Публикация состояния на основе сведений о доступности в календаре Outlook</p></li>
<li><p>Журнал бесед и журналы звонков записываются в почтовый ящик Exchange пользователя</p></li>
<li><p>Список контактов (через единое хранилище контактов)</p>
<div>

> [!NOTE]  
> Клиент Lync Server 2013 обязателен


</div></li>
<li><p>Фото контакта с высоким разрешением в клиенте Lync 2013 и Lync Web App</p></li>
<li><p>Делегирование собрания</p>
<p>Поддерживается только в том случае, если оба пользователя размещены в сети в одном лесу или оба размещены в локальной среде.</p></li>
<li><p>Архивация содержимого (мгновенных сообщений и собраний) в Exchange</p></li>
<li><p>Поиск в архивном контенте</p></li>
<li><p>Голосовая почта</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Интеграция с SharePoint

В следующей таблице перечислены функции, поддерживаемые в гибридном развертывании Lync Server 2013 при интеграции с SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Локальное развертывание SharePoint</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 в локальной среде</strong></p></td>
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

