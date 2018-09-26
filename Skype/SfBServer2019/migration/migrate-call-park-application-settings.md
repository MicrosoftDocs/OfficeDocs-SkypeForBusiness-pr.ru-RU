---
title: Перенос параметров приложения парковки вызовов
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Миграция парковки вызовов, приложения включает в себя подготовки Скайп для пула Business Server 2019 с помощью любого настраиваемого музыки на удержание файлы, загруженные в разделе install прежних версий, восстановление параметров уровня службы и переназначение всех парковки вызовов вокруг для Скайп для пула Business Server 2019. Если в пуле настроены настроенные файлы музыки при удержании, эти файлы необходимо скопировать для нового Скайп для пула Business Server 2019. Кроме того рекомендуется, что создать резервную копию любой парковки вызовов настроить музыку при удержании файлов с другой компьютер для хранения отдельной резервной копии всех настроенных музыки при удержании файлов, которые были отправлены для парковки вызовов. Настроенные файлы музыки при удержании для приложения приостановки звонков хранятся в хранилище файлов пула. Чтобы скопировать звуковых файлов из хранилища файлов пула Скайп для хранилища файлов Business Server 2019, используйте команды Xcopy со следующими параметрами:'
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028826"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="337d5-107">Перенос параметров приложения парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="337d5-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="337d5-108">Миграция приложения приостановки звонков включает в себя Подготовка Скайп для пула Business Server 2019 с помощью любого пользовательских файлов музыки при удержании, загруженные в прежних версий установка, восстановление параметры уровня обслуживания и требуемой версии всех орбиты парковки вызовов Чтобы Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="337d5-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="337d5-109">Если в пуле настроены настроенные файлы музыки при удержании, эти файлы необходимо скопировать для нового Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="337d5-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="337d5-110">Кроме того рекомендуется резервное копирование любого парковки вызовов настраиваемого в файлы музыки при удержании другому получателю хранения отдельной резервной копии всех настроенных музыки при удержании файлов, которые были отправлены для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="337d5-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="337d5-111">Настроенные файлы музыки при удержании для приложения приостановки звонков хранятся в хранилище файлов пула.</span><span class="sxs-lookup"><span data-stu-id="337d5-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="337d5-112">Чтобы скопировать звуковых файлов из хранилища файлов пула Скайп для хранилища файлов Business Server 2019, используйте команды **Xcopy** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="337d5-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="337d5-113">При копировании всех настраиваемых звуковых файлов Скайп для хранилища файлов Business Server 2019 параметров приложения парковки вызовов из Скайп Business Server 2019 пула должна быть настроена и парковка вызовов Орбита диапазоны, которые связаны с пулом прежних версий должен быть назначен Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="337d5-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>
  
<span data-ttu-id="337d5-114">Параметры приложения парковки вызовов включают порог раскладки времени ожидания, включение и отключение музыку при удержании, попыток раскладки максимально допустимое число вызовов и время ожидания запроса.</span><span class="sxs-lookup"><span data-stu-id="337d5-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="337d5-115">Необходимо управлять параметров приложения парковки вызовов с помощью Скайп для консоли Business Server для запуска командлета **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="337d5-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="337d5-116">Не удается управлять параметров приложения парковки вызовов, с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="337d5-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 
  
## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="337d5-117">Заново настройте параметры службы парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="337d5-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="337d5-118">Скайп для сервера переднего плана Business Server 2019 откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="337d5-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="337d5-119">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="337d5-119">At the command line, type the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="337d5-120">Если ваше Скайп для параметров приложения парковки вызовов Business Server 2019 идентичны параметры из прежних версий, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="337d5-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="337d5-121">Параметры приложения парковки вызовов зависят от Скайп Business Server 2019 и сред, используйте командлет ниже как шаблон для обновления этих изменений.</span><span class="sxs-lookup"><span data-stu-id="337d5-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

<span data-ttu-id="337d5-122">Чтобы переназначить все диапазоны орбит парковки вызовов из устаревшего пула для Скайп для пула Business Server 2019, можно использовать Скайп для панели управления Business Server или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="337d5-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="337d5-123">Переназначение всех диапазонов Орбит парковки вызовов, с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="337d5-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="337d5-124">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="337d5-124">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="337d5-125">В левой области выберите **Компоненты голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="337d5-125">In the left pane, select **Voice Features**.</span></span>
    
3. <span data-ttu-id="337d5-126">Перейдите на вкладку **Парковка вызовов** .</span><span class="sxs-lookup"><span data-stu-id="337d5-126">Select the **Call Park** tab.</span></span> 
    
4. <span data-ttu-id="337d5-127">Для каждого диапазона орбиты парковки вызовов, назначенной пулу прежних версий изменение параметров **полное доменное имя конечного сервера** и выберите Скайп для пула Business Server 2019, который будет обрабатывать запросов на парковку вызовов.</span><span class="sxs-lookup"><span data-stu-id="337d5-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 
    
5. <span data-ttu-id="337d5-128">Выберите **Сохранить** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="337d5-128">Select **Commit** to save the changes.</span></span> 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="337d5-129">Переназначение всех диапазонов Орбит парковки вызовов, с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="337d5-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="337d5-130">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="337d5-130">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="337d5-131">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="337d5-131">At the command line, type the following:</span></span>
    
  ```
  Get-CsCallParkOrbit
  ```

    <span data-ttu-id="337d5-132">Этот командлет выводит все диапазоны орбит парковки вызовов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="337d5-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="337d5-133">Все орбиты парковки вызовов **CallParkServiceId** и **CallParkServerFqdn** параметры задаются в виде устаревшего пула, должно быть передано.</span><span class="sxs-lookup"><span data-stu-id="337d5-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 
    
    <span data-ttu-id="337d5-134">Чтобы переназначить прежних версий орбиты парковки вызовов диапазонов для Скайп для Business Server 2019 пула, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="337d5-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

<span data-ttu-id="337d5-135">После переназначение всех диапазонов орбит парковки вызовов для Скайп для пула Business Server 2019, процесс миграции для приложения парковки вызовов будет завершена, и Скайп для пула Business Server 2019 будет обрабатывать все последующие запросы парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="337d5-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>
  

