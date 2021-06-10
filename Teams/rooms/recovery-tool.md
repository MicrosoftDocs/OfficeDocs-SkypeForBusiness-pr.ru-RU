---
title: Используйте средство восстановления приложения "Комнаты Microsoft Teams"
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье рассмотрено, как использовать средство восстановления для Комнаты Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый режим.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117497"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="996af-103">Используйте средство восстановления приложения "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="996af-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="996af-104">В этой статье рассмотрено, как использовать средство восстановления для Комнаты Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый режим.</span><span class="sxs-lookup"><span data-stu-id="996af-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="996af-105">Это средство должно применяться, если в консоли Комнаты Microsoft Teams появляется сообщение об ошибке "устарела системная конфигура" или перед выполнением кнопки сбросить заводские [настройки.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="996af-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="996af-106">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="996af-106">Prerequisites</span></span>

<span data-ttu-id="996af-107">Скачайте последнюю [версию Комнаты Microsoft Teams и](https://go.microsoft.com/fwlink/?linkid=851168) извлеките его на USB-накопитель или в сетевую долю, доступную Комнаты Microsoft Teams устройству.</span><span class="sxs-lookup"><span data-stu-id="996af-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="996af-108">Извлечение файлов из MSI-файла может быть выполнено многими способами.</span><span class="sxs-lookup"><span data-stu-id="996af-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="996af-109">Любой механизм, который извлекает все файлы и сохраняет их структуру каталогов, является допустимым.</span><span class="sxs-lookup"><span data-stu-id="996af-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="996af-110">Один из таких способов — использовать команду, которая представляет полный путь к пакету установки Microsoft Teams Room, и полный путь к папке, в которой должны быть извлечены `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` файлы.</span><span class="sxs-lookup"><span data-stu-id="996af-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="996af-111">Запуск средства</span><span class="sxs-lookup"><span data-stu-id="996af-111">Running the tool</span></span>

1) <span data-ttu-id="996af-112">Войте учетную запись администратора на Комнаты Microsoft Teams и запустите командную команду с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="996af-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="996af-113">Убедитесь, Комнаты Microsoft Teams устройства, на котором вы можете получить доступ к файлам, извлеченным из Комнаты Microsoft Teams `RecoveryTool.ps1 file` установки.</span><span class="sxs-lookup"><span data-stu-id="996af-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="996af-114">Комплект можно найти на сетевой или USB-накопителе, используемом при подготовке необходимых условий.</span><span class="sxs-lookup"><span data-stu-id="996af-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="996af-115">Запустите `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .</span><span class="sxs-lookup"><span data-stu-id="996af-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="996af-116">Чтобы выполнить восстановление до заводских цехов, выполните порядок.</span><span class="sxs-lookup"><span data-stu-id="996af-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="996af-117">При запросе сценария выберите вариант 2. **Сброс.**</span><span class="sxs-lookup"><span data-stu-id="996af-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="996af-118">Если BitLocker, выполните инструкции, предоставленные в конце результата сценария, чтобы отключить его.</span><span class="sxs-lookup"><span data-stu-id="996af-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="996af-119">Выполните восстановление до заводских насеок.</span><span class="sxs-lookup"><span data-stu-id="996af-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="996af-120">Откройте приложение **Параметры** и выберите Обновить безопасность **&.**</span><span class="sxs-lookup"><span data-stu-id="996af-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="996af-121">Перейдите на **вкладку** Восстановление.</span><span class="sxs-lookup"><span data-stu-id="996af-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="996af-122">В **области Сброс этого компьютера** выберите Начать **работу**</span><span class="sxs-lookup"><span data-stu-id="996af-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="996af-123">Выберите **Удалить все**, затем **Далее и** **Сброс**</span><span class="sxs-lookup"><span data-stu-id="996af-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="996af-124">Устройство Комнаты Microsoft Teams может стать непригодным для работы, если во время сброса выбран параметр Сохранить мои файлы: удаление приложений и параметров **Windows,** но сохранение личных файлов.</span><span class="sxs-lookup"><span data-stu-id="996af-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="996af-125">Не выбирайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="996af-125">Do not select this option.</span></span>
      5. <span data-ttu-id="996af-126">Система будет перезагружаема несколько раз.</span><span class="sxs-lookup"><span data-stu-id="996af-126">The system will reboot multiple times.</span></span> <span data-ttu-id="996af-127">После завершения сброса система будет на экране Windows "Вне окна" (OOBE).</span><span class="sxs-lookup"><span data-stu-id="996af-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="996af-128">См. также</span><span class="sxs-lookup"><span data-stu-id="996af-128">See also</span></span>

[<span data-ttu-id="996af-129">Справка по приложению "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="996af-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="996af-130">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="996af-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)