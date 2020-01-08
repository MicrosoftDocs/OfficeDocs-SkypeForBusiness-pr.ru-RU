---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a97a97d96f91b0433c65b7eb3e352dcf47c7d5
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-24_

В этой статье описано, как настроить единую систему обмена сообщениями Exchange (UM) на сервере Microsoft Exchange для использования с корпоративной голосовой связью.

<div>


> [!NOTE]  
> Примеры командлетов в этом разделе содержат синтаксис для версии Exchange 2007 среды Exchange Management Shell. Если вы используете Exchange 2010 или Exchange 2013, ознакомьтесь с соответствующей документацией в соответствии с указанными ссылками.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Настройка сервера, на котором работает UM-сервер Exchange

1.  Создайте абонентскую группу SIP (универсального кода ресурса) для каждого из профилей местоположения вашего голоса. Если вы решили использовать консоль управления Exchange, создайте новую абонентскую группу с защищенным параметром безопасности **(предпочтительно)**.
    
    <div>
    

    > [!WARNING]  
    > Если для параметра безопасности задано значение " <STRONG>SIP secures</STRONG> ", для которого требуется шифрование только за трафик SIP, как было рекомендовано, обратите внимание на то, что этот параметр безопасности для абонентской группы недостаточен, если для пула переднего плана задано шифрование, что означает, что для пула требуется шифрование для трафика SIP и RTP. Если параметры безопасности для абонентской группы и пула несовместимы, все звонки на Exchange UM из пула переднего плана будут завершаться сбоем, что приведет к ошибке, указывающей на то, что у вас есть несовместимый параметр безопасности.

    
    </div>
    
    Если вы используете консоль управления Exchange, введите:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Для получения дополнительных сведений см.:
    
      - В Office Communications Server 2007 вы можете ознакомиться с разрешениями "Создание абонентской группы SIP для единой [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) системы обмена сообщениями" и "New-Умдиалплан: [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)Exchange 2007".
    
      - В [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)Exchange 2010 вы видите раздел "Создание абонентской группы единой системы [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) обмена сообщениями" на странице "New-умдиалплан: Exchange 2010".
    
      - Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".
    
    <div>
    

    > [!NOTE]  
    > Выбор уровня безопасности <STRONG>сипсекуред</STRONG> или <STRONG>Защита</STRONG> зависит от того, активирована или деактивирована ли протокол передачи данных в режиме реального времени (SRTP) для шифрования мультимедиа. Интеграция с единой системой обмена сообщениями Exchange для интеграции с Lync Server 2010 соответствует уровню шифрования в конфигурации мультимедиа Lync Server. Чтобы просмотреть конфигурацию мультимедиа Lync Server, запустите командлет <STRONG>Get-ксмедиаконфигуратион</STRONG> . Подробности можно найти в разделе Get-Ксмедиаконфигуратион в документации по среде управления Lync Server.<BR>Подробнее о том, как выбрать соответствующий параметр безопасности в службе VoIP, можно найти <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">в разделе процесс развертывания для интеграции локальной системы обработки сообщений и Lync Server 2013</A>.

    
    </div>

2.  Чтобы получить полное доменное имя (FQDN) для каждой абонентской группы единой системы обмена сообщениями, выполните следующий командлет:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Для получения дополнительных сведений см.:
    
      - Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)статье "Get-Умдиалплан: Exchange 2007".
    
      - Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)статье "Get-Умдиалплан: Exchange 2010".
    
      - Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".

3.  Запишите имя абонентской группы для каждой абонентской группы единой системы обмена сообщениями. В зависимости от используемой версии Exchange Server может потребоваться использовать полное доменное имя каждого имени абонентского плана в соответствии с именем каждой соответствующей абонентской группы Lync Server, чтобы имена абонентских групп соответствовали друг другу.
    
    <div>
    

    > [!NOTE]  
    > Имена абонентской группы Lync Server должны совпадать с именами абонентских групп UM только в том случае, если абонентская группа UM работает в более <EM>ранней</EM> версии Exchange, чем Exchange 2010 с пакетом обновления 1.

    
    </div>

4.  Добавьте абонентскую группу на сервер, на котором запущена служба Exchange UM, как описано ниже.
    
      - Если вы решили использовать консоль управления Exchange, вы можете добавить абонентскую группу из страницы свойств сервера. Конкретные инструкции можно найти в документации по продукту Exchange Server.
        
        Сведения о том, как добавить сервер единой системы обмена сообщениями в абонентскую группу Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681), можно найти по адресу ".
        
        Для Exchange 2010 вы увидите в [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)разделе "Просмотр или Настройка свойств сервера UM".
        
        Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".
    
      - Если вы используете командную консоль Exchange, выполните указанные ниже действия для каждого из серверов Exchange UM.
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Перед выполнением следующего действия Убедитесь в том, что все пользователи организации голосовой связи настроены с помощью почтового ящика Exchange Server.<BR>Сведения об Exchange 2007 можно найти в библиотеке TechNet на сайте Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007.<BR>Сведения об Exchange 2010 можно найти в библиотеке TechNet на сайте Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010.<BR>При указании политики почтовых ящиков для каждой абонентской группы, созданной в действии 1, выберите либо политику по умолчанию, либо ее созданную.

    
    </div>

5.  Перейдите к \<разделу\>\\сценарии установки Exchange, а затем, если Exchange развернут в одном лесе, введите:
    ```console
    exchucutil.ps1
    ```
    Если Exchange развернут в нескольких лесах, введите:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    где полное доменное имя леса определяет лес, в котором развернут Lync Server.
    
    Если у вас есть одна или несколько абонентских групп UM, которые связаны с несколькими IP-шлюзами, перейдите к действию 6. Если абонентские группы связаны только с одним IP-шлюзом, пропустите шаг 6.
    
    <div>
    

    > [!IMPORTANT]  
    > <EM>После</EM> запуска ексчукутил. ps1 убедитесь в том, что вы перезапустите службу <STRONG>внешнего сервера Lync Server</STRONG> (ртксрв. exe). В противном случае Lync Server не будет определять единую систему обмена сообщениями в топологии.

    
    </div>

6.  Используя среду управления Exchange или консоль управления Exchange, отключите исходящие вызовы для всех IP-шлюзов, связанных с каждой из ваших абонентских планов.
    
    <div>
    

    > [!NOTE]  
    > Этот этап необходим для того, чтобы убедиться в том, что исходящие вызовы на сервере, на котором работает единая система обмена сообщениями Exchange, (например, как в случае с сценариями воспроизведения на телефоне) надежно просматривают корпоративный брандмауэр.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > При выборе IP-шлюза UM, через который разрешены исходящие вызовы, выберите тот, который скорее всего будет обрабатывать весь трафик. Не разрешать исходящий трафик через шлюз IP, который подключается к группе режиссеров Lync Server. Также Избегайте пулов на другом центральном сайте или сайте ветви. Для блокирования исходящих звонков через шлюз IP можно использовать один из указанных ниже способов.

    
    </div>
    
      - Если вы используете консоль управления Exchange, отключите каждый шлюз IP, выполнив следующую команду:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Инструкции для Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)разделе "Set-Умипгатевай: Exchange 2007 Help".
        
        Инструкции для Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)разделе "Set-Умипгатевай: Exchange 2010 Help".
    
      - Если вы используете консоль управления Exchange, снимите флажок **Разрешить исходящие вызовы через этот IP-шлюз** .
    
    <div>
    

    > [!IMPORTANT]  
    > Если абонентская группа SIP для обмена сообщениями с URI связана только с одним IP-шлюзом, не запретите исходящие вызовы через этот шлюз.

    
    </div>

7.  Создание автосекретаря UM для каждой абонентской группы Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Не включайте пробелы в имя автосекретаря.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Для получения дополнительных сведений см.:
    
      - Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)статье "New-Умаутоаттендант: Exchange 2007".
    
      - Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)статье "New-Умаутоаттендант: Exchange 2010".
    
    Необходимо выполнить описанные ниже действия для каждого пользователя, если вы включили пользователей Lync Server для корпоративного голосовой связи и знаете их URI SIP.

8.  Свяжите пользователей Exchange UM (каждый из которых должен быть настроен с помощью почтового ящика Exchange) с абонентской группой UM и создайте универсальный код ресурса (URI) SIP для каждого пользователя.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Сипресаурцеидентифиер</STRONG> в следующем примере должен быть адресом SIP пользователя Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Для получения дополнительных сведений см.:
    
      - Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)статье "Enable-Уммаилбокс: Exchange 2007 Help".
    
      - Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)статье "Enable-Уммаилбокс: Exchange 2010 Help".

</div>

</div>

<span> </span>

</div>

</div>

</div>

