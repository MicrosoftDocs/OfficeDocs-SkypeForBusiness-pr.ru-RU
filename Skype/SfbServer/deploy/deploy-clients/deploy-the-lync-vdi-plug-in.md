---
title: Развертывание подключаемого модуль Lync VDI со Skype для бизнеса Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: В этом разделе обсуждаются процедуры развертывания Skype для бизнеса при подключении к удаленному виртуальному рабочему столу.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805939"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="780ae-103">Развертывание подключаемого модуль Lync VDI со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="780ae-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="780ae-104">В этом разделе обсуждаются процедуры развертывания Skype для бизнеса при подключении к удаленному виртуальному рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="780ae-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="780ae-105">Вопросы планирования рассматриваются в [планировании Skype для бизнеса в средах VDI.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)</span><span class="sxs-lookup"><span data-stu-id="780ae-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="780ae-106">Среда инфраструктуры виртуальных рабочих стола (VDI) используется в некоторых организациях, где вопросы безопасности и соответствия требованиям являются особенно конфиденциальными.</span><span class="sxs-lookup"><span data-stu-id="780ae-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="780ae-107">Их пользователи находятся на локальных компьютерах с Windows и используют клиенты на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="780ae-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="780ae-108">Использование Skype для бизнеса для подключения, например для использования дополнительного подключаемого программного обеспечения VDI.</span><span class="sxs-lookup"><span data-stu-id="780ae-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="780ae-109">Существует два решения, доступных для компонента подключаемого модульного подключения VDI: одно, предложенное корпорацией Майкрософт, и одно решение, предложенное Citrix.</span><span class="sxs-lookup"><span data-stu-id="780ae-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="780ae-110">Корпорация Майкрософт рекомендует использовать новое решение hdX RealTime Optimization Pack в новых развертываниях, но будет продолжать поддерживать исходный подключаемый модуль Lync VDI в течение оставшегося срока его жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="780ae-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="780ae-111">В этом разделе подробно приводится информация о развертывании подключаемого модуль VDI microsoft Lync, который поддерживается только в Windows 7 и Windows 8 или Windows Server 2008, а также поддерживает только клиенты Lync 2013 или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="780ae-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="780ae-112">Обновлять этот подключаемый модуль не планируется, но пакет оптимизации [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) для Skype для бизнеса будет обновлен по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="780ae-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="780ae-113">Подготовка среды для подключаемого модуль Lync VDI</span><span class="sxs-lookup"><span data-stu-id="780ae-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="780ae-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="780ae-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="780ae-115">В Skype для бизнеса Server убедитесь, что для enableMediaRedirection установлено true для всех пользователей подключаемого модульного подключения Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="780ae-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="780ae-116">Подробные сведения см. в справке по cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) и [Set-CsClientPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="780ae-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="780ae-117">На сервере центра обработки данных установите клиент Skype для бизнеса на всех виртуальных рабочих столах.</span><span class="sxs-lookup"><span data-stu-id="780ae-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="780ae-118">На локальных компьютерах установите подключаемый модуль Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="780ae-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="780ae-119">Теперь пользователи должны подключить устройство, например гарнитуру или веб-камеру, к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="780ae-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="780ae-120">Настройка параметров подключения к удаленному рабочему столу</span><span class="sxs-lookup"><span data-stu-id="780ae-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="780ae-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="780ae-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="780ae-122">Чтобы подготовить подключение к удаленному рабочему столу для подключаемого модуль Lync VDI, выполните следующие действия на локальном компьютере:</span><span class="sxs-lookup"><span data-stu-id="780ae-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="780ae-123">Если локальный компьютер работает Windows 8, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="780ae-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="780ae-124">Если на локальном компьютере работает Windows 7 с sp1, установите последнюю версию Windows 8 клиента служб [удаленных рабочих стола.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="780ae-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="780ae-125">Запустите клиент служб удаленных рабочих столов, выбрав в меню **Пуск** пункт **Подключение к удаленному рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="780ae-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="780ae-126">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="780ae-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="780ae-127">Перейдите на вкладку **Локальные ресурсы**. В разделе **Звук удаленного рабочего стола** щелкните **Параметры**, а затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="780ae-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="780ae-128">В разделе **Воспроизведение звука удаленного рабочего стола** выберите **Проигрывать на этом компьютере**.</span><span class="sxs-lookup"><span data-stu-id="780ae-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="780ae-129">В разделе **Запись звука удаленного рабочего стола** выберите **Не записывать**.</span><span class="sxs-lookup"><span data-stu-id="780ae-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="780ae-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="780ae-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="780ae-131">Перейдите на вкладку **Experience** (Взаимодействие). В разделе **Performance** (Производительность) снимите флажок **Persistent bitmap caching** (Постоянное кэширование точечных рисунков).</span><span class="sxs-lookup"><span data-stu-id="780ae-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="780ae-132">Щелкните **вкладку "Общие".** В **компьютере** введите имя виртуального рабочего стола и нажмите кнопку **"Подключиться".**</span><span class="sxs-lookup"><span data-stu-id="780ae-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="780ae-133">Вход и использование Skype для бизнеса на виртуальном рабочем столе</span><span class="sxs-lookup"><span data-stu-id="780ae-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="780ae-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="780ae-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="780ae-135">После включения подключаемого модуль VDI Lync пользователь выполнит следующие действия при входе в Skype для бизнеса на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="780ae-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="780ae-136">Пользователь внося свои учетные данные в клиент Skype для бизнеса, работающий на виртуальном рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="780ae-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="780ae-137">После того как Skype для бизнеса обнаружит подключаемый модуль Lync VDI, Skype для бизнеса запросит у пользователя повторно ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="780ae-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="780ae-138">Рекомендуется, чтобы пользователь установил флажок **Сохранить пароль** в этом диалоговом окне, так как в этом случае ему не придется вводить свои учетные данные при последующем входе в систему.</span><span class="sxs-lookup"><span data-stu-id="780ae-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="780ae-139">Skype для бизнеса начинает сопряжение с подключаемый модуль VDI Lync.</span><span class="sxs-lookup"><span data-stu-id="780ae-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="780ae-140">В этом случае клиент отображает два значка в панели состояния Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="780ae-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="780ae-141">Значок в левом нижнем конце означает, что звуковые устройства недоступны, а мигающий значок в правом нижнем — на то, что идет сопряжение VDI: a.</span><span class="sxs-lookup"><span data-stu-id="780ae-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="780ae-142">После успешного сопряжения VDI значки изменяются, чтобы указать звуковое устройство, которое будет использоваться для вызовов, и успешное сопряжение VDI: b.</span><span class="sxs-lookup"><span data-stu-id="780ae-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="780ae-143">Теперь пользователь может видеть свое присутствие на совместимых с Skype для бизнеса устройствах, подключенных к локальному компьютеру, а также делать вызовы и отвечать на них обычным образом.</span><span class="sxs-lookup"><span data-stu-id="780ae-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="780ae-144">Устранение неполадок подключаемого модуль VDI Lync</span><span class="sxs-lookup"><span data-stu-id="780ae-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="780ae-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="780ae-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="780ae-146">Если после установки подключаемого модуль VDI Lync вы столкнулись с проблемой, обратитесь к следующим разделам.</span><span class="sxs-lookup"><span data-stu-id="780ae-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="780ae-147">Проблемы с установкой подключаемого модуль VDI Lync</span><span class="sxs-lookup"><span data-stu-id="780ae-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="780ae-148">При проблемах с установкой подключаемого модуль Lync VDI проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="780ae-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="780ae-149">Убедитесь в наличии достаточного свободного пространства в папке, указанной в системных переменных TEMP и TMP.</span><span class="sxs-lookup"><span data-stu-id="780ae-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="780ae-150">Убедитесь в том, что защита от записи отключена.</span><span class="sxs-lookup"><span data-stu-id="780ae-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="780ae-151">Инструкции можно найти в документации производителя устройства.</span><span class="sxs-lookup"><span data-stu-id="780ae-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="780ae-152">Диагностика неполадок сопряжения</span><span class="sxs-lookup"><span data-stu-id="780ae-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="780ae-153">Если происходит сбой сопряжения подключаемого модульного подключения Lync VDI, значок сопряжения в правом нижнем цвете отображается как красный "X", как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="780ae-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="780ae-154">Ниже следующую причину сбоев и действия, которые можно принять для устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="780ae-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="780ae-155">**Пользователем введены неправильные учетные данные при входе в систему.**</span><span class="sxs-lookup"><span data-stu-id="780ae-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="780ae-156">Пользователь должен выйти из Skype для бизнеса и снова войти с правильными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="780ae-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="780ae-157">В повторно открывшемся диалоговом окне отобразится уведомление об успешном сопряжении.</span><span class="sxs-lookup"><span data-stu-id="780ae-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="780ae-158">**Запущен еще один экземпляр клиента удаленного рабочего стола.**</span><span class="sxs-lookup"><span data-stu-id="780ae-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="780ae-159">Если они используют подключение к удаленному рабочему столу в Windows, пользователям следует сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="780ae-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="780ae-160">Запустить диспетчер задач: нажмите **Alt+Ctrl+Delete** и выберите **Запустить диспетчер задач**.</span><span class="sxs-lookup"><span data-stu-id="780ae-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="780ae-161">Перейдите на вкладку **Процессы** и проверьте все процессы с именем **mstsc.exe** в списке.</span><span class="sxs-lookup"><span data-stu-id="780ae-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="780ae-162">Выделите каждый из процессов **mstsc.exe** и нажмите **Завершить процесс**.</span><span class="sxs-lookup"><span data-stu-id="780ae-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="780ae-163">Запустите новый сеанс удаленного рабочего стола и повторите попытку подключения.</span><span class="sxs-lookup"><span data-stu-id="780ae-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="780ae-164">**Не удалось установить необходимые файлы.**</span><span class="sxs-lookup"><span data-stu-id="780ae-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="780ae-165">После установки подключаемого модуль на локальном компьютере убедитесь, что эти файлы находятся в папке C:\Program Files\Microsoft Office\Office15 (или соответствующая буква диска):</span><span class="sxs-lookup"><span data-stu-id="780ae-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="780ae-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="780ae-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="780ae-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="780ae-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="780ae-168">**Клиент Skype для бизнеса работает на локальном компьютере.**</span><span class="sxs-lookup"><span data-stu-id="780ae-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="780ae-169">Чтобы использовать подключаемый модуль VDI Lync, клиент Skype для бизнеса не должен работать на локальном компьютере, в противном случае сопряжение не удастся.</span><span class="sxs-lookup"><span data-stu-id="780ae-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="780ae-170">Не следует устанавливать клиент Skype для бизнеса на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="780ae-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="780ae-171">См. также</span><span class="sxs-lookup"><span data-stu-id="780ae-171">See also</span></span>
<span data-ttu-id="780ae-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="780ae-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="780ae-173">Планирование Skype для бизнеса в средах VDI</span><span class="sxs-lookup"><span data-stu-id="780ae-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
