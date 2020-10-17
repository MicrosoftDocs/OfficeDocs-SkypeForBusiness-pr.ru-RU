---
title: 'Lync Server 2013: использование командлетов для отмены подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c64bbc8638ff4478849d74bb24f6e2f9704fa9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535816"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Использование командлетов для обратной подготовки домена для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-29_

Использование командлета  **Disable-CsAdDomain** для отмены этапа подготовки домена.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Использование командлетов для отмены подготовки домена

1.  Войдите на любой сервер в домене как член группы администраторов домена.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Пример:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Если параметр Force присутствует, выполняется откат для подготовки домена, даже если активируются один или несколько серверов переднего плана или серверов аудио-и видеоконференций в домене. Если параметр Force отсутствует, откат подготовки домена завершается, если активированы какие-либо серверы переднего плана или серверы конференций аудио-и видеоконференций в домене.
    
    <div>
    

    > [!NOTE]  
    > Параметр GlobalSettingsDomainController позволяет указать, где хранятся глобальные настройки. Если ваши параметры хранятся в системном контейнере (что типично для обновленных развертываний, в которых глобальный параметр не был перенесен в контейнер конфигурации), определите контроллер домена в корне леса Active Directory. Если глобальные параметры размещены в контейнере конфигурации (что типично для новых или обновленных развертываний, в которых глобальный параметр был перенесен в контейнер конфигурации), определите любой контроллер домена в лесу. Если не указать этот параметр, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных &nbsp; службах Active Directory.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Выполнение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

