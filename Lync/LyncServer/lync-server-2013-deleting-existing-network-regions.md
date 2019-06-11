---
title: 'Lync Server 2013: удаление существующих областей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea9d08121a7d62d10b44f97ff46ff8d4a5ca129e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Удаление существующих областей сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Сетевой регион соединяет различные части сети в нескольких географических регионах. Каждый сетевой регион должен быть связан с центральным сайтом. Центральный сайт — это сайт центра обработки данных, на котором запущена служба политики "Управление допуском звонков" (CAC). Вы можете настроить регионы сети с помощью панели управления Lync Server. Сетевые регионы включают параметры, определяющие, разрешены ли для аудио-и видеоподключений альтернативные пути через Интернет. С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые регионы. Используйте этот раздел для удаления существующих областей сети. Дополнительные сведения о создании и изменении существующих областей сети можно найти [в разделе Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Удаление сетевого региона

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **регион**.

4.  На странице **регион** выберите область, которую вы хотите удалить.
    
    <div>
    

    > [!NOTE]  
    > За один раз можно удалить несколько областей. Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните несколько областей. Кроме того, чтобы выделить все области, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.
    
    <div>
    

    > [!WARNING]  
    > Сетевая область не может быть удалена, если она связана с сетевым сайтом. При попытке удалить регион, связанный с сайтом, появится сообщение об ошибке. Чтобы узнать, связана ли область с любыми сайтами, выберите ее, а затем в меню <STRONG>Правка</STRONG> выберите команду <STRONG>Показать подробности</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

