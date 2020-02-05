---
title: Добавление архивных баз данных в существующее развертывание в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться добавлять архивированные базы данных в развертывание Skype для бизнеса Server.'
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769052"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="8aa3f-103">Добавление архивных баз данных в существующее развертывание в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8aa3f-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="8aa3f-104">**Сводка:** В этой статье рассказывается, как добавить архивированные базы данных в развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="8aa3f-105">Перед настройкой поддержки архивации в развертывании необходимо встроить ее в топологию.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="8aa3f-106">В этой статье объясняется, как использовать Topology Builder для:</span><span class="sxs-lookup"><span data-stu-id="8aa3f-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="8aa3f-107">Добавление архивной базы данных к топологии.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="8aa3f-108">Опубликуйте обновленную топологию, чтобы добавить базу данных архивации в развертывание Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8aa3f-109">Если вы хотите использовать интеграцию Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange для всех пользователей в развертывании, не указывайте параметр **Архивирование хранилища SQL Server** или **Используйте сведения о зеркальном отображении хранилища SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8aa3f-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="8aa3f-110">Добавление архивной базы данных к топологии</span><span class="sxs-lookup"><span data-stu-id="8aa3f-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="8aa3f-111">На компьютере, на котором установлен Skype для бизнеса Server или на котором установлены средства администрирования сервера Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователей).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="8aa3f-112">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="8aa3f-113">В дереве консоли перейдите к пулу переднего плана, где требуется развернуть архивацию, и щелкните на имени этого пула.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="8aa3f-114">В меню **Действие** выберите **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="8aa3f-115">В диалоговом окне **Изменение свойств** щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="8aa3f-116">Прокрутите вниз до раздела **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="8aa3f-117">Установите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="8aa3f-118">В разделе **Архивация хранилища SQL Server** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="8aa3f-119">Чтобы использовать имеющееся хранилище SQL Server в раскрывающемся списке щелкните название нужного хранилища.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="8aa3f-120">Если все пользователи размещены на сервере Microsoft Exchange Server 2013 или более поздней версии, вы можете архивировать Skype для бизнеса для всех пользователей в Exchange.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="8aa3f-121">В этом случае вам не нужно настраивать хранилище архивации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="8aa3f-122">Чтобы указать новое хранилище SQL Server, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="8aa3f-123">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="8aa3f-124">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="8aa3f-125">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="8aa3f-126">Если вы хотите использовать зеркальное отображение хранилища SQL Server, установите флажок **включить зеркальное отображение хранилища SQL**Server, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="8aa3f-127">Чтобы использовать существующее хранилище SQL Server для зеркального отображения, в раскрывающемся списке " **Архивирование хранилища SQL Server** " выберите имя хранилища SQL Server, которое вы хотите использовать для зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="8aa3f-128">Чтобы указать новое хранилище SQL Server для зеркального отображения, нажмите кнопку **создать**, а затем в диалоговом окне **Определение нового хранилища SQL Server** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="8aa3f-129">a)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-129">a.</span></span> <span data-ttu-id="8aa3f-130">В **доменном имени SQL Server**укажите полное доменное имя сервера SQL Server, на котором вы хотите создать новое хранилище SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="8aa3f-131">б)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-131">b.</span></span> <span data-ttu-id="8aa3f-132">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите требуемый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="8aa3f-133">в.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-133">c.</span></span> <span data-ttu-id="8aa3f-134">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="8aa3f-135">При включении зеркального отображения SQL Server и необходимости включения следящего сервера SQL Server (третий, отдельный экземпляр SQL Server, который может определять работоспособность основного SQL Server и зеркальных экземпляров) установите флажок **использовать следящий сервер зеркального отображения SQL Server для включения автоматического перехода на другой ресурс** , а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="8aa3f-136">a)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-136">a.</span></span> <span data-ttu-id="8aa3f-137">В **доменном имени SQL Server**укажите полное доменное имя сервера, на котором вы хотите создать новый следящий сервер SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="8aa3f-138">б)</span><span class="sxs-lookup"><span data-stu-id="8aa3f-138">b.</span></span> <span data-ttu-id="8aa3f-139">Для применения экземпляра по умолчанию щелкните **Экземпляр по умолчанию**; для задания другого экземпляра щелкните **Именованный экземпляр**, затем укажите экземпляр, который будет служить следящим сервером зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="8aa3f-140">в.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-140">c.</span></span> <span data-ttu-id="8aa3f-141">Если указанный экземпляр SQL Server находится в отношении отражения, установите флажок **этот экземпляр SQL находится в отношении зеркального отображения** , а затем в поле **номер зеркального порта**укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="8aa3f-142">Для сохранения конфигурации нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="8aa3f-143">Публикация обновленной топологии для добавления архивной базы данных к развертыванию</span><span class="sxs-lookup"><span data-stu-id="8aa3f-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="8aa3f-144">На компьютере, на котором установлен Skype для бизнеса Server или на котором установлены средства администрирования сервера Skype для бизнеса Server, войдите в систему с помощью учетной записи, которая является членом локальной группы пользователей (или учетной записи с эквивалентными правами пользователей).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8aa3f-145">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для публикации топологии, необходимой для добавления сервера в топологию. Вы должны использовать учетную запись, которая входит в группу **"Администраторы домена"** и группу **рткуниверсалсерверадминс** , и у нее есть разрешения полного доступа (чтение, запись и изменение) в общей папке, которую вы используете для хранения файлов в Skype для бизнеса Server (чтобы Topology Builder мог настроить требуемый список управления доступом на уровне пользователей (DACL) или Учетная запись с эквивалентными правами.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="8aa3f-146">Откройте топологию, созданную в предыдущем разделе, с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="8aa3f-147">В дереве консоли щелкните правой кнопкой мыши **Skype для бизнеса Server**и выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="8aa3f-148">На странице **Публикация топологии** нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="8aa3f-149">На странице **Создание баз данных** убедитесь в том, что база данных выбрана, затем нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8aa3f-150">Если у вас нет соответствующих разрешений на создание баз данных, можно отменить выбор базы данных, чтобы пользователь с нужными разрешениями создал базу данных.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="8aa3f-151">> с помощью построителя топологии можно установить только базы данных на выделенных серверах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="8aa3f-152">Базы данных на серверах SQL Server, выровненные с другими серверными компонентами, необходимо устанавливать с помощью локальной программы установки на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="8aa3f-153">На странице **Завершение мастера публикации** убедитесь, что топология была успешно опубликована, а затем щелкните **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8aa3f-154">После публикации топологии необходимо до начала архивации данных настроить параметры и политики архивации.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="8aa3f-155">Подробности можно найти в разделе [Настройка параметров архивации в Skype для бизнеса Server](configure-archiving-options.md) и [Настройка политик архивирования для Skype для бизнеса Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8aa3f-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

