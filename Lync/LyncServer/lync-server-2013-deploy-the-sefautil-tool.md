---
title: 'Lync Server 2013: развертывание средства Сефаутил'
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
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

Для развертывания и управления получением группового звонка необходимо использовать средство Сефаутил Resource Kit. Это средство входит в состав набора средств для Lync Server 2013 Resource Kit. Прежде чем устанавливать Сефаутил, необходимо иметь доверенный пул приложений в топологии, указать Сефаутил как надежное приложение и включить топологию.

<div>


> [!IMPORTANT]  
> На всех компьютерах, на которых планируется запускать инструмент SEFAUtil, должен быть установлен Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK.



</div>

Вы можете запустить Сефаутил в любом пуле переднего плана в развертывании.

<div>


> [!NOTE]  
> Дополнительные сведения об использовании Сефаутил можно найти в статье блогов TechNet: "как запустить Сефаутил?" по <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>адресу.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Развертывание SEFAUtil

1.  Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  The SEFAUtil tool can be run only on a computer that is part of a trusted application pool. При необходимости определите доверенный пул приложений для пула переднего плана, в котором планируется запускать Сефаутил. At the command line, run:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Определите инструмент SEFAUtil как доверенное приложение. В командной строке выполните следующую команду:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > При необходимости можно использовать другой порт.

    
    </div>

5.  Включите топологию с внесенными изменениями. В командной строке выполните следующую команду:
    
        Enable-CsTopology

6.  Установите средства набора ресурсов Lync Server 2013 на сервер переднего плана, который находится в надежном пуле приложений, созданном на этапе 3.

7.  Проверьте правильность работы инструмента SEFAUtil следующим образом.
    
    1.  Запустите этот инструмент из командной строки Windows с привилегиями администратора, чтобы отобразить параметры переадресации звонков пользователя в текущем развертывании.
        
        <div>
        

        > [!NOTE]  
        > Это средство находится в \Program Files\Microsoft Lync Server 2013 \ Рескит.

        
        </div>
    
    2.  Отобразите параметры переадресации звонков пользователя. В командной строке выполните следующую команду:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        На экране появятся параметры переадресации звонков пользователя.

</div>

</div>

<span> </span>

</div>

</div>

</div>

