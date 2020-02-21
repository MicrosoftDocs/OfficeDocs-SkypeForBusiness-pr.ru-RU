---
title: 'Lync Server 2013: Установка Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a799ba54fe7677ed2ccfa8051f295b2b775cdc0e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Установка Windows PowerShell 3,0 для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-27_

Для успешного развертывания Lync Server 2013 вам потребуется Windows PowerShell 3,0 на каждом компьютере, входящем в вашу топологию Lync Server.

Теперь для систем под управлением Windows Server 2012 или Windows Server 2012 R2 вам не нужно ничего делать и перейти к следующему этапу развертывания, так как PowerShell 3,0 включен в эти операционные системы.

<div>


> [!IMPORTANT]  
> Но для систем под управлением Windows Server 2008 R2 с пакетом обновления 1 (SP1) перед установкой Lync Server 2013 вам потребуется установить оболочку PowerShell 3,0. Чтобы установить PowerShell 3,0, обратитесь к разделу <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Это прямая ссылка на страницу загрузки PowerShell 3,0, а также сведения об их успешном установке.



</div>

После завершения установки или необходимо убедиться, что перед продолжением развертывания Lync Server необходимо убедиться, что PowerShell 3,0 находится на сервере, что происходит очень просто.

1.  На сервере, который нужно проверить, нажмите кнопку **Пуск**, выберите **все программы**, **стандартные**, щелкните **Windows PowerShell**и выберите **Windows PowerShell**.

2.  В консоли Windows PowerShell введите в командной строки следующую команду и нажмите клавишу ВВОД:
    
        Get-Host | Select-Object Version

3.  Если вы установили Windows PowerShell 3,0, вы увидите следующий результат:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

