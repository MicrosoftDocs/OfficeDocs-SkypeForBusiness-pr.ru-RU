---
title: Перенос номеров доступа
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6654c084be4915d48c4148c90b3888295c887f08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Перенос номеров доступа

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

Для переноса номеров доступа с телефонным подключением необходимо выполнить два действия: Запуск командлета **Import-CsLegacyConfiguration** (завершенный ранее в разделе [Импорт политик и параметров](import-policies-and-settings.md)) для переноса абонентских группы и других параметров номеров доступа с телефонным подключением, а также выполнения командлета **Move-CsApplicationEndpoint** для переноса объектов Contact.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Чтобы мигрировать номера для телефонного подключения

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  В дереве консоли щелкните правой кнопкой мыши узел леса, щелкните **Свойства**, затем щелкните **Свойства помощника по конференц-связи**.

3.  На вкладке **Номера для телефонного подключения** щелкните **Обслуживается пулом** для упорядочивания номеров для телефонного подключения по соответствующим пулам и определите все номера для телефонного подключения в пуле, из которого будут перенесены эти номера.

4.  Чтобы определить SIP URI для каждого номера доступа, дважды щелкните номер доступа, чтобы открыть диалоговое окно **Изменить номер помощника конференц-связи**, просмотрите раздел **SIP URI**.

5.  Откройте командную консоль Lync Server.

6.  Для перемещения каждого номера доступа с телефонным подключением в пул, размещенный на Lync Server 2013, выполните команду:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  В средстве администрирования Office Communications Server 2007 R2 на вкладке **номера телефонов для доступа** убедитесь, что в пуле Office communications Server 2007 R2 отсутствуют номера доступа для телефонного подключения, из которого выполняется миграция.

</div>

</div>

<span> </span>

</div>

</div>

</div>

