---
title: 'Lync Server 2013: восстановление содержимого конференций с помощью службы резервного копирования'
description: 'Lync Server 2013: восстановление содержимого конференций с помощью службы резервного копирования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a0037af711948c008e74c5444373ed995f0e6e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555185"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Если сведения о конференциях, содержащиеся в хранилище файлов на интерфейсном пуле, становятся недоступными, необходимо восстановить эти сведения, чтобы пользователи, размещенные в пуле, сохранили свои данные конференций. Если интерфейсный пул, утративший данные конференций, объединен в пару с другим интерфейсным пулом, можно использовать службу резервного копирования для восстановления данных.

Необходимо также выполнить эту задачу, если вследствие сбоя не работает весь пул и необходимо перенести его пользователей в резервный пул. При восстановлении пользователей в исходном пуле необходимо использовать эту процедуру для копирования контента конференций обратно в исходный пул.

Предположим, что пул1 объединен с пулом2, а данные конференций в пуле1 утрачены. Можно использовать следующий командлет для вызова службы резервного копирования для восстановления содержимого:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Восстановление содержимого конференций может занять некоторое время в зависимости от размера. Можно использовать приведенный ниже командлет для проверки состояния процесса:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Процесс завершается, когда этот командлет возвращает значение Steady State для данных в модуле конференций.

</div>

<span> </span>

</div>

</div>

</div>

