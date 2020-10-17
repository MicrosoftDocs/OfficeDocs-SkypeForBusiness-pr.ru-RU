---
title: 'Lync Server 2013: восстановление хранилища файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd1984c6e51866b1ace707f305fb2a6cc356a132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511616"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>Восстановление хранилища файлов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-18_

Хранилища файлов для выпуска Standard Edition обычно размещаются на сервере Standard Edition. Хранилища файлов для Enterprise Edition обычно располагаются на файловом сервере или кластере. В следующей процедуре описывается, как восстановить хранилище файлов.

<div>

## <a name="to-restore-a-file-store"></a>Восстановление хранилища файлов

1.  В случае сбоя хранилища файлов скопируйте соответствующее хранилище файлов из $Backup \\ в расположение хранилища файлов на сервере или сервере Standard Edition, а затем предоставьте к ней общий доступ.
    
    <div>
    

    > [!IMPORTANT]  
    > Путь и имя файла для восстановленного хранилища файлов должны совпадать с хранилищем файлов в резервной копии, чтобы компоненты, использующие эти файлы, могли получать к ним доступ.

    
    </div>

2.  При необходимости задайте списки управления доступом (ACL) для хранилища файлов. В командной строке введите следующую команду.
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Этот шаг необходимо выполнить только в том случае, если вы не используете построитель топологий в процессе восстановления.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

