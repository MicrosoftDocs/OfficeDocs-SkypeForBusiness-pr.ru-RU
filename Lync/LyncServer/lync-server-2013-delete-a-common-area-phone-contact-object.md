---
title: 'Lync Server 2013: удаление объекта контактного телефона общего пользования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38126f54e02738b1f48b42022a9061055e271d18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525726"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Удаление объекта контактного телефона общего пользования в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Возможно, вы захотите удалить объект Contact, связанный с телефоном на общем участке. Например, если удалить телефон из неактивного сотрудника, нет необходимости иметь объект Contact, связанный с этим телефоном. Командлет **Remove – CsCommonAreaPhone** позволяет удалять общие учетные записи телефонной сети. При выполнении этого командлета в списке общедоступных телефонов, возвращенных командлетом **Get-CsCommonAreaPhone**, удаляется телефон. Кроме того, объект Contact, связанный с этим телефоном, удаляется из доменных служб Active Directory.

Используйте **Remove – CsCommonAreaPhone** , чтобы удалить один общий телефон или все общие телефоны, имеющие общий элемент, такие как отображаемое имя или код страны и города. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Удаление указанного телефона на общем участке

  - Следующая команда удаляет телефон общей области с адресом SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Удаление общих телефонов на основе отображаемого имени

  - Эта команда удаляет все общие телефоны, для которых отображаемое имя содержит строковое значение "Построение 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Удаление телефонной области на основе кодов их стран и областей

  - Эта команда удаляет все общие телефоны для США (код страны 1) и код города 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Дополнительные сведения см. в разделе справки для командлета [Remove – CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

