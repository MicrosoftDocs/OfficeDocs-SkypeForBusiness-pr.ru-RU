---
title: Перенос параметров приложения приостановки звонков
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Миграция приложения парковки вызовов включает в себя подготовку пула Skype для бизнеса Server 2019 со всеми пользовательскими музыкальными файлами, которые были отправлены в устаревшей установке, восстановление параметров уровня обслуживания и перераспределение всех орбит для парковки вызовов в пул Skype для бизнеса Server 2019. Если в пуле настроены настроенные файлы для сохранения музыки на удержании, эти файлы необходимо скопировать в новый пул Skype для бизнеса Server 2019. Кроме того, рекомендуется выполнить резервное копирование всех настроенных файлов музыки для сохранения вызовов в другое место назначения, чтобы сохранить отдельную резервную копию всех настроенных файлов музыки для хранения, которые были отправлены для парковки вызовов. Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула. Чтобы скопировать звуковые файлы из хранилища файлов пула в хранилище файлов Skype для бизнеса Server 2019, используйте команду xcopy со следующими параметрами:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752821"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="d4ef0-107">Перенос параметров приложения приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="d4ef0-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="d4ef0-108">Миграция приложения парковки вызовов включает в себя подготовку пула Skype для бизнеса Server 2019 со всеми пользовательскими файлами музыки для хранения, которые были отправлены в устаревшей установке, восстановление параметров уровня службы и повторное указание всех орбит для парковки вызовов в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d4ef0-109">Если в пуле настроены настроенные файлы для сохранения музыки на удержании, эти файлы необходимо скопировать в новый пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d4ef0-110">Кроме того, рекомендуется выполнить резервное копирование всех настроенных файлов музыки для сохранения вызовов в другое место, чтобы сохранить отдельную резервную копию всех настроенных файлов музыки для хранения, которые были отправлены для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="d4ef0-111">Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="d4ef0-112">Чтобы скопировать звуковые файлы из хранилища файлов пула в хранилище файлов Skype для бизнеса Server 2019, используйте команду **xcopy** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="d4ef0-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="d4ef0-113">Когда все настраиваемые аудиофайлы копируются в хранилище файлов Skype для бизнеса Server 2019, необходимо настроить параметры приложения парковки вызовов для пула Skype для бизнеса Server 2019, а Диапазоны орбит парковки вызовов, связанные с пулом прежних версий, должны быть переназначены в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="d4ef0-114">Параметры приложения парковки вызовов включают пороговое значение времени ожидания раскладки, включение или отключение музыки при удержании, максимальное количество попыток ответа на вызовы и запрос времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="d4ef0-115">Для запуска командлета **Set-CsCpsConfiguration** необходимо управлять параметрами приложения парковки вызовов с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="d4ef0-116">Вы не можете управлять параметрами приложения парковки вызовов с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="d4ef0-117">Изменение настроек параметров службы парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="d4ef0-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="d4ef0-118">На сервере переднего плана Skype для бизнеса Server 2019 откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="d4ef0-119">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d4ef0-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4ef0-120">Если параметры приложения парковки вызовов Skype для бизнеса Server 2019 идентичны параметрам прежних версий, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="d4ef0-121">Если параметры приложения парковки вызовов отличаются для сред Skype для бизнеса Server 2019 и прежних версий, используйте приведенный ниже командлет в качестве шаблона для обновления этих изменений.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="d4ef0-122">Чтобы переназначить все диапазоны орбит парковки вызовов из устаревшего пула в пул Skype для бизнеса 2019, вы можете использовать либо панель управления Skype для бизнеса Server, либо консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4ef0-123">Переназначение всех диапазонов орбит парковки вызовов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4ef0-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4ef0-124">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4ef0-125">В области слева выберите **Компоненты голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="d4ef0-126">Перейдите на вкладку **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="d4ef0-127">Для каждого диапазона орбит парковки вызовов, назначенного пулу устаревших элементов, измените **полное доменное имя конечного сервера** и выберите пул Skype для бизнеса Server 2019, который будет обрабатывать запросы на парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="d4ef0-128">Выберите **Зафиксировать**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4ef0-129">Переназначение всех диапазонов орбит парковки вызовов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4ef0-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4ef0-130">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="d4ef0-131">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d4ef0-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="d4ef0-132">Этот командлет выводит список всех диапазонов орбит парковки вызовов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="d4ef0-133">Все орбиты парковки вызовов, для которых заданы параметры **каллпарксервицеид** и **каллпарксерверфкдн** , должны быть переназначены в качестве устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="d4ef0-134">Для перераспределения устаревших диапазонов орбиты парковки вызовов в пул Skype для бизнеса Server 2019 в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d4ef0-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="d4ef0-135">После перераспределения всех диапазонов орбиты парковки вызовов в пул Skype для бизнеса Server 2019 процесс миграции для приложения парковки вызовов будет завершен, а пул Skype для бизнеса Server 2019 будет обрабатывать все будущие запросы на парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="d4ef0-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


