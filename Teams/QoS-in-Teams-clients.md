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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43a4c7ea45fe0feabbe8851cde944a70994829da
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836489"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="45ae5-103">Настройка качества обслуживания в клиентах Windows</span><span class="sxs-lookup"><span data-stu-id="45ae5-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="45ae5-104">Вы можете использовать QoS на основе политики в групповой политике, чтобы установить диапазон портов источника для предопределенного значения DSCP в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="45ae5-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="45ae5-105">Диапазоны портов, указанные в приведенной ниже таблице, являются отправной точкой для создания политики для каждой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="45ae5-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="45ae5-106">*Таблица 1. Рекомендуемые начальные диапазоны портов*</span><span class="sxs-lookup"><span data-stu-id="45ae5-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="45ae5-107">Тип трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="45ae5-107">Media traffic type</span></span>| <span data-ttu-id="45ae5-108">Диапазон портов источника клиента</span><span class="sxs-lookup"><span data-stu-id="45ae5-108">Client source port range</span></span> |<span data-ttu-id="45ae5-109">Протокол</span><span class="sxs-lookup"><span data-stu-id="45ae5-109">Protocol</span></span>|<span data-ttu-id="45ae5-110">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="45ae5-110">DSCP value</span></span>|<span data-ttu-id="45ae5-111">Класс DSCP</span><span class="sxs-lookup"><span data-stu-id="45ae5-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="45ae5-112">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="45ae5-112">Audio</span></span>| <span data-ttu-id="45ae5-113">50000 — 50019</span><span class="sxs-lookup"><span data-stu-id="45ae5-113">50,000–50,019</span></span>|<span data-ttu-id="45ae5-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="45ae5-114">TCP/UDP</span></span>|<span data-ttu-id="45ae5-115">46</span><span class="sxs-lookup"><span data-stu-id="45ae5-115">46</span></span>|<span data-ttu-id="45ae5-116">Беспрепятственная переадресация (EF)</span><span class="sxs-lookup"><span data-stu-id="45ae5-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="45ae5-117">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="45ae5-117">Video</span></span>| <span data-ttu-id="45ae5-118">50020 – 50039</span><span class="sxs-lookup"><span data-stu-id="45ae5-118">50,020–50,039</span></span>|<span data-ttu-id="45ae5-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="45ae5-119">TCP/UDP</span></span>|<span data-ttu-id="45ae5-120">34</span><span class="sxs-lookup"><span data-stu-id="45ae5-120">34</span></span>|<span data-ttu-id="45ae5-121">Гарантированная переадресация (AF41)</span><span class="sxs-lookup"><span data-stu-id="45ae5-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="45ae5-122">Демонстрация приложений и экрана</span><span class="sxs-lookup"><span data-stu-id="45ae5-122">Application/Screen Sharing</span></span>| <span data-ttu-id="45ae5-123">50040 – 50059</span><span class="sxs-lookup"><span data-stu-id="45ae5-123">50,040–50,059</span></span>|<span data-ttu-id="45ae5-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="45ae5-124">TCP/UDP</span></span>|<span data-ttu-id="45ae5-125">18</span><span class="sxs-lookup"><span data-stu-id="45ae5-125">18</span></span>|<span data-ttu-id="45ae5-126">Гарантированная переадресация (AF21)</span><span class="sxs-lookup"><span data-stu-id="45ae5-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="45ae5-127">Везде, где это возможно, настройте параметры качества обслуживания, основанные на политике, в объекте групповой политики.</span><span class="sxs-lookup"><span data-stu-id="45ae5-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="45ae5-128">Описанные ниже действия очень похожи на [настройку диапазонов портов и политики качества обслуживания для клиентов в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), у которых есть некоторые дополнительные сведения, которые могут быть необязательными.</span><span class="sxs-lookup"><span data-stu-id="45ae5-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="45ae5-129">Чтобы создать политику качества звука QoS для домена на компьютерах с Windows 10, сначала войдите на компьютер, на котором установлен компонент управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="45ae5-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="45ae5-130">Откройте средство управления групповыми политиками (нажмите кнопку Пуск, выберите пункт Администрирование, а затем — Управление групповыми политиками), а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="45ae5-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="45ae5-131">В разделе Управление групповой политикой найдите контейнер, в котором нужно создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="45ae5-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="45ae5-132">Например, если все клиентские компьютеры находятся в подразделении с именем " **Клиенты**", Новая политика должна быть создана в подразделении "клиенты".</span><span class="sxs-lookup"><span data-stu-id="45ae5-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="45ae5-133">Щелкните правой кнопкой мыши соответствующий контейнер, а затем выберите команду **создать объект групповой политики в этом домене и свяжите его**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="45ae5-134">В диалоговом окне **создание GPO** введите имя нового объекта групповой политики в поле **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="45ae5-135">Щелкните правой кнопкой мыши только что созданную политику и выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="45ae5-136">В редакторе управления групповыми политиками разверните узел **Конфигурация компьютера**, разверните раздел **Параметры Windows**, щелкните правой кнопкой мыши службу **QoS на основе политики**, а затем выберите команду **создать новую политику**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="45ae5-137">В диалоговом окне **QoS на основе политики** на первой странице в поле **имя** введите имя новой политики.</span><span class="sxs-lookup"><span data-stu-id="45ae5-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="45ae5-138">Выберите **задать значение DSCP** и задайте значение **46**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="45ae5-139">Оставьте параметр **задать частоту исходящих подключений** невыбранным и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="45ae5-140">На следующей странице выберите **только приложения с именем исполняемого файла** и введите имя **Teams. exe**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="45ae5-141">Этот параметр дает политике приоритет только для трафика, соответствующего клиенту Teams.</span><span class="sxs-lookup"><span data-stu-id="45ae5-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="45ae5-142">На третьей странице убедитесь, что выбраны оба **IP-адреса источника** и **конечный IP-адрес** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="45ae5-143">Эти два параметра гарантируют, что пакеты будут управляться независимо от того, на каком компьютере (IP-адрес) отправили пакеты, и какой компьютер (IP-адрес) будет получать пакеты.</span><span class="sxs-lookup"><span data-stu-id="45ae5-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="45ae5-144">На странице 4 выберите **TCP и UDP** из раскрывающегося списка **выберите протокол, к которому применяется политика QoS** .</span><span class="sxs-lookup"><span data-stu-id="45ae5-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="45ae5-145">Протокол TCP (протокол управления передачей) и UDP (датаграмма пользователя) — это два наиболее часто используемых сетевого протокола.</span><span class="sxs-lookup"><span data-stu-id="45ae5-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="45ae5-146">Под заголовком **укажите номер исходного порта**, выберите **из этого исходного порта или диапазона**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="45ae5-147">В сопроводительном текстовом поле введите диапазон портов, зарезервированный для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="45ae5-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="45ae5-148">Например, если вы зарезервированы порты 50000 через порты 50019 для звукового трафика, введите диапазон портов в следующем формате: **50000:50019**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="45ae5-149">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="45ae5-149">Click **Finish**.</span></span>

1. <span data-ttu-id="45ae5-150">Повторите шаги 5-10, чтобы создать политики для демонстрации видео и приложений/рабочего стола, подставив соответствующие значения в шагах 6 и 10.</span><span class="sxs-lookup"><span data-stu-id="45ae5-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="45ae5-151">Новые политики, которые вы создали, вступят в силу, пока групповая политика не будет обновлена на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="45ae5-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="45ae5-152">Несмотря на то что групповая политика периодически обновляется, вы можете немедленно выполнить принудительное обновление, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="45ae5-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="45ae5-153">На каждом компьютере, на котором вы хотите обновить групповую политику, откройте командную команду As Administrator (*Запуск от имени администратора*).</span><span class="sxs-lookup"><span data-stu-id="45ae5-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="45ae5-154">В командной строке введите</span><span class="sxs-lookup"><span data-stu-id="45ae5-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="45ae5-155">Проверка пометки DSCP в объекте групповой политики</span><span class="sxs-lookup"><span data-stu-id="45ae5-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="45ae5-156">Чтобы убедиться в том, что значения объекта групповой политики заданы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="45ae5-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="45ae5-157">Откройте командную команду As Administrator (*Запуск от имени администратора*).</span><span class="sxs-lookup"><span data-stu-id="45ae5-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="45ae5-158">В командной строке введите</span><span class="sxs-lookup"><span data-stu-id="45ae5-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="45ae5-159">Это приведет к формированию отчета об примененных объектах групповой политики и их отправке в текстовый файл с именем *GP. txt*.</span><span class="sxs-lookup"><span data-stu-id="45ae5-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="45ae5-160">Для более удобочитаемого отчета в формате HTML с именем *GP. HTML*введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45ae5-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="45ae5-161">В созданном файле найдите заголовки, **примененные к объектам групповой политики** , и убедитесь в том, что имена объектов групповой политики, созданные ранее, находятся в списке примененных политик.</span><span class="sxs-lookup"><span data-stu-id="45ae5-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="45ae5-162">Откройте редактор реестра и перейдите к разделу</span><span class="sxs-lookup"><span data-stu-id="45ae5-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="45ae5-163">Политики\_\\программного\\обеспечения\\для\_локального компьютера\\hKey Microsoft\\Windows QoS</span><span class="sxs-lookup"><span data-stu-id="45ae5-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="45ae5-164">Проверьте значения в параметрах реестра, перечисленных в таблице 2.</span><span class="sxs-lookup"><span data-stu-id="45ae5-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="45ae5-165">*Таблица 2. Значения для элементов реестра Windows для QoS*</span><span class="sxs-lookup"><span data-stu-id="45ae5-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="45ae5-166">Имя</span><span class="sxs-lookup"><span data-stu-id="45ae5-166">Name</span></span>          |  <span data-ttu-id="45ae5-167">Тип</span><span class="sxs-lookup"><span data-stu-id="45ae5-167">Type</span></span>  |    <span data-ttu-id="45ae5-168">Значение</span><span class="sxs-lookup"><span data-stu-id="45ae5-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="45ae5-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="45ae5-169">Application Name</span></span>    | <span data-ttu-id="45ae5-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-170">REG_SZ</span></span> |  <span data-ttu-id="45ae5-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="45ae5-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="45ae5-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="45ae5-172">DSCP Value</span></span>       | <span data-ttu-id="45ae5-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-173">REG_SZ</span></span> |     <span data-ttu-id="45ae5-174">46</span><span class="sxs-lookup"><span data-stu-id="45ae5-174">46</span></span>      |
   |        <span data-ttu-id="45ae5-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="45ae5-175">Local IP</span></span>        | <span data-ttu-id="45ae5-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="45ae5-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="45ae5-177">Local IP Prefix Length</span></span> | <span data-ttu-id="45ae5-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="45ae5-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="45ae5-179">Local Port</span></span>       | <span data-ttu-id="45ae5-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-180">REG_SZ</span></span> | <span data-ttu-id="45ae5-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="45ae5-181">50000-50019</span></span> |
   |        <span data-ttu-id="45ae5-182">Протокол</span><span class="sxs-lookup"><span data-stu-id="45ae5-182">Protocol</span></span>        | <span data-ttu-id="45ae5-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="45ae5-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="45ae5-184">Remote IP</span></span>        | <span data-ttu-id="45ae5-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="45ae5-186">Префикс удаленного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="45ae5-186">Remote IP Prefix</span></span>    | <span data-ttu-id="45ae5-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="45ae5-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="45ae5-188">Remote Port</span></span>       | <span data-ttu-id="45ae5-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="45ae5-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="45ae5-190">Throttle Rate</span></span>      | <span data-ttu-id="45ae5-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="45ae5-191">REG_SZ</span></span> |     <span data-ttu-id="45ae5-192">-1</span><span class="sxs-lookup"><span data-stu-id="45ae5-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="45ae5-193">Убедитесь в том, что значение для записи имени приложения правильно для нужного клиента, и убедитесь, что в объекте групповой политики отражены значения DSCP и Local Port.</span><span class="sxs-lookup"><span data-stu-id="45ae5-193">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
