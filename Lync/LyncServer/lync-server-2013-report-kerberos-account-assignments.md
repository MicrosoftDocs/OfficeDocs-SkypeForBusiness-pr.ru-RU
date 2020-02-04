---
title: 'Lync Server 2013: отчет о назначениях для учетной записи Kerberos'
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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Отчет о назначениях для учетной записи Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-01-16_

Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.

Вы можете использовать командлет **Get-кскерберосаккаунтассигнмент** , чтобы запросить сведения о назначениях учетных записей проверки подлинности Kerberos и сообщить о текущих заданиях в развертывании.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Запрос назначений учетной записи для проверки подлинности Kerberos для сайта

1.  Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните одну из следующих команд:
    
      - Чтобы запросить все назначения учетной записи для проверки подлинности Kerberos в Организации и вернуть сведения о назначениях для каждого из них, запустите командлет без параметров.
        
            Get-CsKerberosAccountAssignment
    
      - Чтобы запросить все назначения учетной записи для проверки подлинности Kerberos в развертывании и вернуть сведения о назначениях сайтов для каждого из них, выполните командлет с параметром Identity.
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Чтобы запросить все назначения учетной записи проверки подлинности Kerberos на одном сайте и вернуть сведения о назначениях для каждого из них, запустите командлет с параметром Filter.
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Например:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Указание * SiteName для параметра Filter возвращает сведения обо всех сайтах, которые содержат указанное имя сайта в любом месте идентификатора сайта (например, все сайты, содержащие строку Redmond в идентификаторе сайта).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

