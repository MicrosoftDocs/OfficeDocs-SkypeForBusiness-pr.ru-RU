---
title: Реализация качества обслуживания в клиентах группами Майкрософт
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Реализуйте качества обслуживания (QoS) для клиентов, группами Майкрософт.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 157754f38f1304aa0cfe8d48b225b470ec015f4b
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "30211785"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="6a994-103">Набор QoS на клиентах Windows</span><span class="sxs-lookup"><span data-stu-id="6a994-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="6a994-104">QoS на основе политики в рамках групповой политики можно использовать для установки диапазон портов источника для предварительно определенные значения DSCP в клиенте групп.</span><span class="sxs-lookup"><span data-stu-id="6a994-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="6a994-105">Диапазоны портов, указанных в следующей таблице приведены отправной точки для создания политики для каждой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="6a994-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="6a994-106">_Рекомендуется диапазонов начальный порт_</span><span class="sxs-lookup"><span data-stu-id="6a994-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="6a994-107">Тип трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6a994-107">Media traffic type</span></span>| <span data-ttu-id="6a994-108">Диапазон портов источника клиента</span><span class="sxs-lookup"><span data-stu-id="6a994-108">Client source port range</span></span> |<span data-ttu-id="6a994-109">Протокол</span><span class="sxs-lookup"><span data-stu-id="6a994-109">Protocol</span></span>|<span data-ttu-id="6a994-110">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="6a994-110">DSCP value</span></span>|<span data-ttu-id="6a994-111">Класс DSCP</span><span class="sxs-lookup"><span data-stu-id="6a994-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="6a994-112">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="6a994-112">Audio</span></span>| <span data-ttu-id="6a994-113">50 000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="6a994-113">50,000–50,019</span></span>|<span data-ttu-id="6a994-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a994-114">TCP/UDP</span></span>|<span data-ttu-id="6a994-115">46</span><span class="sxs-lookup"><span data-stu-id="6a994-115">46</span></span>|<span data-ttu-id="6a994-116">Беспрепятственная переадресация (EF)</span><span class="sxs-lookup"><span data-stu-id="6a994-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="6a994-117">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="6a994-117">Video</span></span>| <span data-ttu-id="6a994-118">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="6a994-118">50,020–50,039</span></span>|<span data-ttu-id="6a994-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a994-119">TCP/UDP</span></span>|<span data-ttu-id="6a994-120">34</span><span class="sxs-lookup"><span data-stu-id="6a994-120">34</span></span>|<span data-ttu-id="6a994-121">Гарантированная переадресация (AF41)</span><span class="sxs-lookup"><span data-stu-id="6a994-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="6a994-122">Совместное использование приложений и рабочего стола</span><span class="sxs-lookup"><span data-stu-id="6a994-122">Application/Screen Sharing</span></span>| <span data-ttu-id="6a994-123">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="6a994-123">50,040–50,059</span></span>|<span data-ttu-id="6a994-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="6a994-124">TCP/UDP</span></span>|<span data-ttu-id="6a994-125">18</span><span class="sxs-lookup"><span data-stu-id="6a994-125">18</span></span>|<span data-ttu-id="6a994-126">Проверенная переадресации (AF21)</span><span class="sxs-lookup"><span data-stu-id="6a994-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="6a994-127">Где это возможно, настройте параметры качества обслуживания на основе политики в объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="6a994-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="6a994-128">Следующие шаги в [Настройка диапазонов портов и политики качества обслуживания для клиентов в Скайп для Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), который имеет некоторые дополнительные сведения, которые могут быть очень похожи.</span><span class="sxs-lookup"><span data-stu-id="6a994-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="6a994-129">Для создания политики звука качества обслуживания для компьютеров, подключенных доменный Windows 10, сначала выполните вход компьютер, на котором установлена консоль Управление групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="6a994-129">To create a QoS audio policy for domian-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="6a994-130">Откройте консоль Управление групповой политикой (нажмите кнопку Пуск, выберите пункт Администрирование и выберите Управление групповой политикой), а затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6a994-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="6a994-131">В консоли Управление групповой политикой Найдите контейнер, где должен быть создан новой политики.</span><span class="sxs-lookup"><span data-stu-id="6a994-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="6a994-132">Например если на клиентских компьютерах, находятся в Подразделении с именем **Клиенты**, новой политики должны быть созданы в Подразделения клиента.</span><span class="sxs-lookup"><span data-stu-id="6a994-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="6a994-133">Щелкните правой кнопкой мыши соответствующий контейнер и нажмите кнопку **создать объект GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="6a994-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="6a994-134">В диалоговом окне **Новый объект групповой Политики** в поле **имя** введите имя для нового объекта групповой политики и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6a994-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="6a994-135">Щелкните правой кнопкой мыши только что созданную политику и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6a994-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="6a994-136">В редакторе управления групповой политики разверните узлы **Конфигурация компьютера**, параметры **Windows**, щелкните правой кнопкой мыши **QoS на основе политики**и выберите команду **Создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="6a994-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="6a994-137">В диалоговом окне **QoS на основе политики** на первой странице введите имя новой политики в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="6a994-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="6a994-138">Выберите **Укажите значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="6a994-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="6a994-139">Оставьте в поле **Укажите исходящих частоту передачи** не выбран и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a994-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="6a994-140">На следующей странице выберите **только приложения с именем исполняемого файла** и введите имя **Teams.exe**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a994-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="6a994-141">Этот параметр указывает политику только определять приоритеты совпадающих трафика от клиента группами.</span><span class="sxs-lookup"><span data-stu-id="6a994-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="6a994-142">На странице третий убедитесь, что выбраны **все исходный IP-адрес** и **любой конечный IP-адрес** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a994-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="6a994-143">Эти два параметра убедитесь, что пакеты будут управляться независимо от того, какой компьютер (IP-адрес) отправляются пакеты и пакеты будут получены компьютер, который (IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="6a994-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="6a994-144">На странице четырех выберите из раскрывающегося списка **выберите протокол, к которому применяется данная политика качества обслуживания для** **TCP и UDP-ПОРТ** .</span><span class="sxs-lookup"><span data-stu-id="6a994-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="6a994-145">TCP (Transmission Control Protocol) и UDP-ПОРТ (протокол) — это наиболее часто используемых два сетевых протоколов.</span><span class="sxs-lookup"><span data-stu-id="6a994-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="6a994-146">В разделе **Укажите номер порта источника**выберите выберите **этот исходный порт или диапазон**.</span><span class="sxs-lookup"><span data-stu-id="6a994-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="6a994-147">В соответствующем текстовом поле введите диапазон портов зарезервированы для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="6a994-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="6a994-148">Например, если зарезервированные порты 50000 через порты 50019 для трафика аудио, введите диапазон портов, используя следующий формат: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="6a994-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="6a994-149">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="6a994-149">Click **Finish**.</span></span>

11. <span data-ttu-id="6a994-150">Повторите шаги 5 – 10 для создания политики для видео- и приложения и доступ к рабочему столу, подставив соответствующий значения в шаги 6 и 10.</span><span class="sxs-lookup"><span data-stu-id="6a994-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="6a994-151">Новые политики, созданному вами вступят в силу только после обновления групповой политики на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="6a994-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="6a994-152">Несмотря на то, что на собственный периодически обновляет групповой политики, вы можете принудительно немедленного обновления, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6a994-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="6a994-153">На каждом компьютере, для которого требуется обновить групповой политики откройте командную консоль.</span><span class="sxs-lookup"><span data-stu-id="6a994-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="6a994-154">Убедитесь, что командной консоли для запуска от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="6a994-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6a994-155">В командной строке введите</span><span class="sxs-lookup"><span data-stu-id="6a994-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="6a994-156">Проверка маркировку DSCP в объекте групповой политики</span><span class="sxs-lookup"><span data-stu-id="6a994-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="6a994-157">Чтобы убедиться в том, что были заданы значения из объекта групповой политики, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6a994-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="6a994-158">Откройте командную консоль.</span><span class="sxs-lookup"><span data-stu-id="6a994-158">Open a command console.</span></span> <span data-ttu-id="6a994-159">Убедитесь, что командной консоли для запуска от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="6a994-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="6a994-160">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="6a994-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="6a994-161">Это будет создать отчет и отправьте его в текстовый файл с именем gp.txt.</span><span class="sxs-lookup"><span data-stu-id="6a994-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="6a994-162">Кроме того можно ввести следующую команду, чтобы создать те же данные в формате HTML отчет с именем gp.html:</span><span class="sxs-lookup"><span data-stu-id="6a994-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="6a994-163">![Снимок экрана окна консоли, выполнив команду gpresult.] (media/Qos-in-Teams-Image3.png "Снимок экрана окна консоли, выполнив команду gpresult.")</span><span class="sxs-lookup"><span data-stu-id="6a994-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="6a994-164">В созданном файле найдите заголовок **Применения объектов групповой политики** и убедитесь, что имена объектов групповой политики, созданной ранее в списке примененные политики.</span><span class="sxs-lookup"><span data-stu-id="6a994-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="6a994-165">Откройте редактор реестра и перейдите к:</span><span class="sxs-lookup"><span data-stu-id="6a994-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="6a994-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="6a994-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="6a994-167">Проверка значения реестра, перечисленных в таблице 4.</span><span class="sxs-lookup"><span data-stu-id="6a994-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="6a994-168">_В таблице 4. Значения для записи реестра Windows для качества обслуживания_</span><span class="sxs-lookup"><span data-stu-id="6a994-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="6a994-169">Имя</span><span class="sxs-lookup"><span data-stu-id="6a994-169">Name</span></span>          |  <span data-ttu-id="6a994-170">Тип</span><span class="sxs-lookup"><span data-stu-id="6a994-170">Type</span></span>  |    <span data-ttu-id="6a994-171">Значение</span><span class="sxs-lookup"><span data-stu-id="6a994-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="6a994-172">Application Name</span><span class="sxs-lookup"><span data-stu-id="6a994-172">Application Name</span></span>    | <span data-ttu-id="6a994-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-173">REG_SZ</span></span> |  <span data-ttu-id="6a994-174">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="6a994-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="6a994-175">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="6a994-175">DSCP Value</span></span>       | <span data-ttu-id="6a994-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-176">REG_SZ</span></span> |     <span data-ttu-id="6a994-177">46</span><span class="sxs-lookup"><span data-stu-id="6a994-177">46</span></span>      |
   |        <span data-ttu-id="6a994-178">Local IP</span><span class="sxs-lookup"><span data-stu-id="6a994-178">Local IP</span></span>        | <span data-ttu-id="6a994-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="6a994-180">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="6a994-180">Local IP Prefix Length</span></span> | <span data-ttu-id="6a994-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6a994-182">Local Port</span><span class="sxs-lookup"><span data-stu-id="6a994-182">Local Port</span></span>       | <span data-ttu-id="6a994-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-183">REG_SZ</span></span> | <span data-ttu-id="6a994-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="6a994-184">50000-50019</span></span> |
   |        <span data-ttu-id="6a994-185">Протокол</span><span class="sxs-lookup"><span data-stu-id="6a994-185">Protocol</span></span>        | <span data-ttu-id="6a994-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="6a994-187">Remote IP</span><span class="sxs-lookup"><span data-stu-id="6a994-187">Remote IP</span></span>        | <span data-ttu-id="6a994-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="6a994-189">Префикс удаленных IP-адресов</span><span class="sxs-lookup"><span data-stu-id="6a994-189">Remote IP Prefix</span></span>    | <span data-ttu-id="6a994-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="6a994-191">Remote Port</span><span class="sxs-lookup"><span data-stu-id="6a994-191">Remote Port</span></span>       | <span data-ttu-id="6a994-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="6a994-193">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="6a994-193">Throttle Rate</span></span>      | <span data-ttu-id="6a994-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="6a994-194">REG_SZ</span></span> |     <span data-ttu-id="6a994-195">-1</span><span class="sxs-lookup"><span data-stu-id="6a994-195">-1</span></span>      |

5. <span data-ttu-id="6a994-196">Проверьте правильность значение для записи в имя приложения для клиента, которую вы используете и убедитесь, что локальный порт и значением DSCP записи отражают параметров в объекте групповой политики.</span><span class="sxs-lookup"><span data-stu-id="6a994-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
