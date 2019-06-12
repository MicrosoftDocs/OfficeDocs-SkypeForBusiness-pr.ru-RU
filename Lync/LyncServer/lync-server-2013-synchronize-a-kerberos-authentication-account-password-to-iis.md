---
title: Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2010-11-08_

Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.

На сайте, серверы переднего плана, серверы Standard Edition и режиссеры могут использовать учетную запись проверки подлинности Kerberos для проверки подлинности запросов к службе веб-служб. Эта процедура позволяет найти каждый сервер, на котором запущены веб-службы, на сайте, которому была назначена учетная запись Kerberos, и обновить параметры конфигурации служб IIS для использования учетной записи Kerberos. Дополнительные сведения можно найти в разделе [определение пароля учетной записи проверки подлинности Kerberos на сервере Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Установка и Настройка пароля учетной записи для проверки подлинности Kerberos

1.  Войдите в систему исходного компьютера (например, fe01.contoso.com) в качестве участника группы Рткуниверсалсерверадминс.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке оболочки Lync Server Management Shell выполните следующие две команды:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Например:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Имя исходного компьютера и конечного компьютера должно быть полным доменным именем сервера. Полное доменное имя пула нельзя использовать, если оно не совпадает с именем компьютера, который используется в качестве исходного компьютера или конечного компьютера.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

