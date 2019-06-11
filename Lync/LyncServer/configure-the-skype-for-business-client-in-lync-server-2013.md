---
title: Настройка клиента Skype для бизнеса в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa863fd1775fbc2a726806f2dd4fff5fed5dbfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="c5894-102">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c5894-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5894-103">_**Тема последнего изменения:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="c5894-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="c5894-104">**Сводка:** В этой статье описано, как настроить взаимодействие с клиентами для пользователей Skype для бизнеса в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5894-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="c5894-105">Настроить интерфейс клиента можно только в том случае, если на компьютере установлено приложение Lync Server 2013 с установленным накопительным обновлением за декабрь 2014 (5.0.8308.857) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c5894-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="c5894-106">Сведения об обновлении Lync Server 2013 можно найти в статьях [обновления для Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="c5894-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="c5894-107">Skype для бизнеса — это новый пользовательский интерфейс, который основан на потребительских интерфейсах Skype.</span><span class="sxs-lookup"><span data-stu-id="c5894-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="c5894-108">Помимо всех функций Lync, в Skype для бизнеса предусмотрены новые функции, упрощенные элементы управления и знакомые значки.</span><span class="sxs-lookup"><span data-stu-id="c5894-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="c5894-109">Подробные сведения о новом интерфейсе клиента можно найти в разделе [Lync (Skype для бизнеса) – ознакомьтесь со статьей о новых](http://go.microsoft.com/fwlink/?linkid=529022)возможностях.</span><span class="sxs-lookup"><span data-stu-id="c5894-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="c5894-110">Lync Server 2013 поддерживает новый клиентский интерфейс Skype для бизнеса, а также взаимодействие с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="c5894-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="c5894-111">Администратор может выбрать для пользователей предпочтительный режим взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c5894-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="c5894-112">Например, вам может потребоваться развернуть взаимодействие с клиентом Lync, пока пользователи в вашей организации не будут полностью прошли обучение в новом интерфейсе Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c5894-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="c5894-113">Если вы еще не обновили все пользователи в Skype для бизнеса Server 2015, вам может потребоваться, чтобы все пользователи могли использовать одинаковые возможности клиента, пока не будут обновлены до нового сервера.</span><span class="sxs-lookup"><span data-stu-id="c5894-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5894-114">Если в вашей организации одновременно развернуты и Skype для бизнеса Server 2015, и Lync Server 2013, интерфейс по умолчанию будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c5894-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="c5894-115">Когда пользователи запускают Skype для бизнеса в первый раз, они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали пользовательский интерфейс Lync.</span><span class="sxs-lookup"><span data-stu-id="c5894-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="c5894-116">Через несколько минут пользователи просят перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="c5894-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="c5894-117">Дополнительные сведения см. в разделе <STRONG>Режим работы клиента при первом запуске</STRONG> далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c5894-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c5894-118">Взаимодействие с клиентом Lync 2013 не поддерживается в версиях клиентов Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="c5894-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="c5894-119">Перед настройкой клиентской среды на использование клиента Lync 2013 убедитесь, что версия клиента не начинается с цифр "16" (например: 16.x.x.x).</span><span class="sxs-lookup"><span data-stu-id="c5894-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="c5894-120">Configure the client experience</span><span class="sxs-lookup"><span data-stu-id="c5894-120">Configure the client experience</span></span>

<span data-ttu-id="c5894-121">С помощью командлета **Set-CSClientPolicy** с параметром енаблескипеуи вы можете указать интерфейс клиента, который будет отображаться для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c5894-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="c5894-122">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей в Организации, которым затронула Глобальная политика (Помните, что политики сайтов или пользователей переопределяют глобальную политику).</span><span class="sxs-lookup"><span data-stu-id="c5894-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="c5894-123">Следующая команда выбирает взаимодействие с клиентом Lync для всех пользователей в вашей организации, затрагиваемых глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="c5894-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="c5894-124">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="c5894-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="c5894-125">Если вы хотите настроить взаимодействие с клиентами для конкретных пользователей в Организации, вы можете создать новую политику пользователей с помощью командлета **New-CsClientPolicy** , а затем назначить политику для определенных пользователей с помощью функции **Grant-CsClientPolicy** Командлет.</span><span class="sxs-lookup"><span data-stu-id="c5894-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="c5894-126">Например, следующая команда создает новую политику клиента, Салесклиентуи, которая выбирает взаимодействие с клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c5894-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="c5894-127">При выполнении следующей команды политика SalesClientUI назначается всем участникам из отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="c5894-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="c5894-128">Режим работы клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="c5894-128">First launch client behaviors</span></span>

<span data-ttu-id="c5894-129">По умолчанию при первом запуске Skype для бизнеса они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали режим взаимодействия с клиентом Lync, присвоий параметру Енаблескипеуи значение для $False, как описано выше. .</span><span class="sxs-lookup"><span data-stu-id="c5894-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="c5894-130">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="c5894-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="c5894-131">Чтобы отобразить интерфейс Lync при первом запуске клиента Skype для бизнеса, выполните следующие действия до того, как клиент будет запущен в первый раз после обновления.</span><span class="sxs-lookup"><span data-stu-id="c5894-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="c5894-132">Убедитесь в том, что `EnableSkypeUI` значение параметра установлено на $false в той политике, которую вы используете, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="c5894-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="c5894-p108">Обновите системный реестр на компьютере пользователя. Это необходимо сделать до первого запуска клиента Skype для бизнеса. Действие выполняется всего один раз. Сведения о создании объекта групповой политики для обновления реестра на присоединенном к домену компьютере см. далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c5894-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="c5894-136">В разделе \*\* \[файл\_hKey\_приложения\\\\Microsoft\\Office\\\] Lync для текущего пользователя\*\* создайте новый **двоичный** параметр.</span><span class="sxs-lookup"><span data-stu-id="c5894-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="c5894-137">**Имя значения** должно быть **EnableSkypeUI**. Для **данных значения** задайте **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="c5894-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="c5894-138">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5894-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="c5894-139">Теперь интерфейс Lync будет отображаться при первом запуске клиента Skype для бизнеса пользователями.</span><span class="sxs-lookup"><span data-stu-id="c5894-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="c5894-140">Руководство по управлению отображением экрана приветствия</span><span class="sxs-lookup"><span data-stu-id="c5894-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="c5894-141">Когда пользователи открывают клиент Skype для бизнеса, по умолчанию отображается экран приветствия, включающий *семь советов*, которые нужно запросить.</span><span class="sxs-lookup"><span data-stu-id="c5894-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="c5894-142">Вы можете отключить отображение экрана приветствия, но по-прежнему предоставить пользователям доступ к учебнику, добавив следующий параметр реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="c5894-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="c5894-143">В разделе \*\* \[hKey\_текущего\_пользователя\\\\\\Microsoft Office\\15,0\\Lync\] \*\* создайте новый **параметр DWORD (32-разр.)**.</span><span class="sxs-lookup"><span data-stu-id="c5894-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="c5894-144">Для параметра **Имя значение** необходимо указать значение **IsBasicTutorialSeenByUser**, для параметра **Данные значения** — **1**.</span><span class="sxs-lookup"><span data-stu-id="c5894-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="c5894-145">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5894-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="c5894-146">Отключение руководства в клиенте</span><span class="sxs-lookup"><span data-stu-id="c5894-146">Turn off the client tutorial</span></span>

<span data-ttu-id="c5894-147">Чтобы не показывать пользователям руководство, задайте в реестре следующее значение.</span><span class="sxs-lookup"><span data-stu-id="c5894-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="c5894-148">В разделе \*\* \[hKey\_текущего\_пользователя\\\\\\Microsoft Office\\15,0\\Lync\] \*\* создайте новый **параметр DWORD (32-разр.)**.</span><span class="sxs-lookup"><span data-stu-id="c5894-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="c5894-149">Для параметра **Имя значение** необходимо указать значение **TutorialFeatureEnabled**, для параметра **Данные значения** — **0**.</span><span class="sxs-lookup"><span data-stu-id="c5894-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="c5894-150">Чтобы снова включить руководство, задайте для параметра **Данные значения** значение **1**.</span><span class="sxs-lookup"><span data-stu-id="c5894-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="c5894-151">Взаимодействие с клиентом по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c5894-151">Default client experiences</span></span>

<span data-ttu-id="c5894-152">Если в вашей организации одновременно развернуты и Skype для бизнеса Server 2015, и Lync Server, взаимодействие с клиентом будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="c5894-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="c5894-153">В следующей таблице указан первоначальный режим взаимодействия с клиентом в зависимости от версии сервера и параметра пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c5894-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c5894-154">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="c5894-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="c5894-155">Параметр EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="c5894-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="c5894-156">Взаимодействие с клиентом</span><span class="sxs-lookup"><span data-stu-id="c5894-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5894-157">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5894-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c5894-158">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c5894-158">Default</span></span></p></td>
<td><p><span data-ttu-id="c5894-159">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5894-160">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5894-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c5894-161">True</span><span class="sxs-lookup"><span data-stu-id="c5894-161">True</span></span></p></td>
<td><p><span data-ttu-id="c5894-162">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5894-163">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5894-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c5894-164">False</span><span class="sxs-lookup"><span data-stu-id="c5894-164">False</span></span></p></td>
<td><p><span data-ttu-id="c5894-165">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="c5894-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5894-166">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="c5894-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-167">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c5894-167">Default</span></span></p></td>
<td><p><span data-ttu-id="c5894-168">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="c5894-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5894-169">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="c5894-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-170">True</span><span class="sxs-lookup"><span data-stu-id="c5894-170">True</span></span></p></td>
<td><p><span data-ttu-id="c5894-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5894-172">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="c5894-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-173">False</span><span class="sxs-lookup"><span data-stu-id="c5894-173">False</span></span></p></td>
<td><p><span data-ttu-id="c5894-174">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="c5894-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5894-175">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="c5894-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-176">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c5894-176">Default</span></span></p></td>
<td><p><span data-ttu-id="c5894-177">Пользователь запросят перейти в режим взаимодействия с клиентом Lync (пользователь не может переключиться на Skype для бизнеса позже)</span><span class="sxs-lookup"><span data-stu-id="c5894-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5894-178">В следующей таблице показано, как администратор изменяет первоначальные параметры пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="c5894-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c5894-179">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="c5894-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="c5894-180">Параметр пользовательского интерфейса Skype</span><span class="sxs-lookup"><span data-stu-id="c5894-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="c5894-181">Пользовательский интерфейс клиента = Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="c5894-182">Клиентский пользовательский интерфейс = Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5894-183">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5894-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c5894-184">True</span><span class="sxs-lookup"><span data-stu-id="c5894-184">True</span></span></p></td>
<td><p><span data-ttu-id="c5894-185">Пользователь попросят перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="c5894-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5894-187">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5894-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c5894-188">False</span><span class="sxs-lookup"><span data-stu-id="c5894-188">False</span></span></p></td>
<td><p><span data-ttu-id="c5894-189">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="c5894-190">Пользователь запросят переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5894-191">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="c5894-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-192">True</span><span class="sxs-lookup"><span data-stu-id="c5894-192">True</span></span></p></td>
<td><p><span data-ttu-id="c5894-193">Пользователь попросят перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="c5894-194">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5894-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5894-195">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="c5894-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-196">False</span><span class="sxs-lookup"><span data-stu-id="c5894-196">False</span></span></p></td>
<td><p><span data-ttu-id="c5894-197">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="c5894-198">Пользователь запросят переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5894-199">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="c5894-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="c5894-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c5894-200">Default</span></span></p></td>
<td><p><span data-ttu-id="c5894-201">Режим Lync (не удается перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="c5894-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="c5894-202">Пользовательский интерфейс Lync (не удается перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="c5894-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5894-203">Для управления конфигурацией клиента Skype для бизнеса требуются следующие версии исправлений:</span><span class="sxs-lookup"><span data-stu-id="c5894-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="c5894-204">Lync Server 2010 — февраля 2015 (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c5894-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="c5894-205">Дополнительные сведения можно найти в разделе [Обновление для Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="c5894-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="c5894-206">Lync Server 2013 – Декабрь 2014 (5.0.8308.857) для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5894-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="c5894-207">Дополнительные сведения можно найти в разделе [Обновление для Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="c5894-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="c5894-208">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="c5894-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="c5894-p115">Для отображения интерфейса Lync при первом запуске клиента Skype для бизнеса необходимо только один раз обновить реестр. Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения, а не обновлять данные значения. Если при применении GPO новое значение не существует, оно будет создано, а для данных значения будет задано значение 0.</span><span class="sxs-lookup"><span data-stu-id="c5894-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="c5894-p116">В процедуре ниже описывается изменение реестра таким образом, чтобы при первом запуске Skype для бизнеса пользователем отображался интерфейс Lync. С помощью этой процедуры можно также обновить реестр и отключить показ учебного пособия на экране приветствия, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="c5894-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="c5894-214">**Создание объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="c5894-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="c5894-215">Запустите **Консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="c5894-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="c5894-216">Сведения о работе с консолью управления групповыми политиками см. в разделе [Консоль управления групповыми политиками](http://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="c5894-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="c5894-217">Щелкните правой кнопкой мыши узел **Объекты групповой политики** и выберите в меню пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c5894-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="c5894-218">В диалоговом окне **New GPO** (Создание нового объекта групповой политики) введите имя для этого нового объекта групповой политики, например, **MakeLyncDefaultUI**, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c5894-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="c5894-219">Щелкните созданный объект групповой политики правой кнопкой мыши и выберите **Edit** (Редактировать) из меню.</span><span class="sxs-lookup"><span data-stu-id="c5894-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="c5894-220">В **Редакторе управления групповыми политиками** разверните папки **Конфигурация пользователя**, **Параметры**, **Параметры Windows** и выберите узел **Реестр**.</span><span class="sxs-lookup"><span data-stu-id="c5894-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="c5894-221">Щелкните правой кнопкой мыши узел **реестра** и выберите пункт **создать** \> **элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="c5894-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="c5894-222">В диалоговом окне **New Registry Properties** (Новые свойства реестра) обновите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c5894-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c5894-223">Поле</span><span class="sxs-lookup"><span data-stu-id="c5894-223">Field</span></span></th>
    <th><span data-ttu-id="c5894-224">Значение для выбора или ввода</span><span class="sxs-lookup"><span data-stu-id="c5894-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c5894-225"><strong>Действие</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-226"><strong>Создание</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c5894-227"><strong>Куст</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="c5894-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c5894-229"><strong>Ключевой путь</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="c5894-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c5894-231"><strong>Имя значения</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="c5894-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c5894-233"><strong>Тип значения</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="c5894-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c5894-235"><strong>Данные значения</strong></span><span class="sxs-lookup"><span data-stu-id="c5894-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="c5894-236">00000001</span><span class="sxs-lookup"><span data-stu-id="c5894-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="c5894-237">Нажмите кнопку **OK**, чтобы сохранить изменения, затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c5894-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="c5894-238">Далее следует связать созданный объект групповой политики с группой пользователей, которым необходимо назначить политику, например, с подразделением.</span><span class="sxs-lookup"><span data-stu-id="c5894-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="c5894-239">**Назначение политики с помощью объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="c5894-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="c5894-240">В консоли управления групповыми политиками щелкните правой кнопкой мыши на подразделении, которому необходимо назначить групповую политику, и выберите **Связать с существующим объектом групповой политики**.</span><span class="sxs-lookup"><span data-stu-id="c5894-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="c5894-241">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5894-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="c5894-242">На целевом компьютере пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c5894-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="c5894-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="c5894-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="c5894-p117">При применении объекта групповой политики отобразится сообщение "Обновление политики...". После завершения обновления отобразится сообщение "Обновление политики пользователя завершено успешно".</span><span class="sxs-lookup"><span data-stu-id="c5894-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="c5894-246">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c5894-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="c5894-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="c5894-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="c5894-248">Ниже отобразится список назначенных объектов групповой политики с именем созданного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c5894-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="c5894-249">Также можно проверить успешное обновление реестра объектом групповой политики на компьютере пользователя, изучив реестр.</span><span class="sxs-lookup"><span data-stu-id="c5894-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="c5894-250">Откройте редактор реестра и перейдите к \*\* \[программному\_\_обеспечению\\\\текущего пользователя\\в\\разделе\] hKey Microsoft Office Lync\*\* .</span><span class="sxs-lookup"><span data-stu-id="c5894-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="c5894-251">Если объект групповой политики успешно обновил реестр, будет отображаться значение с именем EnableSkypeUI и значением 0.</span><span class="sxs-lookup"><span data-stu-id="c5894-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

