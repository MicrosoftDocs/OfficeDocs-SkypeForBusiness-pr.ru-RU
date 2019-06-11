---
title: 'Lync Server 2013: развертывание типов IP-адресов на сервере-посреднике'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e629b1074f41f1e32795de391b31e8b610f88b2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Развертывание типов IP-адресов на сервере-посреднике для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-07-28_

С помощью построителя топологии выполните действия, описанные в следующей процедуре, чтобы развернуть типы IP-адресов на сервере обновлений.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Развертывание типов IP-адресов на сервере-посреднике

  - В построителе топологии в разделе **Пулы исправлений**щелкните правой кнопкой мыши сервер в пуле и выберите команду **изменить свойства**. (Или же выберите сервер и щелкните **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)

  - В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.
    
    **Диалоговое окно "Изменение свойств" для пула сервера-посредника**
    
    ![Страница общих свойств Lync Server с полным доменным именем] (images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Страница общих свойств Lync Server с полным доменным именем")
    
      - **Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.
        
        <div>
        

        > [!NOTE]  
        > Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).

        
        </div>
    
      - **Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле Primary IP address (Основной IP-адрес).
    
      - **Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.
    
      - **PSTN IP address** (IP-адрес ТСОП). Определите IP-адрес PSTN, если сервер-посредник является автономным. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.
        
        <div>
        

        > [!NOTE]  
        > Установка дополнительных сетевых интерфейсных карт (NIC) для поддержки конфигурации IP-адреса PSTN для Lync Server 2013 не поддерживается на размещенных ролях серверов с разрешениями. Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров для Lync Server 2013 можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

