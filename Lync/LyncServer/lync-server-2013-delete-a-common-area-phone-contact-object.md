---
title: 'Lync Server 2013: удаление объекта контактного телефона для общего города'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17ab84f88417a6f5cb1c96c4cf7b6df45fa24b16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Удаление объекта контактного телефона из общей области в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Возможно, вы захотите удалить объект контакта, связанный с телефонами с общим диапазоном. Например, если вы удалите телефон из вашего сотрудника, нет необходимости иметь объект контакта, связанный с этим телефоном. Командлет **Remove-кскоммонареафоне** позволяет удалить общие учетные записи для телефонной области. При запуске этого командлета телефон удаляется из списка распространенных телефонов, возвращенных функцией **Get-кскоммонареафоне**. Кроме того, объект контакта, связанный с этим телефоном, удаляется из доменных служб Active Directory.

С помощью **Remove-кскоммонареафоне** можно удалить один или несколько стандартных телефонов, которые содержат общий элемент, например отображаемое имя или код страны и города. Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Удаление указанного телефонного телефона с общим регионом

  - Следующая команда удаляет стандартную телефонную область с адресом SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Удаление общих телефонов с областями на основе их отображаемого имени

  - Эта команда удаляет все общие телефоны, в которых отображаемое имя содержит строковое значение "здание 14".
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Удаление общих телефонов с областями на основе кодов стран и городов

  - Эта команда удаляет все обычные телефоны для США (код страны 1) и код города 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-кскоммонареафоне](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

