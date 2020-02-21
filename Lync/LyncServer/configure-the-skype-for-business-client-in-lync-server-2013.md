---
title: Настройка клиента Skype для бизнеса в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b89457c35bc9c9c0150b84ab34f4103776206ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="7c55b-102">Настройка взаимодействия с клиентом с помощью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c55b-103">_**Последнее изменение темы:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="7c55b-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="7c55b-104">**Сводка:** В этом разделе описывается настройка взаимодействия с клиентом для пользователей Skype для бизнеса в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c55b-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="7c55b-105">Настроить взаимодействие с клиентом можно только при использовании Lync Server 2013 с накопительным пакетом обновления за декабрь 2014 (5.0.8308.857) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7c55b-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="7c55b-106">Сведения об обновлении Lync Server 2013 можно найти в статье [Updates for Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="7c55b-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="7c55b-107">Skype для бизнеса обеспечивает новый пользовательский интерфейс, основанный на интерфейсе продукта для потребителей Skype.</span><span class="sxs-lookup"><span data-stu-id="7c55b-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="7c55b-108">В дополнение ко всем функциям Lync, Skype для бизнеса предоставляет новые функции с упрощенными элементами управления и привычными значками.</span><span class="sxs-lookup"><span data-stu-id="7c55b-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="7c55b-109">Более подробную информацию о новом интерфейсе клиента можно узнать в статье [Lync to Skype for Business-просмотреть новые](https://go.microsoft.com/fwlink/?linkid=529022)возможности.</span><span class="sxs-lookup"><span data-stu-id="7c55b-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="7c55b-110">Lync Server 2013 поддерживает новый клиентский интерфейс Skype для бизнеса, а также взаимодействие с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="7c55b-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="7c55b-111">Как администратор вы можете выбрать предпочитаемое взаимодействие с клиентом для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="7c55b-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="7c55b-112">Например, вам может потребоваться развернуть взаимодействие с клиентом Lync, пока пользователи в вашей организации не будут полностью прошли обучение в новом интерфейсе Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c55b-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="7c55b-113">Если вы еще не обновили все пользователи в Skype для бизнеса Server 2015, вам может потребоваться, чтобы все пользователи выполняли те же возможности, пока не будут обновлены до нового сервера.</span><span class="sxs-lookup"><span data-stu-id="7c55b-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7c55b-114">Если в вашей организации используется как Skype для бизнеса Server 2015, так и Lync Server 2013, интерфейс по умолчанию будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7c55b-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="7c55b-115">Когда пользователи впервые запускают Skype для бизнеса, они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали пользовательский интерфейс Lync.</span><span class="sxs-lookup"><span data-stu-id="7c55b-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="7c55b-116">Через несколько минут пользователям предлагается перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="7c55b-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="7c55b-117">Дополнительные сведения приведены в разделе <STRONG>поведение клиента при первом запуске</STRONG> далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7c55b-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7c55b-118">Взаимодействие с клиентом Lync 2013 не является возможностью для версий клиентов Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="7c55b-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="7c55b-119">Прежде чем попытаться настроить клиентскую среду для использования клиента Lync 2013, проверьте версию клиента, чтобы убедиться, что она не начинается с номера 16; Пример: 16. КС.КС.КС.</span><span class="sxs-lookup"><span data-stu-id="7c55b-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="7c55b-120">Настройка взаимодействия с клиентом</span><span class="sxs-lookup"><span data-stu-id="7c55b-120">Configure the client experience</span></span>

<span data-ttu-id="7c55b-121">Вы можете указать взаимодействие с клиентом, которые будут отображаться для пользователей в вашей организации с помощью командлета **Set – CSClientPolicy** с параметром EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="7c55b-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="7c55b-122">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей в Организации, на которые влияет Глобальная политика (Помните, что политики сайта или отдельных пользователей переопределяют глобальную политику):</span><span class="sxs-lookup"><span data-stu-id="7c55b-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="7c55b-123">Следующая команда выбирает взаимодействие с клиентом Lync для всех пользователей в Организации, на которые влияет Глобальная политика:</span><span class="sxs-lookup"><span data-stu-id="7c55b-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="7c55b-124">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="7c55b-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="7c55b-125">Если вы хотите настроить взаимодействие с клиентом для определенных пользователей в Организации, можно создать новую политику пользователей с помощью командлета **New – CsClientPolicy** , а затем назначить политику определенным пользователям с помощью командлета **Grant – CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="7c55b-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="7c55b-126">Например, следующая команда создает новую политику клиента (Салесклиентуи), которая выбирает взаимодействие с клиентом Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="7c55b-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="7c55b-127">Следующая команда назначает политику Салесклиентуи всем участникам отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="7c55b-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="7c55b-128">Поведение клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="7c55b-128">First launch client behaviors</span></span>

<span data-ttu-id="7c55b-129">По умолчанию при первом запуске Skype для бизнеса пользователи всегда видят пользовательский интерфейс Skype для бизнеса, даже если вы выбрали взаимодействие с клиентом Lync, присвоив параметру EnableSkypeUI значение $False, как описано выше. .</span><span class="sxs-lookup"><span data-stu-id="7c55b-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="7c55b-130">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="7c55b-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="7c55b-131">Если вы хотите отобразить пользовательский интерфейс Lync, когда пользователи впервые запускают клиент Skype для бизнеса, выполните следующие действия перед обновлением клиента в первый раз:</span><span class="sxs-lookup"><span data-stu-id="7c55b-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="7c55b-132">Убедитесь, что для параметра `EnableSkypeUI` установлено значение $false в используемой вами политике, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="7c55b-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="7c55b-133">Обновление системного реестра на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="7c55b-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="7c55b-134">Это необходимо сделать до первого запуска клиента Skype для бизнеса, чтобы сделать это только один раз.</span><span class="sxs-lookup"><span data-stu-id="7c55b-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="7c55b-135">Сведения о создании объекта групповой политики для обновления реестра на компьютере, присоединенном к домену, приведены далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7c55b-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="7c55b-136">В разделе \*\* \[hKey\_текущего\_пользователя\\\\Microsoft\\Office\\Lync\] \*\* создайте новое **двоичное** значение.</span><span class="sxs-lookup"><span data-stu-id="7c55b-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="7c55b-137">**Параметр name** должен иметь значение **EnableSkypeUI**, а для параметра **Data value** должно быть задано значение **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="7c55b-138">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c55b-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="7c55b-139">Пользовательский интерфейс Lync теперь отображается, когда пользователи впервые запускают клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c55b-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="7c55b-140">Управление отображением руководства на экране приветствия</span><span class="sxs-lookup"><span data-stu-id="7c55b-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="7c55b-141">Когда пользователи открывают клиент Skype для бизнеса, поведением по умолчанию является отображение экрана приветствия, включающего *семь советов, которые запрашивают*пользователи.</span><span class="sxs-lookup"><span data-stu-id="7c55b-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="7c55b-142">Вы можете отключить отображение экрана приветствия, но по-прежнему разрешите пользователям получать доступ к руководству, добавив следующее значение реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="7c55b-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="7c55b-143">В разделе **\\Microsoft\\Office\\15,0\\\_\_\\Lync\] текущего пользователя, создайте новое значение DWORD (32-бит). \[** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7c55b-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="7c55b-144">**Параметр name** должен иметь значение **исбасиктуториалсинбюсер**, а для **параметра data value** должно быть задано значение **1**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="7c55b-145">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c55b-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="7c55b-146">Отключение руководства клиента</span><span class="sxs-lookup"><span data-stu-id="7c55b-146">Turn off the client tutorial</span></span>

<span data-ttu-id="7c55b-147">Если вы не хотите, чтобы пользователи могли получить доступ к учебнику, вы можете отключить клиентское руководство со следующим параметром реестра:</span><span class="sxs-lookup"><span data-stu-id="7c55b-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="7c55b-148">В разделе **\\Microsoft\\Office\\15,0\\\_\_\\Lync\] текущего пользователя, создайте новое значение DWORD (32-бит). \[** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7c55b-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="7c55b-149">**Параметр name** должен иметь значение **туториалфеатуринаблед**, а для **параметра data value** должно быть задано значение **0**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="7c55b-150">Чтобы снова включить учебник, установите для параметра **значение значение** **1**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="7c55b-151">Взаимодействие с клиентом по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7c55b-151">Default client experiences</span></span>

<span data-ttu-id="7c55b-152">Если в вашей организации одновременно развернуты Skype для бизнеса Server 2015 и Lync Server, взаимодействие с клиентом зависит от версии сервера и параметра пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="7c55b-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="7c55b-153">В следующей таблице показано начальное взаимодействие с клиентом в зависимости от версии сервера и параметра пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7c55b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c55b-154">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="7c55b-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="7c55b-155">Параметр EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="7c55b-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="7c55b-156">Взаимодействие с клиентом</span><span class="sxs-lookup"><span data-stu-id="7c55b-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-157">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c55b-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="7c55b-158">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7c55b-158">Default</span></span></p></td>
<td><p><span data-ttu-id="7c55b-159">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c55b-160">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c55b-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="7c55b-161">Верно</span><span class="sxs-lookup"><span data-stu-id="7c55b-161">True</span></span></p></td>
<td><p><span data-ttu-id="7c55b-162">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-163">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c55b-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="7c55b-164">False</span><span class="sxs-lookup"><span data-stu-id="7c55b-164">False</span></span></p></td>
<td><p><span data-ttu-id="7c55b-165">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="7c55b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c55b-166">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="7c55b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-167">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7c55b-167">Default</span></span></p></td>
<td><p><span data-ttu-id="7c55b-168">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="7c55b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-169">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="7c55b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-170">Верно</span><span class="sxs-lookup"><span data-stu-id="7c55b-170">True</span></span></p></td>
<td><p><span data-ttu-id="7c55b-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c55b-172">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="7c55b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-173">False</span><span class="sxs-lookup"><span data-stu-id="7c55b-173">False</span></span></p></td>
<td><p><span data-ttu-id="7c55b-174">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="7c55b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-175">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="7c55b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-176">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7c55b-176">Default</span></span></p></td>
<td><p><span data-ttu-id="7c55b-177">Пользователь запросил переключиться на интерфейс взаимодействия с клиентом Lync (пользователь не может переключиться на Skype для бизнеса позже)</span><span class="sxs-lookup"><span data-stu-id="7c55b-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c55b-178">В следующей таблице показано взаимодействие с клиентом, когда администратор изменяет первоначальный параметр интерфейса Skype для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="7c55b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c55b-179">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="7c55b-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="7c55b-180">Параметры пользовательского интерфейса Skype</span><span class="sxs-lookup"><span data-stu-id="7c55b-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="7c55b-181">Пользовательский интерфейс клиента = Lync</span><span class="sxs-lookup"><span data-stu-id="7c55b-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="7c55b-182">Пользовательский интерфейс клиента = Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-183">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c55b-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="7c55b-184">Верно</span><span class="sxs-lookup"><span data-stu-id="7c55b-184">True</span></span></p></td>
<td><p><span data-ttu-id="7c55b-185">Пользователь запросил переключиться на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="7c55b-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c55b-187">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c55b-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="7c55b-188">False</span><span class="sxs-lookup"><span data-stu-id="7c55b-188">False</span></span></p></td>
<td><p><span data-ttu-id="7c55b-189">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="7c55b-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="7c55b-190">Пользователь запросил переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="7c55b-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-191">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="7c55b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-192">Верно</span><span class="sxs-lookup"><span data-stu-id="7c55b-192">True</span></span></p></td>
<td><p><span data-ttu-id="7c55b-193">Пользователь запросил переключиться на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="7c55b-194">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c55b-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c55b-195">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="7c55b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-196">False</span><span class="sxs-lookup"><span data-stu-id="7c55b-196">False</span></span></p></td>
<td><p><span data-ttu-id="7c55b-197">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="7c55b-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="7c55b-198">Пользователь запросил переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="7c55b-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c55b-199">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="7c55b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7c55b-200">Default</span></span></p></td>
<td><p><span data-ttu-id="7c55b-201">Режим Lync (не удается переключиться на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="7c55b-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="7c55b-202">Пользовательский интерфейс Lync (не удается переключиться на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="7c55b-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c55b-203">Для управления конфигурацией клиента Skype для бизнеса требуются следующие версии исправлений:</span><span class="sxs-lookup"><span data-stu-id="7c55b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="7c55b-204">Lync Server 2010-Февраль 2015 накопительный пакет обновления (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7c55b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="7c55b-205">Дополнительные сведения см. в статье [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="7c55b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="7c55b-206">Lync Server 2013 – накопительный пакет обновления (5.0.8308.857) для Lync Server 2013, 2014 декабря.</span><span class="sxs-lookup"><span data-stu-id="7c55b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="7c55b-207">Сведения о том, как найти [Обновление для Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="7c55b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="7c55b-208">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="7c55b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="7c55b-209">Обновление реестра для отображения взаимодействия с клиентом Lync при первом запуске клиента Skype для бизнеса следует выполнять только один раз.</span><span class="sxs-lookup"><span data-stu-id="7c55b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="7c55b-210">Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения вместо обновления данных значения.</span><span class="sxs-lookup"><span data-stu-id="7c55b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="7c55b-211">При применении объекта групповой политики, если новое значение не существует, объект групповой политики создаст его и присвойте параметру значение 0.</span><span class="sxs-lookup"><span data-stu-id="7c55b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="7c55b-212">В следующей процедуре описывается, как изменить реестр таким образом, чтобы взаимодействие с клиентом Lync отображалось при первом запуске пользователя в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c55b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="7c55b-213">Эту процедуру можно также использовать для обновления реестра, чтобы отключить руководство с экраном приветствия, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="7c55b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="7c55b-214">**Создание объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="7c55b-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="7c55b-215">Запустите **консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="7c55b-216">Сведения о том, как использовать консоль управления групповыми политиками, можно найти в разделе [консоль управления групповыми](https://go.microsoft.com/fwlink/?linkid=532759)политиками.</span><span class="sxs-lookup"><span data-stu-id="7c55b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="7c55b-217">Щелкните правой кнопкой мыши узел **объекты групповой политики** и выберите команду **создать** в меню.</span><span class="sxs-lookup"><span data-stu-id="7c55b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="7c55b-218">В диалоговом окне **Создание объекта групповой политики** введите имя объекта групповой политики (например, **напримерmakelyncdefaultui**), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="7c55b-219">Щелкните правой кнопкой мыши новый объект групповой политики, который вы только что создали, а затем выберите команду **изменить** в меню.</span><span class="sxs-lookup"><span data-stu-id="7c55b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="7c55b-220">В **редакторе управления групповыми политиками**последовательно разверните узлы **Конфигурация пользователя**, параметры, **Параметры Windows** **, а**затем выберите узел **Реестр** .</span><span class="sxs-lookup"><span data-stu-id="7c55b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="7c55b-221">Щелкните правой кнопкой мыши узел **реестра** и выберите **создать** \> **элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="7c55b-222">В диалоговом окне **новые свойства реестра** обновите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="7c55b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7c55b-223">Поле</span><span class="sxs-lookup"><span data-stu-id="7c55b-223">Field</span></span></th>
    <th><span data-ttu-id="7c55b-224">Значение для выбора или ввода</span><span class="sxs-lookup"><span data-stu-id="7c55b-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7c55b-225"><strong>Действие</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-226"><strong>создание</strong>;</span><span class="sxs-lookup"><span data-stu-id="7c55b-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c55b-227"><strong>Куст</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="7c55b-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c55b-229"><strong>Путь к разделу</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-230">софтваре\микрософт\оффице\линк</span><span class="sxs-lookup"><span data-stu-id="7c55b-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c55b-231"><strong>Имя значения</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="7c55b-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c55b-233"><strong>Тип значения</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="7c55b-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c55b-235"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="7c55b-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c55b-236">00000001</span><span class="sxs-lookup"><span data-stu-id="7c55b-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="7c55b-237">Нажмите кнопку **ОК** , чтобы сохранить изменения, а затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="7c55b-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="7c55b-238">Затем необходимо связать созданный объект групповой политики с группой пользователей, которой необходимо назначить политику, например подразделению.</span><span class="sxs-lookup"><span data-stu-id="7c55b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="7c55b-239">**Использование объекта групповой политики для назначения политики**</span><span class="sxs-lookup"><span data-stu-id="7c55b-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="7c55b-240">В консоли управления групповыми политиками щелкните правой кнопкой мыши подразделение, которому требуется назначить политику, а затем выберите команду **связать с существующим объектом групповой**политики.</span><span class="sxs-lookup"><span data-stu-id="7c55b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="7c55b-241">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7c55b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="7c55b-242">На компьютере конечного пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c55b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="7c55b-243">**gpupdate/Target: User**</span><span class="sxs-lookup"><span data-stu-id="7c55b-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="7c55b-244">Сообщение "обновление политики..." отображается, когда применяется объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="7c55b-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="7c55b-245">После выполнения этой процедуры отображается сообщение "обновление политики пользователя успешно завершено".</span><span class="sxs-lookup"><span data-stu-id="7c55b-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="7c55b-246">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7c55b-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="7c55b-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="7c55b-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="7c55b-248">Отобразится раздел "назначенные объекты групповой политики" с именем созданного ниже объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="7c55b-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="7c55b-249">Вы также можете убедиться, что объект групповой политики успешно обновил реестр на компьютере пользователя, изучив реестр.</span><span class="sxs-lookup"><span data-stu-id="7c55b-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="7c55b-250">Откройте редактор реестра и перейдите к \*\* \[разделу\_текущий\_пользователь\\программное\\обеспечение\\\\Microsoft\] Office Lync\*\* .</span><span class="sxs-lookup"><span data-stu-id="7c55b-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="7c55b-251">Если объект групповой политики успешно обновил реестр, отобразится значение с именем EnableSkypeUI и значением 0.</span><span class="sxs-lookup"><span data-stu-id="7c55b-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

