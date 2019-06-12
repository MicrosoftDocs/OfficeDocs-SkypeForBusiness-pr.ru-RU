---
title: Процесс миграции — сведения
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="49068-102">Процесс миграции — сведения</span><span class="sxs-lookup"><span data-stu-id="49068-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49068-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="49068-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="49068-104">Используйте следующие предварительные требования и подробные инструкции по переносу Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat на Lync Server 2013 и на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="49068-105">Предварительные условия для миграции</span><span class="sxs-lookup"><span data-stu-id="49068-105">Prerequisites for Migration</span></span>

<span data-ttu-id="49068-106">Убедитесь, что вы выполнили следующие предварительные требования, прежде чем переносить Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat на Lync Server 2013 и на сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="49068-107">Разверните хотя бы один пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49068-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="49068-108">Если у вас несколько пулов Lync Server 2013, решите, какой пул Lync Server 2013 будет являться домашним пулом для нового пула серверов для сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49068-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="49068-109">Установите сервер Lync Server 2013, пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="49068-110">Она будет пустой (нет категорий, комнат или надстроек).</span><span class="sxs-lookup"><span data-stu-id="49068-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="49068-111">Прежде чем переносить старые категории, комнаты и надстройки, вы можете создавать комнаты, категории или надстройки на сервере Lync Server 2013, в котором развернута служба сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49068-112">Имейте в виду, что эти вновь созданные элементы могут конфликтовать с устаревшими элементами, которые вы перенесете.</span><span class="sxs-lookup"><span data-stu-id="49068-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="49068-113">Избежать конфликтов именования; в противном случае они будут переписаны после миграции устаревших данных.</span><span class="sxs-lookup"><span data-stu-id="49068-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="49068-114">Подготовка исходных данных для миграции</span><span class="sxs-lookup"><span data-stu-id="49068-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="49068-115">Выполните описанные ниже действия, чтобы правильно подготовить исходные данные для миграции.</span><span class="sxs-lookup"><span data-stu-id="49068-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="49068-116">Создавайте резервные копии исходных баз данных для Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="49068-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="49068-117">Подробные сведения о резервном копировании SQL Server можно найти в <http://go.microsoft.com/fwlink/p/?linkid=254851>статье Обзор резервного копирования (SQL Server).</span><span class="sxs-lookup"><span data-stu-id="49068-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49068-118">Доменные службы Active Directory должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="49068-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="49068-119">В качестве условия миграции вы не можете выполнить миграцию в пул в другом развертывании (в частности, в другом лесу Active Directory).</span><span class="sxs-lookup"><span data-stu-id="49068-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="49068-120">Проверка настроек Lync Server 2010, группового чата или Office Communications Server 2007 R2 групп чата и настройка категории.</span><span class="sxs-lookup"><span data-stu-id="49068-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="49068-121">Любые изменения, внесенные в категории, комнаты или надстройки в существующем устаревшем развертывании, будут выполнены с помощью средства администрирования группового чата.</span><span class="sxs-lookup"><span data-stu-id="49068-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="49068-122">Любые изменения, внесенные в категории, комнаты или надстройки на сервере Lync Server 2013, выполняются с помощью панели управления сервера Lync Server или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49068-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="49068-123">Выполните эти действия для подготовки устаревшей системы к миграции.</span><span class="sxs-lookup"><span data-stu-id="49068-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="49068-124">Сервер сохраняемого чата поддерживает один уровень категорий, в отличие от детального иерархического набора категорий.</span><span class="sxs-lookup"><span data-stu-id="49068-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="49068-125">После миграции подкатегории предваряются с помощью полных имен родительских категорий.</span><span class="sxs-lookup"><span data-stu-id="49068-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="49068-126">Вам может потребоваться упростить и свести к сведению существующую структуру категорий, чтобы она соответствовала вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="49068-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="49068-127">Проверьте **руководителей** в корневой категории.</span><span class="sxs-lookup"><span data-stu-id="49068-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="49068-128">Если на этом уровне есть любые руководители, эти пользователи будут добавлены в **список всех комнат** после миграции в качестве руководителей.</span><span class="sxs-lookup"><span data-stu-id="49068-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="49068-129">Если вы не хотите, чтобы ваша организация не предработала, необходимо удалить эти руководители из корневой категории.</span><span class="sxs-lookup"><span data-stu-id="49068-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="49068-130">Проверьте длину имен комнат.</span><span class="sxs-lookup"><span data-stu-id="49068-130">Verify the length of room names.</span></span> <span data-ttu-id="49068-131">После миграции из-за упрощенных структур категорий, если помещения находятся под дочерней категорией, они имеют префиксы с полными именами родительских категорий.</span><span class="sxs-lookup"><span data-stu-id="49068-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="49068-132">Ограничение наименования — 256 символов, включая имена родительских категорий.</span><span class="sxs-lookup"><span data-stu-id="49068-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="49068-133">Вы должны проверить длину названий комнат и, возможно, сократить длину, если они слишком длинны.</span><span class="sxs-lookup"><span data-stu-id="49068-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="49068-134">В Lync Server 2013, если для параметра \*\*\*\* "параметры приглашений" категории задано значение "истина", для приглашений на помещения в этой категории можно выбрать значение истина или ложь.</span><span class="sxs-lookup"><span data-stu-id="49068-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="49068-135">Тем не менее, если для параметра "Настройка приглашений" задано значение "ложь", в помещениях в этой категории отключены приглашения.</span><span class="sxs-lookup"><span data-stu-id="49068-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="49068-136">Перед переносом необходимо сбросить настройки приглашений в старой версии сервера группового чата Lync Server, если вы хотите, чтобы в ней существовало место (в соответствии с определенной категорией).</span><span class="sxs-lookup"><span data-stu-id="49068-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="49068-137">В противном случае Lync Server 2013 отображает предупреждения и задает для комнат значение по умолчанию false.</span><span class="sxs-lookup"><span data-stu-id="49068-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="49068-138">Если вы использовали файлы в помещениях чата, то после миграции необходимо вручную выполнить их в новом хранилище файлов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="49068-139">Эти средства не выполняют никаких действий.</span><span class="sxs-lookup"><span data-stu-id="49068-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="49068-140">Если у вас есть Федеративные пользователи и помещения с федеративными пользователями, имейте в виду, что сохраняемый сервер чата не поддерживает федерацию.</span><span class="sxs-lookup"><span data-stu-id="49068-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="49068-141">Комнаты, в которых будут перенесены Федеративные пользователи; Однако сами пользователи не смогут получить доступ к содержимому, так как федеративный доступ не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="49068-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="49068-142">Определите, какие помещения, которые вы не хотите переносить, и помечайте их как отключенные.</span><span class="sxs-lookup"><span data-stu-id="49068-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="49068-143">Определите дату, после которой вы хотите перенести содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="49068-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="49068-144">Например, возможно, вы не хотите переносить сообщения, созданные ранее 1 января 2010 г., так как эти сообщения могут быть устаревшими или неприменимыми для миграции.</span><span class="sxs-lookup"><span data-stu-id="49068-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="49068-145">Выполнение миграции</span><span class="sxs-lookup"><span data-stu-id="49068-145">Performing the Migration</span></span>

<span data-ttu-id="49068-146">Выполните указанные ниже действия, чтобы выполнить миграцию сервера группового чата старого.</span><span class="sxs-lookup"><span data-stu-id="49068-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="49068-147">Завершите работу с Lync Server 2010, групповой чат, Office Communications Server 2007 R2 Group чата или Lync Server 2013, сохраняемый серверные службы чата.</span><span class="sxs-lookup"><span data-stu-id="49068-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="49068-148">Все службы должны быть остановлены, поэтому рекомендуется выполнять эти действия в любое время, когда достаточно простоя.</span><span class="sxs-lookup"><span data-stu-id="49068-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="49068-149">Как описано выше, не забудьте создать резервную копию текущей базы данных группового чата.</span><span class="sxs-lookup"><span data-stu-id="49068-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="49068-150">Запустите командлет **Export-Ксперсистентчатдата** Windows PowerShell в качестве участника роли постоянного чата Administrator (ксперсистентчатадминистратор).</span><span class="sxs-lookup"><span data-stu-id="49068-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="49068-151">Подробные сведения о командлетах экспорта и импорта можно найти [в разделе Устранение неполадок с конфигурацией сервера для работы с сохраняемым чат с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="49068-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="49068-152">Проверка экспортированного содержимого.</span><span class="sxs-lookup"><span data-stu-id="49068-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="49068-153">Перед тем как приступить к импорту, закройте сервер Lync Server 2013, а затем службы сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="49068-154">Все службы должны быть остановлены, поэтому запланируйте это действие, когда достаточно времени простоя.</span><span class="sxs-lookup"><span data-stu-id="49068-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="49068-155">Создавайте резервные копии базы данных сохраняемого чата, если вы создали какие-либо категории, комнаты или надстройки в развертывании Lync Server 2013 перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="49068-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="49068-156">Процесс экспорта и импорта может объединять устаревшие данные в развертывание Lync Server 2013, но вы захотите создать резервную копию базы данных в случае непреднамеренного перезаписи содержимого (например, при наличии конфликтов имен).</span><span class="sxs-lookup"><span data-stu-id="49068-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="49068-157">Запустите командлет **Import-Ксперсистентчатдата** Windows PowerShell (средство импорта) с помощью команды **WhatIf** , чтобы заполнить серверный пул для пула серверов сохраняемого чата с перенесенными данными.</span><span class="sxs-lookup"><span data-stu-id="49068-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="49068-158">Некоторые преобразования выполняются в процессе в соответствии с упрощенной моделью администрирования.</span><span class="sxs-lookup"><span data-stu-id="49068-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="49068-159">Устраните все ошибки и предупреждения, которые появляются на экране.</span><span class="sxs-lookup"><span data-stu-id="49068-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="49068-160">Запустите командлет **Import-ксперсистентчатдата** для сервера Windows PowerShell, который входит в состав роли администратора сохраняемого чата (ксперсистентчатадминистратор).</span><span class="sxs-lookup"><span data-stu-id="49068-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="49068-161">Подробные сведения о командлетах экспорта и импорта можно найти [в разделе Устранение неполадок с конфигурацией сервера для работы с сохраняемым чат с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="49068-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="49068-162">Вы должны выполнить XCOPY для всех загруженных файлов (всю папку) в новом хранилище файлов для Lync Server 2013, сохраняемом файле чата.</span><span class="sxs-lookup"><span data-stu-id="49068-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49068-163">Lync 2013 (клиент) не поддерживает отправку и просмотр файлов в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="49068-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="49068-164">Вы по-прежнему можете использовать устаревший клиент для публикации и просмотра файлов в комнате.</span><span class="sxs-lookup"><span data-stu-id="49068-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="49068-165">Перенос URI сервера Lync Server 2010, группового чата или Office Communications Server 2007 R2 Group Chat на сервер Lync Server 2013, сохраняемый объект контакта сервера чата.</span><span class="sxs-lookup"><span data-stu-id="49068-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="49068-166">Описанные ниже действия необходимы в том случае, если для пользователей Lync 2010 Group Chat или Office Communicator 2007 R2 требуется подключение к последней версии Lync 2013, сохраняемому чат (клиенту) после миграции без каких-либо изменений в конфигурации на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="49068-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="49068-167">Удалите учетную запись\<пользователя\>сервера просмотра оксчат @ ИмяДомена. com.</span><span class="sxs-lookup"><span data-stu-id="49068-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="49068-168">Она использовалась для указания службе подстановки в Lync Server 2010, групповой чат.</span><span class="sxs-lookup"><span data-stu-id="49068-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="49068-169">Вы можете удалить пул и удалить из него доверенные записи позже.</span><span class="sxs-lookup"><span data-stu-id="49068-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="49068-170">Создайте конечную точку из устаревшей версии (Сохраняемый объект контакта сервера чата), запустив командлет Windows PowerShell **New-ксперсистентчатендпоинт**с идентичным URI SIP, чтобы старый клиент работал эффективно при перезапуске службы.</span><span class="sxs-lookup"><span data-stu-id="49068-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="49068-171">В этот момент обязательный процесс миграции завершен.</span><span class="sxs-lookup"><span data-stu-id="49068-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="49068-172">Lync 2010 Group Chat (клиенты) или Office Communicator 2007 R2 Group Chat (клиенты) могут подключаться к новым пулам серверов для работы с сохраняемым чат, а затем прозрачно.</span><span class="sxs-lookup"><span data-stu-id="49068-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="49068-173">Следуйте этим дополнительным инструкциям по списанию для Lync Server 2010, группового чата или Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="49068-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="49068-174">Запустите службы сервера сохраняемого чата, включив все компьютеры в новом пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="49068-175">С помощью панели управления Lync Server и командлетов Windows PowerShell убедитесь, что данные успешно перенесены.</span><span class="sxs-lookup"><span data-stu-id="49068-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="49068-176">Удалите приложение Lync 2010 Group Chat или Office Communicator 2007 R2 Group Chat на компьютерах из пула серверов группового чата.</span><span class="sxs-lookup"><span data-stu-id="49068-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="49068-177">Удалите доверенное приложение и доверенный пул приложений с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49068-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="49068-178">Это приведет к удалению этих элементов из хранилища центрального управления и соответствующих записей доверенных служб (Тсес) из Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49068-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="49068-179">Кроме того, этот шаг выполняется с помощью построителя топологии (доверенные приложения и пулы также содержат выделенный узел).</span><span class="sxs-lookup"><span data-stu-id="49068-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="49068-180">Теперь вы можете включить функции сервера для постоянного чата через новые клиенты.</span><span class="sxs-lookup"><span data-stu-id="49068-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="49068-181">Дополнительные сведения о включении сервера сохраняемого чата можно найти [в разделе Развертывание сервера сохраняемого чата в Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="49068-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49068-182">Lync Server 2013 поддерживает несколько пулов серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="49068-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="49068-183">Однако поддерживается перенос группового чата Lync 2010 и группового чата Office Communications Server 2007&nbsp;R2 на один серверный пул lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49068-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="49068-184">Вы можете добавить в развертывание дополнительные пулы серверов для сохранения в соответствии с нормативными потребностями (например, сохранить данные в определенном географическом регионе).</span><span class="sxs-lookup"><span data-stu-id="49068-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

