---
title: 'Lync Server 2013: Проверка параметров конференц-связи с телефонным подключением (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c43646572171a93880dd5013c87a08a2051ab2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530796"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>Необязательно Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2010-11-02_

Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением. Это шаг является необязательным.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Поиск абонентских групп с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа

1.  Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующий командлет:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>Поиск номеров доступа, которые не связаны ни с одним регионом

1.  Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-ServerAdministrator** или **CsAdministrator**.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующий командлет:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.

</div>

</div>

<span> </span>

</div>

</div>

</div>

