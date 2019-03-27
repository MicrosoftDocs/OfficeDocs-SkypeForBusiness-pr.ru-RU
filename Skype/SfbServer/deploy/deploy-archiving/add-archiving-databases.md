---
title: Добавление баз данных архивации к существующему развертыванию в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как добавление баз данных архивации в вашей Скайп для развертывания Business Server.'
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895316"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="13faa-103">Добавление баз данных архивации к существующему развертыванию в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="13faa-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="13faa-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как добавление баз данных архивации в вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="13faa-105">Перед настройкой поддержки архивации в развертывании необходимо встроить ее в топологию.</span><span class="sxs-lookup"><span data-stu-id="13faa-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="13faa-106">Сведения, приведенные в этом разделе объясняется, как использовать построитель топологий, чтобы:</span><span class="sxs-lookup"><span data-stu-id="13faa-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="13faa-107">Добавление архивной базы данных к топологии.</span><span class="sxs-lookup"><span data-stu-id="13faa-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="13faa-108">Публикация обновленной топологии для добавления базы данных архивации к вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="13faa-109">Если вы хотите использовать интеграции с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange для всех пользователей в развертывании, не указывайте **хранилища архивации SQL Server** или **зеркальное отображение хранилища SQL Server для использования** сведений.</span><span class="sxs-lookup"><span data-stu-id="13faa-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="13faa-110">Добавление архивной базы данных к топологии</span><span class="sxs-lookup"><span data-stu-id="13faa-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="13faa-111">На компьютере, на котором работает Скайп для Business Server или на котором Скайп для установлены средства администрирования Business Server, выполните вход с помощью учетной записи, которая является членом локальной группы пользователей (или имеет эквивалентные права пользователя).</span><span class="sxs-lookup"><span data-stu-id="13faa-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="13faa-112">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="13faa-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="13faa-113">В дереве консоли перейдите к пулу переднего плана, где требуется развернуть архивацию, и щелкните на имени этого пула.</span><span class="sxs-lookup"><span data-stu-id="13faa-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="13faa-114">В меню **Действие** выберите **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="13faa-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="13faa-115">В диалоговом окне **Изменение свойств** щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="13faa-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="13faa-116">Прокрутите вниз до раздела **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="13faa-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="13faa-117">Установите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="13faa-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="13faa-118">В разделе **хранилища архивации SQL Server,** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="13faa-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="13faa-119">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="13faa-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="13faa-120">Если всех пользователей размещаются на Microsoft Exchange Server 2013 или выше, можно архивировать Скайп для бизнес-коммуникаций для всех пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="13faa-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="13faa-121">В этом случае не требуется для настройки хранилища архивации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="13faa-122">Чтобы указать новое хранилище SQL Server, нажмите кнопку **Создать**и затем в диалоговом окне **Определение нового хранилища SQL Server** выполните следующие:</span><span class="sxs-lookup"><span data-stu-id="13faa-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="13faa-123">В **Поле полное имя SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="13faa-124">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="13faa-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="13faa-125">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="13faa-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="13faa-126">Если вы хотите использовать зеркальное отображение хранилища SQL Server, выберите **зеркальное отображение хранилища SQL Server для включения**и затем сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="13faa-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="13faa-127">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке **зеркальное хранилище архивации SQL Server** щелкните имя хранилища SQL Server, который будет использоваться для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="13faa-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="13faa-128">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **Создать**и затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="13faa-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="13faa-129">а.</span><span class="sxs-lookup"><span data-stu-id="13faa-129">a.</span></span> <span data-ttu-id="13faa-130">В **Поле полное имя SQL Server**укажите полное доменное имя SQL Server, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="13faa-131">б.</span><span class="sxs-lookup"><span data-stu-id="13faa-131">b.</span></span> <span data-ttu-id="13faa-132">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="13faa-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="13faa-133">в.</span><span class="sxs-lookup"><span data-stu-id="13faa-133">c.</span></span> <span data-ttu-id="13faa-134">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="13faa-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="13faa-135">Если включить зеркальное отображение SQL Server и должны быть включены (третьих, отдельный экземпляр SQL Server, можно определять работоспособности основного сервера SQL Server и зеркального экземпляра) следящий сервер зеркального отображения сервера SQL Server, выберите **следящий сервер зеркального отображения с помощью SQL Server для автоматического отработка отказа** флажок, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="13faa-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="13faa-136">а.</span><span class="sxs-lookup"><span data-stu-id="13faa-136">a.</span></span> <span data-ttu-id="13faa-137">В **Поле полное имя SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новый следящий сервер зеркального отображения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13faa-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="13faa-138">б.</span><span class="sxs-lookup"><span data-stu-id="13faa-138">b.</span></span> <span data-ttu-id="13faa-139">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите экземпляр, который будет служить следящим сервером зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="13faa-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="13faa-140">в.</span><span class="sxs-lookup"><span data-stu-id="13faa-140">c.</span></span> <span data-ttu-id="13faa-141">Если указанный экземпляр SQL Server в отношении зеркального отображения, установите флажок **данный экземпляр SQL связан зеркальным отображением** и затем в поле **номер порта зеркала**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="13faa-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="13faa-142">Для сохранения конфигурации нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="13faa-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="13faa-143">Публикация обновленной топологии для добавления архивной базы данных к развертыванию</span><span class="sxs-lookup"><span data-stu-id="13faa-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="13faa-144">На компьютере, на котором работает Скайп для Business Server или на котором Скайп для установлены средства администрирования Business Server, выполните вход с помощью учетной записи, которая является членом локальной группы пользователей (или имеет эквивалентные права пользователя).</span><span class="sxs-lookup"><span data-stu-id="13faa-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13faa-145">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы пользователей, но чтобы опубликовать топологию, которая требуется для добавления сервера в топологию, необходимо использовать учетную запись, которая является членом группы **Администраторов домена** и **RTCUniversalServer Администраторы** группы, который имеет разрешения на полный доступ (чтение, запись и изменение) на общий файловый ресурс, который используется для Скайп для хранилища файлов Business Server (таким образом, Topology Builder можно настроить список управления доступом требуется (доступом), или значение Учетная запись с эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="13faa-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="13faa-146">Откройте топологию, созданную в предыдущем разделе, с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="13faa-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="13faa-147">В дереве консоли щелкните правой кнопкой мыши **Скайп для Business Server**и нажмите кнопку **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="13faa-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="13faa-148">На странице **Публикация топологии** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="13faa-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="13faa-149">На странице **Создание баз данных** убедитесь в том, что база данных выбрана, затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="13faa-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="13faa-150">Если у вас нет соответствующих разрешений на создание баз данных, можно отменить выбор базы данных, чтобы пользователь с нужными разрешениями создал базу данных.</span><span class="sxs-lookup"><span data-stu-id="13faa-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="13faa-151">> только базы данных на выделенных серверах SQL можно установить с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="13faa-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="13faa-152">Базы данных на серверах SQL Server, выровненные с другими серверными компонентами, необходимо устанавливать с помощью локальной программы установки на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="13faa-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="13faa-153">На странице **Завершение мастера публикации** убедитесь, что топология была успешно опубликована, а затем щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="13faa-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="13faa-154">После публикации топологии необходимо до начала архивации данных настроить параметры и политики архивации.</span><span class="sxs-lookup"><span data-stu-id="13faa-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="13faa-155">Дополнительные сведения см [Настройка архивации политики для Скайп для Business Server](configure-archiving-policies.md)и [настроить параметры для Скайп для сервера архивации](configure-archiving-options.md) .</span><span class="sxs-lookup"><span data-stu-id="13faa-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

