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
description: В этой статье рассмотрено использование средства восстановления для комнат Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый штат.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021727"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="7a94a-103">Используйте средство восстановления приложения "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="7a94a-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="7a94a-104">В этой статье рассмотрено использование средства восстановления для комнат Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый штат.</span><span class="sxs-lookup"><span data-stu-id="7a94a-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="7a94a-105">Это средство следует применять, если в консоли комнат Microsoft Teams появляется сообщение об ошибке "системные настройки устарели" или перед выполнением кнопки "сбросить заводские [настройки".](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="7a94a-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7a94a-106">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="7a94a-106">Prerequisites</span></span>

<span data-ttu-id="7a94a-107">Скачайте последний [пакет установки комнат Microsoft Teams и](https://go.microsoft.com/fwlink/?linkid=851168) извлеките его на USB-накопитель или в обойму, доступную на устройстве Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a94a-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="7a94a-108">Извлечение файлов из MSI-файла может быть выполнено множеством способов.</span><span class="sxs-lookup"><span data-stu-id="7a94a-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="7a94a-109">Любой механизм, который извлекает все файлы и сохраняет их структуру каталогов, приемлем.</span><span class="sxs-lookup"><span data-stu-id="7a94a-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="7a94a-110">Один из таких способов — использовать команду, которая представляет полный путь к пакету установки комнаты Microsoft Teams и полный путь к папке, в которой должны быть извлечены `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` файлы.</span><span class="sxs-lookup"><span data-stu-id="7a94a-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="7a94a-111">Запуск средства</span><span class="sxs-lookup"><span data-stu-id="7a94a-111">Running the tool</span></span>

1) <span data-ttu-id="7a94a-112">Войте учетную запись администратора на устройстве комнат Microsoft Teams и запустите командную подсказку с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="7a94a-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="7a94a-113">Убедитесь, что с устройства комнат Microsoft Teams у вас есть доступ к файлам, извлеченным из пакета установки `RecoveryTool.ps1 file` комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a94a-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="7a94a-114">Комплект можно найти в сетевой сетевой сети или USB-накопителе, используемом при подготовке предварительных условий.</span><span class="sxs-lookup"><span data-stu-id="7a94a-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="7a94a-115">Запустите `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .</span><span class="sxs-lookup"><span data-stu-id="7a94a-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="7a94a-116">Чтобы восстановить заводские функции:</span><span class="sxs-lookup"><span data-stu-id="7a94a-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="7a94a-117">При запросе сценария выберите вариант 2: **Сброс.**</span><span class="sxs-lookup"><span data-stu-id="7a94a-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="7a94a-118">Если bitLocker отключен, следуйте инструкциям в конце сценария.</span><span class="sxs-lookup"><span data-stu-id="7a94a-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="7a94a-119">Выполните восстановление до заводских насов.</span><span class="sxs-lookup"><span data-stu-id="7a94a-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="7a94a-120">Откройте приложение **"Параметры"** и выберите "Обновить & **безопасности"**</span><span class="sxs-lookup"><span data-stu-id="7a94a-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="7a94a-121">Перейдите на **вкладку "Восстановление".**</span><span class="sxs-lookup"><span data-stu-id="7a94a-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="7a94a-122">Под **кнопкой "Восстановить этот компьютер"** выберите **"Начать работу"**</span><span class="sxs-lookup"><span data-stu-id="7a94a-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="7a94a-123">Выберите **"Удалить все",** затем **"Далее"** и **"Сброс"**</span><span class="sxs-lookup"><span data-stu-id="7a94a-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="7a94a-124">Устройство комнат Microsoft Teams может стать непригодным для работы, если команда "Сохранить мои файлы" — удаляет приложения и **параметры,** но сохраняет параметр "Сохранить личные файлы" во время сброса Windows.</span><span class="sxs-lookup"><span data-stu-id="7a94a-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="7a94a-125">Не выбирайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="7a94a-125">Do not select this option.</span></span>
      5. <span data-ttu-id="7a94a-126">Система будет перезагружаема несколько раз.</span><span class="sxs-lookup"><span data-stu-id="7a94a-126">The system will reboot multiple times.</span></span> <span data-ttu-id="7a94a-127">После завершения сброса система будет работать на экране Windows "Выход из окна" (OOBE).</span><span class="sxs-lookup"><span data-stu-id="7a94a-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="7a94a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7a94a-128">See also</span></span>

[<span data-ttu-id="7a94a-129">Справка по приложению "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="7a94a-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="7a94a-130">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="7a94a-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
