---
title: Скачивание и установка Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Скачайте, установите и используйте Windows PowerShell 5.1, чтобы создать удаленный сеанс PowerShell, соединяющийся с приложением Skype для бизнеса Online.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029100"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="e5d54-103">Скачивание и установка Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e5d54-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="e5d54-104">Если вы используете юбилейное обновление Windows 10 или Windows Server 2016, у вас уже должно быть приложение Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="e5d54-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5d54-105">Это обусловлено тем, что это приложение входит в состав этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="e5d54-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="e5d54-106">Чтобы узнать, какую версию Microsoft PowerShell вы используете, выполните следующие действия на компьютере под управлением ОС Windows 7, Windows Server 2008 R2 или Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="e5d54-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="e5d54-107">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные**, **Windows PowerShell** и затем щелкните **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e5d54-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e5d54-108">В консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d54-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="e5d54-109">В окне консоли должны отобразиться примерно такие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5d54-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="e5d54-110">Если возвращается номер версии 5.1, значит вы используете Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="e5d54-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5d54-111">В противном случае вам необходимо установить Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="e5d54-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5d54-112">Для этого можно скачать платформу Windows Management Framework 5.1, в состав которой входит среда Windows PowerShell 5.1, из [Центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="e5d54-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="e5d54-113">Если вы убедились, что у вас установлена версия Windows PowerShell 5.1, необходимо проверить, настроена ли версия PowerShell для работы с удаленно исполняемыми сценариями.</span><span class="sxs-lookup"><span data-stu-id="e5d54-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="e5d54-114">Для этого запустите приложение PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="e5d54-115">В ОС Windows 7, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5d54-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="e5d54-116">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e5d54-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="e5d54-117">Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы подтвердить запуск PowerShell с использованием учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e5d54-118">В системе Windows 8 выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e5d54-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="e5d54-p104">Откройте панель чудо-кнопок и выберите **Поиск**, после чего щелкните правой кнопкой мыши элемент **Windows PowerShell**. Для быстрого доступа к панели чудо-кнопок на любом компьютере под управлением ОС Windows 8 (независимо от наличия сенсорного экрана) нажмите клавишу Windows и, не отпуская ее, клавишу C.</span><span class="sxs-lookup"><span data-stu-id="e5d54-p104">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="e5d54-121">В панели инструментов внизу экрана выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e5d54-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="e5d54-122">Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e5d54-p105">После запуска PowerShell необходимо разрешить работу с удаленными сценариями в политике выполнения. Для этого в консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d54-p105">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="e5d54-125">При выполнении этой команды может появляться следующее сообщение об ошибке: > *Set-ExecutionPolicy: Доступ к разделу реестра "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell" запрещен.*</span><span class="sxs-lookup"><span data-stu-id="e5d54-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="e5d54-126">Как правило, это сообщение выводится, если вы запустили PowerShell без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="e5d54-127">Чтобы исправить эту ошибку, закройте сеанс PowerShell и запустите новый сеанс от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="e5d54-128">Чтобы проверить правильность настройки политики выполнения, в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d54-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="e5d54-129">Если все настроено правильно, команда вернет следующее значение:</span><span class="sxs-lookup"><span data-stu-id="e5d54-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="e5d54-130">Если вы не используете Windows PowerShell 5.1, вам также необходимо скачать и установить платформу Windows Management Framework 5.1 из Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e5d54-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="e5d54-131">Этот пакет установки включает в себя Windows PowerShell 5.1 и Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="e5d54-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="e5d54-132">Его можно использовать, например, если вы работаете в ОС Windows 7 с пакетом обновления 1 (SP1) и еще не выполнили обновление до Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="e5d54-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5d54-133">В системах Windows Server 2016 и Windows 10 с юбилейным обновлением устанавливать приложение Windows PowerShell 5.1 обычно не требуется.</span><span class="sxs-lookup"><span data-stu-id="e5d54-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5d54-134">Версия Windows PowerShell 5.1 входит в состав этих операционных систем.</span><span class="sxs-lookup"><span data-stu-id="e5d54-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="e5d54-135">Перед установкой Windows Management Framework 5.1 проверьте выполнение перечисленных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="e5d54-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="e5d54-136">Убедитесь, что вы скачали правильную версию пакета установки.</span><span class="sxs-lookup"><span data-stu-id="e5d54-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="e5d54-137">Для 64-разрядной версии Windows 7 с пакетом обновления 1 (SP1) скачайте файл Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="e5d54-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="e5d54-138">Для 32-разрядной версии Windows 7 необходимо скачать файл Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="e5d54-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="e5d54-139">Для системы Windows 7 должен быть установлен пакет обновления 1.</span><span class="sxs-lookup"><span data-stu-id="e5d54-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="e5d54-p109">Если вы не знаете свою версию Windows или не уверены, установлен ли у вас пакет обновления 1 для Windows 7, откройте меню **Пуск**, щелкните правой кнопкой мыши пункт **Компьютер** и выберите пункт **Свойства**. Нужная информация будет представлена в диалоговом окне "Система".</span><span class="sxs-lookup"><span data-stu-id="e5d54-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="e5d54-142">Чтобы установить Windows Management Framework 5.1, выполните процедуру из статьи [Установка и настройка WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="e5d54-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="e5d54-p110">После перезагрузки проверьте работоспособность Windows PowerShell и возможность запуска этого приложения от имени администратора. Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5d54-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="e5d54-145">В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="e5d54-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="e5d54-146">Если появится диалоговое окно "Контроль учетных записей", нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e5d54-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e5d54-p111">В появившейся консоли PowerShell необходимо убедиться, что служба WinRM запущена и правильно настроена. Для этого в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d54-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="e5d54-149">На экране появятся сведения о службе WinRM:</span><span class="sxs-lookup"><span data-stu-id="e5d54-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="e5d54-150">Если в столбце состояния не указано, что служба WinRM запущена, запустите ее. Для этого введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d54-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="e5d54-151">После запуска службы WinRM введите следующую команду, чтобы убедиться, что используется базовая проверка подлинности:</span><span class="sxs-lookup"><span data-stu-id="e5d54-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="e5d54-152">На экране появятся примерно следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e5d54-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="e5d54-153">Если настроена и применяется обычная проверка подлинности, вы можете использовать PowerShell для соединения с приложением Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e5d54-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="e5d54-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e5d54-154">Related topics</span></span>
[<span data-ttu-id="e5d54-155">Настройка компьютера для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5d54-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
