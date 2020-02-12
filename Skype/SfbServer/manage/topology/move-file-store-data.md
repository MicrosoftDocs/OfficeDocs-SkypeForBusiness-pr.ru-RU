---
title: Перемещение данных из хранилища файлов в новое хранилище файлов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: Если вам нужно удалить файловый сервер, который в данный момент выступает в качестве хранилища файлов для развертывания Skype для бизнеса Server, или внести другие изменения, которые приводили к недоступности текущего хранилища файлов, сначала необходимо создать новый общий доступ. Затем потребуется выполнить следующую процедуру.
ms.openlocfilehash: 91ba8393a958188e368ff3f8f5d2a85bcfcc1396
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888458"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="9b6f1-104">Перемещение данных из хранилища файлов в новое хранилище файлов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9b6f1-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="9b6f1-105">Если вам нужно удалить файловый сервер, который в данный момент выступает в качестве хранилища файлов для развертывания Skype для бизнеса Server, или внести другие изменения, которые приводили к недоступности текущего хранилища файлов, сначала необходимо создать новый общий доступ.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="9b6f1-106">Затем потребуется выполнить следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="9b6f1-107">Завершите работу служб Skype для бизнеса Server, использующих хранилище файлов, которое вы собираетесь удалить.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="9b6f1-108">Определите хранилище файлов в построителе топологии и опубликуйте изменения, чтобы сделать новое хранилище файлов доступным для развертывания.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="9b6f1-109">Переместите данные в новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="9b6f1-110">Перезапустите серверы или службы.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="9b6f1-111">При необходимости удалите старую локальную папку с файлами и общую папку.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="9b6f1-112">Перемещение данных из старого хранилища файлов в новое</span><span class="sxs-lookup"><span data-stu-id="9b6f1-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="9b6f1-113">Войдите в систему как член группы Рткуниверсерсалсерверадминс или Кссерверадминистратор, в которой установлены средства администрирования сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="9b6f1-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="9b6f1-115">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="9b6f1-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="9b6f1-116">Для каждого пула режиссеров, режиссера, сервера Standard Edition и пула переднего плана, использующего хранилище файлов, которое вы собираетесь удалить, выберите сервер или группу, нажмите кнопку **действие**, а затем — **остановить все службы**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="9b6f1-117">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="9b6f1-118">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а **затем —** **Построитель топологии Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="9b6f1-119">Выберите сервер или пул, использующий хранилище файлов, и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="9b6f1-120">a)</span><span class="sxs-lookup"><span data-stu-id="9b6f1-120">a.</span></span> <span data-ttu-id="9b6f1-121">Щелкните сервер или пул правой кнопкой мыши и выберите команду **Изменить свойства**. </span><span class="sxs-lookup"><span data-stu-id="9b6f1-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="9b6f1-122">б)</span><span class="sxs-lookup"><span data-stu-id="9b6f1-122">b.</span></span> <span data-ttu-id="9b6f1-123">В окне **Изменить свойства** в разделе **Связи**, **Хранилище файлов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="9b6f1-124">в.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-124">c.</span></span> <span data-ttu-id="9b6f1-125">В разделе **Определение нового хранилища файлов** в поле **Полное доменное имя файлового сервера** введите полное доменное имя файлового сервера.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="9b6f1-126">В поле **Общая папка** введите имя новой общей папки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="9b6f1-127">Этот этап определяет новое хранилище файлов для использования в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="9b6f1-128">You define it only once, not for each server.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-128">You define it only once, not for each server.</span></span> <span data-ttu-id="9b6f1-129">Before you publish the topology, you must create the defined file share on the defined file server.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="9b6f1-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b6f1-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="9b6f1-131">Для каждого сервера или пула, использующего хранилище файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="9b6f1-132">a)</span><span class="sxs-lookup"><span data-stu-id="9b6f1-132">a.</span></span> <span data-ttu-id="9b6f1-133">Щелкните сервер или пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="9b6f1-134">б)</span><span class="sxs-lookup"><span data-stu-id="9b6f1-134">b.</span></span> <span data-ttu-id="9b6f1-135">В окне **Изменить свойства** в разделе **Связи**, **Хранилище файлов** выберите новую общую папку, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="9b6f1-136">Опубликуйте топологию, проверьте состояние репликации, а затем запустите мастер развертывания Skype для бизнеса Server, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="9b6f1-137">Дополнительные сведения см. в разделе [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b6f1-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="9b6f1-138">Запустите командную команду: нажмите кнопку **Пуск**, выберите команду **выполнить**и введите cmd. exe.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="9b6f1-139">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9b6f1-139">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="9b6f1-140">Параметр /S копирует файлы, каталоги и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="9b6f1-141">Параметр /XF пропускает файлы с именем Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="9b6f1-142">Текущие версии файла robocopy.exe с параметром /MT существенно повышают скорость копирования благодаря использованию нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="9b6f1-143">Для параметра/LOG используйте путь к каталогу и имя файла журнала в форме К:\логфилес\лог.ткст.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="9b6f1-144">Этот параметр создает файл журнала операций в именованном расположении.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="9b6f1-145">Завершив копирование данных, на панели управления Lync Server щелкните **топология**и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="9b6f1-146">Для каждого сервера или пула, для которого вы остановили службы, выберите сервер или пул, щелкните **Действие**, а затем **Запустить все службы**.         </span><span class="sxs-lookup"><span data-stu-id="9b6f1-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="9b6f1-p111">Удалите старое хранилище файлов из топологии, а затем опубликуйте топологию. Дополнительные сведения см. в статье [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b6f1-p111">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="9b6f1-149">(Необязательно) Войдите на компьютер, на котором содержится удаленное хранилище файлов, с учетной записью, входящей в группу локальных администраторов или администраторов домена, а затем удалите старую общую папку и каталог.</span><span class="sxs-lookup"><span data-stu-id="9b6f1-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b6f1-150">См. также</span><span class="sxs-lookup"><span data-stu-id="9b6f1-150">See also</span></span>

[<span data-ttu-id="9b6f1-151">Переназначение сервера другому хранилищу файлов</span><span class="sxs-lookup"><span data-stu-id="9b6f1-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="9b6f1-152">Удаление хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="9b6f1-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
