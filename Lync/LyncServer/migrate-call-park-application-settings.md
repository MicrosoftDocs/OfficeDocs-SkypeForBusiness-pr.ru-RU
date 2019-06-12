---
title: Перенос параметров приложения приостановки звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="f4320-102">Перенос параметров приложения приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="f4320-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4320-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f4320-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f4320-104">Миграция приложения на приостановку работы из Lync Server 2010 в Lync Server 2013 включает подготовку пула Lync Server 2013 со всеми пользовательскими музыкальными файлами, загруженными в Lync Server 2010, восстановлением параметров уровня обслуживания и нацеливания на них все орбиты на всех оборотах в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4320-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f4320-105">Если настроенные файлы на удержании с хранением сконфигурированы в пуле Lync Server 2010, эти файлы необходимо скопировать в новый пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4320-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="f4320-106">Кроме того, рекомендуется создать резервную копию всех настроенных файлов для сохранения музыки на месте из Lync Server 2010 в другую папку назначения, чтобы сохранить отдельные резервные копии всех настроенных музыкальных файлов, которые были переданы на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="f4320-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="f4320-107">Настроенные на хранение музыкальные файлы для приложения для приостановки звонков хранятся в хранилище файлов пула.</span><span class="sxs-lookup"><span data-stu-id="f4320-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="f4320-108">Чтобы скопировать звуковые файлы из хранилища файлов пула Lync Server 2010 в хранилище файлов Lync Server 2013, используйте команду **xcopy** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="f4320-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="f4320-109">После того как все настроенные аудиофайлы будут скопированы в хранилище файлов Lync Server 2013, должны быть настроены параметры приложения парковки для пула Lync Server 2013 и диапазоны на орбите, связанные с пулом Lync Server 2010, для которого нужно переназначить пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4320-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="f4320-110">Параметры приложения для приема звонков включают пороговое значение тайм-аута отправки, включение или отключение музыки на удержании, максимальное количество попыток раскладки звонков и запрос времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f4320-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="f4320-111">Чтобы запустить командлет **Set-кскпсконфигуратион** , необходимо управлять параметрами приложения на приостановке звонков с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4320-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="f4320-112">Вы не можете управлять параметрами приложения на приостановке звонков с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4320-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="f4320-113">**Изменение параметров службы "Приостановка звонка"**</span><span class="sxs-lookup"><span data-stu-id="f4320-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="f4320-114">На сервере переднего плана Lync Server 2013 откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f4320-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f4320-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f4320-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4320-116">Если параметры приложения для прикрепления звонков в Lync Server 2013 идентичны параметрам устаревшего сервера Lync Server 2010, вы можете пропустить выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="f4320-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="f4320-117">Если параметры приложения приостановки для Lync Server 2013 и Lync Server 2010 отличаются, для обновления этих изменений используйте командлет ниже в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="f4320-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="f4320-118">Чтобы переназначить все диапазоны орбиты на приостановку, из пула Lync Server 2010 в пул Lync Server 2013, вы можете использовать либо панель управления Lync Server, либо консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4320-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="f4320-119">**Переназначение всех диапазонов на орбиту на приостановку работы с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="f4320-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="f4320-120">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4320-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="f4320-121">В левой области выберите пункт **функции голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="f4320-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="f4320-122">Откройте вкладку " **приостановить Звонок** ".</span><span class="sxs-lookup"><span data-stu-id="f4320-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="f4320-123">Для каждого диапазона на расстоянии по орбите, назначенного для пула Lync Server 2010, измените **полное доменное имя** в параметрах конечного сервера и выберите пул Lync Server 2013, который будет обрабатывать запросы на остановку звонков.</span><span class="sxs-lookup"><span data-stu-id="f4320-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="f4320-124">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="f4320-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="f4320-125">**Переназначение всех диапазонов на орбиту на приостановку работы с помощью командной консоли Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="f4320-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="f4320-126">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4320-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f4320-127">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f4320-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="f4320-128">Этот командлет выводит список всех диапазонов орбиты на вкладке "приостановить".</span><span class="sxs-lookup"><span data-stu-id="f4320-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="f4320-129">Все орбиты, в которых параметры **каллпарксервицеид** и **каллпарксерверфкдн** устанавливаются в качестве пула Lync Server 2010, должны быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="f4320-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="f4320-130">Чтобы переназначить диапазоны орбиты для сервера Lync Server 2010 в пул Lync Server 2013, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f4320-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="f4320-131">После того как переназначить все диапазоны орбиты на приостановку звонков в пул Lync Server 2013, процесс миграции для приложения парковки на приостановке будет завершен, а пул Lync Server 2013 будет обрабатывать все будущие запросы на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="f4320-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

