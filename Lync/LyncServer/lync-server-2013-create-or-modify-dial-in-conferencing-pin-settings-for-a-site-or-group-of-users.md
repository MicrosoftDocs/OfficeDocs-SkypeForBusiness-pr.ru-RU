---
title: 'Lync Server 2013: создание или изменение параметров ПИН-кода для конференц-связи с телефонным подключением для сайта или группы пользователей'
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
ms.openlocfilehash: 0ec453051e6ef9786e66a2b4d5f6dc4e48d6656f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="6574f-102">оздание или изменение параметров ПИН-кода для конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей</span><span class="sxs-lookup"><span data-stu-id="6574f-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6574f-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6574f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6574f-104">Выполните эти действия, чтобы создать или изменить политику на уровне пользователя или на уровне сайта (ПИН-код) для конференций с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6574f-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="6574f-105">Подробнее о том, как изменить глобальную политику PIN-кода, можно найти [в разделе Изменение параметров ПИН-кода конференций по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6574f-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="6574f-106">Создание политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="6574f-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="6574f-107">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6574f-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6574f-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6574f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6574f-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6574f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6574f-110">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="6574f-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="6574f-111">На странице **Политика в отношении ПИН-кодов** щелкните **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="6574f-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6574f-p103">Чтобы создать политику на уровне пользователя, щелкните **Политика пользователя**. В окне **Новая политика в отношении ПИН-кодов**, в поле **Имя**, введите имя, описывающее политику.</span><span class="sxs-lookup"><span data-stu-id="6574f-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="6574f-p104">Чтобы создать политику уровня сайта, выберите вариант **Политика сайта**. В поле поиска **Выбор сайта** введите часть или полное имя сайта, для которого требуется создать политику. В списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6574f-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="6574f-117">В поле **Описание** введите описание политики в отношении ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="6574f-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="6574f-p105">В поле **Минимальная длина ПИН-кода** введите или выберите минимальную длину ПИН-кода, которую требуется разрешить. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="6574f-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="6574f-p106">Чтобы иметь возможность задать максимальное число попыток входа перед блокированием пользователя, установите флажок **Задать максимальное число попыток входа**. Если этот параметр не выбран, максимальное число разрешенных попыток входа автоматически определяется в зависимости от длины ПИН-кода. По умолчанию максимальное число попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="6574f-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="6574f-123">Если установлен флажок **Задать максимальное число попыток входа**, в поле **Максимальное число попыток входа** введите или выберите максимальное число попыток входа, которое требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="6574f-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="6574f-p107">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Включить конечный срок действия ПИН-кодов**. Если этот параметр не выбран, ПИН-коды не будут иметь ограничений по сроку действия. По умолчанию ПИН-коды не имеют ограничений по сроку действия.</span><span class="sxs-lookup"><span data-stu-id="6574f-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="6574f-127">Если флажок **Разрешить окончание срока действия ПИН-кода** установлен, то в поле **Срок действия ПИН-кода истекает после (дней)** введите или выберите максимальное число дней, после которых ПИН-коды становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="6574f-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="6574f-p108">В поле **История значений ПИН-кода** введите число ПИН-кодов, которое пользователь должен создать перед тем, как он сможет использовать их повторно. По умолчанию пользователи могут повторно использовать ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="6574f-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="6574f-p109">Чтобы разрешить распространенные последовательности цифр в ПИН-кодах, такие как последовательные номера и повторяющиеся наборы номеров, установите флажок **Разрешить общие шаблоны**. Если не выбрать этот параметр, будут разрешены только сложные наборы цифр. По умолчанию разрешены только сложные наборы цифр.</span><span class="sxs-lookup"><span data-stu-id="6574f-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6574f-133">Мы рекомендуем не разрешать использование распространенных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="6574f-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="6574f-134">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6574f-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="6574f-135">Изменение политики ПИН-кода пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="6574f-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="6574f-136">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6574f-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6574f-137">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6574f-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6574f-138">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6574f-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6574f-139">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="6574f-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="6574f-140">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется изменить, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="6574f-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6574f-141">В окне **Редактирование политики ПИН-кодов** измените необходимые параметры политики (кроме имени политики, которое невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="6574f-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="6574f-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6574f-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

