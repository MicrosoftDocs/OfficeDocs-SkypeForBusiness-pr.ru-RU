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
ms.openlocfilehash: 8d9cce4e6a5e835010dd9afae2e98410680ebcb5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="bf00e-102">Проверка развертывания мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf00e-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf00e-103">_**Последнее изменение темы:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="bf00e-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="bf00e-104">После развертывания службы Mobility Service Lync Server и службы автообнаружения Lync Server запустите тестовую транзакцию, чтобы убедиться, что развертывание работает правильно.</span><span class="sxs-lookup"><span data-stu-id="bf00e-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="bf00e-105">**Test-CsUcwaConference** можно использовать для проверки возможности двух пользователей, которые используют мобильные клиенты Lync 2013 для создания, присоединения и общения в Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf00e-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="bf00e-106">Чтобы использовать эту тестовую транзакцию, необходимы два фактических пользователя или тестовых пользователя, а также их полные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="bf00e-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="bf00e-107">**Test-CsMcxP2PIM** можно использовать для тестирования отправки мгновенного сообщения между двумя пользователями, использующими Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="bf00e-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="bf00e-108">Аналогично **Test-CsUcwaConference**, вы используете двух реальных пользователей или двух предварительно определенных тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="bf00e-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="bf00e-109">Тестирование конференц-связи для мобильных клиентов Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bf00e-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="bf00e-110">Выполните вход в качестве члена роли CsAdministrator на любом компьютере, где установлены Командная консоль Lync Server Management Shell и OCSCore.</span><span class="sxs-lookup"><span data-stu-id="bf00e-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="bf00e-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf00e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bf00e-112">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bf00e-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="bf00e-p103">Вы можете задать учетные данные в сценарии и затем передать его в командлет тестирования. Пример:</span><span class="sxs-lookup"><span data-stu-id="bf00e-p103">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="bf00e-115">Тестирование обмена мгновенными сообщениями между пользователями в Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="bf00e-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="bf00e-116">Выполните вход в качестве члена роли CsAdministrator на любом компьютере, где установлены Командная консоль Lync Server Management Shell и OCSCore.</span><span class="sxs-lookup"><span data-stu-id="bf00e-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="bf00e-117">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf00e-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bf00e-118">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bf00e-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="bf00e-p104">Вы можете задать учетные данные в сценарии и затем передать его в командлет тестирования. Пример:</span><span class="sxs-lookup"><span data-stu-id="bf00e-p104">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf00e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bf00e-121">See Also</span></span>


[<span data-ttu-id="bf00e-122">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="bf00e-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="bf00e-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="bf00e-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

