---
title: Качество обслуживания в клиентах Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Реализация качества обслуживания (QoS) для клиентов Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572567"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="da639-103">Настройка качества обслуживания в клиентах Windows</span><span class="sxs-lookup"><span data-stu-id="da639-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="da639-104">Вы можете использовать QoS на основе политики в групповой политике, чтобы установить диапазон портов источника для предопределенного значения DSCP в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="da639-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="da639-105">Диапазоны портов, указанные в приведенной ниже таблице, являются отправной точкой для создания политики для каждой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="da639-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="da639-106">_Рекомендуемые начальные диапазоны портов_</span><span class="sxs-lookup"><span data-stu-id="da639-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="da639-107">Тип трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="da639-107">Media traffic type</span></span>| <span data-ttu-id="da639-108">Диапазон портов источника клиента</span><span class="sxs-lookup"><span data-stu-id="da639-108">Client source port range</span></span> |<span data-ttu-id="da639-109">Протокол</span><span class="sxs-lookup"><span data-stu-id="da639-109">Protocol</span></span>|<span data-ttu-id="da639-110">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="da639-110">DSCP value</span></span>|<span data-ttu-id="da639-111">Класс DSCP</span><span class="sxs-lookup"><span data-stu-id="da639-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="da639-112">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="da639-112">Audio</span></span>| <span data-ttu-id="da639-113">50000 — 50019</span><span class="sxs-lookup"><span data-stu-id="da639-113">50,000–50,019</span></span>|<span data-ttu-id="da639-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="da639-114">TCP/UDP</span></span>|<span data-ttu-id="da639-115">46</span><span class="sxs-lookup"><span data-stu-id="da639-115">46</span></span>|<span data-ttu-id="da639-116">Беспрепятственная переадресация (EF)</span><span class="sxs-lookup"><span data-stu-id="da639-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="da639-117">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="da639-117">Video</span></span>| <span data-ttu-id="da639-118">50020 – 50039</span><span class="sxs-lookup"><span data-stu-id="da639-118">50,020–50,039</span></span>|<span data-ttu-id="da639-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="da639-119">TCP/UDP</span></span>|<span data-ttu-id="da639-120">34</span><span class="sxs-lookup"><span data-stu-id="da639-120">34</span></span>|<span data-ttu-id="da639-121">Гарантированная переадресация (AF41)</span><span class="sxs-lookup"><span data-stu-id="da639-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="da639-122">Демонстрация приложений и экрана</span><span class="sxs-lookup"><span data-stu-id="da639-122">Application/Screen Sharing</span></span>| <span data-ttu-id="da639-123">50040 – 50059</span><span class="sxs-lookup"><span data-stu-id="da639-123">50,040–50,059</span></span>|<span data-ttu-id="da639-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="da639-124">TCP/UDP</span></span>|<span data-ttu-id="da639-125">18</span><span class="sxs-lookup"><span data-stu-id="da639-125">18</span></span>|<span data-ttu-id="da639-126">Гарантированная переадресация (AF21)</span><span class="sxs-lookup"><span data-stu-id="da639-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="da639-127">Везде, где это возможно, настройте параметры качества обслуживания, основанные на политике, в объекте групповой политики.</span><span class="sxs-lookup"><span data-stu-id="da639-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="da639-128">Описанные ниже действия очень похожи на [настройку диапазонов портов и политики качества обслуживания для клиентов в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), у которых есть некоторые дополнительные сведения, которые могут быть необязательными.</span><span class="sxs-lookup"><span data-stu-id="da639-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="da639-129">Чтобы создать политику качества звука QoS для домена на компьютерах с Windows 10, сначала войдите на компьютер, на котором установлен компонент управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="da639-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="da639-130">Откройте средство управления групповыми политиками (нажмите кнопку Пуск, выберите пункт Администрирование, а затем — Управление групповыми политиками), а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da639-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="da639-131">В разделе Управление групповой политикой найдите контейнер, в котором нужно создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="da639-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="da639-132">Например, если все клиентские компьютеры находятся в подразделении с именем " **Клиенты**", в подразделении клиента следует создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="da639-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="da639-133">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **создать объект групповой политики в этом домене и свяжите его**.</span><span class="sxs-lookup"><span data-stu-id="da639-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="da639-134">В диалоговом окне **создание GPO** введите имя нового объекта групповой политики в поле **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="da639-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="da639-135">Щелкните правой кнопкой мыши только что созданную политику и выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="da639-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="da639-136">В редакторе управления групповыми политиками разверните узел **Конфигурация компьютера**, разверните раздел **Параметры Windows**, щелкните правой кнопкой мыши службу **QoS на основе политики**, а затем выберите команду **создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="da639-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="da639-137">В диалоговом окне **QoS на основе политики** на первой странице в поле **имя** введите имя новой политики.</span><span class="sxs-lookup"><span data-stu-id="da639-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="da639-138">Выберите **задать значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="da639-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="da639-139">Оставьте параметр **задать частоту исходящих подключений** невыбранным и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da639-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="da639-140">На следующей странице выберите **только приложения с именем исполняемого файла** и введите имя **Teams. exe**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da639-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="da639-141">Этот параметр дает политике приоритет только для трафика, соответствующего клиенту Teams.</span><span class="sxs-lookup"><span data-stu-id="da639-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="da639-142">На третьей странице убедитесь, что выбраны оба **IP-адреса источника** и **конечный IP-адрес** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da639-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="da639-143">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, на каком компьютере (IP-адрес) отправили пакеты, и какой компьютер (IP-адрес) будет получать пакеты.</span><span class="sxs-lookup"><span data-stu-id="da639-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="da639-144">На странице 4 выберите **TCP и UDP** из раскрывающегося списка **выберите протокол, к которому применяется политика QoS** .</span><span class="sxs-lookup"><span data-stu-id="da639-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="da639-145">Протокол TCP (протокол управления передачей) и UDP (датаграмма пользователя) — это два наиболее часто используемых сетевого протокола.</span><span class="sxs-lookup"><span data-stu-id="da639-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="da639-146">Под заголовком **укажите номер исходного порта**, выберите **из этого исходного порта или диапазона**.</span><span class="sxs-lookup"><span data-stu-id="da639-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="da639-147">В сопроводительном текстовом поле введите диапазон портов, зарезервированный для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="da639-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="da639-148">Например, если вы зарезервированы порты 50000 через порты 50019 для звукового трафика, введите диапазон портов в следующем формате: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="da639-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="da639-149">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="da639-149">Click **Finish**.</span></span>

11. <span data-ttu-id="da639-150">Повторите шаги 5-10, чтобы создать политики для демонстрации видео и приложений/рабочего стола, подставив соответствующие значения в шагах 6 и 10.</span><span class="sxs-lookup"><span data-stu-id="da639-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="da639-151">Новые политики, которые вы создали, вступят в силу, пока групповая политика не будет обновлена на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="da639-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="da639-152">Несмотря на то что групповая политика периодически обновляется, вы можете немедленно выполнить принудительное обновление, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da639-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="da639-153">На каждом компьютере, для которого вы хотите обновить групповую политику, откройте командную консоль.</span><span class="sxs-lookup"><span data-stu-id="da639-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="da639-154">Убедитесь, что для консоли команд установлен Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="da639-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="da639-155">В командной строке введите</span><span class="sxs-lookup"><span data-stu-id="da639-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="da639-156">Проверка пометки DSCP в объекте групповой политики</span><span class="sxs-lookup"><span data-stu-id="da639-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="da639-157">Чтобы убедиться в том, что значения объекта групповой политики заданы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="da639-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="da639-158">Открытие командной консоли.</span><span class="sxs-lookup"><span data-stu-id="da639-158">Open a command console.</span></span> <span data-ttu-id="da639-159">Убедитесь, что для консоли команд установлен Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="da639-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="da639-160">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="da639-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="da639-161">Это приведет к созданию отчета и его отправке в текстовый файл с именем GP. txt.</span><span class="sxs-lookup"><span data-stu-id="da639-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="da639-162">Вы также можете ввести указанную ниже команду, чтобы получить те же данные в более удобочитаемом HTML-отчете с именем GP. HTML.</span><span class="sxs-lookup"><span data-stu-id="da639-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="da639-163">![Снимок экрана: окно консоли с командой Gpresult.](media/Qos-in-Teams-Image3.png "Снимок экрана: окно консоли с командой Gpresult.")</span><span class="sxs-lookup"><span data-stu-id="da639-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="da639-164">В созданном файле найдите заголовки, **примененные к объектам групповой политики** , и убедитесь в том, что имена объектов групповой политики, созданные ранее, находятся в списке примененных политик.</span><span class="sxs-lookup"><span data-stu-id="da639-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="da639-165">Откройте редактор реестра и перейдите по следующему адресу:</span><span class="sxs-lookup"><span data-stu-id="da639-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="da639-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="da639-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="da639-167">Проверьте значения параметров реестра, перечисленных в таблице 4.</span><span class="sxs-lookup"><span data-stu-id="da639-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="da639-168">_Таблица 4. Значения для элементов реестра Windows для QoS_</span><span class="sxs-lookup"><span data-stu-id="da639-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="da639-169">Имя</span><span class="sxs-lookup"><span data-stu-id="da639-169">Name</span></span>          |  <span data-ttu-id="da639-170">Тип</span><span class="sxs-lookup"><span data-stu-id="da639-170">Type</span></span>  |    <span data-ttu-id="da639-171">Значение</span><span class="sxs-lookup"><span data-stu-id="da639-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="da639-172">Application Name</span><span class="sxs-lookup"><span data-stu-id="da639-172">Application Name</span></span>    | <span data-ttu-id="da639-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-173">REG_SZ</span></span> |  <span data-ttu-id="da639-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="da639-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="da639-175">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="da639-175">DSCP Value</span></span>       | <span data-ttu-id="da639-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-176">REG_SZ</span></span> |     <span data-ttu-id="da639-177">46</span><span class="sxs-lookup"><span data-stu-id="da639-177">46</span></span>      |
   |        <span data-ttu-id="da639-178">Local IP</span><span class="sxs-lookup"><span data-stu-id="da639-178">Local IP</span></span>        | <span data-ttu-id="da639-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="da639-180">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="da639-180">Local IP Prefix Length</span></span> | <span data-ttu-id="da639-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="da639-182">Local Port</span><span class="sxs-lookup"><span data-stu-id="da639-182">Local Port</span></span>       | <span data-ttu-id="da639-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-183">REG_SZ</span></span> | <span data-ttu-id="da639-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="da639-184">50000-50019</span></span> |
   |        <span data-ttu-id="da639-185">Протокол</span><span class="sxs-lookup"><span data-stu-id="da639-185">Protocol</span></span>        | <span data-ttu-id="da639-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="da639-187">Remote IP</span><span class="sxs-lookup"><span data-stu-id="da639-187">Remote IP</span></span>        | <span data-ttu-id="da639-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="da639-189">Префикс удаленного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="da639-189">Remote IP Prefix</span></span>    | <span data-ttu-id="da639-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="da639-191">Remote Port</span><span class="sxs-lookup"><span data-stu-id="da639-191">Remote Port</span></span>       | <span data-ttu-id="da639-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="da639-193">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="da639-193">Throttle Rate</span></span>      | <span data-ttu-id="da639-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="da639-194">REG_SZ</span></span> |     <span data-ttu-id="da639-195">-1</span><span class="sxs-lookup"><span data-stu-id="da639-195">-1</span></span>      |

5. <span data-ttu-id="da639-196">Убедитесь в том, что значение для записи имени приложения правильно для нужного клиента, и убедитесь, что в объекте групповой политики отражены значения DSCP и Local Port.</span><span class="sxs-lookup"><span data-stu-id="da639-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
