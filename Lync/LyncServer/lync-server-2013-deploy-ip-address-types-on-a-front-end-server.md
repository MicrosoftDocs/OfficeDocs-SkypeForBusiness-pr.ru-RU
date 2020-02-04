---
title: 'Lync Server 2013: развертывание типов IP-адресов на сервере переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f70ff3098f11cbb3d3b04602dca9c12a4998a367
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Развертывание типов IP-адресов на сервере переднего плана для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-07-28_

С помощью построителя топологии выполните действия, описанные в описанной ниже процедуре, чтобы развернуть типы IP-адресов на сервере переднего плана.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Развертывание типов IP-адресов на сервере переднего плана

1.  В узле **Enterprise Edition Front End pools** (Интерфейсные пулы Enterprise Edition) щелкните правой кнопкой мыши сервер пула и затем выберите команду **Edit Properties** (Изменить свойства). (Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)

2.  В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.
    
    **Диалоговое окно "Изменение свойств" для пула серверов переднего плана**
    
    ![Диалоговое окно "изменение свойств" сервера переднего плана](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Диалоговое окно "изменение свойств" сервера переднего плана")
    
      - **Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.
        
        <div>
        

        > [!NOTE]  
        > Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).

        
        </div>
    
      - **Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле **Primary IP address** (Основной IP-адрес).
    
      - **Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.
    
      - **PSTN IP address** (IP-адрес ТСОП). Установка дополнительных сетевых интерфейсных карт (NIC) для поддержки конфигурации IP-адреса PSTN для Lync Server 2013 не поддерживается на размещенных ролях серверов с разрешениями. Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров для Lync Server 2013 можно найти в разделе [аппаратные платформы сервера для Lync server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

