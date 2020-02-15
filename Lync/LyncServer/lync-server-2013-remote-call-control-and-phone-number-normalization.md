---
title: 'Lync Server 2013: удаленное управление звонками и нормализация телефонных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-22_

Клиенты Lync загружают правила нормализации телефонных номеров в процессе загрузки файлов службы адресной книги (ABS). В сценариях удаленного управления звонками правила нормализации телефонных номеров службы адресной книги применяются к входящим и исходящим вызовам контроля допуска звонков. Для входящих вызовов пользователя с поддержкой контроля допуска звонков номер телефона вызывающего абонента сначала нормализуется в формате E.164 с помощью шлюза SIP/CSTA или УАТС. Когда Lync Server 2013 Получает вызов от шлюза, он выполняет обратный просмотр номера (RNL) на номере телефона абонента для нормализованного номера в списке контактов Microsoft Office Outlook или глобальном списке адресов (GAL), который хранится в Служба адресной книги. Если при обратном поиске номера успешно получено совпадение, вызывающий абонент идентифицируется по имени в уведомлении о входящем вызове.

Для исходящих звонков по удаленному управлению звонками Lync применяет правила нормализации номера телефона службы адресной книги к набранному номеру перед маршрутизацией вызова в шлюз SIP/CSTA.

Сведения о создании правил нормализации телефонных номеров для удаленного управления звонками приведены в документации по планированию для [абонентских планов и правил нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) .

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Перенос правил нормализации телефонных номеров

При переносе пользователей, для которых ранее было разрешено удаленное управление звонками, изучите следующие разделы документации по миграции:

  - В случае Lync Server 2010 вы найдете в статье Migration [Address Book (миграция адресной книги](migrate-address-book.md) ) в документации по миграции.

  - Сведения о Communications Server 2007 R2 приведены в статье [Миграция адресной книги](migrate-address-book_1.md) в документации по миграции.

</div>

</div>

<span> </span>

</div>

</div>

</div>

