---
title: 'Lync Server 2013: технические требования для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0d1b609f7e053823de68363059d7c8b35c0659
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533936"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Технические требования для архивации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Lync Server 2013 технические требования включают следующее:

  - требования к инфраструктуре;

  - необходимое программное обеспечение, которое должны быть установлены для архивации;

  - требования к хранилищу для архивации;

  - требования к масштабированию и рекомендации для развертывания архивации;

  - требования к производительности и рекомендации для баз данных архивации.

<div>


> [!NOTE]  
> Сведения о масштабировании и производительности недоступны в этом выпуске Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Требования к инфраструктуре

Требования к инфраструктуре архивации Lync Server 2013 такие же, как и для развертывания Lync Server 2013. Дополнительные сведения приведены в статье [Определение требований к инфраструктуре для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) в документации по планированию.

</div>

<div>

## <a name="archiving-prerequisites"></a>Необходимые компоненты для архивации

Lync Server 2013 оптимизирует предварительные требования для архивации из-за следующих условий:

  - Сервер архивации больше не является ролью сервера. Вместо этого агенты единой системы сбора данных выполняются на интерфейсных серверах в пуле и на серверах Standard Edition для захвата данных для архивации, поэтому вам не нужно настраивать отдельные платформы для архивации.

  - При архивации используется хранилище файлов Lync Server 2013 для временного хранения файлов контента собраний, поэтому не нужно настраивать отдельное хранилище файлов для архивации.

  - В Lync Server 2013 очередь сообщений не является обязательной.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Требования к хранилищу для архивации

Кроме того, необходимо настроить инфраструктуру для хранилища архивации. Для этого необходимо выполнить одно или оба следующих действия:

  - **Хранилище Microsoft Exchange**. Файлы содержимого собраний, например презентации PowerPoint, архивируются как вложения. Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных Lync с помощью данных соответствия требованиям Exchange, необходимо использовать Exchange 2013 для развертывания Exchange и гарантировать, что максимальный размер хранилища для файлов контента собраний поддерживается. Если вы развертываете архивацию с помощью параметра интеграции с Microsoft Exchange, архивные данные Lync хранятся только с данными соответствия требованиям Exchange 2013 для пользователей, размещенных на серверах Exchange 2013. Перед развертыванием и включением архивации с помощью функции интеграции с Microsoft Exchange необходимо развернуть Exchange 2013. Если вы решили использовать хранилище Exchange 2013, то нет необходимости развертывать отдельные базы данных SQL Server для архивации, если пользователи Lync не размещены на серверах Exchange 2013.

  - **Хранилище базы данных SQL Server для архивации**. Для поддержки пользователей, которые не размещены на серверах Exchange 2013, или если вы не хотите использовать интеграцию Microsoft Exchange, необходимо развернуть хранилище архивации с помощью базы данных SQL Server. Lync Server 2013 поддерживает следующие 64 — поразрядные версии SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 корпоративный
    
      - Microsoft SQL Server 2012 Стандартный
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express и Microsoft SQL Server 2012 Express не поддерживаются для архивации. 32 – разрядные версии SQL Server не поддерживаются. Дополнительные требования и ограничения SQL Server представлены в разделе <A href="lync-server-2013-database-software-support.md">Поддержка программного обеспечения баз данных в Lync Server 2013</A> в документации по планированию или в документации по поддержке.

    
    </div>
    
    Перед развертыванием и включением архивации необходимо настроить платформы SQL Server. Если у учетной записи, которая будет использоваться для публикации топологии, есть необходимые права и разрешения администратора, вы можете создать базу данных архивации (LcsLog) при публикации топологии. Вы также можете создать базу данных потом, например во время установки. Подробные сведения о SQL Server можно найти в техническом центре SQL Server по адресу [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

