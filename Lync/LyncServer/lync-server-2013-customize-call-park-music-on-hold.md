---
title: 'Lync Server 2013: Настройка музыки парковки вызовов при удержании'
description: 'Lync Server 2013: Настройка музыки парковки вызовов при удержании.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19219e4a77d4be4a18a43255e142339a4af6f463
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544005"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a>Настройка музыки парковки вызовов на удержании в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-10_

Можно указать собственный музыкальный файл, который будет использоваться для хранения музыки, вместо музыкального файла по умолчанию, который поставляется с Lync Server 2013. Чтобы настроить музыку, воспроизводимую при удержании вызова, используйте командлет **Set-CsCallParkServiceMusicOnHoldFile**.

<div>


> [!NOTE]  
> Если вы настраиваете музыку на удержание и хотите использовать ту же музыку для нескольких сайтов, необходимо настроить музыкальный файл для каждого сайта, на котором выполняется приложение парковки вызовов.



</div>

<div>

## <a name="to-customize-the-music-file"></a>Чтобы настроить файл музыки, выполните следующие действия

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > Используйте командлет <STRONG>Get-CsService</STRONG> для идентификации службы. Дополнительные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get – CsService</A>.

    
    </div>
    
    В следующем примере показано, как получить содержимое файла soothingmusic.wma в виде байтового массива и назначить его переменной. Затем аудиофайл назначается для режима приостановки вызовов в качестве музыки, воспроизводимой при удержании вызова. Дополнительные сведения см. в статье [Set – кскаллпарксервицемусиконхолдфиле](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a>См. также


[Set — Кскаллпарксервицемусиконхолдфиле](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get — CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

