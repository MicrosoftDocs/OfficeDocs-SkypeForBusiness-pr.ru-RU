---
title: 'Lync Server 2013: Проверка конференц-связи с телефонным подключением (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fe264b4e9eaacf9dfc5f506adbada7026972eb4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="3f118-102">Необязательно Проверка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f118-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f118-103">_**Последнее изменение темы:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="3f118-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="3f118-104">Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="3f118-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="3f118-105">Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="3f118-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="3f118-p101">Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.</span><span class="sxs-lookup"><span data-stu-id="3f118-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="3f118-109">Этот этап не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="3f118-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="3f118-110">Тестирование номеров доступа для определенного пула</span><span class="sxs-lookup"><span data-stu-id="3f118-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="3f118-111">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3f118-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="3f118-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3f118-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3f118-113">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="3f118-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="3f118-p102">Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения. Флаг –Verbose позволяет получить более подробные сведения о количестве найденных номеров доступа и их описание.</span><span class="sxs-lookup"><span data-stu-id="3f118-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

