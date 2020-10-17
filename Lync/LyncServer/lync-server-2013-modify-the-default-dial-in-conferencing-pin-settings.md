---
title: 'Lync Server 2013: изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию'
description: 'Lync Server 2013: изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3983cb212cd1029232141d7a4b98c9db116c61c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566945"
---
# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="ecdff-103">Изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecdff-103">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecdff-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ecdff-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ecdff-105">Глобальная политика ПИН-кодов определяет правила для ПИН-кодов конференц-связи с телефонным подключением на уровне лесов.</span><span class="sxs-lookup"><span data-stu-id="ecdff-105">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="ecdff-106">Выполните приведенные действия, чтобы изменить политику ПИН-кодов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="ecdff-106">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="ecdff-107">Сведения о создании или изменении политики ПИН-кодов для конференц-связи с телефонным подключением на уровне сайта или пользователя приведены [в статье Создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="ecdff-107">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="ecdff-108">Изменение глобальной политики ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="ecdff-108">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="ecdff-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ecdff-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ecdff-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ecdff-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecdff-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ecdff-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecdff-112">В левой панели навигации щелкните элемент **Conferencing** (Конференции), а затем **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="ecdff-112">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="ecdff-113">На странице **PIN Policy** (Политика ПИН-кодов)  щелкните политику **Global** (Глобальная), нажмите кнопку **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="ecdff-113">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ecdff-p103">В поле **Minimum PIN length** (Минимальная длина ПИН-кода) окна **Edit PIN Policy** (Изменение политики ПИН-кодов) введите или выберите минимально допустимую длину ПИН-кода. По умолчанию установлена минимальная длина, равная пяти цифрам.</span><span class="sxs-lookup"><span data-stu-id="ecdff-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="ecdff-p104">Чтобы указать максимальное число попыток входа, после превышения которого пользователь блокируется, установите флажок **Specify maximum logon attempts** (Указать максимальное число попыток входа). Если его не установить, максимально допустимое число попыток определяется автоматически на основании длины ПИН-кода. По умолчанию максимальное число попыток входа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="ecdff-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="ecdff-119">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="ecdff-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="ecdff-p105">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="ecdff-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="ecdff-123">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="ecdff-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="ecdff-p106">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="ecdff-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="ecdff-p107">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="ecdff-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ecdff-129">Рекомендуется не разрешать простые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="ecdff-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="ecdff-130">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="ecdff-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

