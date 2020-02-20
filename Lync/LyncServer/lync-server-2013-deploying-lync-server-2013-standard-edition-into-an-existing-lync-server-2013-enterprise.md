---
title: 'Lync Server 2013: развертывание Lync Server 2013 Standard Edition в существующем сервере Lync Server 2013 Enterprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Развертывание Lync Server 2013 Standard Edition в существующем сервере Lync Server 2013 Enterprise

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Развертывание сервера Standard Edition в существующем развертывании Enterprise Edition аналогично развертыванию дополнительных ролей сервера. Сервер Standard Edition может быть развернут на другом сайте, что позволяет пользователям на этом сайте размещаться на сервере Standard Edition, а не на пуле переднего плана в глобальной сети (WAN). Процедуры установки нового сайта и серверов на этом сайте уже определены в других разделах документации по [развертыванию Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Определение нового сайта**

1.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.

2.  В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите **создать центральный сайт**.

3.  На странице **указания сайта** задайте имя для этого сайта и при желании введите описание.

4.  Выполните процедуры по определению остальной топологии сайта. Дополнительные сведения см [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Опубликуйте обновленную топологию. Дополнительные сведения см [в статье Publishing Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Установка и установка сервера Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Если вы развернули среду с сервером Standard Edition, процесс установки был начат в мастере развертывания Lync Server с помощью ссылки <STRONG>Подготовка первого сервера Standard</STRONG> Edition для установки исходных файлов базы данных на новый сервер Standard Edition. <STRONG>Не</STRONG> поддерживайте этот процесс при установке сервера Standard Edition в существующем развертывании Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

