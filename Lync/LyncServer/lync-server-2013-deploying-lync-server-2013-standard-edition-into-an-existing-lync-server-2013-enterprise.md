---
title: 'Lync Server 2013: Развертывание Lync Server 2013 Standard Edition на базе существующего развертывания Lync Server 2013 Enterprise'
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
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758023"
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

1.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.

2.  В дереве консоли щелкните правой кнопкой мыши **Lync Server 2013**и выберите пункт **создать центральный сайт**.

3.  На странице **Определение сайта** укажите имя сайта и, при необходимости, введите описание.

4.  Следуйте инструкциям по определению оставшейся части топологии сайта. Подробные сведения можно найти [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Опубликуйте обновленную топологию. Подробности можно найти [в разделе Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Настройка и установка сервера Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Если вы развернули среду только на стандартном сервере выпуска, вы могли бы приступили к установке из мастера развертывания Lync Server, используя ссылку <STRONG>Prepare First Standard Edition</STRONG> , чтобы установить начальные файлы базы данных на новый сервер Standard Edition. <STRONG>Не</STRONG> поддерживайте этот процесс при установке стандартного выпуска сервера в существующем развертывании Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

