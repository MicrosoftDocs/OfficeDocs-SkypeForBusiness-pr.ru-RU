---
title: Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0779612ca4ebf33757f5d392d1619211aeb4a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-01-23_

Чтобы предоставить пользователям Lync Server 2013 с возможностями голосовой почты в размещенной единой системе обмена сообщениями Exchange, необходимо выполнить следующие задачи по настройке на пограничном сервере:

  - Настроить пограничный сервер для федерации.

  - Репликация данных централизованного хранилища управления на пограничный сервер и проверка репликации.

  - Создать поставщика услуг размещения на пограничном сервере.

Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [Set — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [New — CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> Перед выполнением этих действий необходимо создать внешнюю запись DNS SRV для размещения службы Exchange. Дополнительные сведения см. в статье <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange</A>.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>Настройка пограничного сервера для федерации

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет Set-CsAccessEdgeConfiguration, чтобы настроить этот сервер для федерации. Например, выполните следующую команду:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    В предыдущем примере устанавливаются следующие параметры.
    
      - **UseDnsSrvRouting** указывает, что пограничные серверы будут основываться на записях DNS SRV при отправке и получении запросов федерации.
    
      - **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, разрешено ли внутренним пользователям связываться с пользователями в сценарии разделенного домена.
    
      - **EnablePartnerDiscovery** указывает, будет ли Lync Server использовать DNS-записи для обнаружения доменов партнеров, не указанных в списке разрешенных доменов Active Directory. Если значение равно false, Lync Server 2013 будет использоваться только для Федерации с доменами, обнаруженными в списке разрешенных доменов. Этот параметр обязателен, если используется маршрутизация службы DNS. В большинстве развертываний устанавливается значение False, чтобы исключить открытие федерации со всеми партнерами.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>Репликация данных на пограничный сервер и проверка репликации

  - Убедитесь, что репликация на пограничный сервер выполнена в полном объеме. Процедура описана в статье [Проверка подключения между внутренними и пограничными серверами в Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>Создание в пограничном сервере поставщика услуг размещения

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет **New-CsHostingProvider**, чтобы настроить поставщика услуг размещения. Например, выполните следующую команду:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    Команда в предыдущем примере задает следующие параметры:
    
      - Параметр **Identity** задает уникальный строковый идентификатор создаваемого поставщика услуг размещения, в данном случае это **Fabrikam.com**. Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.
    
      - Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.
    
      - Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).
        
        <div>
        

        > [!NOTE]
        > Прежде чем присвоить <CODE>EnableSharedAddressSpace</CODE> значение true, попытайтесь разрешить внутреннюю запись Федерации SRV. Если эту запись невозможно устранить внутренне, необходимо создать записи _sipfederationtls. _tcp. &lt;domain&gt; и _sip. _tls. &lt;домен&gt; во внутренней DNS. Эти записи должны указать на внешний IP-адрес интерфейса доступа пограничного сервера.

        
        </div>
    
      - **Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server 2013. Если установлено значение **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.
    
      - Параметр **ProxyFQDN** задает полное доменное имя прокси-сервера, используемого поставщиком услуг размещения, в данном примере это **proxyserver.fabrikam.com**. Это значение нельзя изменить. Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.
    
      - Параметр "... **" указывает,** включен ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server 2013.
    
      - Параметр **VerficationLevel** указывает разрешенный уровень проверки для сообщений, отправляемых поставщику услуг размещения и от него. Укажите **UseSourceVerification**, что основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения. Если этот уровень не указан, то сообщения будут отклоняться как недоступные для проверки.

</div>

<div>

## <a name="see-also"></a>См. также


[Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки пограничной системы](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Проверка подключения между внутренними и пограничными серверами в Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New — CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

