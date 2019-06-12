---
title: 'Lync Server 2013: использование командлетов для отмены подготовки доменов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Использование командлетов для отмены подготовки доменов для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-29_

Используйте командлет **Disable-ксаддомаин** для реверсирования этапа подготовки домена.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Использование командлетов для реверсирования подготовки домена

1.  Войдите на любой сервер домена, который является членом группы "Администраторы домена".

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Например:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Если параметр принудительно присутствует, подготовка домена откатывается, даже если активирован один или несколько серверов переднего или видеоконференций в домене. Если параметр Force не указан, откат подготовки домена завершается, если активированы какие-либо серверы переднего плана или серверы конференций/V в домене.
    
    <div>
    

    > [!NOTE]  
    > Параметр Глобалсеттингсдомаинконтроллер позволяет указать, где хранятся глобальные параметры. Если ваши параметры хранятся в системном контейнере (обычно это происходит при развертывании обновлений без глобального параметра, перенесенного в контейнер конфигурации), вы можете определить контроллер домена в корне леса Active Directory. Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу. Если этот параметр не указан, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных службах Active&nbsp;Directory.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Проведение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

