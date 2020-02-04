---
title: Перенос номеров доступа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Перенос номеров доступа

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-26_

Для миграции номеров доступа с телефонным подключением необходимо выполнить два действия: Запуск командлета **Import-кслегациконфигуратион** (выполнен ранее в разделе [политики импорта и параметры](import-policies-and-settings.md)) для миграции абонентов и других параметров номеров доступа для телефонного подключения, а также выполнение командлета **Move-ксаппликатионендпоинт** для миграции объектов контакта.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Миграция номеров доступа для телефонного подключения

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  В дереве консоли щелкните правой кнопкой мыши узел леса, выберите пункт **Свойства**, а затем — **свойства участника Конференц**-связи.

3.  На вкладке **номера телефонов Access** выберите **обслуживание по пулам** , чтобы отсортировать номера телефонов Access по связанному пулу, и определите все номера доступа для пула, из которого выполняется миграция.

4.  Чтобы определить URI SIP для каждого номера доступа, дважды щелкните номер доступа, чтобы открыть диалоговое окно **изменить номер участника конференции** , и просмотрите раздел **URI SIP**.

5.  Откройте командную консоль Lync Server Management Shell.

6.  Чтобы переместить каждый номер доступа с телефонным подключением в пул, размещенный на Lync Server 2013, выполните команду:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  В средстве администрирования Office Communications Server 2007 R2 на вкладке **номера телефонов Access** убедитесь в том, что для пула Office Communications Server 2007 R2, из которого выполняется миграция, нет номеров доступа с телефонным подключением.

</div>

</div>

<span> </span>

</div>

</div>

</div>

