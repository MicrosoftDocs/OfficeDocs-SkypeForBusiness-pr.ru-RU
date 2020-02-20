---
title: 'Lync Server 2013: создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b65d62514cabe64381fc002e4c7242c9a782acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="05ca8-102">Создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей</span><span class="sxs-lookup"><span data-stu-id="05ca8-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ca8-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="05ca8-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="05ca8-104">Выполните следующие действия, чтобы создать или изменить политику ПИН-кодов на уровне пользователя или сайта для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="05ca8-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="05ca8-105">Подробнее о том, как изменить глобальную политику ПИН-кодов, можно узнать в статье [изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="05ca8-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="05ca8-106">Создание политики ПИН-кодов на уровне пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="05ca8-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="05ca8-107">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05ca8-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="05ca8-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05ca8-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="05ca8-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05ca8-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="05ca8-110">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="05ca8-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="05ca8-111">На странице **Политика ПИН-кодов** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="05ca8-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="05ca8-p103">Чтобы создать политику на уровне пользователя, щелкните **Политика пользователя**. В окне **Новая политика ПИН-кодов**, в поле **Имя**, введите имя, описывающее политику.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="05ca8-p104">Чтобы создать политику на уровне сайта, щелкните **Политика сайта**. В поле поиска **Выбор сайта** введите все имя или часть имени сайта, для которого требуется создать политику. В списке сайтов щелкните необходимый сайт и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="05ca8-117">В поле **Описание** введите описание политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="05ca8-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="05ca8-p105">В поле **Minimum PIN length (Минимальная длина ПИН-кода)** введите или выберите минимальную длину ПИН-кода, которую планируется разрешить. По умолчанию минимальная длина — пять цифр.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="05ca8-p106">Чтобы иметь возможность задавать максимальное количество попыток входа до блокировки пользователя, установите флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)**. Если этот флажок не установить, то максимальное количество разрешенных попыток определяется автоматически на основе длины ПИН-кода. По умолчанию максимальное количество попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="05ca8-123">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="05ca8-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="05ca8-p107">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="05ca8-127">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="05ca8-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="05ca8-p108">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="05ca8-p109">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="05ca8-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="05ca8-133">Рекомендуется не разрешать простые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="05ca8-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="05ca8-134">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="05ca8-135">Изменение политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="05ca8-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="05ca8-136">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05ca8-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="05ca8-137">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05ca8-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="05ca8-138">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05ca8-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="05ca8-139">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="05ca8-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="05ca8-140">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется изменить, щелкните **Правка**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="05ca8-141">В окне **Редактирование политики ПИН-кодов** измените необходимые параметры политики (кроме имени политики, которое невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="05ca8-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="05ca8-142">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

