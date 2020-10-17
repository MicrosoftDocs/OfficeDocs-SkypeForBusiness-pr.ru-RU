---
title: 'Lync Server 2013: Просмотр сведений о политике расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b5c4b512acc3541b933f583ad69e3f730dc14f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523516"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Просмотр сведений о политике расположения в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

В Lync Server 2013 вы можете использовать политику расположения для применения параметров, относящихся к расширенным функциям 9-1-1 (E9-1-1), а также к параметрам расположения для пользователей или контактов. Политика расположения определяет, активирована ли для пользователя функция E9-1-1 и, если да, то в каком режиме выполняются экстренные вызовы. Например, можно использовать политику расположения, чтобы определить номер экстренного вызова (911 в США), а также должен ли автоматически оповещаться отдел корпоративной безопасности и как маршрутизировать вызов.

Политики расположения можно настроить из группы **конфигурации сети** в панели управления Lync Server 2013. В панели управления Lync Server вы можете просматривать, создавать, изменять и удалять политики расположения. Используйте следующую процедуру для просмотра сведений о политиках расположения. Подробнее о создании или изменении политик расположения можно узнать [в статье Создание или изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Просмотр сведений о политике расположения

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика расположения**.

4.  На странице **Политика расположения** выберите политику расположения, которую хотите изменить.

5.  В меню **Правка** щелкните **Подробнее**.
    
    <div>
    

    > [!NOTE]  
    > Одновременно можно просматривать сведения только об одной политике расположения.

    
    </div>

Отдельная политика, называемая Global, существует по умолчанию и не может быть удалена или переименована. Тем не менее, вы можете изменить глобальную политику. Эта политика будет применяться ко всем пользователям и контактам, если не создавать политики сайта или политики для отдельных пользователей. Политики для отдельных пользователей должны быть применены к определенным пользователям.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение политики расположения в Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

