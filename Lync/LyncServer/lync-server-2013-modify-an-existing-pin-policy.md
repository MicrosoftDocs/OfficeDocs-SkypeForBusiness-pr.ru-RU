---
title: 'Lync Server 2013: изменение существующей политики ПИН-кодов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27f5fcc560f302021effd90ce1b16cafb933ae03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a><span data-ttu-id="9ea65-102">Изменение существующей политики ПИН-кодов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ea65-102">Modify an existing PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ea65-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="9ea65-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="9ea65-104">С помощью вкладки **политика ПИН-кодов** можно предоставить пользователям, подключающимся к Lync 2013 с IP-телефонами, проверку подлинности персонального идентификационного номера (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="9ea65-104">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="9ea65-105">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="9ea65-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="9ea65-106">Дополнительные сведения: [изменение параметров конфигурации существующей веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9ea65-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="9ea65-107">Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла.</span><span class="sxs-lookup"><span data-stu-id="9ea65-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="9ea65-108">Изменение существующей политики ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="9ea65-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="9ea65-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ea65-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9ea65-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ea65-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ea65-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ea65-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ea65-112">На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="9ea65-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="9ea65-113">На странице **Политика ПИН-кода** выберите политику, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9ea65-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9ea65-p103">В окне **Изменение политики ПИН-кода** введите или выберите в поле **Минимальная длина ПИН-кода** минимальную длину ПИН-кода. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="9ea65-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="9ea65-p104">Чтобы указать максимальное число попыток входа, после превышения которого пользователь блокируется, установите флажок **Specify maximum logon attempts** (Указать максимальное число попыток входа). Если его не установить, максимально допустимое число попыток определяется автоматически на основании длины ПИН-кода. По умолчанию максимальное число попыток входа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="9ea65-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="9ea65-119">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="9ea65-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="9ea65-p105">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="9ea65-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="9ea65-123">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="9ea65-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="9ea65-p106">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="9ea65-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="9ea65-p107">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9ea65-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9ea65-129">Рекомендуется не разрешать простые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9ea65-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="9ea65-130">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="9ea65-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

