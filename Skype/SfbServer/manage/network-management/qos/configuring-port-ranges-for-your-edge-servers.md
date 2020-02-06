---
title: Настройка диапазонов портов и качества обслуживания пограничных серверов
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье описано, как настроить диапазоны портов для пограничных серверов и как настроить политику качества обслуживания для пограничных серверов/V.
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817438"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="8d0f9-103">Настройка диапазонов портов и политики качества обслуживания для пограничных серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8d0f9-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="8d0f9-104">В этой статье описано, как настроить диапазоны портов для пограничных серверов и как настроить политику качества обслуживания для пограничных серверов/V.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="8d0f9-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="8d0f9-105">Configure port ranges</span></span>

<span data-ttu-id="8d0f9-106">При использовании пограничных серверов вам не нужно настраивать отдельные диапазоны портов для обмена аудио, видео и приложений. Аналогичным образом диапазоны портов, используемые для пограничных серверов, не должны совпадать с диапазонами портов, используемыми для серверов конференций, приложений и исправлений.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="8d0f9-107">Перед тем как приступить к рассмотрению нашего примера, важно не менять диапазоны портов, так как это может негативно сказаться на некоторых сценариях, если вы выйдете из диапазона портов 50000.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="8d0f9-108">Например, предположим, что для использования следующих диапазонов портов настроены серверы конференций, приложений и исправлений:</span><span class="sxs-lookup"><span data-stu-id="8d0f9-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d0f9-109">Тип пакета</span><span class="sxs-lookup"><span data-stu-id="8d0f9-109">Packet Type</span></span></th>
<th><span data-ttu-id="8d0f9-110">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="8d0f9-110">Starting Port</span></span></th>
<th><span data-ttu-id="8d0f9-111">Количество зарезервированных портов</span><span class="sxs-lookup"><span data-stu-id="8d0f9-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d0f9-112">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="8d0f9-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-113">40803</span><span class="sxs-lookup"><span data-stu-id="8d0f9-113">40803</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-114">8348</span><span class="sxs-lookup"><span data-stu-id="8d0f9-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0f9-115">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="8d0f9-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-116">49152</span><span class="sxs-lookup"><span data-stu-id="8d0f9-116">49152</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-117">8348</span><span class="sxs-lookup"><span data-stu-id="8d0f9-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d0f9-118">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="8d0f9-118">Video</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-119">57500</span><span class="sxs-lookup"><span data-stu-id="8d0f9-119">57500</span></span></p></td>
<td><p><span data-ttu-id="8d0f9-120">8034</span><span class="sxs-lookup"><span data-stu-id="8d0f9-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d0f9-121"><strong>Итоги</strong></span><span class="sxs-lookup"><span data-stu-id="8d0f9-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="8d0f9-122">24730</span><span class="sxs-lookup"><span data-stu-id="8d0f9-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8d0f9-123">Как видите, диапазоны портов для обмена аудио, видео и приложениями начинаются с порта 40803 и включают в себя всего 24732 портов.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="8d0f9-124">При желании вы можете настроить этот граничный сервер так, чтобы он использовал эти общие значения порта, выполнив следующую команду в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="8d0f9-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="8d0f9-125">Вы также можете одновременно настроить все пограничные серверы в Организации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="8d0f9-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="8d0f9-126">Вы можете проверить текущие параметры порта для пограничных серверов с помощью командной консоли Skype для Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8d0f9-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="8d0f9-127">Пока мы предоставляем эти параметры, мы настоятельно рекомендуем вам оставить все, что нужно для настройки порта.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="8d0f9-128">Настройка политики качества обслуживания для пограничного сервера/V</span><span class="sxs-lookup"><span data-stu-id="8d0f9-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="8d0f9-129">Кроме того, чтобы создавать политики QoS для конференций, приложений и серверов исправлений, вам также необходимо создать как голосовые, так и видеополитики для внутренней стороны пограничных серверов A/V.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="8d0f9-130">Тем не менее политики, используемые на пограничных серверах, отличаются от политик, используемых на серверах конференц-связи, приложений и исправлений.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="8d0f9-131">Для серверов конференций, приложений и исправлений вы указали диапазон портов источника; При использовании пограничных серверов необходимо указать диапазон портов назначения.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="8d0f9-132">По этой причине вы не можете просто применить политики QoS, приложения и сервера исправлений на пограничных серверах: эти политики просто не работают.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="8d0f9-133">Вместо этого необходимо создать новые политики и применить эти политики только к пограничным серверам.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="8d0f9-134">Ниже описаны действия, которые необходимо выполнить для создания объектов групповой политики Active Directory, которые можно использовать для управления качеством обслуживания на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="8d0f9-135">Разумеется, возможно, что пограничные серверы — это изолированные серверы, у которых нет учетных записей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="8d0f9-136">В этом случае вы можете использовать локальную групповую политику вместо групповой политики Active Directory: Единственная разница заключается в том, что вы должны создавать эти локальные политики с помощью редактора локальных групповых политик и отдельно создавать одинаковый набор политик на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="8d0f9-137">Чтобы запустить редактор локальной групповой политики на пограничном сервере, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="8d0f9-138">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="8d0f9-139">В диалоговом окне " **выполнить** " введите **gpedit. msc**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="8d0f9-140">Если вы создаете политики на основе Active Directory, вы должны войти на компьютер, на котором установлен компонент управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="8d0f9-141">В этом случае откройте управление групповыми политиками (нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **Управление групповой политикой**) и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="8d0f9-142">В разделе Управление групповой политикой найдите контейнер, в котором нужно создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="8d0f9-143">Например, если все серверные компьютеры Skype для бизнеса находятся в подразделении "Skype для бизнеса", в подразделении сервера Skype для бизнеса необходимо создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="8d0f9-144">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **создать объект групповой политики в этом домене и свяжите его**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="8d0f9-145">В диалоговом окне **создание GPO** введите имя нового объекта групповой политики в поле **имя** (например, в **Skype для бизнеса Server Audio**), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="8d0f9-146">Щелкните созданную политику правой кнопкой мыши и выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="8d0f9-147">Здесь процесс идентичен, независимо от того, создается ли вы политика Active Directory или локальная политика.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="8d0f9-148">В редакторе управления групповыми политиками или в редакторе локальных групповых политик разверните раздел **Конфигурация компьютера**, затем — **политики**, разверните раздел **Параметры Windows**, щелкните правой кнопкой мыши службу **QoS на основе политики**, а затем выберите команду **создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="8d0f9-149">В диалоговом окне **QoS на основе политики** на первой странице в поле **имя** введите имя новой политики (например, "звук" в **Skype для бизнеса Server**).</span><span class="sxs-lookup"><span data-stu-id="8d0f9-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="8d0f9-150">Выберите **задать значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="8d0f9-151">Оставьте параметр **задать частоту исходящих подключений** невыбранным и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="8d0f9-152">На следующей странице убедитесь, что выбраны **все приложения** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="8d0f9-153">Этот параметр предписывает сети искать все пакеты с разметкой DSCP для 46, а не только пакеты, созданные определенным приложением.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="8d0f9-154">На третьей странице убедитесь, что выбраны оба **IP-адреса источника** и **конечный IP-адрес** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="8d0f9-155">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, на каком компьютере (IP-адрес) отправили эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="8d0f9-156">На четвертой странице в раскрывающемся списке выберите протокол **TCP и UDP** , который будет **применяться этой политикой QoS** .</span><span class="sxs-lookup"><span data-stu-id="8d0f9-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="8d0f9-157">Протокол TCP и протокол UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Skype для бизнеса Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="8d0f9-158">В разделе заголовков **укажите номер порта назначения**, выберите один **из конечных портов или диапазонов**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="8d0f9-159">В сопроводительном текстовом поле введите диапазон портов, зарезервированный для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="8d0f9-160">Например, если вы зарезервированы порты 49152 через порты 57500 для звукового трафика, введите диапазон портов в следующем формате: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="8d0f9-161">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-161">Click **Finish**.</span></span>

<span data-ttu-id="8d0f9-162">После создания политики QoS для звукового трафика вы должны создать вторую политику для видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="8d0f9-163">Чтобы создать политику для видео, выполните те же действия, что и при создании политики звука, заменив указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="8d0f9-164">Использование другого (и уникального) имени политики (например, в **Skype для бизнеса Server**).</span><span class="sxs-lookup"><span data-stu-id="8d0f9-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="8d0f9-165">Задайте для параметра DSCP значение **34** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="8d0f9-166">(Обратите внимание, что вам не нужно использовать значение DSCP для 34.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="8d0f9-167">Единственным требованием является использование другого значения DSCP для видео, чем вы использовали для звука.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="8d0f9-168">Используйте ранее настроенный диапазон портов для видеоканала.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="8d0f9-169">Например, если вы зарезервированы порты 57501 – 65535 для видео, задайте диапазон портов следующим образом: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="8d0f9-170">Опять же, это значение должно быть задано в качестве диапазона портов назначения.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="8d0f9-171">Если вы решили создать политику для управления трафиком общего доступа к приложениям, необходимо создать третью политику, которая будет выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="8d0f9-172">Используйте другое (и уникальное) имя политики (например, **общий доступ к приложениям в Skype для бизнеса Server**).</span><span class="sxs-lookup"><span data-stu-id="8d0f9-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="8d0f9-173">Задайте для параметра DSCP значение **24** , а не 46.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="8d0f9-174">(Опять же, вам не нужно использовать значение DSCP, равное 24.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="8d0f9-175">Единственным требованием является использование другого значения DSCP для общего пользования приложениями, чем при использовании звука или видео.)</span><span class="sxs-lookup"><span data-stu-id="8d0f9-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="8d0f9-176">Используйте ранее настроенный диапазон портов для видеоканала.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="8d0f9-177">Например, если у вас есть резервированные порты 40803 – 49151 для совместного использования приложений, задайте диапазон портов следующим образом: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="8d0f9-178">Новые политики, созданные вами, вступят в силу только после обновления групповой политики на серверах пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="8d0f9-179">Хотя групповая политика периодически обновляется сама, вы можете обновить ее принудительно, запустив на каждом нужном компьютере следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="8d0f9-180">Эту команду можно выполнить с сервера Skype для бизнеса или из окна команд, которое выполняется в разделе Учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="8d0f9-181">Чтобы открыть такое окно с правами администратора, в меню **Пуск** правой кнопкой мыши щелкните **Командная строка** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="8d0f9-182">Обратите внимание, что при запуске Гпудате. exe может потребоваться перезапуск пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="8d0f9-183">Чтобы убедиться в том, что сетевые пакеты помечены с использованием соответствующего значения DSCP, необходимо также создать новый параметр реестра на каждом компьютере, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="8d0f9-184">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="8d0f9-185">В диалоговом окне **выполнить** введите **regedit**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="8d0f9-186">В редакторе реестра разверните раздел **\_hKey локальный\_компьютер**, разверните раздел **система**, разверните **куррентконтролсет**, затем — **службы**, а затем — значок **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="8d0f9-187">Щелкните правой кнопкой мыши **tcpip**, наведите указатель на пункт **создать**и выберите **клавишу**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="8d0f9-188">После создания нового раздела реестра введите **QoS**и нажмите КЛАВИШу ввод, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="8d0f9-189">Щелкните правой кнопкой мыши **QoS**, наведите указатель на пункт **создать**и выберите **строковое значение**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="8d0f9-190">После создания нового значения реестра введите команду не **использовать NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="8d0f9-191">Дважды щелкните пункт **не использовать NLA**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="8d0f9-192">В диалоговом окне **изменение строки** введите **1** в поле **значение** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="8d0f9-193">Закройте редактор реестра и перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="8d0f9-193">Close the Registry Editor and reboot your computer.</span></span>
