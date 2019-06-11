---
title: 'Lync Server 2013: восстановление содержимого конференций с помощью службы резервного копирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Если сведения о конференции, хранящиеся в хранилище файлов в пуле переднего плана, становятся недоступными. Эти данные необходимо восстановить таким образом, чтобы пользователи, расположенные в пуле, сохраняли свои данные на Конференции. Если пул переднего плана, который потерял данные конференции, связан с другим пулом переднего плана, вы можете восстановить данные с помощью службы резервного копирования.

Кроме того, вы должны выполнить эту задачу в случае сбоя всего пула, после чего вы должны переключиться между пользователями в резервный пул. Если эти пользователи не переносятся в исходный пул, необходимо выполнить описанные ниже действия, чтобы снова скопировать содержимое конференции в первоначальный пул.

Предположим, что Pool1 связан с Pool2, а данные конференции в Pool1 теряются. Вы можете использовать следующий командлет для вызова службы резервного копирования для восстановления содержимого:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Восстановление содержимого конференции может занять некоторое время в зависимости от его размера. Вы можете проверить состояние процесса с помощью следующего командлета:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Процесс выполняется, если этот командлет возвращает значение стабильного состояния для модуля конференции с данными.

</div>

<span> </span>

</div>

</div>

</div>

