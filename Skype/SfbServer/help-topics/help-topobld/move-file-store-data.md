---
title: Перемещение данных хранения файлов в новый файловый магазин в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Если необходимо удалить файловый сервер, который в настоящее время является хранилищем файлов для развертывания Skype для бизнеса Server 2015, или если необходимо внести другие изменения, которые сделают текущий хранилище файлов недоступным, сначала необходимо создать новую долю. Затем необходимо выполнить следующие действия:'
ms.openlocfilehash: 2d65e517b10a76013fbeb332b183b5b816e99083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119648"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="07643-104">Перемещение данных хранения файлов в новый файловый магазин в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="07643-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="07643-105">Если необходимо удалить файловый сервер, который в настоящее время является хранилищем файлов для развертывания Skype для бизнеса Server 2015, или если необходимо внести другие изменения, которые сделают текущий хранилище файлов недоступным, сначала необходимо создать новую долю.</span><span class="sxs-lookup"><span data-stu-id="07643-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="07643-106">Затем необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="07643-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="07643-107">Отключите службы Skype для бизнеса Server 2015, которые используют файловый магазин, который планируется удалить.</span><span class="sxs-lookup"><span data-stu-id="07643-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="07643-108">Определите хранилище файлов в Topology Builder и опубликуйте изменения, чтобы сделать новый хранилище файлов доступным для развертывания.</span><span class="sxs-lookup"><span data-stu-id="07643-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="07643-109">Перемещение данных в новый файловый магазин.</span><span class="sxs-lookup"><span data-stu-id="07643-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="07643-110">Перезапустите серверы или службы.</span><span class="sxs-lookup"><span data-stu-id="07643-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="07643-111">Дополнительно удалите старую папку и папку файла.</span><span class="sxs-lookup"><span data-stu-id="07643-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="07643-112">Перемещение данных хранения файлов из одного файла в новый файловый магазин</span><span class="sxs-lookup"><span data-stu-id="07643-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="07643-113">Войдите на компьютер в качестве члена группы RTCUniversersalServerAdmins или группы CsServerAdministrator, на которой установлены средства администрирования Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07643-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="07643-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="07643-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07643-115">В левой панели навигации нажмите **кнопку Топология** и нажмите кнопку **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="07643-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="07643-116">Для каждого пула director, director, standard Edition server и переднего плана пула, который использует хранилище файлов, который вы планируете удалить, выберите сервер или пул, щелкните **Действие,** а затем нажмите кнопку Остановить все **службы**.</span><span class="sxs-lookup"><span data-stu-id="07643-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="07643-117">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="07643-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="07643-118">Начните строитель топологии: нажмите кнопку **Начните,** нажмите кнопку Все **программы,** щелкните Skype для бизнеса **Server 2015**, а затем нажмите **Skype для бизнеса Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="07643-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="07643-119">Выберите сервер или пул, использующий хранилище файлов, и сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07643-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="07643-120">Щелкните правой кнопкой мыши сервер или пул, а затем **нажмите кнопку Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="07643-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="07643-121">В **редактировании свойств**, в **соответствии с Ассоциациями**, в **файловый магазин,** нажмите **кнопку New**.</span><span class="sxs-lookup"><span data-stu-id="07643-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="07643-122">В **статье Define New File Store** в файловом сервере **FQDN** введите полное доменное имя (FQDN) файлового сервера.</span><span class="sxs-lookup"><span data-stu-id="07643-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="07643-123">В **файле share** введите имя папки для нового файла, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="07643-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="07643-124">Этот шаг определяет новый хранилище файлов для использования в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="07643-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="07643-125">Вы определяете его только один раз, а не для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="07643-125">You define it only once, not for each server.</span></span> <span data-ttu-id="07643-126">Перед публикацией топологии необходимо создать определенный файл на определенном файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="07643-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="07643-127">Подробные сведения [см. в материале Define the File Store for the Front End.](/previous-versions/office/communications/gg133895(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="07643-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="07643-128">Для каждого сервера или пула, использующего хранилище файлов, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07643-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="07643-129">Щелкните правой кнопкой мыши сервер или пул, а затем нажмите **кнопку Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="07643-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="07643-130">В **статье Изменить свойства**, в соответствии с **Ассоциациями**, в **хранилище файлов** выберите новую долю файлов, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="07643-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="07643-131">Опубликуйте топологию, проверьте состояние репликации и запустите мастер развертывания Skype для бизнес-серверов по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="07643-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="07643-132">Подробные сведения [см. в материале Common Procedures for Removing Lync Servers and Components.](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="07643-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="07643-133">Запуск командной подсказки: **нажмите кнопку Начните,** нажмите **кнопку Выполнить,** а затем введите cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="07643-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="07643-134">Введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07643-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="07643-135">Переключатель /S копирует файлы, каталоги и подтеки.</span><span class="sxs-lookup"><span data-stu-id="07643-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="07643-136">Переключатель /XF пропускает файлы с именем Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="07643-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="07643-137">Текущие версии robocopy.exe с коммутатором /MT значительно увеличивают скорость копирования с помощью нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="07643-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="07643-138">Для коммутатора /LOG используйте путь каталога и имя файла журнала в виде C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="07643-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="07643-139">Этот переключатель создает файл журналов операций в названном расположении.</span><span class="sxs-lookup"><span data-stu-id="07643-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="07643-140">Когда копия данных будет завершена, в панели управления Lync Server щелкните **Топология** и нажмите **кнопку Состояние**.</span><span class="sxs-lookup"><span data-stu-id="07643-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="07643-141">Для каждого сервера или пула, где вы остановили службы, выберите сервер или пул, щелкните **Действие,** а затем нажмите **кнопку Начните все службы.**</span><span class="sxs-lookup"><span data-stu-id="07643-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="07643-142">Удалите старый хранилище файлов из топологии и опубликуй топологию.</span><span class="sxs-lookup"><span data-stu-id="07643-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="07643-143">Подробные сведения см. [в материале Remove a file store.](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="07643-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="07643-144">(Необязательный) Войдите на компьютер, содержащий хранилище файлов, который только что был удален в качестве члена локальной группы администраторов или группы администраторов домена, а затем удалите старый файловый файл и каталог.</span><span class="sxs-lookup"><span data-stu-id="07643-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="07643-145">См. также</span><span class="sxs-lookup"><span data-stu-id="07643-145">See also</span></span>

<span data-ttu-id="07643-146">[Перенаменуем сервер в другой файловый магазин](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="07643-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="07643-147">[Удаление магазина файлов](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="07643-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>