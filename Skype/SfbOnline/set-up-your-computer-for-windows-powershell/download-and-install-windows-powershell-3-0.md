---
title: Скачайте и установите Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568325"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="4d4d3-103">Скачайте и установите Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="4d4d3-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="4d4d3-p101">[] Если вы используете Windows 8.1, Windows 8, Windows Server 2012 R2 или Windows Server 2012, у вас уже должна быть установлена версия Windows PowerShell 3.0, которая входит в состав этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p101">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0. That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="4d4d3-p102">Если вы работаете с Windows 7 или Windows Server 2008 R2, у вас также может быть установлена версия Windows PowerShell 3.0. Тем не менее вместо нее может использоваться версия 2.0, которая изначально поставлялась в составе этих операционных систем. Чтобы узнать, какую версию Microsoft PowerShell вы используете, выполните следующие действия на компьютере под управлением ОС Windows 7 или Windows Server 2008 R2:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p102">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0. However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems. To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="4d4d3-109">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные**, **Windows PowerShell** и затем щелкните **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4d4d3-110">В консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="4d4d3-111">В окне консоли должна появиться информация примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    <span data-ttu-id="4d4d3-p103">Если возвращается номер версии 3.0, значит вы используете Windows PowerShell 3.0. В противном случае вам необходимо установить Windows PowerShell 3.0. Для этого можно скачать платформу Windows Management Framework 3.0, в состав которой входит среда Windows PowerShell 3.0, из [Центра загрузки Майкрософт](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p103">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0. If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0. You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="4d4d3-p104">Если вы убедились, что у вас установлена версия Windows PowerShell 3.0, необходимо проверить, настроена ли версия PowerShell для работы с удаленно исполняемыми сценариями. Для этого запустите приложение PowerShell от имени администратора. В ОС Windows 7, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p104">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts. To do that, start PowerShell as an administrator. On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="4d4d3-118">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="4d4d3-119">Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="4d4d3-120">В ОС Windows 8 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="4d4d3-p105">Откройте панель чудо-кнопок и выберите **Поиск**, после чего щелкните правой кнопкой мыши элемент **Windows PowerShell**. Для быстрого доступа к панели чудо-кнопок на любом компьютере под управлением ОС Windows 8 (независимо от наличия сенсорного экрана) нажмите клавишу Windows и, не отпуская ее, клавишу C.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p105">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="4d4d3-123">В панели инструментов внизу экрана выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="4d4d3-124">Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="4d4d3-p106">После запуска PowerShell необходимо разрешить работу с удаленными сценариями в политике выполнения. Для этого в консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p106">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="4d4d3-127">При выполнении предыдущей команды, вы можете получить следующее сообщение об ошибке: > *Set-ExecutionPolicy: доступ к разделу реестра "HKEY_LOCAL_MACHINE\\программного обеспечения\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell "отказано.*</span><span class="sxs-lookup"><span data-stu-id="4d4d3-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="4d4d3-128">Это сообщение об ошибке, как правило, возникает, если не выполняется PowerShell с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="4d4d3-129">Чтобы исправить эту ошибку, закройте сеанс PowerShell и запустите новый сеанс от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="4d4d3-130">Чтобы проверить правильность настройки политики выполнения, в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="4d4d3-131">Если настройка выполнена правильно, будет возвращено следующее значение:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="4d4d3-p108">Если вы не используете Windows PowerShell 3.0, вам также необходимо скачать и установить платформу Windows Management Framework 3.0 из Центра загрузки Майкрософт. Этот пакет установки включает в себя Windows PowerShell 3.0 и Windows Remote Management (WinRM) 3.0. Его можно использовать в том случае, если вы работаете в ОС Windows 7 и еще не выполнили обновление до Windows PowerShell 3.0. В ОС Windows Server 2012, Windows Server 2012 R2, Windows 8 и Windows 8.1 устанавливать Windows PowerShell 3.0 не требуется. Версия Windows PowerShell 3.0 входит в состав этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p108">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center. This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0. This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0. If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0. Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="4d4d3-137">Перед установкой платформы Windows Management Framework 3.0 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="4d4d3-p109">Убедитесь, что вы скачали правильную версию пакета установки. Для 64-разрядной версии Windows 7 необходимо скачать файл Windows6.1-KB2506143-x64.msu. Для 32-разрядной версии Windows 7 потребуется файл Windows6.1-KB2506143-x86.msu.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p109">Make sure you have downloaded the correct version of the installation package. If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu. If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="4d4d3-141">Если на вашем компьютере установлена ОС Windows 7, проверьте наличие пакета обновления 1 для этой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="4d4d3-p110">Если вы не знаете свою версию Windows или не уверены, установлен ли у вас пакет обновления 1 для Windows 7, откройте меню **Пуск**, щелкните правой кнопкой мыши пункт **Компьютер** и выберите пункт **Свойства**. Нужная информация будет представлена в диалоговом окне "Система".</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p110">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="4d4d3-144">Чтобы установить платформу Windows Management Framework 3.0, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="4d4d3-145">Дважды щелкните установочный MSU-файл ( **Windows6.1-KB2506143-x64.msu** или **Windows6.1-KB2506143-x86.msu**).</span><span class="sxs-lookup"><span data-stu-id="4d4d3-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="4d4d3-146">В окне мастера скачивания и установки обновления на странице **Прочтите лицензионное соглашение (1 из 1)** нажмите кнопку **Я принимаю**.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="4d4d3-147">По завершении установки нажмите кнопку **Перезапустить сейчас**, чтобы перезагрузить компьютер.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="4d4d3-p111">После перезагрузки проверьте работоспособность Windows PowerShell и возможность запуска этого приложения от имени администратора. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p111">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="4d4d3-150">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="4d4d3-151">Если появится диалоговое окно "Контроль учетных записей", нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="4d4d3-p112">В появившейся консоли PowerShell необходимо убедиться, что служба WinRM запущена и правильно настроена. Для этого в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-p112">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="4d4d3-154">На экран будут выведены сведения о службе WinRM:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="4d4d3-155">Если в столбце состояния не указано, что служба WinRM запущена, запустите ее. Для этого введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="4d4d3-156">После запуска службы WinRM выполните следующую команду, чтобы проверить, что в ней используется обычная проверка подлинности:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="4d4d3-157">На экране должна появиться информация примерно следующего вида:</span><span class="sxs-lookup"><span data-stu-id="4d4d3-157">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="4d4d3-158">Если обычная проверка подлинности имеет значение true, а затем вы готовы к использование PowerShell для подключения к Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="4d4d3-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="4d4d3-159">See also</span><span class="sxs-lookup"><span data-stu-id="4d4d3-159">Related topics</span></span>
[<span data-ttu-id="4d4d3-160">Настройка компьютера для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d4d3-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 