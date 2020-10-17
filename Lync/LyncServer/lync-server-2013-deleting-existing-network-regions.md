---
title: 'Lync Server 2013: удаление существующих областей сети'
description: 'Lync Server 2013: удаление существующих областей сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b148f0bd92ad398ab7057a5a291bf3245df3e47e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552675"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Удаление существующих областей сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Область сети связывает части сети, расположенные в различных географических районах. Каждый регион сети должен быть связан с центральным сайтом. Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков. Для настройки областей сети можно использовать панель управления Lync Server. Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений. С помощью панели управления Lync Server можно создавать, изменять и удалять области сети. Используйте этот раздел для удаления существующих областей сети. Сведения о создании или изменении существующих областей сети приведены в статье [Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Удаление области сети

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Конфигурация сети** и выберите элемент **Область**.

4.  На странице **областей** щелкните область, которую следует удалить.
    
    <div>
    

    > [!NOTE]  
    > Можно одновременно удалять несколько областей. Для этого нажмите клавишу CTRL и выберите несколько областей, удерживая клавишу CTRL нажатой. Можно также выбрать все области, нажав пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.
    
    <div>
    

    > [!WARNING]  
    > Нельзя удалить область сети, если она связана с сетевым сайтом. При попытке удалить область, связанную с сайтом, отображается сообщение об ошибке. Чтобы увидеть, связана ли область с какими-либо сайтами, выделите эту область и выберите команду <STRONG>Показать подробности</STRONG> в меню <STRONG>Правка</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

