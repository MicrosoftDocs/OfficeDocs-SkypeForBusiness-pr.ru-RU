---
title: 'Lync Server 2013: развертывание средства SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ff23a228710ecc934e2984f27c63351ccf6d32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Развертывание средства SEFAUtil в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Для развертывания и управления групповой отправке звонков необходимо использовать средство SEFAUtil Resource Kit. Средство является частью средств набора ресурсов Lync Server 2013. Перед установкой SEFAUtil необходимо включить в топологию доверенный пул приложений, указать SEFAUtil в качестве доверенного приложения и включить топологию.

<div>


> [!IMPORTANT]  
> Пакет SDK для Microsoft Unified Communications Managed API (UCMA) 3,0 необходимо установить на любой компьютер, на котором планируется запустить средство SEFAUtil.



</div>

Вы можете запустить SEFAUtil в любом пуле переднего плана в своем развертывании.

<div>


> [!NOTE]  
> Дополнительные сведения о запуске SEFAUtil можно найти в статье блог TechNet "как получить SEFAutil?" по <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>адресу.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений. При необходимости определите доверенный пул приложений для пула переднего плана, где планируется запускать SEFAUtil. В командной строке выполните следующую команду:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Определите средство SEFAUtil в качестве доверенного приложения. В командной строке выполните следующую команду:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > При необходимости можно использовать другой порт.

    
    </div>

5.  Включите топологию с изменениями. В командной строке выполните следующую команду:
    
        Enable-CsTopology

6.  Установите средства набора ресурсов Lync Server 2013 на сервере переднего плана, который находится в пуле доверенных приложений, созданном на шаге 3.

7.  Убедитесь, что средство SEFAUtil работает правильно, как показано ниже.
    
    1.  Запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.
        
        <div>
        

        > [!NOTE]  
        > Средство находится на сайте \Program Files\Microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Отображение параметров переадресации звонков пользователя. В командной строке выполните следующую команду:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Будут отображены параметры переадресации звонков для пользователя.

</div>

</div>

<span> </span>

</div>

</div>

</div>

