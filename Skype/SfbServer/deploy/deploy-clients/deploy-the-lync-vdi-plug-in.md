---
title: Развертывание плагина Lync VDI с помощью Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: В этом разделе обсуждаются процедуры развертывания Skype для бизнеса при подключении к удаленному виртуальному рабочему столу.
ms.openlocfilehash: 8892bf8b8772bdb301f914bca134d61e67ea934b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234407"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="0a87e-103">Развертывание плагина Lync VDI с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0a87e-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="0a87e-104">В этом разделе обсуждаются процедуры развертывания Skype для бизнеса при подключении к удаленному виртуальному рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="0a87e-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="0a87e-105">Вопросы планирования описаны в разделе [планирование Skype для бизнеса в среде VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="0a87e-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="0a87e-106">Среда инфраструктуры виртуальных рабочих столов (VDI) используется в некоторых организациях, имеющих особые требования к безопасности и соответствию.</span><span class="sxs-lookup"><span data-stu-id="0a87e-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="0a87e-107">Пользователи в этих организациях работают с локальными компьютерами Windows и клиентами для виртуального рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="0a87e-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="0a87e-108">Использование Skype для бизнеса для подключения, в котором требуется дополнительное программное обеспечение для VDI.</span><span class="sxs-lookup"><span data-stu-id="0a87e-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="0a87e-109">Существует два решения, которые можно найти в компоненте «плагин» для VDI — один из предлагаемых корпорацией Майкрософт, а другой — Citrix.</span><span class="sxs-lookup"><span data-stu-id="0a87e-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="0a87e-110">Корпорация Майкрософт рекомендует использовать новый пакет оптимизации HDX в режиме реального времени в новых развертываниях, но продолжит поддерживать исходный плагин Lync в VDI для оставшейся части жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="0a87e-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="0a87e-111">В этом разделе приводятся сведения о том, как развернуть внешний элемент Microsoft Lync VDI, который поддерживается только в Windows 7 и Windows 8 или Windows Server 2008 и поддерживает только клиенты Lync 2013 или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0a87e-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="0a87e-112">Вы не планируете обновлять этот подключаемый модуль, но [Пакет оптимизации для HDX в реальном времени](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) для Skype для бизнеса будет обновляться по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0a87e-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="0a87e-113">Подготовка среды для подключаемого модуля VDI для Lync</span><span class="sxs-lookup"><span data-stu-id="0a87e-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="0a87e-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="0a87e-114"></span></span>

1. <span data-ttu-id="0a87e-115">В Skype для бизнеса Server убедитесь, что для Енаблемедиаредиректион для всех пользователей с внешними пользователями Lync VDI установлено значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="0a87e-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="0a87e-116">Подробные сведения можно найти в разделах справки по командлетам [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) и командлету [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0a87e-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="0a87e-117">На сервере центра обработки данных установите клиент Skype для бизнеса на всех виртуальных рабочих столах.</span><span class="sxs-lookup"><span data-stu-id="0a87e-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="0a87e-118">Установите плагин Lync VDI на локальных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0a87e-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="0a87e-119">Теперь пользователям потребуется подключить устройство, например гарнитуру или веб-камеру, к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0a87e-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="0a87e-120">Настройка параметров подключения к удаленному рабочему столу</span><span class="sxs-lookup"><span data-stu-id="0a87e-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="0a87e-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="0a87e-121"></span></span>

<span data-ttu-id="0a87e-122">Чтобы подготовить подключение к удаленному рабочему столу для плагина Lync VDI, выполните указанные ниже действия на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0a87e-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="0a87e-123">Если на локальном компьютере установлена операционная система Windows 8, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="0a87e-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="0a87e-124">Если на локальном компьютере установлена операционная система Windows 7 с пакетом обновления 1 (SP1), установите последнюю версию [клиента служб удаленных рабочих столов](https://go.microsoft.com/fwlink/p/?LinkId=268032)для Windows 8.</span><span class="sxs-lookup"><span data-stu-id="0a87e-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="0a87e-125">Запустите клиент служб удаленных рабочих столов, выбрав в меню \*\*Пуск \*\* пункт **Подключение к удаленному рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="0a87e-126">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="0a87e-127">Перейдите на вкладку **Локальные ресурсы**. В разделе **Звук удаленного рабочего стола** щелкните **Параметры**, а затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0a87e-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="0a87e-128">В разделе **Воспроизведение звука удаленного рабочего стола** выберите **Проигрывать на этом компьютере**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="0a87e-129">В разделе **Запись звука удаленного рабочего стола** выберите **Не записывать**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="0a87e-130">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="0a87e-131">Перейдите на вкладку **Взаимодействие**. В разделе **Производительность** снимите флажок **Постоянное кэширование точечных рисунков**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="0a87e-132">Перейдите на вкладку **Общие**. В поле **Компьютер** введите имя виртуального рабочего стола, а затем нажмите кнопку **Подключить**. </span><span class="sxs-lookup"><span data-stu-id="0a87e-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="0a87e-133">Вход в Skype для бизнеса и работа с ним на виртуальном рабочем столе</span><span class="sxs-lookup"><span data-stu-id="0a87e-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="0a87e-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="0a87e-134"></span></span>

<span data-ttu-id="0a87e-135">После включения Plug-in Lync пользователь выполняет указанные ниже действия при входе в Skype для бизнеса на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="0a87e-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="0a87e-136">Пользователь вводит свои учетные данные в клиент Skype для бизнеса, работающий на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="0a87e-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="0a87e-137">После того как Skype для бизнеса обнаружит плагин Lync VDI, в Skype для бизнеса пользователю будет предложено повторно ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0a87e-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="0a87e-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span><span class="sxs-lookup"><span data-stu-id="0a87e-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="0a87e-139">В Skype для бизнеса начинается связывание с помощью плагина Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="0a87e-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="0a87e-140">В этом случае клиент отображает два значка в строке состояния Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0a87e-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="0a87e-141">Значок в левой части экрана указывает на то, что звуковые устройства недоступны, а значок мигания справа внизу указывает на то, что выполняется связывание VDI.</span><span class="sxs-lookup"><span data-stu-id="0a87e-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="0a87e-142">После успешного связывания VDI значки изменяются, указывая звуковое устройство, которое будет использоваться для звонков и успешное связывание VDI: b.</span><span class="sxs-lookup"><span data-stu-id="0a87e-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="0a87e-143">Теперь пользователь может видеть свое присутствие на устройствах, поддерживающих Skype для бизнеса, которые подключены к локальному компьютеру, и размещайте и отвечайте на звонки в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="0a87e-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="0a87e-144">Устранение неполадок подключаемого модуля VDI для Lync</span><span class="sxs-lookup"><span data-stu-id="0a87e-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="0a87e-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="0a87e-145"></span></span>

<span data-ttu-id="0a87e-146">Ниже приведены разделы, которые содержат сведения о проблемах установки подключаемого модуля Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="0a87e-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="0a87e-147">Проблемы при установке подключаемого модуля VDI для Lync </span><span class="sxs-lookup"><span data-stu-id="0a87e-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="0a87e-148">Если у вас возникли проблемы при установке плагина Lync VDI, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="0a87e-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="0a87e-149">Убедитесь в наличии достаточного свободного пространства в папке, указанной в системных переменных TEMP и TMP.</span><span class="sxs-lookup"><span data-stu-id="0a87e-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="0a87e-150">Убедитесь в том, что защита от записи отключена.</span><span class="sxs-lookup"><span data-stu-id="0a87e-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="0a87e-151">Инструкции можно найти в документации изготовителя устройства.</span><span class="sxs-lookup"><span data-stu-id="0a87e-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="0a87e-152">Устранение неполадок сопряжения</span><span class="sxs-lookup"><span data-stu-id="0a87e-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="0a87e-153">Если связывание с внешним подключением Lync VDI завершается сбоем, значок связывания в правом нижнем углу отображается как красный крестик, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0a87e-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="0a87e-154">Далее перечислены возможные причины ошибок и рекомендуемые меры по исправлению. </span><span class="sxs-lookup"><span data-stu-id="0a87e-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="0a87e-155">**Пользователем введены неправильные учетные данные при входе в систему.**</span><span class="sxs-lookup"><span data-stu-id="0a87e-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="0a87e-156">Пользователь должен выйти из Skype для бизнеса и войти в систему с правильными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="0a87e-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="0a87e-157">В повторно открывшемся диалоговом окне отобразится уведомление об успешном сопряжении.</span><span class="sxs-lookup"><span data-stu-id="0a87e-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="0a87e-158">**Выполняется другой экземпляр клиента удаленного рабочего стола.**</span><span class="sxs-lookup"><span data-stu-id="0a87e-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="0a87e-159">Если они используют подключение к удаленному рабочему столу в Windows, пользователи должны выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0a87e-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="0a87e-160">Запустите диспетчер задач: нажмите клавиши **ALT+CTRL+DELETE** и выберите пункт **Запустить диспетчер задач**.</span><span class="sxs-lookup"><span data-stu-id="0a87e-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="0a87e-161">Перейдите на вкладку **Процессы** и найдите все процессы с именем **mstsc.exe** в списке.</span><span class="sxs-lookup"><span data-stu-id="0a87e-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="0a87e-162">Выделите каждый процесс **mstsc.exe** и нажмите кнопку **Завершить процесс**. </span><span class="sxs-lookup"><span data-stu-id="0a87e-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="0a87e-163">Запустите новый сеанс удаленного рабочего стола и повторите попытку подключения. </span><span class="sxs-lookup"><span data-stu-id="0a87e-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="0a87e-164">**Не удалось установить необходимые файлы.**</span><span class="sxs-lookup"><span data-stu-id="0a87e-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="0a87e-165">После установки подключаемого модуля на локальный компьютер в папке C:\Program Files\Microsoft Office\Office15 (буква диска может быть другой) должны появиться следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="0a87e-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="0a87e-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="0a87e-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="0a87e-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="0a87e-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="0a87e-168">**Клиент Skype для бизнеса запущен на локальном компьютере.**</span><span class="sxs-lookup"><span data-stu-id="0a87e-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="0a87e-169">Для использования плагина Lync VDI на локальном компьютере не должен выполняться клиент Skype для бизнеса, в противном случае связывание завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="0a87e-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="0a87e-170">Рекомендуется не устанавливать клиент Skype для бизнеса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0a87e-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0a87e-171">См. также</span><span class="sxs-lookup"><span data-stu-id="0a87e-171">See also</span></span>
<span data-ttu-id="0a87e-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="0a87e-172"></span></span>

[<span data-ttu-id="0a87e-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="0a87e-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
