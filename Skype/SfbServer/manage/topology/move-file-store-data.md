---
title: Move File Store Data to a New File Store in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Если вам нужно удалить файловый сервер, который в настоящее время действует как хранилище файлов для развертывания Skype для бизнеса Server, или если необходимо внести другие изменения, которые делают текущее хранилище файлов недоступным, сначала необходимо создать новую обную папку. Затем необходимо выполнить следующие действия:'
ms.openlocfilehash: 1ea1f6f038a5d589f9a2c3f480a5c9e589c324f3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816369"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="f6712-104">Move File Store Data to a New File Store in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6712-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="f6712-105">Если вам нужно удалить файловый сервер, который в настоящее время действует как хранилище файлов для развертывания Skype для бизнеса Server, или если необходимо внести другие изменения, которые делают текущее хранилище файлов недоступным, сначала необходимо создать новую обную папку.</span><span class="sxs-lookup"><span data-stu-id="f6712-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="f6712-106">Затем необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6712-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="f6712-107">Завершение работы служб Skype для бизнеса Server, которые используют хранилище файлов, которое планируется удалить.</span><span class="sxs-lookup"><span data-stu-id="f6712-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="f6712-108">Определите хранилище файлов в средстве построитель топологий и опубликуйте изменения, чтобы сделать новое хранилище файлов доступным для развертывания.</span><span class="sxs-lookup"><span data-stu-id="f6712-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="f6712-109">Переместит данные в новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="f6712-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="f6712-110">Перезапустите серверы или службы.</span><span class="sxs-lookup"><span data-stu-id="f6712-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="f6712-111">При желании удалите старую обную папку и папку файлов.</span><span class="sxs-lookup"><span data-stu-id="f6712-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="f6712-112">Перемещение данных из одного файловой папки в новое хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="f6712-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="f6712-113">Войдите на компьютер в качестве члена группы RTCUniversersalServerAdmins или CsServerAdministrator, на котором установлен Skype для бизнеса Server, administrative Tools.</span><span class="sxs-lookup"><span data-stu-id="f6712-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="f6712-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f6712-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f6712-115">В левой панели навигации щелкните **"Топология"** и выберите **"Состояние".**</span><span class="sxs-lookup"><span data-stu-id="f6712-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="f6712-116">Для каждого пула директоров, директора, сервера Standard Edition и пула переднего плана, который использует хранилище файлов, которое планируется удалить, выберите сервер или пул, нажмите кнопку **"Действие"** и выберите "Остановить **все** службы".</span><span class="sxs-lookup"><span data-stu-id="f6712-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="f6712-117">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6712-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="f6712-118">Start Topology Builder: Click **Start,** click **All Programs,** click **Skype for Business Server**, and then click Skype for Business Server **Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="f6712-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="f6712-119">Выберите сервер или пул, использующий хранилище файлов, и сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f6712-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="f6712-120">а.</span><span class="sxs-lookup"><span data-stu-id="f6712-120">a.</span></span> <span data-ttu-id="f6712-121">Щелкните правой кнопкой мыши сервер или пул и выберите **"Изменить свойства".**</span><span class="sxs-lookup"><span data-stu-id="f6712-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="f6712-122">б.</span><span class="sxs-lookup"><span data-stu-id="f6712-122">b.</span></span> <span data-ttu-id="f6712-123">In **Edit properties**, under **Associations**, under **File store,** click **New**.</span><span class="sxs-lookup"><span data-stu-id="f6712-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="f6712-124">c.</span><span class="sxs-lookup"><span data-stu-id="f6712-124">c.</span></span> <span data-ttu-id="f6712-125">В области "Определение нового файлового **магазина"** введите полное доменное имя файлового сервера.</span><span class="sxs-lookup"><span data-stu-id="f6712-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="f6712-126">В **области "Файл"** введите имя новой папки и нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="f6712-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="f6712-127">На этом этапе определяется новое хранилище файлов для использования в построителье топологий.</span><span class="sxs-lookup"><span data-stu-id="f6712-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="f6712-128">Вы определяете его только один раз, а не для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="f6712-128">You define it only once, not for each server.</span></span> <span data-ttu-id="f6712-129">Прежде чем опубликовать топологию, необходимо создать определенный файловой папки на определенном файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="f6712-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="f6712-130">Подробные сведения см. [в подкатеке "Определение файловой папки для переднего входа".](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6712-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="f6712-131">Для каждого сервера или пула, который использует хранилище файлов, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f6712-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="f6712-132">а.</span><span class="sxs-lookup"><span data-stu-id="f6712-132">a.</span></span> <span data-ttu-id="f6712-133">Щелкните правой кнопкой мыши сервер или пул и выберите **"Изменить свойства".**</span><span class="sxs-lookup"><span data-stu-id="f6712-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="f6712-134">б.</span><span class="sxs-lookup"><span data-stu-id="f6712-134">b.</span></span> <span data-ttu-id="f6712-135">В **области "Изменение свойств"** в **"Связи"** в хранилище **файлов** выберите новый файловый файл и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="f6712-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="f6712-136">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f6712-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="f6712-137">Подробные сведения см. в общих процедурах удаления [серверов и компонентов Lync.](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6712-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="f6712-138">Запустите командную команду:  **"Начните",**"Выполнить" и введите cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="f6712-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="f6712-139">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6712-139">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="f6712-140">Переключатель /S копирует файлы, каталоги и подкадиректоры.</span><span class="sxs-lookup"><span data-stu-id="f6712-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="f6712-141">Переключатель /XF пропускает все файлы с именем Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="f6712-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="f6712-142">Текущие версии robocopy.exe с коммутатором /MT значительно увеличивают скорость копирования с помощью нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="f6712-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="f6712-143">Для переключателя /LOG используйте путь к каталогу и имя файла журнала в форме C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="f6712-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="f6712-144">Этот переключатель создает файл журнала операций в именоваемом расположении.</span><span class="sxs-lookup"><span data-stu-id="f6712-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="f6712-145">После завершения копирования данных в панели управления Lync Server щелкните "Топология" **и** выберите **"Состояние".**</span><span class="sxs-lookup"><span data-stu-id="f6712-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="f6712-146">Для каждого сервера или пула, на котором остановлены службы, выберите сервер или пул, нажмите кнопку **"Действие"** и выберите **"Запустить все службы".**</span><span class="sxs-lookup"><span data-stu-id="f6712-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="f6712-147">Удалите старое хранилище файлов из топологии и опубликуем топологию.</span><span class="sxs-lookup"><span data-stu-id="f6712-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="f6712-148">Подробные сведения см. [в подстраивке "Удаление файловой папки".](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6712-148">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="f6712-149">(Необязательно) Войдите на компьютер, содержащий хранилище файлов, которое вы только что удалили в качестве члена локальной группы администраторов или группы администраторов домена, а затем удалите старую папку и каталог.</span><span class="sxs-lookup"><span data-stu-id="f6712-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6712-150">См. также</span><span class="sxs-lookup"><span data-stu-id="f6712-150">See also</span></span>

[<span data-ttu-id="f6712-151">Перенамерование сервера в другое хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="f6712-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="f6712-152">Удаление файловой папки</span><span class="sxs-lookup"><span data-stu-id="f6712-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
