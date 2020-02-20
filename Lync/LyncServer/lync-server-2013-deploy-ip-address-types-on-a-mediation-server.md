---
title: 'Lync Server 2013: развертывание типов IP-адресов на сервере-посреднике'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e7e8e897eb0bb37539284c2de5fa3dd478c28e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Развертывание типов IP-адресов на сервере-посреднике для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-07-28_

С помощью построителя топологий выполните действия, описанные в следующей процедуре, для развертывания типов IP-адресов на сервере-посреднике.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Развертывание типов IP-адресов на сервере-посреднике

  - В построителе топологий в разделе **Пулы-посредники**щелкните правой кнопкой мыши сервер в пуле, а затем выберите команду **изменить свойства**. (Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)

  - В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6).
    
    **Диалоговое окно "Изменение свойств" для пула сервера-посредника**
    
    ![Страница общих свойств Lync Server с полным доменным именем](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Страница общих свойств Lync Server с полным доменным именем")
    
      - **Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.
        
        <div>
        

        > [!NOTE]  
        > Это рекомендуемый параметр для конфигураций с IP версии 6 (IPv6).

        
        </div>
    
      - **Ограничить использование службы для выбранных IP-адресов**. Выберите этот параметр, чтобы указать конкретный адрес, который будет использоваться на новом сервере. Если выбран данный параметр, необходимо ввести значения для основного IP-адреса.
    
      - **Основной IP-адрес**. Введите IP-адрес, который сервер будет использовать для всех коммуникаций, кроме ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адреса.
    
      - **PSTN IP address** (IP-адрес ТСОП). Определите IP-адрес PSTN, когда сервер-посредник является изолированным. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.
        
        <div>
        

        > [!NOTE]  
        > Установка дополнительных сетевых интерфейсных плат (NIC) для поддержки конфигурации IP-адреса PSTN для Lync Server 2013 не поддерживается на совмещенных ролях серверов-посредников. Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров для Lync Server 2013 вы найдете в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

