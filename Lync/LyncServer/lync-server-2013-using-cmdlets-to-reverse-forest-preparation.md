---
title: 'Lync Server 2013: использование командлетов для отмены подготовки леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e3104f07934e590dc22ac9f5000601bc8166b6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535796"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Использование командлетов для отмены подготовки леса для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-06-19_

Используйте командлет **Disable-CsAdForest**, чтобы отменить этап подготовки леса.

<div>


> [!WARNING]  
> При запуске командлета <STRONG>Disable – CsAdForest</STRONG> в среде, где также развернута Предыдущая версия Lync Server, также будут удалены глобальные параметры для предыдущей версии.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Использование командлетов для отмены подготовки леса

1.  Выполните вход в систему компьютера, который подключен к домену в качестве члена группы администраторов домена в корневом домене леса.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Пример:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Параметр Force определяет, следует ли инициировать принудительное выполнение задачи. Если этот параметр отсутствует, команда не будет выполняться, если даже один домен в лесу все еще подготовлен для Lync Server 2013. Если параметр Force указан, выполнение действия продолжается независимо от состояния других доменов в лесу.
    
    Если параметр GroupDomain не указан, значением по умолчанию является локальный домен.

</div>

<div>

## <a name="see-also"></a>См. также


[Выполнение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

