---
title: 'Lync Server 2013: Настройка поддержки федерации для домена Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27780806e064aae82aa36cee96d9fafcdba2eddb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525976"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Настройка поддержки федерации для домена Lync Online в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Для Федерации с Microsoft Lync Online 2010 пользователь должен выполнить следующие действия:

  - Настройте поддержку домена для клиента Lync Online 2010 (например, contoso.onmicrosoft.com). Как указано в разделе [необходимые условия для Федерации с помощью клиента Lync Online 2013 в](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) этой документации, вы уже включили Федерацию для своей организации. Для поддержки федерации необходимо указать метод, который будет использоваться для управления доступом в федеративных доменах. Если ваша организация настроена на использование обнаружения, Добавление домена в список разрешенных организаций является необязательным. Если вы не включили обнаружение доменов, необходимо добавить доменное имя клиента Lync Online в список разрешенных доменов. Имя домена можно добавить с помощью панели управления Lync Server или командлета **New – CSAllowedDomain** . Для получения дополнительных сведений об использовании панели управления Lync Server, в том числе для включения обнаружения доменов, ознакомьтесь со статьей [Управление федеративными поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по операциям. Для получения дополнительных сведений об использовании командлета **New – CSAllowedDomain** для добавления домена, ознакомьтесь со статьей [New – CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) в документации по операциям.
    
    <div>
    

    > [!NOTE]  
    > Клиент Lync Online может иметь несколько доменов. Если вы хотите создать федерацию с несколькими доменами, необходимо настроить поддержку для каждого отдельного домена, с которым будет поддерживаться Федерация, а администратор Lync Online должен включить федерацию для каждого из доменов в федеративный.

    
    </div>

  - Настройте поддержку поставщика услуг хостинга для домена клиента Lync Online 2010, с которым вы хотите создать федерацию. С помощью процедуры, описанной в этом разделе, можно настроить поддержку поставщика услуг хостинга.
    
    <div>
    

    > [!NOTE]  
    > Этот шаг необходим только для Федерации с доменом клиента Lync Online, а не для Федерации с доменом, развернутым локально в расположении федеративного партнера.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Настройка поддержки поставщика услуг хостинга

1.  На сервере переднего плана запустите командную консоль Lync Server: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.

2.  Запустите командлет **New – CsHostingProvider** , чтобы создать и настроить поставщика услуг хостинга. Например, выполните следующую команду:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Команда в предыдущем примере задает следующие параметры:
    
      - **Identity** указывает уникальный идентификатор строкового значения для поставщика услуг хостинга, который вы создаете. Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.
    
      - Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Это значение нельзя изменить. Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.
    
      - **Верификатионлевел** указывает, как (или если) сообщения, отправляемые от поставщика услуг хостинга, проходят проверку, чтобы убедиться, что они отправлены от этого поставщика.
    
      - Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.
    
      - Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).
    
      - **Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server. Если установлено значение **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.
    
      - Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server.
    
    Подробнее об использовании этого командлета можно узнать в статье [New – CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) в документации по операциям.

</div>

</div>

<span> </span>

</div>

</div>

</div>

