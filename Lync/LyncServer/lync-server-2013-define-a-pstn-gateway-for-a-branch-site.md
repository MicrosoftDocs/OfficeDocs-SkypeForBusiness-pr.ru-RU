---
title: 'Lync Server 2013: определение шлюза ТСОП для сайта филиала'
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
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Определение шлюза ТСОП для сайта филиала в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Выполните эту процедуру на центральном веб-сайте, который включает по крайней мере один пул переднего плана или сервер Standard Edition.

<div>


> [!IMPORTANT]  
> Перед выполнением процедуры должны быть выполнены следующие условия: 
> <UL>
> <LI>
> <P>Программа связи Lync&nbsp;Server 2013 должна быть настроена на центральном сайте.</P>
> <LI>
> <P>Сервер-посредник должен быть развернут на центральном сайте.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Определение шлюза PSTN

1.  Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server**, а затем — **Построитель топологии Lync Server**.

2.  В дереве консоли разверните узел центрального сайта, разверните **узлы офисов филиалов**, разверните имя сайта филиала, для которого вы хотите определить шлюз для публичной коммутируемой телефонной сети (PSTN), а затем разверните раздел **Общие компоненты**.

3.  Щелкните правой кнопкой **шлюзы PSTN**и выберите команду **создать шлюз IP/КТСОП**.

4.  В диалоговом окне **Определение нового шлюза IP/КТСОП** выберите пункт **FQDN или IP-адрес шлюза**, а затем введите полное доменное имя (FQDN) или IP-адрес шлюза, который вы развертываете на сайте филиала.

5.  Выберите **прослушивающий порт для IP/КТСОП**и подтвердите значения по умолчанию.

6.  В списке **транспортный протокол SIP** выберите транспортный протокол, который использует шлюз, и нажмите кнопку **ОК**.
    
    <div>
    

    > [!NOTE]  
    > Из соображений безопасности мы настоятельно рекомендуем использовать шлюз PSTN, поддерживающий протокол TLS.

    
    </div>

<div>


> [!TIP]  
> Используйте командлет <STRONG>Set-кспстнгатевай</STRONG> , чтобы изменить свойства шлюза PSTN. Подробные сведения об этом можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-кспстнгатевай</A>в справке Lync Server Management Shell.



</div>

**Следующий шаг** для обеспечения устойчивости сайтов филиалов: [Настройка пользователей для обеспечения устойчивости сайтов филиалов в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Параметры развертывания шлюза ТСОП в Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

