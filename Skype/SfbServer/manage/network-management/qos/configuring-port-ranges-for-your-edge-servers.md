---
title: Настройка диапазонов портов и качества обслуживания для пограничных серверов
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описывается настройка диапазонов портов для пограничных серверов и настройка политики качества обслуживания для вашей A / V пограничных серверов.
ms.openlocfilehash: 38fb71f995b1e4569b1bae11cc809ff0c5b358cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913078"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="2ea6c-103">Настройка диапазонов портов и политики качества обслуживания для пограничных серверов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2ea6c-103">Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server</span></span>

<span data-ttu-id="2ea6c-104">В этой статье описывается настройка диапазонов портов для пограничных серверов и настройка политики качества обслуживания для вашей A / V пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-104">This article describes how to configure port ranges for Edge Servers and how to configure a Quality of Service policy for your A/V Edge Servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="2ea6c-105">Настройка диапазонов портов</span><span class="sxs-lookup"><span data-stu-id="2ea6c-105">Configure port ranges</span></span>

<span data-ttu-id="2ea6c-106">Для пограничных серверов нет необходимости Настройка диапазонов портов для аудио-, видео и общий доступ к приложениям; Аналогичным образом диапазоны портов, используемый для пограничных серверов не обязательно должны совпадать диапазоны портов, используемые на серверах конференц-связи, приложений и посредника.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-106">With Edge servers, you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2ea6c-107">Прежде чем продолжить в нашем примере, мы важно приложите, что время существования этот параметр, мы рекомендуем не изменяйте диапазонов портов, как это может отрицательно сказаться на некоторые сценарии, при перемещении вне диапазона 50000 порт.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-107">Before we proceed with our example, it's important to stress that while this option exists, we recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="2ea6c-108">Например предположим, что вы настроили серверах конференц-связи, приложений и посредника для использования этих диапазонов портов:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-108">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ea6c-109">Тип пакета</span><span class="sxs-lookup"><span data-stu-id="2ea6c-109">Packet Type</span></span></th>
<th><span data-ttu-id="2ea6c-110">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="2ea6c-110">Starting Port</span></span></th>
<th><span data-ttu-id="2ea6c-111">Количество зарезервированных портов</span><span class="sxs-lookup"><span data-stu-id="2ea6c-111">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ea6c-112">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="2ea6c-112">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-113">40803</span><span class="sxs-lookup"><span data-stu-id="2ea6c-113">40803</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-114">8348</span><span class="sxs-lookup"><span data-stu-id="2ea6c-114">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea6c-115">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="2ea6c-115">Audio</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-116">49152</span><span class="sxs-lookup"><span data-stu-id="2ea6c-116">49152</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-117">8348</span><span class="sxs-lookup"><span data-stu-id="2ea6c-117">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ea6c-118">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="2ea6c-118">Video</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-119">57500</span><span class="sxs-lookup"><span data-stu-id="2ea6c-119">57500</span></span></p></td>
<td><p><span data-ttu-id="2ea6c-120">8034</span><span class="sxs-lookup"><span data-stu-id="2ea6c-120">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ea6c-121"><strong>Итоги</strong></span><span class="sxs-lookup"><span data-stu-id="2ea6c-121"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="2ea6c-122">24730</span><span class="sxs-lookup"><span data-stu-id="2ea6c-122">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ea6c-123">Как можно видеть, диапазонов портов для аудио-, видео и начать порт 40803 общего доступа к приложениям и охватывать всего 24732 портов.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-123">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="2ea6c-124">При необходимости можно настроить заданного пограничного сервера для их использования в целом порта значения, выполнив команду, аналогичную этой из внутри Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-124">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Skype for Business Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="2ea6c-125">Или использовать следующую команду, чтобы одновременно настроить все пограничные серверы в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-125">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="2ea6c-126">Вы можете проверить текущие настройки портов для пограничных серверов с помощью этой Скайп для командной консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-126">You can verify the current port settings for your Edge Servers by using this Skype for Business Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="2ea6c-127">Еще раз пока мы предлагаем эти параметры, настоятельно рекомендуется оставить вещей, как и для конфигурации порта.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-127">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a><span data-ttu-id="2ea6c-128">Настройка политики качества обслуживания для вашей A / V пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="2ea6c-128">Configure a QoS policy for your A/V Edge Servers</span></span>

<span data-ttu-id="2ea6c-129">Помимо создания политики качества обслуживания для серверов конференц-связи, приложений и посредника, необходимо создать политики звука и видео для внутреннего сайта вашей A / V пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-129">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="2ea6c-130">Тем не менее политики, используемые на пограничных серверах отличаются от политики, используемые на серверах конференц-связи, приложений и посредника.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-130">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="2ea6c-131">Для серверов конференц-связи, приложений и посредника указанный диапазон портов источника; для пограничных серверов необходимо указать диапазон портов назначения.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-131">For the Conferencing, Application, and Mediation servers, you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="2ea6c-132">Таким образом, нельзя применить просто конференц-связи, приложений и Mediation server QoS политики для пограничных серверов: эти политики просто не будут работать.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-132">Because of this, you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="2ea6c-133">Вместо этого необходимо создать новые политики и применять эти политики к пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-133">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="2ea6c-134">В следующей процедуре описывается процесс создания объектов групповой политики Active Directory, которые могут использоваться для управления качества обслуживания на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-134">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="2ea6c-135">Конечно возможно, что пограничных серверов, изолированных серверов, у которых нет учетных записей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-135">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="2ea6c-136">Если это так, можно использовать вместо групповой политики Active Directory локальной групповой политики: единственное отличие — необходимо создать эти локальные политики с помощью редактора локальной групповой политики и по отдельности необходимо создать один и тот же набор политик на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-136">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="2ea6c-137">Запуск редактора локальной групповой политики на пограничном сервере, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-137">To start the Local Group Policy Editor on an Edge server, do the following:</span></span>

1.  <span data-ttu-id="2ea6c-138">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-138">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2ea6c-139">В диалоговом окне **выполнить** введите **gpedit.msc**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-139">In the **Run** dialog box, type **gpedit.msc**, and then press ENTER.</span></span>

<span data-ttu-id="2ea6c-140">При создании политики на основе Active Directory, затем необходимо войти в систему на компьютере, где установлено управление групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-140">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="2ea6c-141">В этом случае откройте консоль Управление групповой политикой (нажмите кнопку **Пуск**, выберите пункт **Администрирование**и выберите **Управление групповой политикой**), а затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-141">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following steps:</span></span>

1.  <span data-ttu-id="2ea6c-142">В консоли Управление групповой политикой Найдите контейнер, где должен быть создан новой политики.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-142">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="2ea6c-143">Например если все Скайп для компьютеров Business Server, находятся в Подразделении с именем Скайп для Business Server, новой политики следует создавать в Скайп Business Server Подразделения.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-143">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="2ea6c-144">Щелкните правой кнопкой мыши соответствующий контейнер и нажмите кнопку **создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-144">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="2ea6c-145">В диалоговом окне **Новый объект групповой Политики** введите имя для нового объекта групповой политики в поле **имя** (например, **Скайп для Business Server Audio**) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-145">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server Audio**), and then click **OK**.</span></span>

4.  <span data-ttu-id="2ea6c-146">Щелкните правой кнопкой мыши созданную политику и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-146">Right-click the newly-created policy, and then click **Edit**.</span></span>

<span data-ttu-id="2ea6c-147">Здесь процесс одинаков независимо от того, создаете ли вы политику Active Directory или локальную политику:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-147">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="2ea6c-148">В редакторе управления групповой политики или редактора локальной групповой политики разверните узлы **Конфигурация компьютера**, затем узел **политики**, параметры **Windows**, щелкните правой кнопкой мыши **QoS на основе политики**и нажмите кнопку **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-148">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="2ea6c-149">В диалоговом окне **QoS на основе политики** на первой странице введите имя новой политики (например, **Скайп для Business Server Audio**) в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="2ea6c-149">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="2ea6c-150">Выберите **Укажите значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-150">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="2ea6c-151">Оставьте в поле **Укажите исходящих частоту передачи** не выбран и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-151">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="2ea6c-152">На следующей странице убедитесь в том, что выбран пункт **все приложения** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-152">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="2ea6c-153">Этот параметр указывает сети для поиска всех пакетов с помощью разметки DSCP 46, не только пакетов, созданный с конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-153">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="2ea6c-154">На странице третий убедитесь, что выбраны **все исходный IP-адрес** и **любой конечный IP-адрес** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-154">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="2ea6c-155">Эти два параметра убедитесь, что пакеты будут управляться независимо от того, какой компьютер пакеты отправляемых (IP-адрес) и (IP-адрес) компьютер, который будет получать эти пакеты.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-155">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="2ea6c-156">На странице четырех выберите в раскрывающемся списке **выберите протокол, к которому применяется данная политика качества обслуживания для** **TCP и UDP-ПОРТ** .</span><span class="sxs-lookup"><span data-stu-id="2ea6c-156">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="2ea6c-157">TCP (Transmission Control Protocol) и UDP-ПОРТ (протокол) — это два сетевых протоколов, чаще всего используемые Скайп Business Server и его клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-157">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

6.  <span data-ttu-id="2ea6c-158">В разделе **Укажите номер порта назначения**, выберите **этот порт назначения или диапазон**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-158">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="2ea6c-159">В соответствующем текстовом поле введите диапазон портов зарезервированы для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-159">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="2ea6c-160">Например, если зарезервированные порты 49152 через порты 57500 для трафика аудио, введите диапазон портов, используя следующий формат: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-160">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="2ea6c-161">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-161">Click **Finish**.</span></span>

<span data-ttu-id="2ea6c-162">После создания политики качества обслуживания для трафика аудио, необходимо создать второй политики для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-162">After you have created the QoS policy for audio traffic, you should create a second policy for video traffic.</span></span> <span data-ttu-id="2ea6c-163">Создание политики для видео, выполните ту же основную процедуру, были выполнены при создании политики звука, что следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-163">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="2ea6c-164">Используйте другое (и уникальное) политики имя (например, **Скайп для видео Business Server**).</span><span class="sxs-lookup"><span data-stu-id="2ea6c-164">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="2ea6c-165">Установите значение DSCP **34** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-165">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="2ea6c-166">(Обратите внимание на то, что нет необходимости использовать значение DSCP 34.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-166">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="2ea6c-167">Единственное требование — это использовать разные значения DSCP видео, не используемых для совершения.)</span><span class="sxs-lookup"><span data-stu-id="2ea6c-167">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="2ea6c-168">Используйте диапазон портов ранее настроенные для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-168">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2ea6c-169">Например, если зарезервированные порты 57501 до 65 535 для видео, необходимо задать диапазон портов на этот: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-169">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="2ea6c-170">Опять же это должен быть настроен как конечного диапазона портов.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-170">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="2ea6c-171">Если вы решите создать политику для управления трафика общего доступа приложения, необходимо создать третью политику, внеся следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-171">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="2ea6c-172">Используйте другое (и уникальное) политики имя (например, **Скайп для Business Server общий доступ к приложениям**).</span><span class="sxs-lookup"><span data-stu-id="2ea6c-172">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="2ea6c-173">Задайте значение DSCP **24** вместо 46.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-173">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="2ea6c-174">(Еще раз, вам не нужно использовать значение DSCP 24.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-174">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="2ea6c-175">Единственное требование — это использовать разные значения DSCP для общего доступа к приложениям, не используется для аудио или видео.)</span><span class="sxs-lookup"><span data-stu-id="2ea6c-175">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="2ea6c-176">Используйте диапазон портов ранее настроенные для видео-трафика.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-176">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="2ea6c-177">Например, если зарезервированные порты 40803 до 49151 для общего доступа к приложениям, необходимо задать диапазон портов на этот: **40803:49151**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-177">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="2ea6c-178">Новые политики, созданные вами, не вступят в силу только после обновления групповой политики на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-178">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="2ea6c-179">Хотя групповая политика периодически обновляется сама, вы можете обновить ее принудительно, запустив на каждом нужном компьютере следующую команду.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-179">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="2ea6c-180">Эту команду можно выполнить из внутри Скайп для Business Server или из любого окно командной строки, на котором выполняется с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-180">This command can be run from within the Skype for Business Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="2ea6c-181">Чтобы открыть такое окно с правами администратора, в меню **Пуск** правой кнопкой мыши щелкните **Командная строка** и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-181">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="2ea6c-182">Обратите внимание на то, что может потребоваться перезапустить на пограничном сервере даже после выполнения Gpudate.exe.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-182">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="2ea6c-183">Чтобы обеспечить, что сетевых пакетов соответствующим значением DSCP, следует также создать новый раздел реестра на каждом компьютере, выполнив следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="2ea6c-183">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="2ea6c-184">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-184">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2ea6c-185">В диалоговом окне **выполнить** введите **regedit**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-185">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="2ea6c-186">В редакторе реестра разверните **HKEY\_ЛОКАЛЬНОГО\_МАШИНЫ**, разверните узлы **системы**, разверните **CurrentControlSet**, разверните узел **службы**и затем **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-186">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="2ea6c-187">Щелкните правой кнопкой мыши **Tcpip**, выберите команду **Создать**и затем щелкните **раздел**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-187">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="2ea6c-188">После создания нового раздела реестра введите **качества обслуживания**и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-188">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="2ea6c-189">Щелкните правой кнопкой мыши **QoS**, выберите команду **Создать**и затем **Строковый параметр**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-189">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="2ea6c-190">После создания нового значения реестра введите **не используйте NLA**и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-190">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2ea6c-191">Дважды щелкните значок, **не использующие NLA**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-191">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="2ea6c-192">В диалоговом окне **Изменение строкового параметра** в поле **значение** введите **1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-192">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="2ea6c-193">Закройте редактор реестра и перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-193">Close the Registry Editor and reboot your computer.</span></span>
