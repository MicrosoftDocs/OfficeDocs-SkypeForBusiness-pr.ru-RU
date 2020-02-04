---
title: 'Lync Server 2013: Восстановление стандартного сервера выпуска'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="39b3d-102">Восстановление сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b3d-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b3d-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="39b3d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="39b3d-104">Если сервер Standard Edition, на котором не размещено центральное хранилище управления, не работает, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="39b3d-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="39b3d-105">Если центральное хранилище Management завершается сбоем, ознакомьтесь со сведениями о том, как [восстановить сервер, на котором размещено центральное хранилище, в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="39b3d-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="39b3d-106">Прежде чем начать восстановление, мы рекомендуем использовать копию системы с изображением.</span><span class="sxs-lookup"><span data-stu-id="39b3d-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="39b3d-107">Вы можете использовать это изображение как точку отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="39b3d-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="39b3d-108">После установки операционной системы и сервера SQL Server вы можете использовать копию изображения, а также восстановить или повторно зарегистрировать сертификаты.</span><span class="sxs-lookup"><span data-stu-id="39b3d-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="39b3d-109">Восстановление сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="39b3d-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="39b3d-110">Начните с чистого или нового сервера с таким же полным доменным именем (FQDN), как и у компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или порегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="39b3d-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39b3d-111">Следуйте инструкциям по развертыванию сервера в своей организации, чтобы выполнить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="39b3d-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="39b3d-112">Войдите в свою учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс и локальную группу администраторов, войдя на сервер, который вы хотите восстановить.</span><span class="sxs-lookup"><span data-stu-id="39b3d-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="39b3d-113">Восстановите хранилище файлов, скопировав нужное хранилище файлов из $Backup в хранилище файлов на сервере и предоставьте общий доступ к ней.</span><span class="sxs-lookup"><span data-stu-id="39b3d-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="39b3d-114">Путь и имя файла для восстановленного хранилища файлов должны совпадать с заархивированным хранилищем файлов, чтобы компоненты, использующие эти файлы, могли получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="39b3d-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="39b3d-115">Запустить построитель топологии:</span><span class="sxs-lookup"><span data-stu-id="39b3d-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="39b3d-116">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39b3d-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="39b3d-117">Нажмите кнопку **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="39b3d-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="39b3d-118">Выберите топологию и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="39b3d-118">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="39b3d-119">Нажмите кнопку **Да** , чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="39b3d-119">Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="39b3d-120">Перейдите в папку установки Lync Server или мультимедиа, а затем запустите мастер развертывания Lync Server, расположенный на странице \\Setup\\\\. exe.</span><span class="sxs-lookup"><span data-stu-id="39b3d-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="39b3d-121">С помощью мастера развертывания Lync Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="39b3d-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="39b3d-122">Выполните **Шаг 1: установите локальное хранилище конфигураций** , чтобы установить локальные файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="39b3d-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="39b3d-123">Запустите **Шаг 2: Настройка или удаление компонентов Lync Server** для установки ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39b3d-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="39b3d-124">Запустите **Шаг 3: запросите, установите или назначьте сертификаты** для назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="39b3d-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="39b3d-125">Выполните **Шаг 4: запуск служб** для запуска служб на сервере.</span><span class="sxs-lookup"><span data-stu-id="39b3d-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="39b3d-126">Подробные сведения о запуске мастера развертывания можно найти в документации по развертыванию роли сервера, которую вы восстанавливаете.</span><span class="sxs-lookup"><span data-stu-id="39b3d-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="39b3d-127">Восстановите данные пользователя, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="39b3d-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="39b3d-128">Скопируйте Експортедусердата. zip из $Backup\\ в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="39b3d-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="39b3d-129">Прежде чем восстанавливать данные пользователя, необходимо остановить службы Lync.</span><span class="sxs-lookup"><span data-stu-id="39b3d-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="39b3d-130">Для этого введите:</span><span class="sxs-lookup"><span data-stu-id="39b3d-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="39b3d-131">Чтобы восстановить данные пользователя, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="39b3d-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="39b3d-132">Например:</span><span class="sxs-lookup"><span data-stu-id="39b3d-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="39b3d-133">Перезапустите службы Lync, введя:</span><span class="sxs-lookup"><span data-stu-id="39b3d-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="39b3d-134">Если группа ответа развернута на этом стандартном сервере выпуска, восстановите данные конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="39b3d-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="39b3d-135">Подробности можно найти [в разделе Восстановление параметров группы ответов в Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="39b3d-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="39b3d-136">Если вы развернули сохраняемый чат на этом стандартном сервере Standard Edition, восстановите базу данных сохраняемого чата (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="39b3d-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="39b3d-137">Если вы использовали резервную копию SQL Server для резервного копирования базы данных сохраняемого чата, используйте процедуры восстановления SQL Server для ее восстановления.</span><span class="sxs-lookup"><span data-stu-id="39b3d-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="39b3d-138">Если вы использовали командлет Export-Ксперсистентчатдата для его резервного копирования, восстановите его с помощью Import-Ксперсистентчатдата.</span><span class="sxs-lookup"><span data-stu-id="39b3d-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

