---
title: Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95baeb1e3d55fd2c7ae3137b36c07a7974836bdb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-11-08_

Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.

На сайте серверы переднего плана, серверы Standard Edition и директора могут использовать учетную запись проверки подлинности Kerberos для проверки подлинности запросов к службе веб-служб. Эта процедура размещает каждый сервер, на котором запущены веб-службы, на сайте, которому была назначена учетная запись Kerberos, и обновляет параметры конфигурации служб IIS для использования учетной записи Kerberos. Для получения дополнительных сведений см. Введите [пароль учетной записи проверки подлинности Kerberos на сервере в Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Порядок задания и настройки пароля учетной записи проверки подлинности Kerberos

1.  Войдите в систему исходного компьютера (например, fe01.contoso.com) в качестве члена группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке Командная консоль Lync Server выполните две следующие команды:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Пример:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Имена исходного и конечного компьютеров должны быть полными доменными именами (FQDN) сервера. Имя FQDN пула можно использовать только в том случае, если имя пула совпадает с именем компьютера, который используется в качестве исходного или конечного компьютера.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

