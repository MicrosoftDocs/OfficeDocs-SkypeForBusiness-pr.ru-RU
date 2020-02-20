---
title: Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfc267d20b9df284e458ff5883cfebb4c1e5b0b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-07_

Устройства для обеспечения связи в филиалах Microsoft Lync Server 2013 не могут быть связаны с пулом переднего плана Microsoft Lync Server 2010 в качестве регистратора резервных копий. SBA должен быть связан с интерфейсным пулом Microsoft Lync Server 2013. Эти действия предполагают использование Microsoft Lync Server 2013 SBA. Выполните эту процедуру на центральном сайте.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Добавление сайтов филиалов с помощью Microsoft Lync Server 2013 SBA к топологии

1.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.

2.  В дереве консоли разверните центральный сайт, разверните **сайты филиалов**, а затем щелкните **New Branch Site** (Новый сайт филиала).

3.  В диалоговом окне **Define New Branch Site** (Задать новый сайт филиала) щелкните **Name** (Имя), а затем введите имя нового сайта филиала.

4.  (Необязательно) Щелкните **Description** (Описание), а затем введите содержательное описание сайта филиала.

5.  Нажмите кнопку **Далее**.

6.  (Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:
    
      - Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.
    
      - Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.
    
      - Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.

7.  Нажмите кнопку **Далее**, а затем выполните одно из следующих действий:
    
      - Если вы используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, убедитесь, что установлен флажок Открыть новый список для установки, **когда этот мастер закроется** .
    
      - Если вы не используете устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах на этом сайте, снимите флажок **открыть мастер создания для обеспечения связи после закрытия этого мастера** .
    
      - Нажмите кнопку **Готово**, а затем следуйте инструкциям в открывшемся мастере. Сведения об элементах мастера можно найти [в разделе Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).

8.  Повторите предыдущие действия для каждого сайта филиала, который вы хотите добавить в топологию.

</div>

<div>

## <a name="see-also"></a>См. также


[Определение устройства или сервера для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Определение шлюза PSTN для сайта филиала в Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

