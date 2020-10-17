---
title: 'Lync Server 2013: Проверка развертывания для мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fefcdaf1fc84151fd37d7ff29acf66d742425d7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527616"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>Проверка развертывания мобильных устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

После развертывания службы Mobility Service Lync Server и службы автообнаружения Lync Server запустите тестовую транзакцию, чтобы убедиться, что развертывание работает правильно. **Test-CsUcwaConference** можно использовать для проверки возможности двух пользователей, которые используют мобильные клиенты Lync 2013 для создания, присоединения и общения в Конференции. Чтобы использовать эту тестовую транзакцию, необходимы два фактических пользователя или тестовых пользователя, а также их полные учетные данные.

**Test-CsMcxP2PIM** можно использовать для тестирования отправки мгновенного сообщения между двумя пользователями, использующими Lync 2010 Mobile. Аналогично **Test-CsUcwaConference**, вы используете двух реальных пользователей или двух предварительно определенных тестовых пользователей.

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>Тестирование конференц-связи для мобильных клиентов Lync 2013

1.  Выполните вход в качестве члена роли CsAdministrator на любом компьютере, где установлены Командная консоль Lync Server Management Shell и OCSCore.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду.
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Вы можете задать учетные данные в сценарии и затем передать его в командлет тестирования. Пример:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>Тестирование обмена мгновенными сообщениями между пользователями в Lync 2010 Mobile

1.  Выполните вход в качестве члена роли CsAdministrator на любом компьютере, где установлены Командная консоль Lync Server Management Shell и OCSCore.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  В командной строке введите следующую команду.
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Вы можете задать учетные данные в сценарии и затем передать его в командлет тестирования. Пример:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>См. также


[Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

