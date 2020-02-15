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
ms.openlocfilehash: c742e6e7e5cedc773e0275700a738afd26a6777d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Отчет о назначениях учетных записей Kerberos в Lync Server 2013

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
        
        Пример:
        
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

