---
title: Экспорт топологии и ее копирование на внешние носители для установки в пограничной топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки в пограничной топологии

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-08_

После публикации топологии мастеру развертывания Lync Server требуется доступ к данным центрального хранилища, чтобы начать процесс развертывания на сервере. Во внутренней сети данные доступны непосредственно с серверов, но пограничные серверы, которые не входят в внутренний домен, не могут получить доступ к данным. Чтобы данные конфигурации топологии были доступны для развертывания пограничного сервера, необходимо экспортировать данные топологии в файл и скопировать его на внешний носитель (например, USB-накопитель или сетевую общую информацию, доступную с пограничного сервера) перед запуском среды выполнения Lync Server. Мастер лоймент на пограничном сервере. Выполните описанные ниже действия, чтобы сделать данные конфигурации топологии доступными на пограничном сервере, который вы развертываете.

<div>


> [!NOTE]
> После установки Lync Server 2013 на пограничном сервере вы можете управлять пограничным сервером с помощью средств администрирования внутренней сети, которые автоматически реплицируют конфигурацию на любые пограничные серверы в развертывании. Единственным исключением является назначение и установка сертификатов, остановка и запуск служб, которые должны быть выполнены на пограничном сервере.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Как сделать данные топологии доступными на пограничном сервере с помощью командной консоли Lync Server Management Shell

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  В командной консоли Lync Server выполните следующий командлет:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Скопируйте экспортированный файл на внешний носитель (например, USB-накопитель или сетевую общую сеть, доступную на пограничном сервере во время развертывания).

</div>

</div>

<span> </span>

</div>

</div>

</div>

