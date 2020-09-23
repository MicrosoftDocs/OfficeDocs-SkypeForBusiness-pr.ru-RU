---
title: Перемещение данных из хранилища файлов в новое хранилище файлов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Если необходимо удалить файловый сервер, который в настоящее время действует как хранилище файлов для развертывания Skype для бизнеса Server 2015, или если необходимо внести другие изменения, которые приведут к недоступности текущего хранилища файлов, сначала необходимо создать новый общий ресурс. Затем необходимо выполнить следующие действия:'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215590"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="ad6b7-104">Перемещение данных из хранилища файлов в новое хранилище файлов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ad6b7-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="ad6b7-105">Если необходимо удалить файловый сервер, который в настоящее время действует как хранилище файлов для развертывания Skype для бизнеса Server 2015, или если необходимо внести другие изменения, которые приведут к недоступности текущего хранилища файлов, сначала необходимо создать новый общий ресурс.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="ad6b7-106">Затем необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="ad6b7-107">Завершите работу служб Skype для бизнеса Server 2015, использующих хранилище файлов, которое планируется удалить.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="ad6b7-108">Определите хранилище файлов в построителе топологий и опубликуйте изменения, чтобы новое хранилище файлов стало доступным для развертывания.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="ad6b7-109">Перемещение данных в новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="ad6b7-110">Перезапустите серверы или службы.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="ad6b7-111">При необходимости удалите старый файловый ресурс и папку с файлами.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="ad6b7-112">Перемещение данных из хранилища файлов из одного хранилища файлов в новое</span><span class="sxs-lookup"><span data-stu-id="ad6b7-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="ad6b7-113">Войдите на компьютер в качестве члена группы Рткуниверсерсалсерверадминс или CsServerAdministrator, в которой установлены средства администрирования Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="ad6b7-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ad6b7-115">В левой панели навигации щелкните Topology ( **топология**), а затем щелкните **Status (состояние**).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="ad6b7-116">Для каждого пула директоров, директора, сервера Standard Edition и пула переднего плана, использующего хранилище файлов, которое планируется удалить, выберите сервер или пул, щелкните **действие**, а затем щелкните **остановить все службы**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="ad6b7-117">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="ad6b7-118">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Skype для бизнеса Server 2015**и **Построитель 2015Topology Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="ad6b7-119">Выберите сервер или пул, который использует хранилище файлов, и выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="ad6b7-120">Щелкните сервер или пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="ad6b7-121">В окне **изменение свойств**в разделе **связи**в разделе **хранилище файлов**нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="ad6b7-122">В разделе **Определение нового хранилища файлов**в поле полное доменное имя **файлового сервера**введите полное доменное имя (FQDN) файлового сервера.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="ad6b7-123">В разделе **файловый ресурс**введите имя папки для нового общего файлового ресурса, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="ad6b7-124">Этот шаг определяет новое хранилище файлов для использования в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="ad6b7-125">Она определена только один раз, а не для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-125">You define it only once, not for each server.</span></span> <span data-ttu-id="ad6b7-126">Перед публикацией топологии необходимо создать определенный файловый ресурс на определенном файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="ad6b7-127">Дополнительные сведения см. в разделе [Определение хранилища файлов для внешнего](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="ad6b7-128">Для каждого сервера или пула, использующего хранилище файлов, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="ad6b7-129">Щелкните сервер или пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="ad6b7-130">В диалоговом окне **изменение свойств**в разделе **связи**в **хранилище файлов**выберите новый общий файловый ресурс, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="ad6b7-131">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="ad6b7-132">Подробные сведения о том, как [удалять серверы и компоненты Lync](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx), приведены в разделе Общие процедуры.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="ad6b7-133">Запустите командную строку: нажмите кнопку **Пуск**, выберите пункт **выполнить**и введите cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="ad6b7-134">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="ad6b7-135">Параметр/S копирует файлы, каталоги и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="ad6b7-136">Параметр/КСФ пропускает все файлы с именем Meeting. Active.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="ad6b7-137">Текущие версии robocopy.exe с параметром/MT значительно увеличивают скорость копирования с помощью нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="ad6b7-138">В качестве параметра/LOG укажите путь к каталогу и имя файла журнала в форме C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="ad6b7-139">Этот параметр создает файл журнала операций в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="ad6b7-140">После завершения копирования данных в панели управления Lync Server щелкните **топология**, а затем щелкните **состояние**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="ad6b7-141">Для каждого сервера или пула, в котором вы остановили службы, выберите сервер или пул, щелкните **действие**, а затем нажмите кнопку **запустить все службы**.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="ad6b7-142">Удалите старое хранилище файлов из топологии, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="ad6b7-143">Дополнительные сведения см. [в разделе Удаление хранилища файлов](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="ad6b7-144">Необязательно Выполните вход на компьютер, содержащий хранилище файлов, которое вы только что удалили в качестве члена группы "Локальные администраторы" или "Администраторы домена", а затем удалите старый файловый ресурс и каталог.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad6b7-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ad6b7-145">See also</span></span>

[<span data-ttu-id="ad6b7-146">Переназначение сервера в другое хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="ad6b7-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="ad6b7-147">Удаление хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="ad6b7-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
