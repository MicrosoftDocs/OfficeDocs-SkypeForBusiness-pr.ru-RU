---
title: 'Lync Server 2013: выполнение искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Выполнение виртуальных транзакций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-08-18_

Синтетические транзакции обычно выполняются двумя способами. Вы можете использовать командлеты Кшеалсмониторингконфигуратион, чтобы настроить пользователей для каждого из своих пулов регистраторов. Эти тестовые пользователи — это пары пользователей, которые были предварительно настроены для использования с искусственными транзакциями. (Как правило, они являются тестовыми учетными записями, а не учетными записями, принадлежащими реальным пользователям.) При использовании тестовых пользователей, настроенных для пула, вы можете выполнить искусственную транзакцию для этого пула, не задавая удостоверения (и учетные данные для) учетных записей пользователей, участвующих в тестировании.

Вы также можете выполнить искусственную транзакцию с помощью реальных учетных записей пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, вы можете выполнить искусственную транзакцию с помощью этих двух учетных записей пользователей (а не для пары тестовых учетных записей), а затем попробовать диагностировать и устранить проблему. Если вы решите провести искусственную транзакцию с использованием фактических учетных записей пользователей, необходимо указать имена для входа и пароли для каждого пользователя.

<div>

## <a name="see-also"></a>См. также


[Настройка пользователей и параметров конфигурации для проверки узла-наблюдателя в Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Специальные инструкции по настройке для виртуальных транзакций в Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

