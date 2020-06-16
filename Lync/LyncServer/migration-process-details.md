---
title: Процесс миграции — сведения
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="a7248-102">Процесс миграции — сведения</span><span class="sxs-lookup"><span data-stu-id="a7248-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7248-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a7248-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a7248-104">Используйте следующие предварительные требования и подробное описание действий по переносу Lync Server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat в Lync Server 2013, сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="a7248-105">Необходимые компоненты для миграции</span><span class="sxs-lookup"><span data-stu-id="a7248-105">Prerequisites for Migration</span></span>

<span data-ttu-id="a7248-106">Перед переносом Lync Server 2010, группового чата или Office Communications Server 2007 R2 в Lync Server 2013 и сервер сохраняемого чата убедитесь, что выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="a7248-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="a7248-107">Разверните по крайней мере один пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7248-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="a7248-108">Если у вас несколько пулов Lync Server 2013, решите, какой пул Lync Server 2013 будет домашним пулом для нового пула серверов сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7248-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="a7248-109">Установите сервер пула сервера сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7248-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="a7248-110">Он будет пустым (без категорий, комнат или надстроек).</span><span class="sxs-lookup"><span data-stu-id="a7248-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="a7248-111">Прежде чем переносить старые категории, комнаты или надстройки, вы можете создавать комнаты, категории или надстройки в среде Lync Server 2013, сохраняемом сервере сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7248-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span><span class="sxs-lookup"><span data-stu-id="a7248-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="a7248-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span><span class="sxs-lookup"><span data-stu-id="a7248-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="a7248-114">Подготовка исходных данных к миграции</span><span class="sxs-lookup"><span data-stu-id="a7248-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="a7248-115">Выполните следующие действия, чтобы должным образом подготовить исходные данные для миграции.</span><span class="sxs-lookup"><span data-stu-id="a7248-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="a7248-116">Создайте резервную копию исходных баз данных для Lync Server 2010, группового чата или Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="a7248-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="a7248-117">Подробные сведения о резервном копировании SQL Server можно найти в разделе "Обзор резервного копирования (SQL Server)" <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="a7248-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7248-118">Доменные службы Active Directory должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="a7248-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="a7248-119">В качестве условия миграции невозможно выполнить миграцию в пул в другом развертывании (в частности, в другом лесу Active Directory).</span><span class="sxs-lookup"><span data-stu-id="a7248-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="a7248-120">Изучите комнаты чата и Настройка категорий в Lync Server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="a7248-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="a7248-121">Все изменения в категориях, комнатах или надстройках в существующем развертывании прежних версий будут выполняться средством администрирования группового чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a7248-122">Любые изменения, внесенные в категории, комнаты или надстройки в Lync Server 2013, развертывание сервера сохраняемого чата выполняются с помощью панели управления Lync Server или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7248-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="a7248-123">Выполните следующие действия, чтобы подготовить старую систему к миграции.</span><span class="sxs-lookup"><span data-stu-id="a7248-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="a7248-124">Сервер сохраняемого чата поддерживает один уровень категорий в отличие от детального иерархического набора категорий.</span><span class="sxs-lookup"><span data-stu-id="a7248-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="a7248-125">После миграции к подкатегориям добавляются префиксы с полными именами родительских категорий.</span><span class="sxs-lookup"><span data-stu-id="a7248-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="a7248-126">Возможно, вы захотите упростить существующую структуру категорий, чтобы полученная структура удовлетворяла вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="a7248-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="a7248-127">Verify the **Managers** at the root Category.</span><span class="sxs-lookup"><span data-stu-id="a7248-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="a7248-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span><span class="sxs-lookup"><span data-stu-id="a7248-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="a7248-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span><span class="sxs-lookup"><span data-stu-id="a7248-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="a7248-130">Verify the length of room names.</span><span class="sxs-lookup"><span data-stu-id="a7248-130">Verify the length of room names.</span></span> <span data-ttu-id="a7248-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span><span class="sxs-lookup"><span data-stu-id="a7248-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="a7248-132">The naming limit is 256 characters, including parent category names.</span><span class="sxs-lookup"><span data-stu-id="a7248-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="a7248-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span><span class="sxs-lookup"><span data-stu-id="a7248-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="a7248-134">В Lync Server 2013, если для параметров **приглашения** категории задано значение true, вы можете выбрать true или false для приглашений на комнаты в этой категории.</span><span class="sxs-lookup"><span data-stu-id="a7248-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="a7248-135">Однако, если для настроек приглашений категории задано значение «False», приглашения для комнат в этой категории отключены.</span><span class="sxs-lookup"><span data-stu-id="a7248-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="a7248-136">Перед переносом необходимо сбросить параметры приглашений в устаревшей версии сервера группы Lync Server Group Chat, если вы хотите, чтобы комнаты существовали в определенной категории.</span><span class="sxs-lookup"><span data-stu-id="a7248-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="a7248-137">В противном случае в ходе миграции Lync Server 2013 отображает предупреждения и задает для комнат значение по умолчанию false.</span><span class="sxs-lookup"><span data-stu-id="a7248-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="a7248-138">Если вы использовали файлы в комнатах чата, то после миграции необходимо вручную выполнить XCOPY для файлов в новом хранилище файлов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="a7248-139">Инструменты этого не делают.</span><span class="sxs-lookup"><span data-stu-id="a7248-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="a7248-140">Если у вас есть Федеративные пользователи и комнаты с федеративными пользователями, имейте в виду, что сервер сохраняемого чата не поддерживает федерацию.</span><span class="sxs-lookup"><span data-stu-id="a7248-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="a7248-141">Комнаты с федеративными пользователями будут перенесены, но сами пользователи не смогут получить доступ к содержимому, так как федеративный доступ не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a7248-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="a7248-142">Определите комнаты, которые не требуется переносить, и отметьте их как отключенные.</span><span class="sxs-lookup"><span data-stu-id="a7248-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="a7248-143">Identify the date beyond which you want to migrate the chat room content.</span><span class="sxs-lookup"><span data-stu-id="a7248-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="a7248-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span><span class="sxs-lookup"><span data-stu-id="a7248-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="a7248-145">Выполнение миграции</span><span class="sxs-lookup"><span data-stu-id="a7248-145">Performing the Migration</span></span>

<span data-ttu-id="a7248-146">Выполните указанные ниже действия, чтобы перенести сервер группового чата прежних версий.</span><span class="sxs-lookup"><span data-stu-id="a7248-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="a7248-147">Завершите работу Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat или Lync Server 2013, службы сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="a7248-148">Необходимо остановить все службы, поэтому запланируйте для этого время с достаточным периодом простоя.</span><span class="sxs-lookup"><span data-stu-id="a7248-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="a7248-149">Как описывалось ранее, обязательно создайте резервную копию текущей базы данных для группового чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="a7248-150">Выполните командлет **Export-CsPersistentChatData** для Windows PowerShell в качестве члена роли администратора сохраняемого чата (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="a7248-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="a7248-151">Дополнительные сведения о командлетах экспорта и импорта приведены [в разделе Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="a7248-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="a7248-152">Изучите экспортированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="a7248-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="a7248-153">Прежде чем приступать к импорту, завершите работу сервера Lync Server 2013, службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="a7248-154">Необходимо остановить все службы, поэтому запланируйте для этого время с достаточным периодом простоя.</span><span class="sxs-lookup"><span data-stu-id="a7248-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="a7248-155">Выполните резервное копирование базы данных сохраняемого чата, если вы создали категории, комнаты или надстройки в развертывании Lync Server 2013 до миграции.</span><span class="sxs-lookup"><span data-stu-id="a7248-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="a7248-156">Процесс экспорта/импорта будет иметь возможность объединить устаревшие данные с развертыванием Lync Server 2013, но необходимо выполнить резервное копирование базы данных, если контент случайно перезаписывается (например, если существуют конфликты имен).</span><span class="sxs-lookup"><span data-stu-id="a7248-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="a7248-157">Запустите командлет Windows PowerShell **Import-CsPersistentChatData** (средство импорта) с помощью команды **WhatIf** для заполнения фонового сервера пула сервера сохраняемого чата перенесенными данными.</span><span class="sxs-lookup"><span data-stu-id="a7248-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="a7248-158">В процессе выполняются некоторые преобразования для применения упрощенной модели администрирования.</span><span class="sxs-lookup"><span data-stu-id="a7248-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="a7248-159">При наличии ошибок или предупреждений устраните их.</span><span class="sxs-lookup"><span data-stu-id="a7248-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="a7248-160">Запустите командлет **Import-CsPersistentChatData** Windows PowerShell для сервера сохраняемого чата в качестве члена роли администратора сохраняемого чата (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="a7248-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="a7248-161">Дополнительные сведения о командлетах экспорта и импорта приведены [в разделе Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="a7248-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="a7248-162">Необходимо выполнить XCOPY для всех загруженных файлов (всю папку) в новое хранилище файлов сохраняемого чата Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7248-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7248-163">Lync 2013 (клиент) не поддерживает отправку и просмотр файлов в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="a7248-164">Вы все так же можете использовать старый клиент для публикации и просмотра файлов в комнате.</span><span class="sxs-lookup"><span data-stu-id="a7248-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="a7248-165">Попросите URI сервера Lync Server 2010, группового чата или Office Communications Server 2007 R2 на серверный объект Contact в Lync Server 2013, сохраняемый чат Server.</span><span class="sxs-lookup"><span data-stu-id="a7248-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="a7248-166">Следующие действия необходимы, если пользователям Lync 2010 Group Chat или Office Communicator 2007 R2 требуется подключиться к последнему Lync 2013, сохраняемый чат (клиент) после миграции без каких-либо изменений конфигурации на стороне клиента:</span><span class="sxs-lookup"><span data-stu-id="a7248-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="a7248-167">Удалите \<domainName\> учетную запись пользователя сервера поиска OCSChat@. com.</span><span class="sxs-lookup"><span data-stu-id="a7248-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="a7248-168">Он использовался для ссылки на службу подстановки в Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="a7248-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="a7248-169">Удалить пул и доверенные записи можно позже.</span><span class="sxs-lookup"><span data-stu-id="a7248-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="a7248-170">Создайте конечную точку устаревшего (контактный объект сервера сохраняемого чата), выполнив командлет Windows PowerShell **New-CsPersistentChatEndpoint**с идентичным URI SIP, чтобы устаревший клиент работал эффективно при перезапуске службы.</span><span class="sxs-lookup"><span data-stu-id="a7248-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="a7248-171">Обязательный процесс миграции в этот момент завершается.</span><span class="sxs-lookup"><span data-stu-id="a7248-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="a7248-172">Lync 2010 Group Chat (клиенты) или Office Communicator 2007 R2 Group Chat (клиенты) могут подключаться к новому пулу серверов сохраняемого чата, а затем прозрачно.</span><span class="sxs-lookup"><span data-stu-id="a7248-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="a7248-173">Выполните следующие дополнительные действия по списанию для Lync Server 2010, группового чата или Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="a7248-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="a7248-174">Запустите службы сервера сохраняемого чата, включив все компьютеры в новом пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="a7248-175">Используйте панель управления Lync Server и командлеты Windows PowerShell, чтобы убедиться, что данные успешно перенесены.</span><span class="sxs-lookup"><span data-stu-id="a7248-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="a7248-176">Удалите Lync 2010 Group Chat или Office Communicator 2007 R2 Group Chat с компьютеров в пуле серверов группового чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="a7248-177">Удалите доверенное приложение и пул доверенных приложений с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7248-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a7248-178">Это приведет к удалению этих элементов из центрального хранилища управления и связанных записей доверенной службы (Тсес) из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7248-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="a7248-179">Кроме того, этот шаг работает с помощью построителя топологий (Кроме того, у доверенных приложений и пулов есть выделенный узел).</span><span class="sxs-lookup"><span data-stu-id="a7248-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="a7248-180">Теперь вы можете включить функции сервера сохраняемого чата с помощью новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="a7248-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="a7248-181">Дополнительные сведения о том, как включать сервер сохраняемого чата, приведены [в статье Развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7248-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a7248-182">Lync Server 2013 поддерживает несколько пулов серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="a7248-183">Однако мы поддерживаем перенос группового чата в Lync 2010 или Office Communications Server 2007 R2 &nbsp; в один пул серверов Lync server 2013, сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="a7248-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="a7248-184">В развертывание можно добавить новые пулы серверов сохраняемого чата в соответствии с нормативными требованиями (например, хранение данных в определенном географическом регионе).</span><span class="sxs-lookup"><span data-stu-id="a7248-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

