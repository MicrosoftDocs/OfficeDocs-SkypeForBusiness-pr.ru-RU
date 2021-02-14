---
title: Изменение параметров базы данных архива в Skype для бизнеса Server
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: Сводка. Узнайте, как изменить параметры базы данных архива для Skype для бизнеса Server.
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817699"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="e372e-103">Изменение параметров базы данных архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e372e-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="e372e-104">**Сводка:** Узнайте, как изменить параметры базы данных архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e372e-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="e372e-105">При развертывании архивирования с SQL Server хранения данных для хранения данных для любого из пользователей можно внести следующие изменения в хранилище базы данных:</span><span class="sxs-lookup"><span data-stu-id="e372e-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="e372e-106">Используйте другую SQL Server для архивирования хранилища.</span><span class="sxs-lookup"><span data-stu-id="e372e-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="e372e-107">К ним относятся основная база данных архива и любая база данных, используемая для SQL Server зеркального отражания.</span><span class="sxs-lookup"><span data-stu-id="e372e-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="e372e-108">Переключение на интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="e372e-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="e372e-109">Если все пользователи размещены на серверах Exchange и вы хотите использовать хранилище Microsoft Exchange для всех пользователей в развертывании, удалите базы данных SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="e372e-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="e372e-110">Чтобы внести какие-либо из этих изменений, необходимо запустить построитель топологий, внести изменения и опубликовать топологию еще раз.</span><span class="sxs-lookup"><span data-stu-id="e372e-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="e372e-111">Не **указываю** архивную SQL Server  хранения или SQL Server для хранения данных зеркального SQL Server, если у вас нет пользователей Skype для бизнеса, которые не находятся на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="e372e-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="e372e-112">Изменение параметров базы данных архивирования</span><span class="sxs-lookup"><span data-stu-id="e372e-112">Change Archiving database options</span></span>

1. <span data-ttu-id="e372e-113">На компьютере со Skype для бизнеса Server или на котором установлены средства администрирования Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="e372e-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e372e-114">Топологию можно определить с помощью учетной записи, которая является членом локальной группы пользователей, но для публикации топологии, необходимой для добавления  компонента в топологию, Необходимо использовать учетную запись, которая является членом группы администраторов домена и группы **RTCUniversalServerAdmins** и имеет разрешения на полный доступ (т. е. чтение, запись и изменение) в файловом хранилище, используемом для файлового хранилище Skype для бизнеса Server (то есть, чтобы построитель топологий можно было настроить необходимые списки управления доступом на основе дискреционного доступа (DACLs) или учетную запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="e372e-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="e372e-115">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="e372e-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="e372e-116">В дереве консоли перейдите к интерфейсному пулу, в котором развернута служба архивирования, и затем щелкните название пула, где нужно изменить параметры базы данных.</span><span class="sxs-lookup"><span data-stu-id="e372e-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="e372e-117">В меню **Действие** выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e372e-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="e372e-118">В окне **Изменение свойств** щелкните **Общее**.</span><span class="sxs-lookup"><span data-stu-id="e372e-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="e372e-119">Прокрутите вниз до **Архивирование**.</span><span class="sxs-lookup"><span data-stu-id="e372e-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="e372e-120">В **Архивирование**, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e372e-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="e372e-121">Чтобы сменить хранилище SQL Server в **Архивное хранилище SQL Server**, в раскрывающемся списке сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e372e-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="e372e-122">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="e372e-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="e372e-123">Чтобы указать новое хранилище SQL Server нажмите **Создать** и затем в окне **Определение новое хранилище SQL Server** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e372e-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="e372e-124">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="e372e-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="e372e-125">Чтобы указать новое хранилище SQL Server, нажмите кнопку "Новый", а затем в диалоговом **окне "Определение** нового SQL Server Store" сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e372e-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="e372e-126">В **SQL Server FQDN** укажите FQDN сервера, на котором необходимо создать новое SQL Server хранилище.</span><span class="sxs-lookup"><span data-stu-id="e372e-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="e372e-127">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите **Именованный экземпляр**, и затем укажите нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e372e-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="e372e-128">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в окне зеркального отношения, а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="e372e-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="e372e-129">Чтобы добавить хранилище SQL Server для зеркалирования или изменить хранилище для зеркалирования установите флажок **Включить зеркалирование хранилища SQL Server**, и затем сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e372e-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="e372e-130">Чтобы использовать существующее хранилище SQL Server для зеркального SQL Server, щелкните имя SQL Server, которое вы хотите использовать для зеркального зеркального отражания. </span><span class="sxs-lookup"><span data-stu-id="e372e-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="e372e-131">Чтобы указать новое хранилище SQL Server для зеркального отражания, нажмите кнопку **"Новый",** а затем в диалоговом окне "Определение нового SQL Server **Store"** сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="e372e-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="e372e-132">а.</span><span class="sxs-lookup"><span data-stu-id="e372e-132">a.</span></span> <span data-ttu-id="e372e-133">В **SQL Server Укажите FQDN** SQL Server, на котором вы хотите SQL Server хранилище.</span><span class="sxs-lookup"><span data-stu-id="e372e-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="e372e-134">б.</span><span class="sxs-lookup"><span data-stu-id="e372e-134">b.</span></span> <span data-ttu-id="e372e-135">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите нажмите **Именованный экземпляр**, и затем укажите нужный.</span><span class="sxs-lookup"><span data-stu-id="e372e-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="e372e-136">в.</span><span class="sxs-lookup"><span data-stu-id="e372e-136">c.</span></span> <span data-ttu-id="e372e-137">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в окне зеркального отношения, а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="e372e-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="e372e-138">Если вы включаете зеркальное SQL Server и хотите добавить или изменить свидетель зеркального зеркального SQL Server (третий отдельный экземпляр SQL Server, который может обнаруживать состояние основного сервера SQL Server и зеркальных экземпляров), выберите свидетель зеркального SQL Server use **SQL Server,** чтобы включить автоматический отключающийся экземпляр, а затем сделайте одно из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e372e-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="e372e-139">а.</span><span class="sxs-lookup"><span data-stu-id="e372e-139">a.</span></span> <span data-ttu-id="e372e-140">В SQL Server В качестве **FQDN** укажите FQDN сервера, на котором необходимо создать новый SQL Server зеркального зеркального отражания.</span><span class="sxs-lookup"><span data-stu-id="e372e-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="e372e-141">б.</span><span class="sxs-lookup"><span data-stu-id="e372e-141">b.</span></span> <span data-ttu-id="e372e-142">Либо нажмите **Экземпляр по умолчанию**, либо **Именованный экземпляр**, чтобы указать нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e372e-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="e372e-143">в.</span><span class="sxs-lookup"><span data-stu-id="e372e-143">c.</span></span> <span data-ttu-id="e372e-144">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в окне зеркального отношения, а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="e372e-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="e372e-145">Чтобы переключиться на интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange (если все пользователи в развертывании размещены на серверах Exchange), удалите все сведения для баз данных архивации.</span><span class="sxs-lookup"><span data-stu-id="e372e-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="e372e-146">Если у вас есть пользователи Skype для бизнеса, которые не находятся на серверах Exchange Server, не удаляйте SQL Server данных.</span><span class="sxs-lookup"><span data-stu-id="e372e-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="e372e-147">Чтобы сохранить конфигурацию, нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e372e-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e372e-148">Изменения, внесенные в построитель топологий, не вступает в силу до публикации новой топологии.</span><span class="sxs-lookup"><span data-stu-id="e372e-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="e372e-149">Дополнительные сведения см. в дополнительных сведениях о добавлении баз данных архивации [в существующее развертывание в Skype для бизнеса Server.](../../deploy/deploy-archiving/add-archiving-databases.md)</span><span class="sxs-lookup"><span data-stu-id="e372e-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="e372e-150">Изменение расположения базы данных архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e372e-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="e372e-151">В большинстве случаев изменять расположение базы данных архивации, указанное при установке сервера архивации, не требуется.</span><span class="sxs-lookup"><span data-stu-id="e372e-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="e372e-152">Однако при сбое оборудования или другой проблеме сервер архива можно указать на новую базу данных с помощью **cmdlet Set-CsArchivingServer.**</span><span class="sxs-lookup"><span data-stu-id="e372e-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="e372e-153">В следующем примере изменяется расположение базы данных архивации для сервера архивации ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span><span class="sxs-lookup"><span data-stu-id="e372e-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="e372e-154">В этом примере новая база данных расположена по адресу ArchivingDatabase:atl-sql-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="e372e-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


