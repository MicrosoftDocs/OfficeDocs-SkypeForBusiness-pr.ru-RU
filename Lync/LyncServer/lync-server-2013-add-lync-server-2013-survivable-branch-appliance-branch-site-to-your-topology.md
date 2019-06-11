---
title: Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-07_

Microsoft Lync Server 2013 (СБА) не может быть связан с пулом переднего плана Microsoft Lync Server 2010 в качестве регистратора резервных копий. СБА должен быть связан с пулом внешних интерфейсов Microsoft Lync Server 2013. Эти действия предполагают наличие Microsoft Lync Server 2013 СБА. Выполните эту процедуру на центральном веб-сайте.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Добавление сайтов филиалов с Microsoft Lync Server 2013 СБА в топологию

1.  Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.

2.  В дереве консоли разверните узел центрального сайта, разверните узел **сайты филиалов**и выберите пункт **создать сайт филиала**.

3.  В диалоговом окне **Определение нового сайта ветви** щелкните **имя**и введите имя для нового сайта ветви.

4.  Необязательно Нажмите кнопку **Описание**и введите понятное описание сайта филиала.

5.  Нажмите кнопку **Далее**.

6.  Необязательно В диалоговом окне **Определение нового сайта ветви** выполните одно из указанных ниже действий.
    
      - Щелкните **город**и введите имя города, в котором находится сайт филиала.
    
      - Щелкните область или **регион**, а затем введите имя состояния или региона, в котором находится сайт филиала.
    
      - Щелкните **код страны**, а затем введите четырехзначный код звонка для страны или региона, в котором расположен сайт филиала.

7.  Нажмите кнопку **Далее**, а затем выполните одно из указанных ниже действий.
    
      - Если вы используете работающее работающее устройство филиала или его временный сервер филиала на этом сайте, убедитесь, что установлен флажок **открыть новый бесперебойный мастер при закрытом окне мастера** .
    
      - Если вы не используете работающее работающее устройство филиала или бесперебойную подразделение сервера на этом сайте, снимите флажок **открыть новый бесперебойный мастер, когда этот мастер** закроется.
    
      - Нажмите кнопку **Готово**, а затем следуйте указаниям в открывшемся мастере. Сведения об элементах мастера можно найти [в разделе Определение работающего устройства филиала или сервера в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Повторите описанные выше действия для всех сайтов филиалов, которые нужно добавить в топологию.

</div>

<div>

## <a name="see-also"></a>См. также


[Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Определение шлюза ТСОП для сайта филиала в Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Настройка магистрали без обхода мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

