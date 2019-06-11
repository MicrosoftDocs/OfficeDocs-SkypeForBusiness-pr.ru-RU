---
title: 'Lync Server 2013: вход в виртуальную машину и использование на ней Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Вход в виртуальную машину и использование на ней Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

После включения надстройки VDI выполняются описанные ниже действия, когда пользователь входит в Lync 2013.

1.  Пользователь вводит свои учетные данные в клиент Lync 2013, работающий на виртуальной машине.

2.  После того как Lync обнаружит доступность плагина VDI, Lync предложит пользователю повторно ввести свои учетные данные. In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.

3.  Lync начинает связывание с помощью плагина VDI. Перед завершением связывания клиент отображает в строке состояния Lync два значка. Значок внизу слева указывает на то, что звуковое устройство недоступно, а значок мигания справа внизу указывает на то, что связывание VDI выполняется, как показано ниже.
    
    ![Значок LYNC VDI] , показывающий успешное связывание (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Значок LYNC VDI") , показывающий успешное связывание  

4.  После успешного сопряжения подключаемого модуля VDI значки изменяются и теперь обозначают аудиоустройство, которое будет использоваться для выполнения вызовов, а также успешное сопряжение VDI:
    
    ![Значок связывания в LYNC VDI] , демонстрирующий успешное создание (images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Значок связывания в LYNC VDI") , демонстрирующий успешное создание  

5.  После пар Lync с подключаемым модулем VDI пользователь может видеть свое присутствие на устройствах, совместимых с Lync, которые подключены к локальному компьютеру. Теперь пользователь может размещать и отвечать на звонки в обычном режиме.

</div>

<span> </span>

</div>

</div>

</div>

