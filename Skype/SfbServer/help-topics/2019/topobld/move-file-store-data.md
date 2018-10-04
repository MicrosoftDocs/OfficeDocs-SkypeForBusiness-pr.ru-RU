---
title: Перемещение файлового хранилища данных в новое хранилище файлов в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: Если необходимо удалить файлового сервера, который в данный момент действует как хранилище файлов для вашего Скайп для развертывания Business Server или если требуется внести другие изменения, которые сделают текущий файл хранилище недоступен, необходимо сначала создать новую общую папку. Затем потребуется выполнить следующую процедуру.
ms.openlocfilehash: 5051e7ef9c0008fb3b98f7e4b7c67a06a5465d1e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375924"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="811db-104">Перемещение файлового хранилища данных в новое хранилище файлов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="811db-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="811db-105">Если необходимо удалить файлового сервера, который в данный момент действует как хранилище файлов для вашего Скайп для развертывания Business Server или если требуется внести другие изменения, которые сделают текущий файл хранилище недоступен, необходимо сначала создать новую общую папку.</span><span class="sxs-lookup"><span data-stu-id="811db-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="811db-106">Затем потребуется выполнить следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="811db-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="811db-107">Завершение работы Скайп для служб Business Server, использующих хранилище файлов, которое планируется удалить.</span><span class="sxs-lookup"><span data-stu-id="811db-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="811db-108">Определите хранилище файлов в построителе топологий и публикация изменений становится доступной для развертывания нового файла хранения.</span><span class="sxs-lookup"><span data-stu-id="811db-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="811db-109">Переместите данные в новое хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="811db-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="811db-110">Перезапустите серверы или службы.</span><span class="sxs-lookup"><span data-stu-id="811db-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="811db-111">При необходимости удалите старую локальную папку с файлами и общую папку.</span><span class="sxs-lookup"><span data-stu-id="811db-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="811db-112">Перемещение данных из старого хранилища файлов в новое</span><span class="sxs-lookup"><span data-stu-id="811db-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="811db-113">Войдите на компьютер как член группы RTCUniversersalServerAdmins или CsServerAdministrator установленными Скайп для Business Server, средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="811db-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="811db-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="811db-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="811db-115">В левой панели навигации щелкните **Топология**, а затем **Состояние**. </span><span class="sxs-lookup"><span data-stu-id="811db-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="811db-116">Для каждого пула директоров, директора, сервера Standard Edition и пула переднего плана, который использует хранилище файлов, который планируется удалить выберите сервера или пула, щелкните **Действие**и нажмите кнопку **Остановить все службы**.</span><span class="sxs-lookup"><span data-stu-id="811db-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="811db-117">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="811db-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="811db-118">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для Business Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="811db-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="811db-119">Выберите сервер или пул, использующий хранилище файлов, и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="811db-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="811db-120">Щелкните сервер или пул правой кнопкой мыши и выберите команду **Изменить свойства**. </span><span class="sxs-lookup"><span data-stu-id="811db-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="811db-121">В окне **Изменить свойства** в разделе **Связи**, **Хранилище файлов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="811db-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="811db-p103">В разделе **Определение нового хранилища файлов** в поле **Полное доменное имя файлового сервера** введите полное доменное имя файлового сервера. В поле **Общая папка** введите имя новой общей папки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="811db-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="811db-124">Это действие задает новое хранилище файлов для использования в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="811db-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="811db-125">Можно определить его только один раз, не для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="811db-125">You define it only once, not for each server.</span></span> <span data-ttu-id="811db-126">Перед публикацией топологии необходимо создать определенный файловый ресурс на сервере определенный файл.</span><span class="sxs-lookup"><span data-stu-id="811db-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="811db-127">Дополнительные сведения см [определить хранилище файлов для сервера переднего плана](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="811db-127">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

11. <span data-ttu-id="811db-128">Для каждого сервера или пула, использующего хранилище файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="811db-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="811db-129">Щелкните сервер или пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="811db-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="811db-130">В окне **Изменить свойства** в разделе **Связи**, **Хранилище файлов** выберите новую общую папку, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="811db-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="811db-131">Опубликуйте топологию, проверьте состояние репликации и запустите Скайп для мастера развертывания сервера Business при необходимости.</span><span class="sxs-lookup"><span data-stu-id="811db-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="811db-132">Для получения дополнительных сведений просмотрите [Распространенные процедур для удаления Lync серверов и компонентов](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="811db-132">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

15. <span data-ttu-id="811db-133">Откройте окно командной строки: нажмите кнопку **Пуск**, выберите команду **выполнить**и введите cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="811db-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="811db-134">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="811db-134">At the command line, type the following:</span></span>

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="811db-135">Параметр /S копирует файлы, каталоги и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="811db-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="811db-136">Параметр /XF пропускает файлы с именем Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="811db-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="811db-137">Текущие версии файла robocopy.exe с параметром /MT существенно повышают скорость копирования благодаря использованию нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="811db-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="811db-138">Для параметра/log используйте имя каталога журнала и путь файла в виде C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="811db-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="811db-139">Этот параметр создает файл журнала операций в именованном расположении.</span><span class="sxs-lookup"><span data-stu-id="811db-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="811db-140">По завершении копирования данных, в панели управления Lync Server, щелкните **Топология**и нажмите кнопку **состояние**.</span><span class="sxs-lookup"><span data-stu-id="811db-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="811db-141">Для каждого сервера или пула, для которого вы остановили службы, выберите сервер или пул, щелкните **Действие**, а затем **Запустить все службы**.</span><span class="sxs-lookup"><span data-stu-id="811db-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="811db-142">Удалите старое хранилище файлов из топологии, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="811db-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="811db-143">Дополнительные сведения см [удаления хранилища файлов](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="811db-143">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

20. <span data-ttu-id="811db-144">(Необязательно) Войдите на компьютер, на котором содержится удаленное хранилище файлов, с учетной записью, входящей в группу локальных администраторов или администраторов домена, а затем удалите старую общую папку и каталог.</span><span class="sxs-lookup"><span data-stu-id="811db-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="811db-145">См. также</span><span class="sxs-lookup"><span data-stu-id="811db-145">See also</span></span>

[<span data-ttu-id="811db-146">Переназначение сервера для различных хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="811db-146">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="811db-147">Удаление хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="811db-147">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)