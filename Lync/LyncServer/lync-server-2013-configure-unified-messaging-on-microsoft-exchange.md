---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями в Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d05939f9d15f992d350a6bb756fe3c6b9839c37b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

В этом разделе описывается настройка единой системы обмена сообщениями Exchange на сервере Microsoft Exchange для использования с корпоративной голосовой связью.

<div>


> [!NOTE]  
> В примерах, приведенных в этом разделе, представлен синтаксис для Exchange 2007 с помощью командной консоли Exchange. Если вы используете Exchange 2010 или Exchange 2013, ознакомьтесь с соответствующей документацией, как показано на этой странице.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Настройка сервера, на котором работает единая система обмена сообщениями Exchange Server

1.  Создайте абонентскую группу универсального кода ресурса (URI) SIP для каждого профиля расположения вашей корпоративной голосовой связи. Если вы решили использовать консоль управления Exchange, создайте новую абонентскую абонентскую систему с **защищенным (предпочтительным)** параметром безопасности.
    
    <div>
    

    > [!WARNING]  
    > Если для параметра безопасности задано значение <STRONG>SIP Secured</STRONG> , требующее обязательного шифрования только для трафика SIP, как было сказано ранее, обратите внимание на то, что этот параметр безопасности для абонентской группы недостаточен, если для пула переднего плана настроено требование шифрования, что означает, что для пула требуется шифрование для трафика SIP и RTP. Если параметры безопасности абонентской группы и пула несовместимы, все вызовы Exchange единой системы обмена сообщениями из пула переднего плана завершатся ошибкой, что приведет к ошибке, указывающей на то, что параметр безопасности несовместим.

    
    </div>
    
    Если используется Командная консоль Exchange, введите:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Дополнительные сведения см. в следующих статьях:
    
      - Для Office Communications Server 2007 в [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666)разделе "как создать абонентскую систему URI SIP единой системы обмена сообщениями" at и "New – UMDialPlan: Exchange 2007 Help".
    
      - Для Exchange 2010 в разделе "Создание абонентской группы единой системы обмена [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) сообщениями" и "New – UMDialPlan: Exchange 2010 [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680)Help".
    
      - Для Exchange 2013 в [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".
    
    <div>
    

    > [!NOTE]  
    > Выбор уровня безопасности <STRONG>сипсекуред</STRONG> или <STRONG>Secure зависит от того,</STRONG> активирована или отключена передача протокола безопасности в режиме реального времени (SRTP) для шифрования мультимедиа. Для интеграции Lync Server 2010 с единой системой обмена сообщениями Exchange она должна соответствовать уровню шифрования в конфигурации мультимедиа Lync Server. Конфигурацию мультимедиа Lync Server можно просмотреть, выполнив командлет <STRONG>Get – CsMediaConfiguration</STRONG> . Дополнительные сведения см. в статье Get – CsMediaConfiguration в документации по консоли управления Lync Server.<BR>Дополнительные сведения о выборе соответствующего параметра безопасности VoIP приведены в разделе <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</A>.

    
    </div>

2.  Выполните следующий командлет для получения полного доменного имени (FQDN) для каждой абонентской группы единой системы обмена сообщениями:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Дополнительные сведения см. в следующих статьях:
    
      - Для Exchange 2007 в разделе "Get – UMDialplan: Exchange 2007 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).
    
      - Для Exchange 2010 в разделе "Get – UMDialplan: Exchange 2010 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).
    
      - Для Exchange 2013 в [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".

3.  Запишите имя абонентской группы каждой абонентской группы единой системы обмена сообщениями. В зависимости от используемой версии Exchange Server может потребоваться использовать полное доменное имя каждого имени абонентской группы в соответствии с именем каждой соответствующей абонентской группы Lync Server, чтобы имена абонентских групп соотнесены.
    
    <div>
    

    > [!NOTE]  
    > Имена абонентской группы Lync Server должны сопоставлять имена абонентской группы единой системы обмена сообщениями только в том случае, если абонентская группа единой системы обмена сообщениями работает в более <EM>ранней</EM> версии Exchange, чем Exchange 2010 SP1

    
    </div>

4.  Добавьте абонентскую группу на сервер, на котором работает единая система обмена сообщениями Exchange, как показано ниже.
    
      - Если вы решили использовать консоль управления Exchange, вы можете добавить абонентскую схему из страницы свойств для сервера. Конкретные инструкции можно найти в документации по продукту Exchange Server.
        
        В разделе "как добавить сервер единой системы обмена сообщениями в абонентскую абонентию для Exchange [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681)2007".
        
        Для Exchange 2010 можно ознакомиться в статье "Просмотр или Настройка свойств сервера единой системы обмена сообщениями" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).
        
        Для Exchange 2013 в [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".
    
      - Если вы используете командную консоль Exchange, выполните указанные ниже действия для каждого сервера единой системы обмена сообщениями Exchange.
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Перед выполнением следующего действия Убедитесь, что все пользователи корпоративной голосовой связи настроены с помощью почтового ящика Exchange Server.<BR>Для Exchange 2007 ознакомьтесь с разадресом библиотеки TechNet для Exchange <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007 по адресу.<BR>Для Exchange 2010 ознакомьтесь с разадресом библиотеки TechNet для Exchange <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010 по адресу.<BR>При указании политики почтовых ящиков для каждой абонентской группы, созданной на шаге 1, выберите либо политику по умолчанию, либо одну из созданных.

    
    </div>

5.  Перейдите в \<раздел сценарии каталога\>\\установки Exchange, а затем, если Exchange развернут в едином лесу, введите:
    ```console
    exchucutil.ps1
    ```
    Если Exchange развертывается в нескольких лесах, введите:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    где полное доменное имя леса указывает лес, в котором развернут Lync Server.
    
    Если вы используете одну или несколько абонентских групп единой системы обмена сообщениями, которые связаны с несколькими шлюзами IP, перейдите к шагу 6. Если абонентские группы связаны только с одним шлюзом IP, пропустите шаг 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Обязательно перезапустите службу <STRONG>Сервер переднего плана Lync Server</STRONG> (rtcsrv.exe) <EM>после</EM> выполнения скрипта exchucutil.ps1. В противном случае Lync Server не будет обнаруживать единую систему обмена сообщениями в топологии.

    
    </div>

6.  С помощью командной консоли Exchange или консоли управления Exchange отключите исходящий вызов для всех шлюзов IP, которые связаны с каждой абонентской абонентской группы.
    
    <div>
    

    > [!NOTE]  
    > Это необходимо, чтобы убедиться, что исходящие вызовы, выполняемые сервером, на котором работает единая система обмена сообщениями Exchange Server, для внешних пользователей (например, как в случае с помощью сценариев проигрывания на телефоне) надежно проходят через корпоративный брандмауэр.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > При выборе шлюза IP единой системы обмена сообщениями, с помощью которого можно разрешить исходящие вызовы, выберите один из них, который скорее всего будет обрабатывать весь трафик. Не разрешать исходящий трафик через шлюз IP, который подключается к пулу директорий Lync Server. Кроме того, не следует использовать пулы на другом центральном сайте или сайте филиала. Для блокирования исходящих вызовов через шлюз IP можно использовать любой из указанных ниже способов.

    
    </div>
    
      - Если вы используете командную консоль Exchange, отключите каждый шлюз IP, выполнив следующую команду:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Для Exchange 2007, в разделе "Set – UMIPGateway: Exchange 2007 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687)в.
        
        Для Exchange 2010, в разделе "Set – UMIPGateway: Exchange 2010 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688)в.
    
      - Если вы используете консоль управления Exchange, снимите флажок **Разрешить исходящие вызовы через этот шлюз IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Если абонентская группа URI SIP единой системы обмена сообщениями связана только с одним шлюзом IP, не запретите исходящие вызовы через этот шлюз.

    
    </div>

7.  Создание автосекретаря единой системы обмена сообщениями для каждой абонентской группы Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Имя автосекретаря не должно содержать пробелов.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Дополнительные сведения см. в следующих статьях:
    
      - В разделе "New – UMAutoAttendant используется: Exchange 2007 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689)Exchange 2007.
    
      - В разделе "New – UMAutoAttendant используется: Exchange 2010 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690)Exchange 2010.
    
    Следующий шаг необходимо выполнить для каждого пользователя после включения пользователей Lync Server для корпоративной голосовой связи и получения сведений об URI SIP.

8.  Свяжите пользователей единой системы обмена сообщениями Exchange (каждая из которых должна быть настроена с помощью почтового ящика Exchange) с абонентской группой единой системы обмена сообщениями и Создайте URI SIP для каждого пользователя.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Сипресаурцеидентифиер</STRONG> в следующем примере должен быть SIP адресом пользователя Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Дополнительные сведения см. в следующих статьях:
    
      - Для Exchange 2007 см. в [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691)разделе "Enable – UMMailbox: Exchange 2007 Help".
    
      - Для Exchange 2010 см. в [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692)разделе "Enable – UMMailbox: Exchange 2010 Help".

</div>

</div>

<span> </span>

</div>

</div>

</div>

