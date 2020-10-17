---
title: Экспорт топологии и ее копирование на внешние носители для установки в пограничной топологии
description: Экспортируйте топологию и скопируйте ее на внешние носители для установки пограничного сервера.
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
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564765"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

После публикации топологии мастеру развертывания Lync Server требуется доступ к данным центрального хранилища управления, чтобы начать процесс развертывания на сервере. Во внутренней сети данные доступны непосредственно с серверов, однако пограничные серверы за пределами внутреннего домена не могут получить доступ к этим данным. Чтобы сделать данные конфигурации топологии доступными для развертывания пограничного сервера, необходимо экспортировать данные топологии в файл и скопировать его на внешний носитель (например, USB-диск или сетевую папку, доступную с пограничного сервера) перед запуском мастера развертывания Lync Server на пограничном сервере. Используйте следующую процедуру, чтобы сделать ваши данные о конфигурации топологии доступными развертываемому пограничному серверу.

<div>


> [!NOTE]
> После установки Lync Server 2013 на пограничном сервере управление пограничным сервером осуществляется с помощью средств администрирования внутренней сети, которые автоматически реплицируют конфигурацию на пограничные серверы в развертывании. Единственным исключением является назначение и установка сертификатов и остановка и запуск служб — обе эти операции необходимо выполнять на пограничном сервере.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Обеспечение доступа к данным о топологии на пограничном сервере с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  В командной консоли Lync Server выполните следующий командлет:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Скопируйте экспортированный файл на внешний носитель (например, USB-диск или в сетевую общую папку, доступную с пограничного сервера во время развертывания).

</div>

</div>

<span> </span>

</div>

</div>

</div>

