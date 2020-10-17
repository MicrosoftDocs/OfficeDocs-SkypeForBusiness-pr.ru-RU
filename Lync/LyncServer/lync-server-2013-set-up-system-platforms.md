---
title: 'Lync Server 2013: Настройка системных платформ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bd5bff0b215060b1d352d5cc5798b114140c15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509786"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a>Настройка системных платформ в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Перед началом развертывания сервера сохраняемого чата необходимо установить требуемую операционную систему на оборудовании, удовлетворяющем требованиям к системе на серверах:

Сведения о поддерживаемом оборудовании для серверов, на которых работает Lync Server 2013, серверы баз данных и файловые серверы, приведены в статье Supported [Hardware for Lync server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке. Сведения о поддерживаемых операционных системах и программном обеспечении можно найти в статье поддержка [серверного программного обеспечения и инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) в документации по поддержке. Дополнительные сведения о требованиях по обновлению Windows приведены в статье дополнительные сведения о [поддержке серверов и требованиях в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) в документации по поддержке.

Сервер переднего плана сервера сохраняемого чата, **PersistentChatService**, можно развернуть на одном или нескольких изолированных компьютерах в пуле Lync Server 2013 Enterprise Edition. Они не могут быть размещены на серверах переднего плана Lync Server Enterprise Edition. Сервер сохраняемого чата может быть развернут загрузчиком так же, как и другие роли Lync Server. Веб-службы **сохраняемого чата для отправки и загрузки файлов**, а также **веб-службы сохраняемого чата для управления комнатами чата** — это веб-компоненты, развернутые на серверах переднего плана Lync Server 2013.

Один сервер переднего плана сервера сохраняемого чата может поддерживать 20 000 активных пользователей. Пул серверов сохраняемого чата может иметь до 4 активных интерфейсов, поддерживающих всего 80 000 одновременно работающих пользователей. Внутренний сервер сохраняемого чата, **PersistentChatStore**, хранит комнаты и категории чата. Рекомендуется установить **PersistentChatStore** на выделенном внутреннем сервере SQL Server в пуле Enterprise Edition; Несмотря на то, что мы поддерживаем совместное размещение внешних серверов Lync Server 2013 и **PersistentChatStore** в одном экземпляре SQL Server.

Если вашей организации требуется поддержка соответствия требованиям, ее можно установить с помощью построителя топологий. Служба соответствия сервера сохраняемого чата установлена на том же компьютере, что и сервер переднего плана сервера сохраняемого чата. Для совместимости требуется отдельная база данных. Сведения о требованиях соответствия требованиям для сервера сохраняемого чата приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.

Для каждой топологии требуется как минимум сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением баз данных SQL Server. Построитель топологий поддерживает несколько пулов серверов сохраняемого чата. Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и для любого пула развертывания [Lync server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

Вы также можете развернуть сервер сохраняемого чата в Lync Server 2013 Standard Edition. В этом случае сервер переднего плана **PersistentChatService** размещается на сервере Standard Edition, и вы можете развернуть внутренний сервер **PersistentChatStore** на локальном экземпляре SQL Server Express.

<div>


> [!IMPORTANT]  
> Мы не поддерживаем выпуск сервера сохраняемого чата &nbsp; Standard Edition для обеспечения высокой доступности. Производительность и масштабирование будут ограничены. Кроме того, поддерживаются только новые развертывания сервера Standard Edition для сервера persistent Chat &nbsp; . Мы не поддерживаем обновление Lync Server 2010, сервер группового чата до версии &nbsp; сервера сохраняемого чата для сервера Standard Chat для Lync server 2013 &nbsp; .



</div>

<div>

## <a name="see-also"></a>См. также


[Дополнительная поддержка и требования к серверу в Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Поддерживаемое оборудование для Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Планирование сервера сохраняемого чата в Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

