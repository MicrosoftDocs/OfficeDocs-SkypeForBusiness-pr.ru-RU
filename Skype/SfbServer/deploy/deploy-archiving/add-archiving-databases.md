---
title: Добавление баз данных архивации в существующее развертывание в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: Сводка. В этом разделе вы узнаете, как добавить базы данных архивации в развертывание Skype для бизнеса Server.
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820679"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="f639d-103">Добавление баз данных архивации в существующее развертывание в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f639d-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="f639d-104">**Сводка:** В этом разделе вы узнаете, как добавить базы данных архивации в развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f639d-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="f639d-105">Перед настройкой развертывания для поддержки архивации необходимо включить архив в топологию.</span><span class="sxs-lookup"><span data-stu-id="f639d-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="f639d-106">В этой теме объясняется, как использовать построитель топологий для:</span><span class="sxs-lookup"><span data-stu-id="f639d-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="f639d-107">Добавьте базу данных архива в топологию.</span><span class="sxs-lookup"><span data-stu-id="f639d-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="f639d-108">Опубликуйте обновленную топологию, чтобы добавить базу данных архивации в развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f639d-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f639d-109">Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange для всех пользователей в развертывании, не указывайте хранилище архивации **SQL Server** или используйте **SQL Server store mirroring** information.</span><span class="sxs-lookup"><span data-stu-id="f639d-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="f639d-110">Добавление базы данных архива в топологию</span><span class="sxs-lookup"><span data-stu-id="f639d-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="f639d-111">На компьютере со Skype для бизнеса Server или на котором установлены средства администрирования Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="f639d-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="f639d-112">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f639d-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="f639d-113">В дереве консоли перейдите к пулу переднего входа, в котором необходимо развернуть архив, а затем щелкните имя пула переднего конца, в котором необходимо развернуть архив.</span><span class="sxs-lookup"><span data-stu-id="f639d-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="f639d-114">В меню **Действие** выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="f639d-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="f639d-115">В окне **Изменение свойств** щелкните **Общее**.</span><span class="sxs-lookup"><span data-stu-id="f639d-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="f639d-116">Прокрутите вниз до **Архивирование**.</span><span class="sxs-lookup"><span data-stu-id="f639d-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="f639d-117">Select the **Archiving** check box.</span><span class="sxs-lookup"><span data-stu-id="f639d-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="f639d-118">В **хранилище архивных SQL Server архива сделайте** одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f639d-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="f639d-119">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="f639d-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="f639d-120">Если все ваши пользователи находятся в Microsoft Exchange Server 2013 или выше, вы можете архивировать коммуникации Skype для бизнеса для всех пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="f639d-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="f639d-121">В этом случае вам не нужно настраивать SQL Server архива.</span><span class="sxs-lookup"><span data-stu-id="f639d-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="f639d-122">Чтобы указать новое хранилище SQL Server, нажмите кнопку "Новый", а затем в диалоговом **окне "Определение** нового SQL Server Store" сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f639d-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="f639d-123">В **SQL Server FQDN** укажите FQDN сервера, на котором необходимо создать новое SQL Server хранилище.</span><span class="sxs-lookup"><span data-stu-id="f639d-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="f639d-124">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите **Именованный экземпляр**, и затем укажите нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f639d-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="f639d-125">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в поле "Зеркальное отношение", а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f639d-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="f639d-126">Если вы хотите использовать зеркальное SQL Server хранения, выберите **"Включить зеркальное SQL Server Store",** а затем сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f639d-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="f639d-127">Чтобы использовать существующее хранилище SQL Server для зеркального SQL Server, щелкните имя SQL Server, которое вы хотите использовать для зеркального зеркального отражания. </span><span class="sxs-lookup"><span data-stu-id="f639d-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="f639d-128">Чтобы указать новое хранилище SQL Server для зеркального отражания, нажмите кнопку **"Новый",** а затем в диалоговом окне "Определение нового SQL Server **Store"** сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f639d-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="f639d-129">а.</span><span class="sxs-lookup"><span data-stu-id="f639d-129">a.</span></span> <span data-ttu-id="f639d-130">В **SQL Server Укажите FQDN** SQL Server, на котором вы хотите SQL Server хранилище.</span><span class="sxs-lookup"><span data-stu-id="f639d-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="f639d-131">б.</span><span class="sxs-lookup"><span data-stu-id="f639d-131">b.</span></span> <span data-ttu-id="f639d-132">Либо нажмите **Экземпляр по умолчанию** либо, чтобы указать другой экземпляр нажмите нажмите **Именованный экземпляр**, и затем укажите нужный.</span><span class="sxs-lookup"><span data-stu-id="f639d-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="f639d-133">в.</span><span class="sxs-lookup"><span data-stu-id="f639d-133">c.</span></span> <span data-ttu-id="f639d-134">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в поле "Зеркальное отношение", а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f639d-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="f639d-135">Если включено зеркальное SQL Server и необходимо включить свидетель зеркального SQL Server (третий отдельный экземпляр SQL Server, который может обнаруживать состояние основного экземпляра SQL Server и зеркального экземпляра), выберите свидетель зеркального SQL Server Use **SQL Server,** чтобы включить автоматический отбой, а затем сделайте одно из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f639d-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="f639d-136">а.</span><span class="sxs-lookup"><span data-stu-id="f639d-136">a.</span></span> <span data-ttu-id="f639d-137">В SQL Server В качестве **FQDN** укажите FQDN сервера, на котором необходимо создать новый SQL Server зеркального зеркального отражания.</span><span class="sxs-lookup"><span data-stu-id="f639d-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="f639d-138">б.</span><span class="sxs-lookup"><span data-stu-id="f639d-138">b.</span></span> <span data-ttu-id="f639d-139">Либо нажмите **Экземпляр по умолчанию**, либо **Именованный экземпляр**, чтобы указать нужный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f639d-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="f639d-140">в.</span><span class="sxs-lookup"><span data-stu-id="f639d-140">c.</span></span> <span data-ttu-id="f639d-141">Если указанный экземпляр SQL Server находится в зеркальном отношении, выберите этот экземпляр **SQL** в поле "Зеркальное отношение", а затем в номере порта **mirror** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="f639d-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="f639d-142">Чтобы сохранить конфигурацию, нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f639d-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="f639d-143">Публикация обновленной топологии для добавления базы данных архивации в развертывание</span><span class="sxs-lookup"><span data-stu-id="f639d-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="f639d-144">На компьютере со Skype для бизнеса Server или на котором установлены средства администрирования Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователя).</span><span class="sxs-lookup"><span data-stu-id="f639d-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f639d-145">Топологию можно определить с помощью учетной записи, которая является членом локальной группы пользователей, но для публикации топологии Для добавления сервера в  топологию необходимо использовать учетную запись, которая является членом группы администраторов домена и группы **RTCUniversalServerAdmins** и имеет разрешения на полный доступ (чтение, запись и изменение) к файловому файлу, используемому для файлового хранилище Skype для бизнеса Server (чтобы построитель топологий можно было настроить необходимый список управления доступом на основе дискреционного доступа (DACLs) или учетную запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="f639d-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="f639d-146">Откройте топологию, созданную в предыдущем разделе, с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f639d-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="f639d-147">В дереве консоли щелкните правой кнопкой **мыши Skype для бизнеса Server** и выберите "Опубликовать **топологию".**</span><span class="sxs-lookup"><span data-stu-id="f639d-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="f639d-148">На странице **Публикация топологии** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f639d-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="f639d-149">На странице **Создание баз данных** убедитесь, что выбрана база данных, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f639d-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f639d-150">Если у вас нет соответствующих разрешений на создание баз данных, можно отменить выбор базы данных, чтобы пользователь с нужными разрешениями создал базу данных.</span><span class="sxs-lookup"><span data-stu-id="f639d-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="f639d-151">> с помощью построитель топологий можно устанавливать только базы данных на выделенных SQL-серверах.</span><span class="sxs-lookup"><span data-stu-id="f639d-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="f639d-152">Базы данных на SQL серверов, которые размещены с другими серверными компонентами, должны быть установлены путем локальной установки на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f639d-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="f639d-153">На странице **Завершение работы мастера публикации** убедитесь, что топология успешно опубликована, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f639d-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f639d-154">После публикации топологии нужно настроить параметры и политики архивации, чтобы получить возможность архивации контента.</span><span class="sxs-lookup"><span data-stu-id="f639d-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="f639d-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server.](configure-archiving-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f639d-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

