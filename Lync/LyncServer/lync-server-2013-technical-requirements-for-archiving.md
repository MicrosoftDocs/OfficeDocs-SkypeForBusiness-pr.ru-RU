---
title: 'Lync Server 2013: технические требования для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Технические требования для архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-09_

Технические требования для Lync Server 2013 включают следующее:

  - Требования к инфраструктуре.

  - Необходимое программное обеспечение, которое должно быть установлено для архивации.

  - Требования к хранилищу данных для архивации.

  - Требования и рекомендации по масштабированию для развертывания архивов.

  - Требования к производительности и рекомендации для баз данных архивации.

<div>


> [!NOTE]  
> Сведения о масштабировании и производительности недоступны в этом выпуске Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Требования к инфраструктуре

В Lync Server 2013 для хранения требований к инфраструктуре используется то же самое, что и для развертывания Lync Server 2013. Подробности можно найти в разделе [Определение требований инфраструктуры для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) в документации по планированию.

</div>

<div>

## <a name="archiving-prerequisites"></a>Предварительные требования для архивации

Lync Server 2013 оптимизирует предварительные требования для архивации из-за указанных ниже действий.

  - Сервер архивации больше не является ролью сервера. Вместо этого агенты Объединенного сбора данных выполняются на серверах переднего плана и серверах стандартных выпусков, чтобы захватывать данные для архивации, чтобы не настраивать отдельные системные платформы для архивации.

  - При архивации используется хранилище файлов Lync Server 2013 для временного хранения файлов содержимого собрания, поэтому вы не настраиваете отдельное хранилище файлов для архивации.

  - В Lync Server 2013 очередь сообщений не требуется.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Требования к хранилищу данных для архивации

Кроме того, необходимо настроить инфраструктуру хранения архивов. Сюда относятся один или оба следующих варианта:

  - **Хранилище Microsoft Exchange**. Meeting content files, such as PowerPoint presentations, are archived as attachments. Если вы хотите использовать интеграцию с Microsoft Exchange, чтобы данные архива Lync хранились с данными о соответствиях Exchange, необходимо использовать Exchange 2013 для развертывания Exchange и убедиться в том, что максимальный размер хранилища поддерживает хранение файлов содержимого собраний. Если вы разворачиваете архивацию с помощью параметра интеграции Microsoft Exchange, архивные данные Lync сохраняются с данными соответствия требованиям Exchange 2013 только для пользователей, которые размещены на серверах Exchange 2013. Перед развертыванием и включением архивации с помощью параметра интеграции Microsoft Exchange необходимо развернуть Exchange 2013. Если вы решили использовать хранилище Exchange 2013, вам не нужно развертывать отдельные базы данных SQL Server для архивации, если только у вас нет пользователей Lync на серверах Exchange 2013.

  - **Хранилище базы данных SQL Server для архивации**. Для поддержки пользователей, не использующих серверы Exchange 2013, или если вы не хотите использовать параметр интеграции Microsoft Exchange, необходимо развернуть хранилище архивации с помощью базы данных SQL Server. Lync Server 2013 поддерживает следующие 64-разрядные версии SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 корпоративный
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express и Microsoft SQL Server 2012 Express не поддерживают архивацию. 32-разрядные версии SQL Server не поддерживаются. Дополнительные требования и ограничения SQL Server можно найти в разделе <A href="lync-server-2013-database-software-support.md">Поддержка программного обеспечения баз данных в Lync Server 2013</A> в документации по планированию или в документации по поддержке.

    
    </div>
    
    Перед развертыванием и включением архивации необходимо настроить платформы SQL Server. Если учетная запись, которую планируется использовать для публикации топологии, имеет соответствующие права и разрешения администратора, базу данных архивации (LcsLog) можно создать при публикации топологии. Кроме того, вы можете создать базу данных позже, в том числе в ходе процедуры установки. Подробные сведения о SQL Server можно найти в центре SQL Server TechCenter [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)по адресу.

</div>

</div>

<span> </span>

</div>

</div>

</div>

