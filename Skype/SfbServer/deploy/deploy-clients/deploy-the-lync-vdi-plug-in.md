---
title: Развертывание подключаемого модуля VDI для Lync в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: В этом разделе рассматриваются процедуры развертывания для использования Скайп для бизнеса при подключении к удаленной виртуальных рабочих столов.
ms.openlocfilehash: 47491b4409f21386cf28f811b6c2c3cbffe1e69b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501673"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="f331d-103">Развертывание подключаемого модуля VDI для Lync в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f331d-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f331d-104">В этом разделе рассматриваются процедуры развертывания для использования Скайп для бизнеса при подключении к удаленной виртуальных рабочих столов.</span><span class="sxs-lookup"><span data-stu-id="f331d-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="f331d-105">Среда инфраструктуры виртуальных рабочих столов (VDI) используется в некоторых организациях, имеющих особые требования к безопасности и соответствию.</span><span class="sxs-lookup"><span data-stu-id="f331d-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f331d-106">Пользователи в этих организациях работают с локальными компьютерами Windows и клиентами для виртуального рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="f331d-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f331d-107">Для использования Скайп для бизнеса на подключение так, требуется дополнительное программное обеспечение инфраструктуры виртуальных рабочих СТОЛОВ для подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="f331d-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f331d-108">Существует два решения для компонента подключаемого модуля инфраструктуры виртуальных рабочих СТОЛОВ - один предлагаемых корпорацией Майкрософт и один предлагаемыми Citrix.</span><span class="sxs-lookup"><span data-stu-id="f331d-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f331d-109">Корпорация Майкрософт рекомендует использовать новое решение HDX в реальном времени Optimization Pack новые развертывания, но будет для поддержки исходного подключаемого модуля VDI Lync для оставшейся части его жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="f331d-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f331d-110">В этом разделе содержатся сведения о развертывании Microsoft Lync подключаемого модуля VDI, который поддерживается только в Windows 7 и Windows 8 или Windows Server 2008 и поддерживает только Lync 2013 или Скайп для клиентов Business 2015.</span><span class="sxs-lookup"><span data-stu-id="f331d-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="f331d-111">Не планируется обновление этого подключаемого модуля, но [Citrix HDX в реальном времени Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) для Скайп для бизнеса будут обновлены при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f331d-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f331d-112">Подготовка среды для подключаемого модуля VDI для Lync</span><span class="sxs-lookup"><span data-stu-id="f331d-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f331d-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f331d-113"></span></span>

1. <span data-ttu-id="f331d-114">Убедитесь в Скайп для Business Server 2015 EnableMediaRedirection имеет значение TRUE для всех пользователей, подключаемый модуль VDI для Lync.</span><span class="sxs-lookup"><span data-stu-id="f331d-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f331d-115">Для получения дополнительных сведений ознакомьтесь с разделами справки для командлета [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) и командлет [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f331d-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f331d-116">На сервере центра данных установите Скайп для клиента Business 2015 на всех виртуальных рабочих столов.</span><span class="sxs-lookup"><span data-stu-id="f331d-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f331d-117">На локальных компьютерах установите подключаемый модуль VDI для Lync.</span><span class="sxs-lookup"><span data-stu-id="f331d-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f331d-118">Теперь пользователям потребуется подключить устройство, например гарнитуру или веб-камеру, к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f331d-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f331d-119">Настройка параметров подключения к удаленному рабочему столу</span><span class="sxs-lookup"><span data-stu-id="f331d-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f331d-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f331d-120"></span></span>

<span data-ttu-id="f331d-121">Чтобы подготовить подключение к удаленному рабочему столу для подключаемого модуля VDI Lync, выполните следующие действия на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f331d-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f331d-122">Если локальный компьютер работает под управлением Windows 8, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="f331d-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f331d-123">Если локальный компьютер работает под управлением Windows 7 с пакетом обновления 1, установка последней версии Windows 8, [клиент служб удаленных рабочих столов](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="f331d-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f331d-124">Запустите клиент служб удаленных рабочих столов, выбрав в меню **Пуск ** пункт **Подключение к удаленному рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="f331d-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f331d-125">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="f331d-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="f331d-126">Перейдите на вкладку **Локальные ресурсы**. В разделе **Звук удаленного рабочего стола** щелкните **Параметры**, а затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f331d-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="f331d-127">В разделе **Воспроизведение звука удаленного рабочего стола** выберите **Проигрывать на этом компьютере**.</span><span class="sxs-lookup"><span data-stu-id="f331d-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="f331d-128">В разделе **Запись звука удаленного рабочего стола** выберите **Не записывать**.</span><span class="sxs-lookup"><span data-stu-id="f331d-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="f331d-129">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f331d-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="f331d-130">Перейдите на вкладку **Взаимодействие**. В разделе **Производительность** снимите флажок **Постоянное кэширование точечных рисунков**.</span><span class="sxs-lookup"><span data-stu-id="f331d-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f331d-131">Перейдите на вкладку **Общие**. В поле **Компьютер** введите имя виртуального рабочего стола, а затем нажмите кнопку **Подключить**. </span><span class="sxs-lookup"><span data-stu-id="f331d-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f331d-132">Вход в Skype для бизнеса и работа с ним на виртуальном рабочем столе</span><span class="sxs-lookup"><span data-stu-id="f331d-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f331d-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f331d-133"></span></span>

<span data-ttu-id="f331d-134">После включения подключаемого модуля VDI Lync пользователь выполняет следующие действия при входе в Скайп для бизнеса 2015 на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="f331d-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f331d-135">Пользователь вводит свои учетные данные в к Скайп для клиента Business 2015, работающим на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="f331d-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f331d-136">После Скайп для бизнеса 2015 обнаруживает подключаемого модуля VDI Lync, Скайп для бизнеса 2015 пользователю повторного ввода учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f331d-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f331d-137">В данном диалоговом рекомендуется пользователей установите флажок **Сохранить пароль** , чтобы он или она не должен будет ввести учетные данные во время последующих входа в.</span><span class="sxs-lookup"><span data-stu-id="f331d-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f331d-138">Скайп для бизнеса 2015 начинается связывания с подключаемого модуля VDI Lync.</span><span class="sxs-lookup"><span data-stu-id="f331d-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f331d-139">Во время, которое происходит клиента отображает два значка в Скайп для строки состояния 2015 бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f331d-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="f331d-140">Значок в нижнем левом углу указывает на то, что доступные аудиоустройства отсутствуют, а мигающий значок в нижнем правом углу — на то, что выполняется процесс сопряжения VDI.</span><span class="sxs-lookup"><span data-stu-id="f331d-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="f331d-141">После успешного сопряжения подключаемого модуля VDI значки изменяются и теперь обозначают аудиоустройство, которое будет использоваться для выполнения вызовов, а также успешное сопряжение VDI:</span><span class="sxs-lookup"><span data-stu-id="f331d-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="f331d-142">Пользователь теперь можно просмотреть его присутствии Скайп для бизнеса 2015 совместимых устройств, подключенных к локальному компьютеру и поместите и отвечать на звонки в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="f331d-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f331d-143">Устранение неполадок подключаемого модуля VDI для Lync</span><span class="sxs-lookup"><span data-stu-id="f331d-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f331d-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f331d-144"></span></span>

<span data-ttu-id="f331d-145">Ниже приведены разделы, которые содержат сведения о проблемах установки подключаемого модуля Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f331d-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f331d-146">Проблемы при установке подключаемого модуля VDI для Lync </span><span class="sxs-lookup"><span data-stu-id="f331d-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f331d-147">При наличии проблем при установке подключаемого модуля VDI Lync, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="f331d-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f331d-148">Убедитесь в наличии достаточного свободного пространства в папке, указанной в системных переменных TEMP и TMP.</span><span class="sxs-lookup"><span data-stu-id="f331d-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f331d-149">Убедитесь в том, что защита от записи отключена.</span><span class="sxs-lookup"><span data-stu-id="f331d-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f331d-150">Обратитесь к документации производителя устройства для получения инструкций.</span><span class="sxs-lookup"><span data-stu-id="f331d-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f331d-151">Устранение неполадок сопряжения</span><span class="sxs-lookup"><span data-stu-id="f331d-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f331d-152">Когда связывания на подключаемый модуль VDI для Lync не удается, значок связывания в нижнем правом отображается как красный значок «X» как показано:</span><span class="sxs-lookup"><span data-stu-id="f331d-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f331d-153">Далее перечислены возможные причины ошибок и рекомендуемые меры по исправлению. </span><span class="sxs-lookup"><span data-stu-id="f331d-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f331d-154">**Пользователем введены неправильные учетные данные при входе в систему.**</span><span class="sxs-lookup"><span data-stu-id="f331d-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f331d-155">Пользователь должен выйти из Скайп для бизнеса и снова выполните вход с помощью правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f331d-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f331d-156">В повторно открывшемся диалоговом окне отобразится уведомление об успешном сопряжении.</span><span class="sxs-lookup"><span data-stu-id="f331d-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f331d-157">**Выполняется другой экземпляр клиента удаленного рабочего стола.**</span><span class="sxs-lookup"><span data-stu-id="f331d-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f331d-158">Если используется подключение к удаленному рабочему столу в Windows, пользователь должен выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="f331d-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f331d-159">Запустите диспетчер задач: нажмите клавиши **ALT+CTRL+DELETE** и выберите пункт **Запустить диспетчер задач**.</span><span class="sxs-lookup"><span data-stu-id="f331d-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f331d-160">Перейдите на вкладку **Процессы** и найдите все процессы с именем **mstsc.exe** в списке.</span><span class="sxs-lookup"><span data-stu-id="f331d-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f331d-161">Выделите каждый процесс **mstsc.exe** и нажмите кнопку **Завершить процесс**. </span><span class="sxs-lookup"><span data-stu-id="f331d-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f331d-162">Запустите новый сеанс удаленного рабочего стола и повторите попытку подключения. </span><span class="sxs-lookup"><span data-stu-id="f331d-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f331d-163">**Не удалось установить необходимые файлы.**</span><span class="sxs-lookup"><span data-stu-id="f331d-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f331d-164">После установки подключаемого модуля на локальный компьютер в папке C:\Program Files\Microsoft Office\Office15 (буква диска может быть другой) должны появиться следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="f331d-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f331d-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f331d-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f331d-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f331d-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="f331d-167">**Скайп для клиента Business 2015 выполняется на локальном компьютере.**</span><span class="sxs-lookup"><span data-stu-id="f331d-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f331d-168">Чтобы использовать VDI для Lync подключаемый модуль Скайп для клиента Business 2015 не должна выполняться на локальном компьютере, в противном случае связывания завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f331d-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f331d-169">Рекомендуется пользователь не следует устанавливать Скайп для клиента Business 2015 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f331d-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f331d-170">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="f331d-170">See also</span></span>
<span data-ttu-id="f331d-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f331d-171"></span></span>

[<span data-ttu-id="f331d-172">Планирование Скайп для бизнеса в средах инфраструктуры виртуальных рабочих СТОЛОВ</span><span class="sxs-lookup"><span data-stu-id="f331d-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)