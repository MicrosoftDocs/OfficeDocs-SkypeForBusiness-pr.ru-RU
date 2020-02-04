---
title: 'Lync Server 2013: установка Windows PowerShell 3.0'
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
ms.openlocfilehash: 7cd8b4b48f2ff5a50ef7cafc1ec39671f672670f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Установка Windows PowerShell 3.0 для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-27_

Для успешного развертывания Lync Server 2013 вам потребуется Windows PowerShell 3,0 на всех компьютерах, входящих в вашу топологию Lync Server.

Теперь для систем под управлением Windows Server 2012 или Windows Server 2012 R2 вам не нужно ничего делать, и можно перейти к следующему этапу развертывания, так как PowerShell 3,0 входит в эти операционные системы.

<div>


> [!IMPORTANT]  
> Но для систем под управлением Windows Server 2008 R2 SP1 вам потребуется установить PowerShell 3,0 как необходимый компонент, прежде чем устанавливать Lync Server 2013 или не будет работать. Чтобы установить PowerShell 3,0, ознакомьтесь со сведениями о <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">платформе Windows Management Framework 3,0</A>. Это прямая ссылка на страницу загрузки PowerShell 3,0, а также сведения об ее успешном установке.



</div>

После того как вы закончите установку или хотите убедиться, что перед тем как продолжить развертывание Lync Server, убедитесь, что приложение PowerShell 3,0 находится на сервере, если это необходимо.

1.  На сервере, который вы хотите проверить, нажмите **кнопку Пуск**, **выберите все программы**, затем **стандартные**, выберите **Windows PowerShell**и щелкните **Windows PowerShell**.

2.  В командной строке консоли Windows PowerShell введите указанную ниже команду и нажмите клавишу ВВОД.
    
        Get-Host | Select-Object Version

3.  Если вы установили Windows PowerShell 3,0, отобразится следующий результат:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

