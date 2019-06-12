---
title: 'Lync Server 2013: проверка репликации схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Проверка репликации схемы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-29_

Перед запуском подготовки леса вручную убедитесь, что Секция схемы реплицирована.

<div>

## <a name="to-manually-verify-schema-replication"></a>Проверка репликации схемы вручную

1.  Войдите в систему на контроллере домена, который является членом группы администраторов предприятия.

2.  Откройте оснастку "Редактирование ADSI", нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — пункт **ADSI Edit**.
    
    <div>
    

    > [!TIP]  
    > Кроме того, вы можете запустить <STRONG>ADSIEdit. msc</STRONG> из командной строки.

    
    </div>

3.  В дереве консоли управления (MMC), если он еще не установлен, нажмите кнопку изменить в **ADSI**.

4.  В меню **Действие** щелкните **Подключиться к**.

5.  В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.

6.  В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion. Если этот объект существует, а значение атрибута **ранжеуппер** — 1150, а значение атрибута **ранжеловер** — 3, схема была успешно обновлена и реплицирована. Если этот объект не существует или значения атрибутов **ранжеуппер** и **ранжеловер** не заданы, схема не была изменена или не была реплицирована.

</div>

<div>

## <a name="see-also"></a>См. также


[Проведение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Подготовка схемы Active Directory в Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

