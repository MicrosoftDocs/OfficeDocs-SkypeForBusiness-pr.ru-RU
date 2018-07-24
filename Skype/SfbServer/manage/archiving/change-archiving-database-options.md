---
title: Изменение параметров базы данных архивации в Скайп Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Сводка: Узнайте, как изменить базы данных параметров архивации для Скайп для Business Server.'
ms.openlocfilehash: af1cc1e6398652efac5be20114dac6bf228ef892
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21010080"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="7cbfc-103">Изменение параметров базы данных архивации в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="7cbfc-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="7cbfc-104">**Сводка:** Узнайте, как изменение базы данных параметров архивации для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="7cbfc-105">При развертывании архивации с помощью хранилища сервера SQL Server для архивации хранилища, используемого для каких-либо пользователей, можно изменить следующие базы данных хранилища:</span><span class="sxs-lookup"><span data-stu-id="7cbfc-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="7cbfc-106">Используйте в другую базу данных SQL Server для архивации хранилища.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="7cbfc-107">Этот компонент включает основной базы данных архивирования и любой базы данных, которая будет использоваться для зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="7cbfc-108">Переключитесь в интеграции с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="7cbfc-109">Если всех пользователей размещены на серверах Exchange, необходимо использовать Microsoft Exchange хранилища для всех пользователей в вашем развертывании необходимо удалить хранилища базы данных SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="7cbfc-110">Чтобы сделать любой из этих изменений, необходимо выполнить Topology Builder, внесите необходимые изменения и затем опубликовать эту топологию еще раз.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="7cbfc-111">Не указывайте **хранилища архивации SQL Server** или **зеркальное отображение хранилища SQL Server для включения** информации, при отсутствии Скайп для бизнес-пользователей, которые не размещаются на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="7cbfc-112">Изменение параметров архивной базы данных</span><span class="sxs-lookup"><span data-stu-id="7cbfc-112">Change Archiving database options</span></span>

1. <span data-ttu-id="7cbfc-113">На компьютере, на котором работает Скайп для Business Server или на котором Скайп для установлены средства администрирования Business Server, выполните вход с помощью учетной записи, которая является членом локальной группы пользователей (или имеет эквивалентные права пользователя).</span><span class="sxs-lookup"><span data-stu-id="7cbfc-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cbfc-114">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы пользователей, но чтобы опубликовать топологию, которая требуется для добавления компонента в топологии, необходимо использовать учетную запись, которая является членом группы **Администраторов домена** и **RTCUniversalSer verAdmins** группы, который имеет разрешения на полный доступ (то есть, чтение, запись и изменение) для общей папки, которое используется для Скайп для хранилища файлов Business Server (то есть, чтобы Topology Builder можно настроить элемент управления необходимые доступом списки (доступом) или учетной записи с эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="7cbfc-115">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="7cbfc-116">В дереве консоли перейдите к интерфейсному пулу, в котором развернута служба архивирования, и затем щелкните название пула, где нужно изменить параметры базы данных.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="7cbfc-117">В меню **Действие** выберите **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="7cbfc-118">В диалоговом окне **Изменение свойств** щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="7cbfc-119">Прокрутите вниз до раздела **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="7cbfc-120">В разделе **Архивация** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-120">In **Archiving**, do the following:</span></span>
    
  - <span data-ttu-id="7cbfc-121">Для перехода к другому существующему хранилищу SQL Server в раскрывающемся списке **Хранилище архивации SQL Server** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
  - <span data-ttu-id="7cbfc-122">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
  - <span data-ttu-id="7cbfc-123">Для задания нового хранилища SQL Server щелкните **Создать**, затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
    - <span data-ttu-id="7cbfc-124">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
    - <span data-ttu-id="7cbfc-125">Чтобы указать новое хранилище SQL Server, нажмите кнопку **Создать**и затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие:</span><span class="sxs-lookup"><span data-stu-id="7cbfc-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="7cbfc-126">В **Поле полное имя SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
      - <span data-ttu-id="7cbfc-127">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
      - <span data-ttu-id="7cbfc-128">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="7cbfc-129">Если требуется добавить хранилище SQL Server для зеркального отображения или назначить для зеркального отображения хранилища SQL Server другое существующее хранилище, установите флажок **Включить зеркалирование хранилища SQL Server**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
    - <span data-ttu-id="7cbfc-130">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке **зеркальное хранилище архивации SQL Server** щелкните имя хранилища SQL Server, который будет использоваться для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
    - <span data-ttu-id="7cbfc-131">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **Создать**и затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="7cbfc-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
      <span data-ttu-id="7cbfc-132">а.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-132">a.</span></span> <span data-ttu-id="7cbfc-133">В **Поле полное имя SQL Server**укажите полное доменное имя SQL Server, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
      <span data-ttu-id="7cbfc-134">б.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-134">b.</span></span> <span data-ttu-id="7cbfc-135">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
      <span data-ttu-id="7cbfc-136">в.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-136">c.</span></span> <span data-ttu-id="7cbfc-137">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="7cbfc-138">Если включить зеркальное отображение SQL Server и нужно добавить или изменить (третьих, отдельный экземпляр SQL Server, можно определять работоспособности основного сервера и зеркального экземпляра SQL Server) следящий сервер зеркального отображения сервера SQL Server, выберите **следящий сервер зеркального отображения с помощью SQL Server, чтобы включения автоматического переключения** флажок, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7cbfc-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="7cbfc-139">а.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-139">a.</span></span> <span data-ttu-id="7cbfc-140">В **Поле полное имя SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новый следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="7cbfc-141">б.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-141">b.</span></span> <span data-ttu-id="7cbfc-142">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите экземпляр, который будет служить следящим сервером зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="7cbfc-143">в.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-143">c.</span></span> <span data-ttu-id="7cbfc-144">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
  - <span data-ttu-id="7cbfc-145">Чтобы переключиться на интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange (если все пользователи вашей развертки размещаются на серверах Exchange), удалите все данные для баз данных архивации.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7cbfc-146">При наличии любого Скайп для бизнес-пользователей, которые не размещаются на серверах Exchange, не удаляйте сведения о хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="7cbfc-147">Для сохранения конфигурации нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7cbfc-148">Изменения, внесенные в построителе топологий не вступят в силу только после публикации новой топологии.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="7cbfc-149">Дополнительные сведения см [Добавить баз данных архивации к существующему развертыванию в Скайп для Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7cbfc-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="7cbfc-150">Изменение расположения архивной базы данных с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cbfc-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="7cbfc-151">Как правило, изменять указанное при установке сервера архивации расположение архивной базы данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="7cbfc-152">Однако в случае аппаратного сбоя или другой неполадки можно с помощью командлета **Set-CsArchivingServer** задать для сервера архивации другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="7cbfc-153">В следующем примере изменяется местоположение базы данных архивирования для ArchivingServer:atl-cs-001.contoso.com сервера архивирование.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="7cbfc-154">Для новой базы данных задается ArchivingDatabase:atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7cbfc-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


