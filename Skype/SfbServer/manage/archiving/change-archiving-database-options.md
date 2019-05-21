---
title: Изменение параметров базы данных для архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Сводка: сведения о том, как изменить параметры архивированной базы данных для сервера Skype для бизнеса Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299988"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="95362-103">Изменение параметров базы данных для архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="95362-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="95362-104">**Сводка:** Сведения о том, как изменить параметры базы данных для архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="95362-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="95362-105">Если вы разворачиваете архивацию с помощью хранилища SQL Server для хранения данных для любого из ваших пользователей, вы можете внести следующие изменения в хранилище базы данных.</span><span class="sxs-lookup"><span data-stu-id="95362-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="95362-106">Используйте другую базу данных SQL Server для хранения архивов.</span><span class="sxs-lookup"><span data-stu-id="95362-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="95362-107">Сюда относится основная база данных архивации и любая база данных, которую вы используете для зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="95362-108">Переход на Microsoft Exchange Integration для хранения архивированных данных и файлов на серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="95362-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="95362-109">Если все пользователи находятся на серверах Exchange и вы хотите использовать хранилище Microsoft Exchange для всех пользователей в развертывании, необходимо удалить из топологии базы данных из магазина SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="95362-110">Чтобы внести оба эти изменения, необходимо запустить построитель топологии, внести изменения, а затем опубликовать топологию еще раз.</span><span class="sxs-lookup"><span data-stu-id="95362-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="95362-111">Не указывайте режим **архивации в хранилище SQL Server** или включите сведения о **зеркальном отображении хранилища SQL Server** , если только у вас нет пользователей Skype для бизнеса, не подключенных к серверам Exchange.</span><span class="sxs-lookup"><span data-stu-id="95362-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="95362-112">Изменение параметров архивной базы данных</span><span class="sxs-lookup"><span data-stu-id="95362-112">Change Archiving database options</span></span>

1. <span data-ttu-id="95362-113">На компьютере, на котором установлен Skype для бизнеса Server или на котором установлены средства администрирования сервера Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователей).</span><span class="sxs-lookup"><span data-stu-id="95362-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="95362-114">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления компонента в топологию, необходимо использовать учетную запись, которая входит в группу **"Администраторы домена"** и **рткуниверсалсер Верадминс** , и у нее есть разрешения на полный доступ (то есть чтение, запись и изменение) в общей папке, которую вы используете для хранения файлов в Skype для бизнеса Server (то есть построителю топологии может настроить требуемый контроль доступа на уровне пользователей). списки (DACL) или учетная запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="95362-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="95362-115">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="95362-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="95362-116">В дереве консоли перейдите к интерфейсному пулу, в котором развернута служба архивирования, и затем щелкните название пула, где нужно изменить параметры базы данных.</span><span class="sxs-lookup"><span data-stu-id="95362-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="95362-117">В меню **Действие** выберите **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="95362-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="95362-118">В диалоговом окне **Изменение свойств** щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="95362-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="95362-119">Прокрутите вниз до раздела **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="95362-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="95362-120">В разделе **Архивация** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95362-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="95362-121">Для перехода к другому существующему хранилищу SQL Server в раскрывающемся списке **Хранилище архивации SQL Server** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95362-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="95362-122">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="95362-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="95362-123">Для задания нового хранилища SQL Server щелкните **Создать**, затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95362-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="95362-124">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="95362-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="95362-125">Чтобы указать новое хранилище SQL Server, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="95362-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="95362-126">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="95362-127">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="95362-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="95362-128">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="95362-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="95362-129">Если требуется добавить хранилище SQL Server для зеркального отображения или назначить для зеркального отображения хранилища SQL Server другое существующее хранилище, установите флажок **Включить зеркалирование хранилища SQL Server**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95362-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="95362-130">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке " **Архивирование хранилища SQL Server** " выберите имя хранилища SQL Server, которое вы хотите использовать для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="95362-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="95362-131">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="95362-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="95362-132">a)</span><span class="sxs-lookup"><span data-stu-id="95362-132">a.</span></span> <span data-ttu-id="95362-133">В **доменном имени SQL Server**укажите полное доменное имя сервера SQL Server, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="95362-134">б)</span><span class="sxs-lookup"><span data-stu-id="95362-134">b.</span></span> <span data-ttu-id="95362-135">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="95362-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="95362-136">в.</span><span class="sxs-lookup"><span data-stu-id="95362-136">c.</span></span> <span data-ttu-id="95362-137">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="95362-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="95362-138">Если вы включите зеркальное отображение SQL Server и хотите добавить или изменить следящий сервер SQL Server (третий, отдельный экземпляр SQL Server, который может определять работоспособность основного сервера SQL Server и зеркальных экземпляров), выберите параметр **использовать свидетель зеркального отображения SQL Server. Установите флажок Включить автоматический переход на другой ресурс** , а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="95362-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="95362-139">a)</span><span class="sxs-lookup"><span data-stu-id="95362-139">a.</span></span> <span data-ttu-id="95362-140">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новый следящий сервер SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="95362-141">б)</span><span class="sxs-lookup"><span data-stu-id="95362-141">b.</span></span> <span data-ttu-id="95362-142">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите экземпляр, который будет служить следящим сервером зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="95362-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="95362-143">в.</span><span class="sxs-lookup"><span data-stu-id="95362-143">c.</span></span> <span data-ttu-id="95362-144">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="95362-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="95362-145">Чтобы переключиться на интеграцию Microsoft Exchange для хранения данных и файлов на серверах Exchange (если все пользователи находятся в вашем развертывании на серверах Exchange), удалите все данные для архивации баз данных.</span><span class="sxs-lookup"><span data-stu-id="95362-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="95362-146">Если у вас есть пользователи Skype для бизнеса, которые не размещены на серверах Exchange, не удаляйте данные из хранилища SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95362-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="95362-147">Для сохранения конфигурации нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95362-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="95362-148">Изменения, внесенные в построителе топологии, вступают в силу только после публикации новой топологии.</span><span class="sxs-lookup"><span data-stu-id="95362-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="95362-149">Подробности можно найти [в разделе Добавление архивированных баз данных в существующее развертывание в Skype для бизнеса Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="95362-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="95362-150">Изменение расположения архивной базы данных с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95362-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="95362-151">Как правило, изменять указанное при установке сервера архивации расположение архивной базы данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="95362-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="95362-152">Однако в случае аппаратного сбоя или другой неполадки можно с помощью командлета **Set-CsArchivingServer** задать для сервера архивации другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="95362-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="95362-153">В следующем примере показано, как изменить расположение базы данных архивации для сервера архивации Арчивингсервер: ATL-CS-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="95362-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="95362-154">Для новой базы данных задается ArchivingDatabase:atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="95362-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


