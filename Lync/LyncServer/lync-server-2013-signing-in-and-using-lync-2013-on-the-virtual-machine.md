---
title: 'Lync Server 2013: вход и использование Lync 2013 на виртуальной машине'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e638fd734f00633b22664b4d4862733eb6d078da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>Вход на виртуальную машину и использование Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

После включения подключаемого модуля VDI при входе пользователя в Lync 2013 выполняются следующие действия.

1.  Пользователь вводит свои учетные данные в клиент Lync 2013, работающий на виртуальной машине.

2.  После того как Lync обнаружит доступность подключаемого модуля VDI, Lync предложит пользователю повторно ввести свои учетные данные. Рекомендуется, чтобы пользователь установил флажок **Сохранить пароль** в этом диалоговом окне, так как в этом случае ему не придется вводить свои учетные данные при последующем входе в систему.

3.  Lync начинает связывание с подключаемым модулем VDI. До завершения связывания клиент отображает два значка в строке состояния Lync. Значок в нижнем левом углу указывает на то, что доступные аудиоустройства отсутствуют, а мигающий значок в нижнем правом углу — на то, что выполняется процесс сопряжения VDI, как показано ниже:
    
    ![Значок VDI для Lync, иллюстрирующий успешные операции связывания](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Значок VDI для Lync, иллюстрирующий успешные операции связывания")  

4.  После успешного сопряжения подключаемого модуля VDI значки изменяются и теперь обозначают аудиоустройство, которое будет использоваться для выполнения вызовов, и успешное сопряжение VDI:
    
    ![Значок связывания VDI Lync с успешным выполнением](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Значок связывания VDI Lync с успешным выполнением")  

5.  После пар Lync с подключаемым модулем VDI пользователь может видеть сведения о присутствии устройств, совместимых с Lync, подключенных к локальному компьютеру. Теперь пользователь может выполнять вызовы и отвечать на них в обычном режиме.

</div>

<span> </span>

</div>

</div>

</div>

