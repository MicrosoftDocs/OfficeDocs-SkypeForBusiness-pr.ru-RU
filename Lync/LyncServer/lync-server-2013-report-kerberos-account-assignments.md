---
title: 'Lync Server 2013: отчет о назначениях учетных записей Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 608757b71903ce5290f5f75936b5e5a3904f07fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536336"
---
# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Отчет о назначениях учетных записей Kerberos в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-01-16_

Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.

Можно использовать командлет **Get-CsKerberosAccountAssignment** для запроса информации о назначениях учетной записи проверки подлинности Kerberos и получения сведений о текущих назначениях в вашем развертывании.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Запрос назначений учетной записи проверки подлинности Kerberos для сайта

1.  В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке выполните одну из следующих команд:
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в организации и возвратить сведения о каждом из них, запустите командлет без каких-либо параметров:
        
            Get-CsKerberosAccountAssignment
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в развертывании и возвратить сведения о каждом из них, запустите командлет с параметром Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos на отдельном сайте и возвратить сведения о каждом из них, запустите командлет с параметром Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > При указании значения *имя_сайта для параметра Filter возвращает информацию обо всех сайтах, содержащих указанное имя в любой части идентификатора сайта (например, все сайты, содержащие слово Redmond в идентификаторе).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

