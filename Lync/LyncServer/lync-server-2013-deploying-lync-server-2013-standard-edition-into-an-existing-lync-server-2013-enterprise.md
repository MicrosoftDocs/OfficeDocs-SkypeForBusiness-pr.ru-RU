---
title: 'Lync Server 2013: Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Развертывание стандартного выпуска сервера в существующем развертывании Enterprise Edition похоже на развертывание дополнительных ролей сервера. Сервер Standard Edition может быть развернут на другом сайте, что позволяет пользователям на нем работать на сервере Standard Edition, а не в пуле переднего плана в глобальной сети. Процедуры для установки нового сайта и серверов на этом сайте уже определены в других разделах документации по [развертыванию Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Определение нового сайта**

1.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.

2.  В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите пункт **создать центральный сайт**.

3.  На странице **Определение сайта** укажите имя сайта и, при необходимости, введите описание.

4.  Следуйте инструкциям по определению оставшейся части топологии сайта. Подробные сведения можно найти [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Опубликуйте обновленную топологию. Подробности можно найти [в разделе Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Настройка и установка сервера Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Если вы развернули среду только на стандартном сервере выпуска, вы начали процесс настройки из мастера развертывания Lync Server с помощью ссылки " <STRONG>подготовить первый выпуск Standard Edition</STRONG> " для установки исходных файлов базы данных в новый. Сервер Standard Edition. <STRONG>Не</STRONG> поддерживайте этот процесс при установке стандартного выпуска сервера в существующем развертывании Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

