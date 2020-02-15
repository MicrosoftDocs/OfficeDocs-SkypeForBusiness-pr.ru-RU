---
title: 'Lync Server 2013: Настройка маршрутов голосовой связи для исходящих вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5c74a11adfb3785196352f3c03772028e73ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Маршрут голосовой связи Lync Server 2013 связывает номера телефонов назначения с одним или несколькими шлюзами телефонной сети общего пользования (PSTN) или магистрали SIP, а также с одной или несколькими записями использования PSTN.

**Просмотр маршрутов голосовой связи с помощью панели управления Lync Server**

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Щелкните **Маршрутизация голосовой связи**.

3.  Щелкните **Маршрут**.

4.  Дважды щелкните маршрут голосовой связи для просмотра дополнительных свойств в списке маршрутов голосовой связи или выберите маршрут и щелкните пункт **Изменить**. Затем щелкните **Подробнее**.
    
    <div>
    

    > [!NOTE]  
    > Одновременно можно просматривать подробные сведения только по одному маршруту.

    
    </div>

**Просмотр маршрутов голосовой связи с помощью Windows PowerShell**

  - Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**. Маршруты голосовой связи можно просмотреть с помощью Windows PowerShell и командлета **Get – ксвоицерауте** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.
    
    Чтобы просмотреть сведения обо всех маршрутах голосовой связи, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsVoiceRoute
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Дополнительные сведения см в документации по планированию <A href="lync-server-2013-voice-routes.md">в Lync Server 2013</A> .



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание маршрута голосовой связи в Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Управление маршрутизацией голосовой связи в Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

