---
title: Реализация качества обслуживания (QoS) в клиентах Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Узнайте, как использовать качество обслуживания (QoS) для оптимизации сетевого трафика для настольного клиента Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526406"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="9019d-103">Реализация качества обслуживания (QoS) в клиентах Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9019d-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="9019d-104">Вы можете использовать качество обслуживания (QoS) на основе политики в групповой политике, чтобы установить диапазон портов источника для предопределяемого значения DSCP в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="9019d-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="9019d-105">Диапазоны портов, указанные в таблице ниже, являются отправной точкой для создания политики для каждой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="9019d-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="9019d-106">*Таблица 1. Рекомендуемые диапазоны исходных портов*</span><span class="sxs-lookup"><span data-stu-id="9019d-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="9019d-107">Тип медиатрафика</span><span class="sxs-lookup"><span data-stu-id="9019d-107">Media traffic type</span></span>| <span data-ttu-id="9019d-108">Диапазон портов источника клиента </span><span class="sxs-lookup"><span data-stu-id="9019d-108">Client source port range</span></span> |<span data-ttu-id="9019d-109">Протокол</span><span class="sxs-lookup"><span data-stu-id="9019d-109">Protocol</span></span>|<span data-ttu-id="9019d-110">Значение DSCP</span><span class="sxs-lookup"><span data-stu-id="9019d-110">DSCP value</span></span>|<span data-ttu-id="9019d-111">Класс DSCP</span><span class="sxs-lookup"><span data-stu-id="9019d-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="9019d-112">Звук</span><span class="sxs-lookup"><span data-stu-id="9019d-112">Audio</span></span>| <span data-ttu-id="9019d-113">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="9019d-113">50,000–50,019</span></span>|<span data-ttu-id="9019d-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9019d-114">TCP/UDP</span></span>|<span data-ttu-id="9019d-115">46</span><span class="sxs-lookup"><span data-stu-id="9019d-115">46</span></span>|<span data-ttu-id="9019d-116">Беспрепятственная переадресация (EF)</span><span class="sxs-lookup"><span data-stu-id="9019d-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="9019d-117">Видео</span><span class="sxs-lookup"><span data-stu-id="9019d-117">Video</span></span>| <span data-ttu-id="9019d-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="9019d-118">50,020–50,039</span></span>|<span data-ttu-id="9019d-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9019d-119">TCP/UDP</span></span>|<span data-ttu-id="9019d-120">34</span><span class="sxs-lookup"><span data-stu-id="9019d-120">34</span></span>|<span data-ttu-id="9019d-121">Гарантированная переадресация (AF41)</span><span class="sxs-lookup"><span data-stu-id="9019d-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="9019d-122">Приложение / Разделение экрана</span><span class="sxs-lookup"><span data-stu-id="9019d-122">Application/Screen Sharing</span></span>| <span data-ttu-id="9019d-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="9019d-123">50,040–50,059</span></span>|<span data-ttu-id="9019d-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="9019d-124">TCP/UDP</span></span>|<span data-ttu-id="9019d-125">18</span><span class="sxs-lookup"><span data-stu-id="9019d-125">18</span></span>|<span data-ttu-id="9019d-126">Гарантированная пересылка (AF21)</span><span class="sxs-lookup"><span data-stu-id="9019d-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="9019d-127">По возможности настройте параметры QoS на основе политики в объекте групповой политики.</span><span class="sxs-lookup"><span data-stu-id="9019d-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="9019d-128">Следующие действия очень похожи на настройку диапазонов портов и политику качества обслуживания для клиентов в Skype для бизнеса  [Server,](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)где есть некоторые дополнительные сведения, которые могут не потребоваться.</span><span class="sxs-lookup"><span data-stu-id="9019d-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="9019d-129">Чтобы создать политику QoS для компьютеров с Windows 10, которые присоединились к домену, сначала войдите в систему на компьютере, на котором установлено управление групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="9019d-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="9019d-130">Откройте пункт "Управление групповой политикой" (нажмите кнопку "Начните", выберите пункт "Администрирование" и "Управление групповой политикой") и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9019d-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="9019d-131">В области управления групповыми политиками найдите контейнер, в котором нужно создать новую политику.</span><span class="sxs-lookup"><span data-stu-id="9019d-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="9019d-132">Например, если все клиентские компьютеры расположены в OU **Clients,** новая политика должна быть создана в клиентских клиентах.</span><span class="sxs-lookup"><span data-stu-id="9019d-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="9019d-133">Щелкните правой кнопкой мыши нужный контейнер, а затем выберите "Создать GPO" в этом домене **и привяжете его сюда.**</span><span class="sxs-lookup"><span data-stu-id="9019d-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="9019d-134">В **диалоговом** окне "Новый объект групповой политики"  введите имя нового объекта групповой политики в поле "Имя" и нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="9019d-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="9019d-135">Щелкните созданную политику правой кнопкой мыши и выберите **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9019d-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="9019d-136">В редакторе управления групповыми политиками раз щелкните "Конфигурация **компьютера",** разйдите в параметры **Windows,** щелкните **QoS** на основе политики правой кнопкой мыши и выберите "Создать новую **политику".**</span><span class="sxs-lookup"><span data-stu-id="9019d-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="9019d-137">В **диалоговом окне QoS** на странице открытия введите имя новой политики в поле **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="9019d-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="9019d-138">Выберите **"Задать значение DSCP"** и установите значение **46.**</span><span class="sxs-lookup"><span data-stu-id="9019d-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="9019d-139">Оставьте **невыбираемой укажите исходящие** тарифы и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="9019d-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="9019d-140">На следующей странице  выберите только приложения с этим **исполняемым** именем, введите имяTeams.exeи нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="9019d-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="9019d-141">Этот параметр предписывает политике только приоритетировать трафик, совпадающий с клиентом Teams.</span><span class="sxs-lookup"><span data-stu-id="9019d-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="9019d-142">На третьей странице убедитесь,  что выбраны  ip-адреса всех исходных и всех ip-адресов назначения, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="9019d-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="9019d-143">Эти два параметра гарантируют управление пакетами независимо от того, какой компьютер (IP-адрес) отправил пакеты и какой компьютер (IP-адрес) будет получать пакеты.</span><span class="sxs-lookup"><span data-stu-id="9019d-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="9019d-144">На странице 4 выберите **TCP** и UDP в списке **Select the protocol this QoS policy applies to** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9019d-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="9019d-145">TCP (Transmission Control Protocol) и UDP (User Datagram Protocol) — это два наиболее распространенных сетевых протокола.</span><span class="sxs-lookup"><span data-stu-id="9019d-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="9019d-146">Под заголовком **"Укажите номер порта источника"** выберите **"Из этого порта или диапазона источника".**</span><span class="sxs-lookup"><span data-stu-id="9019d-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="9019d-147">В текстовом поле введите диапазон порта, зарезервированный для передачи звука.</span><span class="sxs-lookup"><span data-stu-id="9019d-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="9019d-148">Например, если вы зарезервированы порты от 50000 до портов 50019 для аудиопотока, введите диапазон портов в таком формате: **50000:50019.**</span><span class="sxs-lookup"><span data-stu-id="9019d-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="9019d-149">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9019d-149">Click **Finish**.</span></span>

1. <span data-ttu-id="9019d-150">Повторите действия 5–10 для создания политик общего доступа к видео, приложениям и рабочему столу, заменив соответствующие значения на шагах 6 и 10.</span><span class="sxs-lookup"><span data-stu-id="9019d-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="9019d-151">Новые политики вступает в силу только после обновления групповой политики на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9019d-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="9019d-152">Хотя групповая политика периодически обновляется самостоятельно, вы можете немедленно обновить ее, вы предприняв указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9019d-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="9019d-153">На каждом компьютере, для которого вы хотите обновить групповую политику, откройте командную подсказку от администратора *(запуск от администратора).*</span><span class="sxs-lookup"><span data-stu-id="9019d-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="9019d-154">В командной области введите</span><span class="sxs-lookup"><span data-stu-id="9019d-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="9019d-155">Проверка маркировки DSCP в объекте групповой политики</span><span class="sxs-lookup"><span data-stu-id="9019d-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="9019d-156">Чтобы убедиться в том, что значения из объекта групповой политики за настроены, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9019d-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="9019d-157">Открытие командной подсказки от администратора *(запуск от администратора).*</span><span class="sxs-lookup"><span data-stu-id="9019d-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="9019d-158">В командной области введите</span><span class="sxs-lookup"><span data-stu-id="9019d-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="9019d-159">При этом будет создаваться отчет примененных GGPOS и отправляться в текстовый файл *с* gp.txt.</span><span class="sxs-lookup"><span data-stu-id="9019d-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="9019d-160">Для более учитываемого HTML-отчета *с именемgp.html* введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9019d-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="9019d-161">В созданном файле наймем заголовок "Примененные объекты групповой политики" и убедитесь, что имена объектов групповой политики, созданных ранее, находятся в списке примененных политик. </span><span class="sxs-lookup"><span data-stu-id="9019d-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="9019d-162">Откройте редактор реестра и перейдите в</span><span class="sxs-lookup"><span data-stu-id="9019d-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="9019d-163">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS</span><span class="sxs-lookup"><span data-stu-id="9019d-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="9019d-164">Проверьте значения записей реестра, перечисленных в таблице 2.</span><span class="sxs-lookup"><span data-stu-id="9019d-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="9019d-165">*Таблица 2. Значения для записей реестра Windows для QoS*</span><span class="sxs-lookup"><span data-stu-id="9019d-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="9019d-166">Имя</span><span class="sxs-lookup"><span data-stu-id="9019d-166">Name</span></span>          |  <span data-ttu-id="9019d-167">Тип</span><span class="sxs-lookup"><span data-stu-id="9019d-167">Type</span></span>  |    <span data-ttu-id="9019d-168">Значение</span><span class="sxs-lookup"><span data-stu-id="9019d-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="9019d-169">Application Name</span><span class="sxs-lookup"><span data-stu-id="9019d-169">Application Name</span></span>    | <span data-ttu-id="9019d-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-170">REG_SZ</span></span> |  <span data-ttu-id="9019d-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="9019d-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="9019d-172">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="9019d-172">DSCP Value</span></span>       | <span data-ttu-id="9019d-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-173">REG_SZ</span></span> |     <span data-ttu-id="9019d-174">46</span><span class="sxs-lookup"><span data-stu-id="9019d-174">46</span></span>      |
   |        <span data-ttu-id="9019d-175">Local IP</span><span class="sxs-lookup"><span data-stu-id="9019d-175">Local IP</span></span>        | <span data-ttu-id="9019d-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="9019d-177">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="9019d-177">Local IP Prefix Length</span></span> | <span data-ttu-id="9019d-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="9019d-179">Local Port</span><span class="sxs-lookup"><span data-stu-id="9019d-179">Local Port</span></span>       | <span data-ttu-id="9019d-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-180">REG_SZ</span></span> | <span data-ttu-id="9019d-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="9019d-181">50000-50019</span></span> |
   |        <span data-ttu-id="9019d-182">Протокол</span><span class="sxs-lookup"><span data-stu-id="9019d-182">Protocol</span></span>        | <span data-ttu-id="9019d-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="9019d-184">Remote IP</span><span class="sxs-lookup"><span data-stu-id="9019d-184">Remote IP</span></span>        | <span data-ttu-id="9019d-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="9019d-186">Префикс удаленного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="9019d-186">Remote IP Prefix</span></span>    | <span data-ttu-id="9019d-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="9019d-188">Remote Port</span><span class="sxs-lookup"><span data-stu-id="9019d-188">Remote Port</span></span>       | <span data-ttu-id="9019d-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="9019d-190">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="9019d-190">Throttle Rate</span></span>      | <span data-ttu-id="9019d-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="9019d-191">REG_SZ</span></span> |     <span data-ttu-id="9019d-192">-1</span><span class="sxs-lookup"><span data-stu-id="9019d-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="9019d-193">Убедитесь, что значение для имени приложения правильно для клиента, который вы используете, и убедитесь, что значения DSCP и локальный порт отражают параметры в объекте групповой политики.</span><span class="sxs-lookup"><span data-stu-id="9019d-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9019d-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9019d-194">Related topics</span></span>

[<span data-ttu-id="9019d-195">Реализация качества обслуживания (QoS) в Teams</span><span class="sxs-lookup"><span data-stu-id="9019d-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)