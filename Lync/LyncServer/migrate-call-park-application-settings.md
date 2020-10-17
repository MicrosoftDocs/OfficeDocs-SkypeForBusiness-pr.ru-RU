---
title: Перенос параметров приложения приостановки звонков
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503566"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="66607-102">Перенос параметров приложения приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="66607-102">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66607-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="66607-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="66607-104">Миграция приложения парковки вызовов с Lync Server 2010 на Lync Server 2013 включает подготовку пула Lync Server 2013 с любыми файлами специальной музыки для хранения файлов, которые были отправлены в Lync Server 2010, восстановление параметров уровня обслуживания и перераспределение всех орбит для парковки вызовов в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66607-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="66607-105">Если настроенные файлы музыки на удержании настроены в пуле Lync Server 2010, эти файлы необходимо скопировать в новый пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66607-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="66607-106">Кроме того, рекомендуется выполнить резервное копирование всех настроенных файлов музыки для хранения на удержании вызовов из Lync Server 2010 в другое место, чтобы сохранить отдельную резервную копию всех настроенных файлов музыки для хранения, которые были отправлены для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="66607-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="66607-107">Настраиваемые файлы музыки при удержании для приложения парковки вызовов хранятся в файловом хранилище пула.</span><span class="sxs-lookup"><span data-stu-id="66607-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="66607-108">Чтобы скопировать звуковые файлы из хранилища файлов пула Lync Server 2010 в хранилище файлов Lync Server 2013, используйте команду **xcopy** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="66607-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="66607-109">Когда все настраиваемые аудиофайлы копируются в хранилище файлов Lync Server 2013, необходимо настроить параметры приложения парковки вызовов для пула Lync Server 2013, а Диапазоны орбит парковки вызовов, связанные с пулом Lync Server 2010, необходимо переназначить в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66607-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="66607-110">Параметры приложения парковки вызовов включают пороговое значение времени ожидания ответа на вызов, включение или выключение воспроизведения музыки при удержании, максимальное число попыток ответа на вызов и запрос на таймаут.</span><span class="sxs-lookup"><span data-stu-id="66607-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="66607-111">Для запуска командлета **Set – CsCpsConfiguration** необходимо управлять параметрами приложения парковки вызовов с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="66607-112">Вы не можете управлять параметрами приложения парковки вызовов с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="66607-113">**Изменение настроек параметров службы парковки вызовов**</span><span class="sxs-lookup"><span data-stu-id="66607-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="66607-114">На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="66607-115">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="66607-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66607-116">Если параметры приложения парковки вызовов Lync Server 2013 идентичны параметрам устаревшего сервера Lync Server 2010, вы можете пропустить выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="66607-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="66607-117">Если параметры приложения парковки вызовов отличаются в средах Lync Server 2013 и Lync Server 2010, используйте приведенный ниже командлет в качестве шаблона для обновления этих изменений.</span><span class="sxs-lookup"><span data-stu-id="66607-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="66607-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"– Каллпиккуптимеаутсрешолд" <LS2010 CPS TimeSpan> "енаблемусиконхолд" <LS2010 CPS value> "— макскаллпиккупаттемптс" <LS2010 CPS pickup attempts> "OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="66607-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="66607-119">Чтобы переназначить все диапазоны орбит парковки вызовов из пула Lync Server 2010 в пул Lync Server 2013, можно использовать либо панель управления Lync Server, либо командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="66607-120">**Переназначение всех диапазонов орбит парковки вызовов с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="66607-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="66607-121">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="66607-122">В области слева выберите **Компоненты голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="66607-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="66607-123">Перейдите на вкладку **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="66607-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="66607-124">Для каждого диапазона орбит парковки вызовов, назначенного пулу Lync Server 2010, измените **полное доменное имя конечного сервера** и выберите пул Lync Server 2013, который будет обрабатывать запросы на парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="66607-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="66607-125">Выберите **Зафиксировать**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="66607-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="66607-126">**Переназначьте все диапазоны орбит парковки вызовов с помощью оболочки управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="66607-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="66607-127">Откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66607-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="66607-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="66607-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="66607-129">Этот командлет выводит список всех диапазонов орбит парковки вызовов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="66607-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="66607-130">Все орбиты парковки вызовов с параметрами **каллпарксервицеид** и **каллпарксерверфкдн** , установленными в качестве пула Lync Server 2010, должны быть переназначены.</span><span class="sxs-lookup"><span data-stu-id="66607-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="66607-131">Чтобы переназначить диапазоны орбиты парковки вызовов Lync Server 2010 для пула Lync Server 2013, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="66607-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="66607-132">После перераспределения всех диапазонов орбиты парковки вызовов в пул Lync Server 2013 процесс миграции для приложения парковки вызовов будет завершен, а пул Lync Server 2013 будет обрабатывать все будущие запросы на парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="66607-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

