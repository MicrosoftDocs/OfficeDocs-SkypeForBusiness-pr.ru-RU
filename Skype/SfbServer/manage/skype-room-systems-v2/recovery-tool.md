---
title: С помощью средства восстановления системы комнаты Скайп версии 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описывается использование средства восстановления для v2 Скайп комнаты систем, который можно использовать для переноса устаревший системы в поддерживаемых состояний.
ms.openlocfilehash: cd8e05be686cef1df44f364c515a6116edf06209
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504980"
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="6ee6a-103">С помощью средства восстановления системы комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="6ee6a-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="6ee6a-104">В этой статье описывается использование средства восстановления для v2 Скайп комнаты систем, который можно использовать для переноса устаревший системы в поддерживаемых состояний.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="6ee6a-105">Это средство можно использовать при консоли v2 систем комнаты Скайп отображает ошибку «устаревший конфигурации системы».</span><span class="sxs-lookup"><span data-stu-id="6ee6a-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="6ee6a-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="6ee6a-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="6ee6a-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="6ee6a-107">Prerequisites</span></span>

<span data-ttu-id="6ee6a-108">Загрузить последнюю версию [пакета установки версии 2 Скайп комнаты систем](https://go.microsoft.com/fwlink/?linkid=851168) и извлеките его USB памяти упрощенный или в сетевой папке доступной для устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="6ee6a-109">Кроме того, может потребоваться установить [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="6ee6a-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="6ee6a-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="6ee6a-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="6ee6a-111">Проверьте версию Windows</span><span class="sxs-lookup"><span data-stu-id="6ee6a-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="6ee6a-112">Для входа в учетную запись администратора, перейдя на **Параметры > настройки Windows > Admin входа в** с устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="6ee6a-113">Этот параметр, чтобы сводит на экране входа в систему.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="6ee6a-114">Войти в учетную запись администратора, администратора по умолчанию учетной записи из которых `admin` с паролем `sfb`.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="6ee6a-115">Выберите в меню "Пуск" и типом `winver.exe` в поле поиска и нажмите кнопку \**Выполните команду* на результат.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="6ee6a-116">Запишите номер после «Версия» во второй строке области сведений.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="6ee6a-117">Если версия показано 1607 или более ранних версий, следуйте указаниям в <a href="#Windows-up">Windows Update до восстановления</a> действия перед proceding для действия <a href="#Perform">выполнить восстановление</a> .</span><span class="sxs-lookup"><span data-stu-id="6ee6a-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="6ee6a-118">Если версия показано больше 1607, указания только <a href="#Perform">выполнить восстановление</a>.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="6ee6a-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="6ee6a-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="6ee6a-120">Обновление Windows до восстановления (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="6ee6a-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="6ee6a-121">Хотя по-прежнему вход в качестве администратора, запуска с повышенными привилегиями строке Powershell.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="6ee6a-122">Выполните команду `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="6ee6a-123">Запустите Центр обновления Windows и установите обновление для Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="6ee6a-124">После обновления для 1709 завершения входа обратно в учетной записи администратора и установите [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="6ee6a-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="6ee6a-125">Обновление может быть выполнено по ссылке или с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="6ee6a-126">При желании установите дополнительные доступные обновления из центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="6ee6a-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="6ee6a-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="6ee6a-128">Выполнение восстановления</span><span class="sxs-lookup"><span data-stu-id="6ee6a-128">Perform a recovery</span></span>

1. <span data-ttu-id="6ee6a-129">Войдите в учетную запись администратора на устройстве версии 2 Скайп комнаты систем и запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="6ee6a-130">Проверка с устройства версии 2 Скайп комнаты систем, которые могут получить доступ к `RecoveryTool.ps1` файл, который включается в файлы, извлеченные из пакета установки систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="6ee6a-131">Комплект можно найти в сетевую папку или USB-диска, используемый при подготовке необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="6ee6a-132">Выполните команду Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="6ee6a-133">При появлении запроса выберите параметр сценария `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="6ee6a-134">По завершении перезагрузите устройство систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="6ee6a-135">Он автоматически перезагрузить и возникающие полностью восстановленную еще раз.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="6ee6a-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="6ee6a-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="6ee6a-137">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="6ee6a-137">See also</span></span>
 
[<span data-ttu-id="6ee6a-138">Справка по версии 2 Скайп комнаты систем</span><span class="sxs-lookup"><span data-stu-id="6ee6a-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="6ee6a-139">Управление Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="6ee6a-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)