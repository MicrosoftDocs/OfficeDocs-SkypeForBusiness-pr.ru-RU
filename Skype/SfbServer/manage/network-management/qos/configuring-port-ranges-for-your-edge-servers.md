---
title: Настройка диапазонов портов и качества обслуживания для ваших серверов
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье описывается, как настроить диапазоны портов для edge Servers и как настроить политику качества обслуживания для ваших серверов A/V Edge.
ms.openlocfilehash: c88f784fe1956fa16b8464caa4f9f26e5c61005e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832909"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="aed47-103">Настройка диапазонов портов и политики качества обслуживания для ваших серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="aed47-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="aed47-104">В этой статье описывается, как настроить диапазоны портов для edge Servers и как настроить политику качества обслуживания для ваших серверов A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="aed47-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="aed47-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="aed47-105">Configure port ranges</span></span>

<span data-ttu-id="aed47-106">С помощью edge-серверов не нужно настраивать отдельные диапазоны портов для общего доступа к звукам, видео и приложениям; Аналогичным образом, диапазоны портов, используемые для серверов-посредников, не должны совпадать с диапазонами портов, используемыми для серверов conferencing, Application и Mediation.</span><span class="sxs-lookup"><span data-stu-id="aed47-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="aed47-107">Прежде чем приступить к нашему примеру, важно подчеркнуть, что, хотя этот параметр существует, мы не рекомендуем изменять диапазоны портов, так как это может отрицательно сказаться на некоторых сценариях при выходе из диапазона портов 50000.</span><span class="sxs-lookup"><span data-stu-id="aed47-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="aed47-108">Например, предположим, что серверы конференций, приложений и сервер-посредник настроены для использования следующих портов.</span><span class="sxs-lookup"><span data-stu-id="aed47-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aed47-109">Тип пакета</span><span class="sxs-lookup"><span data-stu-id="aed47-109">Packet Type</span></span></th>
<th><span data-ttu-id="aed47-110">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="aed47-110">Starting Port</span></span></th>
<th><span data-ttu-id="aed47-111">Количество зарезервированных портов</span><span class="sxs-lookup"><span data-stu-id="aed47-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aed47-112">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="aed47-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="aed47-113">40803</span><span class="sxs-lookup"><span data-stu-id="aed47-113">40803</span></span></p></td>
<td><p><span data-ttu-id="aed47-114">8348</span><span class="sxs-lookup"><span data-stu-id="aed47-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aed47-115">"Audio" (Аудио);</span><span class="sxs-lookup"><span data-stu-id="aed47-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="aed47-116">49152</span><span class="sxs-lookup"><span data-stu-id="aed47-116">49152</span></span></p></td>
<td><p><span data-ttu-id="aed47-117">8348</span><span class="sxs-lookup"><span data-stu-id="aed47-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aed47-118">Видео</span><span class="sxs-lookup"><span data-stu-id="aed47-118">Video</span></span></p></td>
<td><p><span data-ttu-id="aed47-119">57500</span><span class="sxs-lookup"><span data-stu-id="aed47-119">57500</span></span></p></td>
<td><p><span data-ttu-id="aed47-120">8034</span><span class="sxs-lookup"><span data-stu-id="aed47-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aed47-121"><strong>Итоги</strong></span><span class="sxs-lookup"><span data-stu-id="aed47-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="aed47-122">24730</span><span class="sxs-lookup"><span data-stu-id="aed47-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aed47-123">Как видно, диапазоны портов для общего доступа к звукам, видео и приложениям начинаются с порта 40803 и включают в себя 24732 порта.</span><span class="sxs-lookup"><span data-stu-id="aed47-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="aed47-124">При этом можно настроить указанный сервер на использование этих общих значений портов, выдав команду, аналогичную этой, в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="aed47-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="aed47-125">Можно также одновременно настроить все пограничные серверы в организации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="aed47-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="aed47-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span><span class="sxs-lookup"><span data-stu-id="aed47-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="aed47-127">Опять же, хотя мы предоставляем эти параметры, мы настоятельно рекомендуем оставить все как есть для конфигурации порта.</span><span class="sxs-lookup"><span data-stu-id="aed47-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="aed47-128">Настройка политики QoS для ваших серверов A/V Edge</span><span class="sxs-lookup"><span data-stu-id="aed47-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="aed47-129">Помимо создания политик QoS для серверов аудио- и видеоконференций, приложений и серверов-посредников, необходимо также создать политики аудио- и видеосвязи для внутренней стороны ваших серверов аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="aed47-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="aed47-130">Однако политики, используемые на ваших серверах, отличаются от политик, используемых на серверах conferencing, Application и Mediation.</span><span class="sxs-lookup"><span data-stu-id="aed47-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="aed47-131">Для серверов-служб, приложений и серверов-посредников указан диапазон исходных портов; с помощью edge-серверов необходимо указать диапазон портов назначения.</span><span class="sxs-lookup"><span data-stu-id="aed47-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="aed47-132">Из-за этого нельзя просто применить политики QoS сервера-посредника и службы приложений к своим серверам-посредникам: эти политики просто не будут работать.</span><span class="sxs-lookup"><span data-stu-id="aed47-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="aed47-133">Вместо этого необходимо создать новые политики и применить их только к своим серверам.</span><span class="sxs-lookup"><span data-stu-id="aed47-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="aed47-134">В приведенной ниже процедуре описан процесс создания объектов групповой политики Active Directory, которые могут использоваться для управления качеством обслуживания на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="aed47-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="aed47-135">Конечно, возможно, что ваши пограничные серверы являются автономными серверами без учетных записей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aed47-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="aed47-136">В этом случае можно использовать локальную групповую политику вместо групповой политики Active Directory: единственное различие состоит в том, что необходимо создать эти локальные политики с помощью редактора локальной групповой политики, и нужно отдельно создавать один и тот же набор политик на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="aed47-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="aed47-137">Чтобы запустить редактор локальных групповых политик на сервере, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="aed47-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="aed47-138">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="aed47-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="aed47-139">В **диалоговом** окне "Выполнить" введите **gpedit.msc** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="aed47-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="aed47-140">Если вы создаете политику на основе Active Directory, войдите на компьютер, где установлен компонент управления групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="aed47-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="aed47-141">В этом случае откройте управление групповой политикой (нажмите кнопку "Начните", выберите пункт "Администрирование", а затем щелкните "Управление групповой политикой"), а затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="aed47-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="aed47-142">В консоли управления групповыми политиками найдите контейнер, в котором следует создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="aed47-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="aed47-143">Например, если все компьютеры Skype для бизнеса Server находятся в OU Под названием Skype для бизнеса Server, новую политику следует создать в OU Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="aed47-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="aed47-144">Щелкните правой кнопкой мыши соответствующий контейнер и выберите "Создать **GPO в этом** домене" и связать его здесь.</span><span class="sxs-lookup"><span data-stu-id="aed47-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="aed47-145">В **диалоговом** окне "Новый объект групповой политики"  введите имя нового объекта групповой политики в поле "Имя" (например, Skype для бизнеса **Server Audio),** а затем нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="aed47-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="aed47-146">Щелкните правой кнопкой мыши созданную политику и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="aed47-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="aed47-147">С этого момента процесс одинаков независимо от того, создаете ли вы политику Active Directory или локальную политику:</span><span class="sxs-lookup"><span data-stu-id="aed47-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="aed47-148">В редакторе управления групповой политикой или редакторе локальной групповой политики последовательно разверните узлы **Конфигурация компьютера**, **Политики**, **Параметры Windows**, щелкните правой кнопкой мыши **QoS на основе политики**, а затем щелкните **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="aed47-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="aed47-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio)** in the **Name** box.</span><span class="sxs-lookup"><span data-stu-id="aed47-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="aed47-150">Выберите поле **Укажите значение DSCP** и установите значение **46**.</span><span class="sxs-lookup"><span data-stu-id="aed47-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="aed47-151">Оставьте поле **Укажите частоту передачи** пустым и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aed47-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="aed47-152">На следующей странице убедитесь, что выбраны все приложения, и нажмите кнопку **"Далее".** </span><span class="sxs-lookup"><span data-stu-id="aed47-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="aed47-153">Этот параметр дает указание сети искать все пакеты со значением DSCP 46, а не только пакеты, созданные определенным приложением.</span><span class="sxs-lookup"><span data-stu-id="aed47-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="aed47-154">На третьей странице убедитесь, что выбраны  как любой исходный **IP-адрес,** так и любой адрес назначения, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="aed47-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="aed47-155">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, с какого компьютера (IP-адреса) отправляются эти пакеты, и какой компьютер (IP-адрес) будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="aed47-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="aed47-156">На четвертой странице выберите **TCP и UDP** в раскрывающемся списке **Выберите протокол, к которому применяется политика QoS**.</span><span class="sxs-lookup"><span data-stu-id="aed47-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="aed47-157">TCP (Transmission Control Protocol) и UDP (User Datagram Protocol) — это два сетевых протокола, которые чаще всего используются в Skype для бизнеса Server и его клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="aed47-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="aed47-158">Под заголовком **Укажите номер порта назначения** выберите **От этого порта или диапазона назначения**.</span><span class="sxs-lookup"><span data-stu-id="aed47-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="aed47-159">В соответствующем текстовом поле введите диапазон портов, зарезервированный для передачи аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="aed47-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="aed47-160">Например, если вы зарезервировали порты от 49152 до портов 57500 для аудио-трафика, введите диапазон портов в таком формате: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="aed47-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="aed47-161">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="aed47-161">Click **Finish**.</span></span>

<span data-ttu-id="aed47-162">После создания политики QoS для аудио-трафика следует создать вторую политику для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="aed47-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="aed47-163">Чтобы создать политику для видео, выполните ту же процедуру, которая использовалась для создания политики звука, сделав следующие замены.</span><span class="sxs-lookup"><span data-stu-id="aed47-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="aed47-164">Используйте другое (и уникальное) имя политики (например, **Skype для бизнеса Server Video).**</span><span class="sxs-lookup"><span data-stu-id="aed47-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="aed47-p113">Для значения DSCP вместо 46 укажите **34**. (Следует отметить, что вы не обязаны использовать значение DSCP 34. Единственное требование состоит в том, что для видео и звука должны использоваться разные значения DSCP.)</span><span class="sxs-lookup"><span data-stu-id="aed47-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="aed47-168">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="aed47-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="aed47-169">Например, если для видео зарезервированы порты от 57501 до 65535, установите диапазон портов: **57501:65535.**</span><span class="sxs-lookup"><span data-stu-id="aed47-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="aed47-170">Опять же, этот диапазон нужно настроить как диапазона портов назначения.</span><span class="sxs-lookup"><span data-stu-id="aed47-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="aed47-171">Если вы решили создать политику для управления трафиком общего доступа к приложениям, необходимо создать третью политику, сделав следующие замены:</span><span class="sxs-lookup"><span data-stu-id="aed47-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="aed47-172">Используйте другое (и уникальное) имя политики (например, Общий доступ к приложениям Skype для бизнеса **Server).**</span><span class="sxs-lookup"><span data-stu-id="aed47-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="aed47-p115">Для значения DSCP вместо 46 укажите **24**. (Еще раз, вы не обязаны использовать значение DSCP 24. Единственное требование состоит в том, что для общего доступа к приложениям должно использоваться значение DSCP, отличное от используемого для звука или видео.)</span><span class="sxs-lookup"><span data-stu-id="aed47-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="aed47-176">Используйте ранее настроенный диапазон портов для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="aed47-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="aed47-177">Например, если вы зарезервировали порты с 40803 по 49151 для общего доступа к приложениям, установите диапазон портов: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="aed47-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="aed47-p117">Созданные политики не вступят в силу до обновления групповой политики на пограничных серверах. Хотя групповая политика периодически обновляется самостоятельно, вы можете обновить ее принудительно, выполнив следующую команду на каждом компьютере, на котором требуется обновить групповую политику:</span><span class="sxs-lookup"><span data-stu-id="aed47-p117">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="aed47-180">Эту команду можно выполнить из Skype для бизнеса Server или из любого командного окна, запущенного с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="aed47-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="aed47-181">Для запуска окна командной строки с учетными данными администратора нажмите кнопку **Пуск**, щелкните правой кнопкой **Командная строка**, а затем выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="aed47-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="aed47-182">Учтите, что вам может потребоваться перезапустить пограничный сервер после выполнения Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="aed47-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="aed47-183">Чтобы обеспечить отметку сетевых пакетов соответствующим значением DSCP, необходимо также создать новый раздел реестра, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="aed47-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="aed47-184">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="aed47-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="aed47-185">В **диалоговом** окне "Выполнить" введите **regedit** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="aed47-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="aed47-186">В редакторе реестра развертка **HKEY \_ LOCAL \_ MACHINE,** развернуть **SYSTEM,** **развернуть CurrentControlSet,** развернуть службы, а затем развернуть **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="aed47-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="aed47-187">Щелкните правой кнопкой пункт **Tcpip**, выберите **Создать**, затем щелкните **Раздел**.</span><span class="sxs-lookup"><span data-stu-id="aed47-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="aed47-188">После создания нового ключа реестра введите **QoS** и нажмите клавишу ВВОД, чтобы переименовать ключ.</span><span class="sxs-lookup"><span data-stu-id="aed47-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="aed47-189">Щелкните правой кнопкой мыши **QoS**, выберите пункт **Создать**, затем щелкните **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="aed47-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="aed47-190">После создания нового значения реестра введите "Не использовать **NLA"** и нажмите ввод, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="aed47-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="aed47-191">Дважды щелкните **Do no use NLA**.</span><span class="sxs-lookup"><span data-stu-id="aed47-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="aed47-192">В **диалоговом окне** "Изменение  строки" введите **1** в поле данных "Значение" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="aed47-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="aed47-193">Закройте редактор реестра и перезагружайте компьютер.</span><span class="sxs-lookup"><span data-stu-id="aed47-193">Close the Registry Editor and reboot your computer.</span></span>
