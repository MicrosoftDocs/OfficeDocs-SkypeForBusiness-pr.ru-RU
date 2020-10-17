---
title: 'Lync Server 2013: Удаление проверки подлинности Kerberos для сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fdf5a304d428efb3b1192d02ade0187f052171
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536416"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>В Lync Server 2013 удаление проверки подлинности Kerberos для сайта

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-01-16_

Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.

Если необходимо удалить проверку подлинности Kerberos с узла или прекратить использование узла, необходимо удалить назначение учетной записи проверки подлинности Kerberos с узла с помощью командлета **Remove-CsKerberosAccountAssignment**. Используйте следующую процедуру для удаления назначения учетной записи проверки подлинности Kerberos, что приводит к удалению назначения со всех компьютеров узла.

<div class=" ">


> [!WARNING]  
> Если вы безвозвратно удаляете учетную запись с включенной проверкой подлинности Kerberos, следует использовать оснастку "Active Directory — пользователи и компьютеры", чтобы удалить его из доменных служб Active Directory после удаления назначения. Если вы планируете использовать данный объект в дальнейшем, возможно, потребуется сохранить объект Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Удаление проверки подлинности Kerberos с узла

1.  В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните две следующие команды в командной строке:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Пример:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

