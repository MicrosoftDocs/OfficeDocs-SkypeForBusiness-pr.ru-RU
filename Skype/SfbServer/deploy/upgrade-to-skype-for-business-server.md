---
title: Обновление до Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: Сводка. сведения о том, как перейти с Lync Server 2013 на Skype для бизнеса Server 2015. Загрузите бесплатную пробную версию Skype для бизнеса Server 2015 в центре оценки Майкрософт по адресу https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.
ms.openlocfilehash: c024cde12ce30f3d143bf5f3e34400cc49cb46b5
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791557"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="e429b-104">Upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e429b-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e429b-105">**Сводка:** Сведения о том, как перейти с Lync Server 2013 на Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e429b-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="e429b-106">Загрузите бесплатную пробную версию Skype для бизнеса Server 2015 в [центре оценки Майкрософт](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="e429b-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="e429b-107">Чтобы перейти с Lync Server 2013 на Skype для бизнеса Server 2015 с помощью построителя топологии Skype для бизнеса Server и новой функции обновления на месте, выполните действия, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="e429b-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="e429b-108">Если вы хотите перейти с Lync Server 2010 или Office Communications Server 2007 R2, ознакомьтесь со сведениями о том, [как выполнить обновление до Skype для бизнеса Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e429b-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e429b-109">Обновления на месте были выпущены в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e429b-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e429b-110">Поддерживается параллельное сосуществование. Дополнительные сведения можно найти [в разделе Переход на Skype для бизнеса Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) .</span><span class="sxs-lookup"><span data-stu-id="e429b-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="e429b-111">Переход с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e429b-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="e429b-112">Обновление Lync Server 2013 до Skype для бизнеса Server 2015 включает установку необходимого программного обеспечения, использование построителя топологии Skype для бизнеса Server для обновления баз данных в пуле и использование обновления на месте в Skype для бизнеса Server серверы, связанные с пулом.</span><span class="sxs-lookup"><span data-stu-id="e429b-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="e429b-113">В этом разделе приведена процедура обновления, состоящая из восьми шагов.</span><span class="sxs-lookup"><span data-stu-id="e429b-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="e429b-114">До начала работы</span><span class="sxs-lookup"><span data-stu-id="e429b-114">Before you begin</span></span>

- <span data-ttu-id="e429b-115">Просмотрите раздел [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="e429b-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="e429b-116">Ознакомьтесь с [требованиями к серверу в Skype для бизнеса Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e429b-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="e429b-117">[Установите необходимые требования для Skype для бизнеса Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="e429b-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="e429b-118">[Установите Skype для бизнеса Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="e429b-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="e429b-119">Шаг 1. Установка средств администрирования и загрузка топологии</span><span class="sxs-lookup"><span data-stu-id="e429b-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="e429b-120">Подключитесь к компьютеру в топологии, на которой не установлены Lync Окскоре или другие компоненты Lync.</span><span class="sxs-lookup"><span data-stu-id="e429b-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="e429b-121">На установочном носителе Skype для бизнеса Server 2015 запустите **файл Setup. exe** из **OCS_Volume \setup\amd64**.</span><span class="sxs-lookup"><span data-stu-id="e429b-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="e429b-122">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="e429b-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="e429b-123">Примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="e429b-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="e429b-124">В мастере развертывания нажмите **Установить средства администрирования** и выполните процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="e429b-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Снимок экрана мастера развертывания со ссылкой на вызываемую функцию "Установить средства администрирования".](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="e429b-126">На начальном экране Windows откройте построитель топологии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e429b-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="e429b-127">Выберите **Загрузить топологию из существующего развертывания** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e429b-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="e429b-128">Введите имя топологии и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e429b-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="e429b-129">Перейдите в папку, где сохранена топология, и создайте ее копию.</span><span class="sxs-lookup"><span data-stu-id="e429b-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="e429b-130">Шаг 2. Обновление и публикация топологии с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="e429b-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="e429b-131">Прежде чем начать процесс обновления, для пулов, которые планируется обновить, должны быть запущены все службы.</span><span class="sxs-lookup"><span data-stu-id="e429b-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="e429b-132">Это обеспечит репликацию изменений топологии в локальную базу данных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="e429b-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="e429b-133">Перед обновлением сохраните копию топологии.</span><span class="sxs-lookup"><span data-stu-id="e429b-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="e429b-134">После обновления вы не сможете понизить уровень топологии. > если ваши службы находятся на том же сервере, что и базы данных, например, служба сохраняемого чата находится на том же компьютере, что и база данных для работы с сохраняемым чат, пропустите этот шаг и перейдите к действию 4.</span><span class="sxs-lookup"><span data-stu-id="e429b-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="e429b-135">После остановки служб запустите на каждом сервере настройку обновления на месте для обновления локальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="e429b-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e429b-p108">Если топология имеет внутреннюю зеркальную базу данных, тогда **при публикации топологии** с помощью построителя топологий отобразятся и основная и зеркальная базы данных. Убедитесь, что все базы данных запущены на основном сервере, а при публикации топологии выберите только основную, а не зеркальную базу данных. В противном случае после публикации топологии отобразится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e429b-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="e429b-138">Выберите один из вариантов ниже, чтобы обновить и опубликовать новую топологию с помощью построителя топологии Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e429b-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="e429b-139">После выполнения указанных шагов и публикации обновленной топологии перейдите к шагу 3 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e429b-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="e429b-140">Вариант 1. Обновление изолированного интерфейсного пула и связанных с ним хранилищ архивных данных и данных наблюдения</span><span class="sxs-lookup"><span data-stu-id="e429b-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="e429b-141">Если для обновляемого пула задана зависимость от хранилищ архивных данных и данных наблюдения, при выполнении следующих шагов эти хранилища также обновляются.</span><span class="sxs-lookup"><span data-stu-id="e429b-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="e429b-142">В построителе топологии щелкните правой кнопкой мыши пул Lync Server 2013, выберите команду **Обновить до Skype для бизнеса Server 2015**и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="e429b-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="e429b-144">В построителе топологии щелкните**топология публикации** **действий** > или**опубликовать\*\*\*\*топологию** >  **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Снимок экрана меню действий с параметром топологии публикации в построителе топологий.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="e429b-146">В процессе публикации выберите установку базу данных в хранилищах архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="e429b-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="e429b-147">Вариант 2: Обновление пула переднего плана без обновления архивации и наблюдения за хранилищами</span><span class="sxs-lookup"><span data-stu-id="e429b-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="e429b-p110">При выполнении указанных ниже шагов для выбранного пула отключаются архивация и наблюдение. После обновления с пулом не будут связаны хранилища архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="e429b-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="e429b-150">В построителе топологии выберите пул Lync Server 2013, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="e429b-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="e429b-151">Удалите зависимость с сохранением и мониторингом хранилищ в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e429b-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="e429b-152">Перейдите к разделу**изменение свойств** **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="e429b-153">Снимите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="e429b-153">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана флажка архивации в диалоговом окне изменения свойств.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="e429b-155">Снимите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="e429b-155">Clear the **Monitoring** check box.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показан флажок наблюдения.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="e429b-157">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите команду **Обновить до Skype для бизнеса Server 2015**и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="e429b-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="e429b-159">В построителе топологии щелкните**топология публикации** **действий** > или**опубликовать\*\*\*\*топологию** >  **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="e429b-160">Вариант 3: Обновление пула переднего плана и его связь с новым приложением Skype для бизнеса Server 2015 архивирование и мониторинг хранилищ</span><span class="sxs-lookup"><span data-stu-id="e429b-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="e429b-161">При выполнении следующих шагов архивация и наблюдения останавливаются в прежних хранилищах и запускаются во вновь созданных хранилищах.</span><span class="sxs-lookup"><span data-stu-id="e429b-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="e429b-162">В построителе топологии выберите пул Lync Server 2013, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="e429b-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="e429b-163">Удалите зависимость с сохранением и мониторингом хранилищ в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e429b-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="e429b-164">Перейдите к разделу**изменение свойств** **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="e429b-165">Снимите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="e429b-165">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана флажка архивации в диалоговом окне изменения свойств.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="e429b-167">Снимите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="e429b-167">Clear the **Monitoring** check box.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показан флажок наблюдения.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="e429b-169">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите команду **Обновить до Skype для бизнеса Server 2015**и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="e429b-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="e429b-171">Создайте новое хранилище SQL для архивации.</span><span class="sxs-lookup"><span data-stu-id="e429b-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="e429b-172">Выберите команду**изменить параметры**пула и **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="e429b-173">Установите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="e429b-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="e429b-174">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e429b-174">Click **New**.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показана кнопка "Создать" в разделе "Архивация".](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="e429b-176">Создайте новое хранилище SQL для наблюдения.</span><span class="sxs-lookup"><span data-stu-id="e429b-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="e429b-177">Выберите команду**изменить параметры**пула и **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="e429b-178">Установите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="e429b-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="e429b-179">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e429b-179">Click **New**.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показана кнопка "Создать" в разделе наблюдения.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="e429b-181">В построителе топологии щелкните**топология публикации** **действий** > или**опубликовать\*\*\*\*топологию** >  **действия** > .</span><span class="sxs-lookup"><span data-stu-id="e429b-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="e429b-182">В процессе публикации выберите установку базы данных в новое хранилище архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="e429b-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="e429b-183">Шаг 3. Ожидание репликации</span><span class="sxs-lookup"><span data-stu-id="e429b-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="e429b-184">Дождитесь публикации обновленной топологии на всех серверах в данной среде путем репликации.</span><span class="sxs-lookup"><span data-stu-id="e429b-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="e429b-185">Шаг 4. Остановка всех служб в обновляемом пуле</span><span class="sxs-lookup"><span data-stu-id="e429b-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="e429b-186">На каждом сервере, обслуживающем пул, который вы собираетесь обновить, выполните в PowerShell следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e429b-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="e429b-187">Мы рекомендуем использовать Disable-Кскомпутер, так как вам может потребоваться перезагрузить сервер в процессе обновления на месте.</span><span class="sxs-lookup"><span data-stu-id="e429b-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="e429b-188">В случае применения команды Stop-CsWindowsService возможен автоматический запуск некоторых служб после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="e429b-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="e429b-189">Это может привести к сбою обновления на месте.</span><span class="sxs-lookup"><span data-stu-id="e429b-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="e429b-190">Шаг 5. Обновление интерфейсных пулов и серверов, не входящих в этот пул</span><span class="sxs-lookup"><span data-stu-id="e429b-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="e429b-191">Перед обновлением установите все новые необходимые компоненты, необходимые для использования Skype для бизнеса Server 2015, который содержит: > не менее 32 ГБ свободного места перед обновлением.</span><span class="sxs-lookup"><span data-stu-id="e429b-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="e429b-192">Кроме того, убедитесь, что диск является фиксированным локальным диском, а не подключен к USB или FireWire. приложение #a0 форматируется с помощью файловой системы NTFS и не содержит файла подкачки. > PowerShell версии 6.2.9200.0 или более поздней. > установленное обновление для Lync Server 2013. > SQL Server 2012 с пакетом обновления 1 (SP1). > (устанавливается автоматически при использовании Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2- [KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="e429b-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="e429b-193">Используйте обновление на месте на каждом сервере для обновления пула переднего плана, пограничного пула, сервера-посредника и пула сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="e429b-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="e429b-194">На каждом сервере запустите **файл Setup. exe** с **OCS_Volume \setup\amd64** на установочном носителе Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e429b-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="e429b-195">Принимайте условия лицензионного соглашения и следуйте инструкциям по обновлению на месте.</span><span class="sxs-lookup"><span data-stu-id="e429b-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="e429b-196">Повторите эти действия для каждого сервера в пуле переднего плана и на каждом сервере пула, не являющегося интерфейсом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e429b-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e429b-197">В процессе обновления на месте может появиться запрос на перезагрузку сервера.</span><span class="sxs-lookup"><span data-stu-id="e429b-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="e429b-198">Подтвердите перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="e429b-198">That's ok.</span></span> <span data-ttu-id="e429b-199">После перезагрузки обновление на месте продолжится с того места, с которого она была выключена.</span><span class="sxs-lookup"><span data-stu-id="e429b-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="e429b-200">При успешном завершении обновления на месте отображается следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="e429b-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Снимок экрана, на котором показано успешное выполнение обновления на месте.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="e429b-202">Шаг 6. Повторный запуск служб на всех обновленных серверах</span><span class="sxs-lookup"><span data-stu-id="e429b-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="e429b-203">Перед перезапуском служб убедитесь, что%Програмдата%\виндовсфабрик не существует на всех серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e429b-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="e429b-204">If it exists, delete it before starting the services.</span><span class="sxs-lookup"><span data-stu-id="e429b-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="e429b-205">После обновления всех серверов в пуле переднего плана перезапустите службы, используя следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e429b-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="e429b-p115">Если к моменту запуска обновления на месте уже была потребность в обязательной перезагрузке системы, процесс обновления на месте не будет запрашивать выполнение перезагрузки в конце установки. Поэтому при попытке запустить службы с помощью командлета Start-CSPool первый сервер переднего плана получит ряд исключительных ситуаций. Для устранения этих ошибок перезагрузите все серверы в пуле и снова запустите командлет.</span><span class="sxs-lookup"><span data-stu-id="e429b-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="e429b-209">Снова запустите службы на серверах, не входящих в интерфейсный пул, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e429b-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="e429b-210">После нажатия кнопки **ОК** на странице обновления на месте отображается следующее напоминание о необходимости завершить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="e429b-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Снимок экрана, на котором показаны действия после успешного выполнения обновления на месте.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="e429b-212">Шаг 7: Проверка работы функции Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e429b-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="e429b-213">Чтобы убедиться в том, что обновление для обновленного пула прошло успешно, проверьте, правильно ли работают функции Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e429b-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="e429b-214">Шаг 8. Обновление дополнительных пулов</span><span class="sxs-lookup"><span data-stu-id="e429b-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="e429b-215">Повторите приведенные в этом разделе шаги для обновления всех дополнительных пулов в данной среде.</span><span class="sxs-lookup"><span data-stu-id="e429b-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="e429b-216">Устранение неполадок при обновлении на месте</span><span class="sxs-lookup"><span data-stu-id="e429b-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="e429b-217">В случае сбоя обновления на месте может отображаться сообщение, подобное показанному на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="e429b-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Снимок экрана, на котором показан сбой обновления на месте из-за отсутствия установки требуемого накопительного пакета обновления.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="e429b-219">Просмотрите полное сообщение внизу страницы, содержащее указания по устранению неполадки.</span><span class="sxs-lookup"><span data-stu-id="e429b-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="e429b-220">Для просмотра подробных сведений выберите **Просмотреть журналы**.</span><span class="sxs-lookup"><span data-stu-id="e429b-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="e429b-221">Если при обновлении на месте происходит сбой **проверки готовности к обновлению** или **установки недостающих необходимых компонентов**, убедитесь, что на сервере установлены все последние обновления Windows Server, Lync Server и SQL Server, а также все необходимое программное обеспечение и роли.</span><span class="sxs-lookup"><span data-stu-id="e429b-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="e429b-222">Чтобы получить список необходимых данных, ознакомьтесь со сведениями [о серверных требованиях для Skype для бизнеса server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) и [установите необходимые условия для Skype для бизнеса Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e429b-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e429b-223">См. также</span><span class="sxs-lookup"><span data-stu-id="e429b-223">See also</span></span>

[<span data-ttu-id="e429b-224">Планирование обновления до Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e429b-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="e429b-225">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e429b-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="e429b-226">Установка обязательных компонентов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e429b-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="e429b-227">Установка Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e429b-227">Install Skype for Business Server 2015</span></span>](install/install.md)
