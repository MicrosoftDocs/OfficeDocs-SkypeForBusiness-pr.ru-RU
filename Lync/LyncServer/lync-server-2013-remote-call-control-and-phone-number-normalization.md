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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-22_

Клиенты Lync загружают правила нормализации номера телефона в рамках скачивания файла службы адресной книги (ABS). В сценариях удаленного управления звонками правила нормализации номера телефонной книги применяются к входящим и исходящим звонкам удаленного управления звонками. Для входящих звонков с удаленным пользователем, поддерживающим управление звонками, номер телефона, используемый для вызывающего абонента, сначала нормализован на формат E. 164 либо с помощью шлюза SIP/КСТА, либо из частной сети обмена филиалами (УАТС). Когда Lync Server 2013 получает звонок от шлюза, он выполняет обратный просмотр номера (РНЛ) на номере телефона вызывающего абонента со стандартным номером в списке контактов Microsoft Office Outlook или глобальном списке адресов (GAL), который хранится в Служба адресной книги. Если обратный поиск номеров успешно находит совпадение, вызывающий объект определяется по имени в уведомлении о входящем звонке.

Для исходящих вызовов удаленного управления звонками Lync применяет правила нормализации номера телефона службы адресной книги к набору номера перед тем, как перенаправить звонок на шлюз SIP/КСТА.

Дополнительные сведения о создании правил нормализации номера телефона для удаленного управления звонками можно найти [в разделе планы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) в документации по планированию.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Миграция правил нормализации номера телефона

Если вы переносите пользователей, для которых уже разрешено удаленное управление звонками, ознакомьтесь со следующими разделами в документации по миграции.

  - Для Lync Server 2010 — в разделе [Миграция адресной книги](migrate-address-book.md) в документации по миграции.

  - Сервер Communications Server 2007 R2 можно найти в разделе [Миграция адресной книги](migrate-address-book_1.md) в документации по миграции.

</div>

</div>

<span> </span>

</div>

</div>

</div>

