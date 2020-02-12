---
title: Перенос параметров приложения приостановки звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Миграция приложения на приостановке звонков включает в себя подготовку пула приложений Skype для бизнеса Server 2019 со всеми пользовательскими музыкальными файлами, загруженными в устаревшей версии, восстанавливая параметры уровня обслуживания и нацеливание всех орбиты на весь занятие Пул 2019 в Skype для бизнеса Server. Если настроенные на хранение файлы хранятся в пуле, эти файлы необходимо скопировать в новый пул 2019 в Skype для бизнеса Server. Кроме того, рекомендуется создать резервную копию всех настроенных файлов для сохранения музыки на удержании в другой точке назначения, чтобы сохранить отдельные резервные копии всех настроенных музыкальных файлов, которые были отправлены для приостановки звонков. Настроенные на хранение музыкальные файлы для приложения для приостановки звонков хранятся в хранилище файлов пула. Чтобы скопировать звуковые файлы из хранилища файлов пула в хранилище файлов Skype для бизнеса Server 2019, используйте команду xcopy со следующими параметрами:'
ms.openlocfilehash: 058f2f1652dcb7c05730fd058e9867a4c2dee8af
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888138"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="2a80d-107">Перенос параметров приложения приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="2a80d-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="2a80d-108">Миграция приложения на приостановке звонков включает в себя подготовку пула приложений Skype для бизнеса Server 2019 со всеми файлами для хранения музыкальных файлов, которые были загружены в устаревшем экземпляре, восстановление параметров уровня службы и перенацеливание всех орбиты для всех звонков в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2a80d-109">Если настроенные на хранение файлы хранятся в пуле, эти файлы необходимо скопировать в новый пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2a80d-110">Кроме того, рекомендуется выполнить резервное копирование всех настроенных файлов для сохранения музыки на хранение на другом месте, чтобы сохранить отдельные резервные копии всех настроенных на хранение музыкальных файлов, которые были загружены для приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="2a80d-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="2a80d-111">Настроенные на хранение музыкальные файлы для приложения для приостановки звонков хранятся в хранилище файлов пула.</span><span class="sxs-lookup"><span data-stu-id="2a80d-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="2a80d-112">Чтобы скопировать звуковые файлы из хранилища файлов пула в хранилище файлов Skype для бизнеса Server 2019, используйте команду **xcopy** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="2a80d-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="2a80d-113">После того как все настроенные звуковые файлы будут скопированы в хранилище файлов Skype для бизнеса Server 2019, должны быть настроены параметры приложения для остановки звонков в пуле для Skype для бизнеса Server 2019, а также диапазоны на орбите, связанные с устаревшим пулом. необходимо переназначить в пул 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="2a80d-114">Параметры приложения для приема звонков включают пороговое значение тайм-аута отправки, включение или отключение музыки на удержании, максимальное количество попыток отправки звонков и запрос времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="2a80d-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="2a80d-115">Чтобы запустить командлет **Set-кскпсконфигуратион** , необходимо управлять параметрами приложения на приостановке звонков с помощью командной консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="2a80d-116">Вы не можете управлять параметрами приложения на приостановке звонков с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="2a80d-117">Изменение параметров службы "Приостановка звонка"</span><span class="sxs-lookup"><span data-stu-id="2a80d-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="2a80d-118">На сервере переднего плана Skype для бизнеса Server 2019 откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="2a80d-119">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2a80d-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a80d-120">Если параметры приложения для приостановки звонков в Skype для бизнеса Server 2019 идентичны параметрам прежних версий, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="2a80d-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="2a80d-121">Если параметры приложения парковки на приостановке в среде для Skype для бизнеса Server 2019 и устаревшие среды отличаются, для обновления этих изменений используйте командлет ниже в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="2a80d-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="2a80d-122">Чтобы переназначить все диапазоны на орбиту из устаревшего пула в пул Skype для Business Server 2019, вы можете использовать либо панель управления Skype для бизнеса, либо серверную консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2a80d-123">Переназначение всех диапазонов на орбиту с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2a80d-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2a80d-124">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="2a80d-125">В левой области выберите пункт **функции голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="2a80d-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="2a80d-126">Откройте вкладку " **приостановить Звонок** ".</span><span class="sxs-lookup"><span data-stu-id="2a80d-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="2a80d-127">Для каждого диапазона на расстоянии по орбите, назначенного устаревшему пулу, измените **полное доменное имя** в параметрах конечного сервера и выберите пул 2019 Skype для бизнеса Server, который будет обрабатывать запросы на остановку звонков.</span><span class="sxs-lookup"><span data-stu-id="2a80d-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="2a80d-128">Нажмите **кнопку Сохранить,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="2a80d-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2a80d-129">Переназначение всех диапазонов на орбиту на приостановку работы с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2a80d-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="2a80d-130">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a80d-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="2a80d-131">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2a80d-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="2a80d-132">Этот командлет выводит список всех диапазонов орбиты на вкладке "приостановить".</span><span class="sxs-lookup"><span data-stu-id="2a80d-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="2a80d-133">Все орбиты, для которых установлены параметры **каллпарксервицеид** и **каллпарксерверфкдн** , заданные как пул старого пула, должны быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="2a80d-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="2a80d-134">Чтобы переназначить диапазон орбиты на приостановку на начало в Skype для бизнеса Server 2019, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2a80d-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="2a80d-135">После того как переназначить все диапазоны на орбиту на странице в Skype для бизнеса Server 2019, процесс миграции для этого приложения будет завершен, а пул Skype для бизнеса Server 2019 будет обрабатывать все будущие запросы на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="2a80d-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


