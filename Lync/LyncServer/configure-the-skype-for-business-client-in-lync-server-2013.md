---
title: Настройка клиента Skype для бизнеса в Lync Server 2013
description: Настройка клиента Skype для бизнеса в Lync Server 2013.
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
ms.openlocfilehash: c7f75ae0fa61d9048991934a0ecce7a886079961
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542975"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="0e5aa-103">Настройка взаимодействия с клиентом с помощью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-103">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e5aa-104">_**Последнее изменение темы:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="0e5aa-104">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="0e5aa-105">**Сводка:** В этом разделе описывается настройка взаимодействия с клиентом для пользователей Skype для бизнеса в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-105">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="0e5aa-106">Настроить взаимодействие с клиентом можно только при использовании Lync Server 2013 с накопительным пакетом обновления за декабрь 2014 (5.0.8308.857) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-106">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="0e5aa-107">Сведения об обновлении Lync Server 2013 можно найти в статье [Updates for Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="0e5aa-107">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="0e5aa-108">Skype для бизнеса обеспечивает новый пользовательский интерфейс, основанный на интерфейсе продукта для потребителей Skype.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-108">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="0e5aa-109">В дополнение ко всем функциям Lync, Skype для бизнеса предоставляет новые функции с упрощенными элементами управления и привычными значками.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-109">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="0e5aa-110">Более подробную информацию о новом интерфейсе клиента можно узнать в статье [Lync to Skype for Business-просмотреть новые](https://go.microsoft.com/fwlink/?linkid=529022)возможности.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-110">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="0e5aa-111">Lync Server 2013 поддерживает новый клиентский интерфейс Skype для бизнеса, а также взаимодействие с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-111">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="0e5aa-112">Как администратор вы можете выбрать предпочитаемое взаимодействие с клиентом для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-112">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="0e5aa-113">Например, вам может потребоваться развернуть взаимодействие с клиентом Lync, пока пользователи в вашей организации не будут полностью прошли обучение в новом интерфейсе Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-113">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="0e5aa-114">Если вы еще не обновили все пользователи в Skype для бизнеса Server 2015, вам может потребоваться, чтобы все пользователи выполняли те же возможности, пока не будут обновлены до нового сервера.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-114">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e5aa-115">Если в вашей организации используется как Skype для бизнеса Server 2015, так и Lync Server 2013, интерфейс по умолчанию будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-115">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="0e5aa-116">Когда пользователи впервые запускают Skype для бизнеса, они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали пользовательский интерфейс Lync.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-116">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="0e5aa-117">Через несколько минут пользователям предлагается перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-117">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="0e5aa-118">Дополнительные сведения приведены в разделе <STRONG>поведение клиента при первом запуске</STRONG> далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-118">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0e5aa-119">Взаимодействие с клиентом Lync 2013 не является возможностью для версий клиентов Skype для бизнеса 2016.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-119">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="0e5aa-120">Прежде чем попытаться настроить клиентскую среду для использования клиента Lync 2013, проверьте версию клиента, чтобы убедиться, что она не начинается с номера 16; Пример: 16. КС.КС.КС.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-120">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="0e5aa-121">Настройка взаимодействия с клиентом</span><span class="sxs-lookup"><span data-stu-id="0e5aa-121">Configure the client experience</span></span>

<span data-ttu-id="0e5aa-122">Вы можете указать взаимодействие с клиентом, которые будут отображаться для пользователей в вашей организации с помощью командлета **Set – CSClientPolicy** с параметром EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-122">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="0e5aa-123">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей в Организации, на которые влияет Глобальная политика (Помните, что политики сайта или отдельных пользователей переопределяют глобальную политику):</span><span class="sxs-lookup"><span data-stu-id="0e5aa-123">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="0e5aa-124">Следующая команда выбирает взаимодействие с клиентом Lync для всех пользователей в Организации, на которые влияет Глобальная политика:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-124">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="0e5aa-125">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-125">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="0e5aa-126">Если вы хотите настроить взаимодействие с клиентом для определенных пользователей в Организации, можно создать новую политику пользователей с помощью командлета **New – CsClientPolicy** , а затем назначить политику определенным пользователям с помощью командлета **Grant – CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="0e5aa-126">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="0e5aa-127">Например, следующая команда создает новую политику клиента (Салесклиентуи), которая выбирает взаимодействие с клиентом Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-127">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="0e5aa-128">Следующая команда назначает политику Салесклиентуи всем участникам отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-128">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="0e5aa-129">Поведение клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="0e5aa-129">First launch client behaviors</span></span>

<span data-ttu-id="0e5aa-130">По умолчанию при первом запуске Skype для бизнеса он всегда будет отображаться в пользовательском интерфейсе Skype для бизнеса, даже если вы выбрали взаимодействие с клиентом Lync, присвоив параметру EnableSkypeUI значение $False, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-130">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="0e5aa-131">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-131">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="0e5aa-132">Если вы хотите отобразить пользовательский интерфейс Lync, когда пользователи впервые запускают клиент Skype для бизнеса, выполните следующие действия перед обновлением клиента в первый раз:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-132">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="0e5aa-133">Убедитесь, что для параметра установлено значение `EnableSkypeUI` $false в используемой вами политике, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-133">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="0e5aa-134">Обновление системного реестра на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-134">Update the system registry on the user's computer.</span></span> <span data-ttu-id="0e5aa-135">Это необходимо сделать до первого запуска клиента Skype для бизнеса, чтобы сделать это только один раз.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-135">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="0e5aa-136">Сведения о создании объекта групповой политики для обновления реестра на компьютере, присоединенном к домену, приведены далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-136">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="0e5aa-137">В разделе \*\* \[ hKey \_ текущего \_ пользователя \\ \\ Microsoft \\ Office \\ Lync \] \*\* создайте новое **двоичное** значение.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-137">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="0e5aa-138">**Параметр name** должен иметь значение **EnableSkypeUI**, а для параметра **Data value** должно быть задано значение **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-138">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="0e5aa-139">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-139">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="0e5aa-140">Пользовательский интерфейс Lync теперь отображается, когда пользователи впервые запускают клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-140">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="0e5aa-141">Управление отображением руководства на экране приветствия</span><span class="sxs-lookup"><span data-stu-id="0e5aa-141">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="0e5aa-142">Когда пользователи открывают клиент Skype для бизнеса, поведением по умолчанию является отображение экрана приветствия, включающего *семь советов, которые запрашивают*пользователи.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-142">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="0e5aa-143">Вы можете отключить отображение экрана приветствия, но по-прежнему разрешите пользователям получать доступ к руководству, добавив следующее значение реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-143">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="0e5aa-144">В разделе \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] текущего пользователя\*\* , создайте новое **значение DWORD (32-бит)**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-144">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="0e5aa-145">**Параметр name** должен иметь значение **исбасиктуториалсинбюсер**, а для **параметра data value** должно быть задано значение **1**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-145">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="0e5aa-146">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-146">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="0e5aa-147">Отключение руководства клиента</span><span class="sxs-lookup"><span data-stu-id="0e5aa-147">Turn off the client tutorial</span></span>

<span data-ttu-id="0e5aa-148">Если вы не хотите, чтобы пользователи могли получить доступ к учебнику, вы можете отключить клиентское руководство со следующим параметром реестра:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-148">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="0e5aa-149">В разделе \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] текущего пользователя\*\* , создайте новое **значение DWORD (32-бит)**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-149">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="0e5aa-150">**Параметр name** должен иметь значение **туториалфеатуринаблед**, а для **параметра data value** должно быть задано значение **0**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-150">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="0e5aa-151">Чтобы снова включить учебник, установите для параметра **значение значение** **1**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-151">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="0e5aa-152">Взаимодействие с клиентом по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0e5aa-152">Default client experiences</span></span>

<span data-ttu-id="0e5aa-153">Если в вашей организации одновременно развернуты Skype для бизнеса Server 2015 и Lync Server, взаимодействие с клиентом зависит от версии сервера и параметра пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-153">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="0e5aa-154">В следующей таблице показано начальное взаимодействие с клиентом в зависимости от версии сервера и параметра пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-154">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0e5aa-155">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="0e5aa-155">Server version</span></span></p></th>
<th><p><span data-ttu-id="0e5aa-156">Параметр EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="0e5aa-156">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="0e5aa-157">Взаимодействие с клиентом</span><span class="sxs-lookup"><span data-stu-id="0e5aa-157">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-158">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e5aa-158">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-159">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="0e5aa-159">Default</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-160">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-160">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e5aa-161">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e5aa-161">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-162">Верно</span><span class="sxs-lookup"><span data-stu-id="0e5aa-162">True</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-163">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-163">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e5aa-164">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-165">False</span><span class="sxs-lookup"><span data-stu-id="0e5aa-165">False</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-166">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-166">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e5aa-167">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-167">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-168">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="0e5aa-168">Default</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-169">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-169">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-170">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-170">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-171">Верно</span><span class="sxs-lookup"><span data-stu-id="0e5aa-171">True</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-172">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-172">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e5aa-173">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-173">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-174">False</span><span class="sxs-lookup"><span data-stu-id="0e5aa-174">False</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-175">Пользователь запросил переключение в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените значение параметра UI на $true)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-175">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-176">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-176">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-177">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="0e5aa-177">Default</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-178">Пользователь запросил переключиться на интерфейс взаимодействия с клиентом Lync (пользователь не может переключиться на Skype для бизнеса позже)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-178">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e5aa-179">В следующей таблице показано взаимодействие с клиентом, когда администратор изменяет первоначальный параметр интерфейса Skype для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-179">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0e5aa-180">Версия сервера</span><span class="sxs-lookup"><span data-stu-id="0e5aa-180">Server version</span></span></p></th>
<th><p><span data-ttu-id="0e5aa-181">Параметры пользовательского интерфейса Skype</span><span class="sxs-lookup"><span data-stu-id="0e5aa-181">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="0e5aa-182">Пользовательский интерфейс клиента = Lync</span><span class="sxs-lookup"><span data-stu-id="0e5aa-182">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="0e5aa-183">Пользовательский интерфейс клиента = Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-183">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-184">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e5aa-184">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-185">Верно</span><span class="sxs-lookup"><span data-stu-id="0e5aa-185">True</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-186">Пользователь запросил переключиться на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-186">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-187">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-187">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e5aa-188">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e5aa-188">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-189">False</span><span class="sxs-lookup"><span data-stu-id="0e5aa-189">False</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-190">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="0e5aa-190">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-191">Пользователь запросил переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="0e5aa-191">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-192">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-192">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-193">Верно</span><span class="sxs-lookup"><span data-stu-id="0e5aa-193">True</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-194">Пользователь запросил переключиться на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-194">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-195">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e5aa-195">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e5aa-196">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-196">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-197">False</span><span class="sxs-lookup"><span data-stu-id="0e5aa-197">False</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-198">Пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="0e5aa-198">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-199">Пользователь запросил переключиться на пользовательский интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="0e5aa-199">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e5aa-200">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-200">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-201">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="0e5aa-201">Default</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-202">Режим Lync (не удается переключиться на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-202">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="0e5aa-203">Пользовательский интерфейс Lync (не удается переключиться на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-203">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e5aa-204">Для управления конфигурацией клиента Skype для бизнеса требуются следующие версии исправлений:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-204">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="0e5aa-205">Lync Server 2010-Февраль 2015 накопительный пакет обновления (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-205">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="0e5aa-206">Дополнительные сведения см. в статье [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="0e5aa-206">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="0e5aa-207">Lync Server 2013 – накопительный пакет обновления (5.0.8308.857) для Lync Server 2013, 2014 декабря.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-207">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="0e5aa-208">Сведения о том, как найти [Обновление для Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="0e5aa-208">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="0e5aa-209">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="0e5aa-209">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="0e5aa-210">Обновление реестра для отображения взаимодействия с клиентом Lync при первом запуске клиента Skype для бизнеса следует выполнять только один раз.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-210">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="0e5aa-211">Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения вместо обновления данных значения.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-211">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="0e5aa-212">При применении объекта групповой политики, если новое значение не существует, объект групповой политики создаст его и присвойте параметру значение 0.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-212">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="0e5aa-213">В следующей процедуре описывается, как изменить реестр таким образом, чтобы взаимодействие с клиентом Lync отображалось при первом запуске пользователя в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-213">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="0e5aa-214">Эту процедуру можно также использовать для обновления реестра, чтобы отключить руководство с экраном приветствия, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-214">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="0e5aa-215">**Создание объекта групповой политики**</span><span class="sxs-lookup"><span data-stu-id="0e5aa-215">**To create the GPO**</span></span>

1.  <span data-ttu-id="0e5aa-216">Запустите **консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-216">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="0e5aa-217">Сведения о том, как использовать консоль управления групповыми политиками, можно найти в разделе [консоль управления групповыми](https://go.microsoft.com/fwlink/?linkid=532759)политиками.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-217">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="0e5aa-218">Щелкните правой кнопкой мыши узел **объекты групповой политики** и выберите команду **создать** в меню.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-218">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="0e5aa-219">В диалоговом окне **Создание объекта групповой политики** введите имя объекта групповой политики (например, **напримерmakelyncdefaultui**), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-219">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0e5aa-220">Щелкните правой кнопкой мыши новый объект групповой политики, который вы только что создали, а затем выберите команду **изменить** в меню.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-220">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="0e5aa-221">В **редакторе управления групповыми политиками**последовательно разверните узлы **Конфигурация пользователя**, параметры, **Параметры Windows** **, а**затем выберите узел **Реестр** .</span><span class="sxs-lookup"><span data-stu-id="0e5aa-221">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="0e5aa-222">Щелкните правой кнопкой мыши узел **реестра** и выберите **создать** \> **элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-222">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="0e5aa-223">В диалоговом окне **новые свойства реестра** обновите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-223">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="0e5aa-224">Поле</span><span class="sxs-lookup"><span data-stu-id="0e5aa-224">Field</span></span></th>
    <th><span data-ttu-id="0e5aa-225">Значение для выбора или ввода</span><span class="sxs-lookup"><span data-stu-id="0e5aa-225">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="0e5aa-226"><strong>Действие</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-226"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-227"><strong>создание</strong>;</span><span class="sxs-lookup"><span data-stu-id="0e5aa-227"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0e5aa-228"><strong>Куст</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-228"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-229">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="0e5aa-229">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0e5aa-230"><strong>Путь к разделу</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-230"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-231">софтваре\микрософт\оффице\линк</span><span class="sxs-lookup"><span data-stu-id="0e5aa-231">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0e5aa-232"><strong>Имя значения</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-232"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-233">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="0e5aa-233">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="0e5aa-234"><strong>Тип значения</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-234"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-235">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="0e5aa-235">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="0e5aa-236"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="0e5aa-236"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="0e5aa-237">00000001</span><span class="sxs-lookup"><span data-stu-id="0e5aa-237">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="0e5aa-238">Нажмите кнопку **ОК** , чтобы сохранить изменения, а затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-238">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="0e5aa-239">Затем необходимо связать созданный объект групповой политики с группой пользователей, которой необходимо назначить политику, например подразделению.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-239">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="0e5aa-240">**Использование объекта групповой политики для назначения политики**</span><span class="sxs-lookup"><span data-stu-id="0e5aa-240">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="0e5aa-241">В консоли управления групповыми политиками щелкните правой кнопкой мыши подразделение, которому требуется назначить политику, а затем выберите команду **связать с существующим объектом групповой**политики.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-241">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="0e5aa-242">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-242">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="0e5aa-243">На компьютере конечного пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-243">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="0e5aa-244">**gpupdate/Target: User**</span><span class="sxs-lookup"><span data-stu-id="0e5aa-244">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="0e5aa-245">Сообщение "обновление политики..." отображается, когда применяется объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-245">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="0e5aa-246">После выполнения этой процедуры отображается сообщение "обновление политики пользователя успешно завершено".</span><span class="sxs-lookup"><span data-stu-id="0e5aa-246">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="0e5aa-247">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0e5aa-247">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="0e5aa-248">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="0e5aa-248">**gpresult /r**</span></span>
    
    <span data-ttu-id="0e5aa-249">Отобразится раздел "назначенные объекты групповой политики" с именем созданного ниже объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-249">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="0e5aa-250">Вы также можете убедиться, что объект групповой политики успешно обновил реестр на компьютере пользователя, изучив реестр.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-250">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="0e5aa-251">Откройте редактор реестра и перейдите к разделу \*\* \[ \_ текущий \_ пользователь \\ программное обеспечение \\ Microsoft \\ Office \\ Lync \] \*\* .</span><span class="sxs-lookup"><span data-stu-id="0e5aa-251">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="0e5aa-252">Если объект групповой политики успешно обновил реестр, отобразится значение с именем EnableSkypeUI и значением 0.</span><span class="sxs-lookup"><span data-stu-id="0e5aa-252">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

