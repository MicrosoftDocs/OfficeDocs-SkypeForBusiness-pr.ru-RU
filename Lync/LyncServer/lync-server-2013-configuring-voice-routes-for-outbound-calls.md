---
title: 'Lync Server 2013: настройка маршрутов голосовой связи для исходящих звонков'
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
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Настройка маршрутов голосовой связи для исходящих звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Голосовой маршрут Lync Server 2013 связывает конечные телефонные номера с помощью одного или нескольких шлюзов или магистральных каналов коммутируемой телефонной сети, а также одной или нескольких записей об использовании КТСОП.

**Просмотр маршрутов голосовой связи с помощью панели управления Lync Server**

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Нажмите кнопку **Маршрутизация голоса**.

3.  Щелкните **Маршрут**.

4.  Дважды щелкните голосовой маршрут для просмотра дополнительных свойств из списка голосовых маршрутов или выберите маршрут и нажмите кнопку **изменить**. Затем нажмите кнопку **Показать подробности**.
    
    <div>
    

    > [!NOTE]  
    > Вы можете просматривать только подробные сведения по одному маршруту за раз.

    
    </div>

**Просмотр маршрутов голосовой связи с помощью Windows PowerShell**

  - Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**. Голосовые маршруты можно просматривать с помощью Windows PowerShell и командлета **Get-ксвоицерауте** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.
    
    Чтобы просмотреть сведения о всех голосовых маршрутах, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsVoiceRoute
    
    Команда возвращает примерно следующую информацию:
    
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
> Подробности можно найти <A href="lync-server-2013-voice-routes.md">в разделе маршруты к голосовой связи в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание голосового маршрута в Lync Server 2013](lync-server-2013-create-a-voice-route.md)

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

