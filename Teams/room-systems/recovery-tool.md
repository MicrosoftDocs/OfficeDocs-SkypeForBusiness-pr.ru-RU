---
title: Используйте средство восстановления приложения "Комнаты Microsoft Teams"
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии.
ms.openlocfilehash: 90e6db7739a4a95e3f1fbde62f5b8dd8bde9e237
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427991"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="477b3-103">Используйте средство восстановления приложения "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="477b3-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="477b3-104">В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="477b3-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="477b3-105">Это средство можно использовать, если на консоли Microsoft Teams появляется сообщение об ошибке "системные конфигурации устарели".</span><span class="sxs-lookup"><span data-stu-id="477b3-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="477b3-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="477b3-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="477b3-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="477b3-107">Prerequisites</span></span>

<span data-ttu-id="477b3-108">Скачайте последний [установочный пакет Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) и извлеките его в сетевую папку, доступную для устройства с поддержкой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="477b3-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="477b3-109">Также может потребоваться установить [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="477b3-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="477b3-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="477b3-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="477b3-111">Проверка версии Windows</span><span class="sxs-lookup"><span data-stu-id="477b3-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="477b3-112">Войдите в учетную запись администратора, перейдя в **параметры> параметр Windows> "Администратор"** с устройства Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="477b3-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="477b3-113">Этот параметр открывает экран входа.</span><span class="sxs-lookup"><span data-stu-id="477b3-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="477b3-114">Войдите в учетную запись администратора, `admin` используя учетную запись администратора по умолчанию с паролем. `sfb`</span><span class="sxs-lookup"><span data-stu-id="477b3-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="477b3-115">В меню "Пуск" введите текст `winver.exe` в поле поиска и нажмите \**выполнить команду* .</span><span class="sxs-lookup"><span data-stu-id="477b3-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="477b3-116">Обратите внимание на число после "Version" на второй строке области сведений.</span><span class="sxs-lookup"><span data-stu-id="477b3-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="477b3-117">Если отображается версия 1607 или более ранней версии, выполните действия, описанные в статье <a href="#Windows-up">Обновление Windows перед восстановлением</a> , прежде чем припроцединг к выполнению действий по <a href="#Perform">восстановлению</a> .</span><span class="sxs-lookup"><span data-stu-id="477b3-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="477b3-118">Если указанная версия больше 1607, выполните действия, описанные в разделе <a href="#Perform">выполнение восстановления</a>.</span><span class="sxs-lookup"><span data-stu-id="477b3-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="477b3-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="477b3-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="477b3-120">Обновление Windows перед восстановлением (при необходимости)</span><span class="sxs-lookup"><span data-stu-id="477b3-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="477b3-121">Войдя в систему под учетной записью администратора, запустите запрос PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="477b3-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="477b3-122">Запустите команду `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="477b3-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="477b3-123">Запустите обновление Windows и установите обновление для Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="477b3-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="477b3-124">После обновления 1709 снова войдите в учетную запись администратора и установите [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="477b3-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="477b3-125">Обновление может быть выполнено из ссылки или с помощью центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="477b3-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="477b3-126">На необязательном этапе установите дополнительные обновления, доступные в Windows Update.</span><span class="sxs-lookup"><span data-stu-id="477b3-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="477b3-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="477b3-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="477b3-128">Выполнение восстановления</span><span class="sxs-lookup"><span data-stu-id="477b3-128">Perform a recovery</span></span>

1. <span data-ttu-id="477b3-129">Войдите в учетную запись администратора на устройстве комнат Microsoft Teams и запустите командную команду с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="477b3-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="477b3-130">Убедитесь в том, что на устройстве Microsoft Teams есть доступ к `RecoveryTool.ps1` файлу, который входит в файлы, извлеченные из пакета установки комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="477b3-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="477b3-131">Комплект можно найти в сетевой папке или USB-накопителе, используемом при подготовке необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="477b3-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="477b3-132">Запустите команду `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="477b3-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="477b3-133">При появлении запроса с параметром `1:"Repair System"`SELECT сценария.</span><span class="sxs-lookup"><span data-stu-id="477b3-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="477b3-134">После завершения работы перезагрузите устройство Microsoft Teams комнаты.</span><span class="sxs-lookup"><span data-stu-id="477b3-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="477b3-135">Она будет автоматически перезагружена, а второй раз восстановить ее.</span><span class="sxs-lookup"><span data-stu-id="477b3-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="477b3-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="477b3-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="477b3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="477b3-137">See also</span></span>
 
[<span data-ttu-id="477b3-138">Справка по приложению "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="477b3-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="477b3-139">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="477b3-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
