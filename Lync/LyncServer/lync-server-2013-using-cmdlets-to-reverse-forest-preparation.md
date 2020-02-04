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
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Использование командлетов для отмены подготовки леса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-06-19_

Используйте командлет **Disable-ксадфорест** для реверсирования этапа подготовки леса.

<div>


> [!WARNING]  
> Если запустить командлет <STRONG>Disable-ксадфорест</STRONG> в среде, где также уже развернута Предыдущая версия Lync Server, будут также удалены глобальные параметры для предыдущей версии.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Использование командлетов для обратной подготовки леса

1.  Войдите в систему на компьютере, который входит в состав домена, в качестве члена группы администраторов домена в корневом домене леса.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Например:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Параметр Force указывает, требуется ли принудительное выполнение задачи. Если этот параметр не указан, команда не будет выполняться, если даже один домен в лесу все еще подготовлен для Lync Server 2013. Если указан параметр Force, действие будет продолжено независимо от состояния других доменов в лесу.
    
    Если параметр Граупдомаин не указан, значение по умолчанию — локальный домен.

</div>

<div>

## <a name="see-also"></a>См. также


[Проведение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

