---
title: 'Lync Server 2013: проверка репликации схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 483a8125969fffc0db2c8f72bca3fc5b8001d943
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527626"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Проверка репликации схемы Active Directory в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-29_

Прежде чем перейти к подготовке леса, вручную проверьте, был ли реплицирован раздел схемы.

<div>

## <a name="to-manually-verify-schema-replication"></a>Проверка репликации схемы вручную

1.  Выполните вход на контроллер домена с учетной записью члена группы "Администраторы предприятия".

2.  Чтобы открыть редактор ADSI, нажмите кнопку **Пуск**, выберите **Администрирование** и затем выберите **Редактирование ADSI**.
    
    <div>
    

    > [!TIP]  
    > Для открытия редактора также можно запустить оснастку <STRONG>adsiedit.msc</STRONG> в командной строке.

    
    </div>

3.  В дереве консоли управления (MMC) выберите **Редактирование ADSI**.

4.  В меню **Действие**щелкните **Подключиться к**.

5.  В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.

6.  В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion. Если объект существует, атрибут **rangeUpper** имеет значение 1150, а атрибут **rangeLower** — значение 3, то схема была успешно обновлена и реплицирована. Если этот объект не существует или значения атрибутов **rangeUpper** и **rangeLower** отличаются от указанных выше, то обновление и репликация схемы не выполнены.

</div>

<div>

## <a name="see-also"></a>См. также


[Выполнение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Подготовка схемы Active Directory в Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

