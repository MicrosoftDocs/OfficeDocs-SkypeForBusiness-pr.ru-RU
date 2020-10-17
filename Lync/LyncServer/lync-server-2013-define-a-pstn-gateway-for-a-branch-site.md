---
title: 'Lync Server 2013: определение шлюза PSTN для сайта филиала'
description: 'Lync Server 2013: определение шлюза PSTN для сайта филиала.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17fb1004366fef17f57d7e8b7d14696e1e3f0fbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567775"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Определение шлюза PSTN для сайта филиала в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Выполните эту процедуру на центральном сайте, который содержит по крайней мере один интерфейсный пул или сервер Standard Edition.

<div>


> [!IMPORTANT]  
> Перед выполнением процедуры должны соблюдаться следующие условия. 
> <UL>
> <LI>
> <P>&nbsp;На центральном сайте должно быть настроено коммуникационное программное обеспечение Lync Server 2013.</P>
> <LI>
> <P>Сервер-посредник должен быть развернут на центральном сайте.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Определение шлюза ТСОП

1.  В меню **Пуск** последовательно выберите пункты **Все программы**, **Microsoft Lync Server** и **Построитель топологий**.

2.  В дереве консоли разверните центральный сайт, разверните узел **Сайты филиалов**, разверните имя сайта филиала, для которого вы хотите определить шлюз ТСОП, а затем разверните узел **Общие компоненты**.

3.  Щелкните правой кнопкой мыши элемент **Шлюзы ТСОП** и выберите команду **Создать шлюз IP/ТСОП**.

4.  В диалоговом окне **Определение нового шлюза IP/ТСОП** щелкните элемент **Полное доменное имя или IP-адрес шлюза** и введите полное доменное имя или IP-адрес шлюза, который вы развертываете на сайте филиала.

5.  Щелкните элемент **Прослушивающий порт для шлюза IP/ТСОП** и примите значения по умолчанию.

6.  В списке **Транспортный протокол SIP** выберите транспортный протокол, используемый шлюзом, и нажмите кнопку **ОК**.
    
    <div>
    

    > [!NOTE]  
    > В целях обеспечения безопасности мы настоятельно рекомендуем использовать шлюз ТСОП, поддерживающий протокол TLS.

    
    </div>

<div>


> [!TIP]  
> Для изменения свойств шлюза ТСОП используйте командлет <STRONG>Set-CsPstnGateway</STRONG>. Дополнительные сведения см. в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set – CsPstnGateway</A>в справке по консоли управления Lync Server.



</div>

**Следующий шаг** к устойчивости сайта филиала: [Настройка пользователей для обеспечения устойчивости сайта филиала в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Варианты развертывания шлюза PSTN в Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

