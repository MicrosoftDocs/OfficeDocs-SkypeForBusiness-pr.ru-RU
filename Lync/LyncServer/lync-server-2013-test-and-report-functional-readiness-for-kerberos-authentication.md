---
title: Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-01-16_

Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.

С помощью командлета Windows PowerShell **Test-кскерберосаккаунтассигнмент** можно протестировать и сообщить о готовности назначения сайта для проверки подлинности Kerberos. Эта команда отправляет запрос на сайт, указанный в требуемом параметре удостоверения. Необязательный параметр отчета заставляет командлет записать отчет в формате HTML в C:\\журналы на компьютере, на котором она выполняется. Необязательный параметр подробной информации выводит сведения о действиях на экран.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Тестирование и создание отчетов о готовности проверки подлинности Kerberos для сайта

1.  Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующую команду:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Например:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

