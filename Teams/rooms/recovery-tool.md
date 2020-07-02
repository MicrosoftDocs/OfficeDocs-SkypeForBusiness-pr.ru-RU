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
description: В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021727"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="cb61d-103">Используйте средство восстановления приложения "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="cb61d-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="cb61d-104">В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="cb61d-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="cb61d-105">Это средство следует применять в том случае, если на консоли Microsoft Teams появляется сообщение об ошибке "системные конфигурации устарело" или перед выполнением принудительного [восстановления фабрики](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span><span class="sxs-lookup"><span data-stu-id="cb61d-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb61d-106">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="cb61d-106">Prerequisites</span></span>

<span data-ttu-id="cb61d-107">Скачайте последний [установочный пакет Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) и извлеките его в сетевую папку, доступную для устройства с поддержкой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cb61d-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="cb61d-108">Извлечение файлов из MSI может осуществляться многими способами.</span><span class="sxs-lookup"><span data-stu-id="cb61d-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="cb61d-109">Любой механизм, извлекающий все файлы и сохраняющий их структуру каталогов, является приемлемым.</span><span class="sxs-lookup"><span data-stu-id="cb61d-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="cb61d-110">Один из таких способов — это использование команды, `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` где `PathToMsi` представлен полный путь к установочному пакету Microsoft Teams, и `PathToTarget` представляет полный путь к папке, в которую вы хотите извлечь файлы.</span><span class="sxs-lookup"><span data-stu-id="cb61d-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="cb61d-111">Запуск средства</span><span class="sxs-lookup"><span data-stu-id="cb61d-111">Running the tool</span></span>

1) <span data-ttu-id="cb61d-112">Войдите в учетную запись администратора на устройстве комнат Microsoft Teams и запустите командную команду с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="cb61d-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="cb61d-113">Убедитесь в том, что на устройстве Microsoft Teams есть доступ к `RecoveryTool.ps1 file` файлам, которые содержатся в файлах, извлеченных из пакета установки комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cb61d-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="cb61d-114">Комплект можно найти в сетевой папке или USB-накопителе, используемом при подготовке необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="cb61d-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="cb61d-115">Выполнить `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .</span><span class="sxs-lookup"><span data-stu-id="cb61d-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="cb61d-116">Для выполнения заводского восстановления выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cb61d-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="cb61d-117">По запросу выберите вариант 2: **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="cb61d-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="cb61d-118">Если BitLocker включен, выполните инструкции, приведенные в конце вывода сценария, чтобы отключить его.</span><span class="sxs-lookup"><span data-stu-id="cb61d-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="cb61d-119">Выполните восстановление фабрики.</span><span class="sxs-lookup"><span data-stu-id="cb61d-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="cb61d-120">Откройте приложение " **Параметры** " и выберите пункт " **Обновить & безопасность** ".</span><span class="sxs-lookup"><span data-stu-id="cb61d-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="cb61d-121">Перейдите на вкладку **Восстановление** .</span><span class="sxs-lookup"><span data-stu-id="cb61d-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="cb61d-122">Под пунктом **Сброс этого компьютера**выберите "начало **работы** "</span><span class="sxs-lookup"><span data-stu-id="cb61d-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="cb61d-123">Выберите **удалить все**, затем **Далее** и **Сброс** .</span><span class="sxs-lookup"><span data-stu-id="cb61d-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="cb61d-124">Устройство Microsoft Teams комнаты может быть недоступно, если параметр **сохранить мои файлы — удаляет приложения и параметры, но** при этом в процессе восстановления Windows выводится состояние личных файлов.</span><span class="sxs-lookup"><span data-stu-id="cb61d-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="cb61d-125">Не выбирайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="cb61d-125">Do not select this option.</span></span>
      5. <span data-ttu-id="cb61d-126">Система будет перезагружена несколько часов.</span><span class="sxs-lookup"><span data-stu-id="cb61d-126">The system will reboot multiple times.</span></span> <span data-ttu-id="cb61d-127">После завершения сброса система будет отображаться на экране приветствия Windows ("нет на работе").</span><span class="sxs-lookup"><span data-stu-id="cb61d-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="cb61d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cb61d-128">See also</span></span>

[<span data-ttu-id="cb61d-129">Справка по приложению "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="cb61d-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="cb61d-130">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="cb61d-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
