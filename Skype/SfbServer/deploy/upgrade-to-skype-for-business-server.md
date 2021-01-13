---
title: Обновление до Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Сводка. Узнайте, как обновить Lync Server 2013 до Skype для бизнеса Server 2015. Скачайте бесплатную пробную версия Skype для бизнеса Server 2015 в Центре оценки Майкрософт по https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ссылке:'
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820429"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="d67ec-104">Обновление до Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d67ec-105">**Сводка:** Узнайте, как обновить Lync Server 2013 до Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d67ec-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="d67ec-106">Скачайте бесплатную пробную версия Skype для бизнеса Server 2015 из [Центра оценки Майкрософт.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="d67ec-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="d67ec-107">Используйте процедуры, показанные в этом документе, для обновления Lync Server 2013 до Skype для бизнеса Server 2015 с помощью построщика топологий Skype для бизнеса Server и новой функции In-Place обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="d67ec-108">Если вы хотите обновить Lync Server 2010 или Office Communications Server 2007 R2, см. план обновления до Skype для бизнеса [Server 2015.](../plan-your-deployment/upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d67ec-109">Обновления на месте были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d67ec-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d67ec-110">Поддерживается сосуществование, см. дополнительные сведения о миграции в Skype для бизнеса [Server 2019.](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="d67ec-111">Обновление с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67ec-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="d67ec-112">Обновление Lync Server 2013 до Skype для бизнеса Server 2015 включает установку необходимого программного обеспечения, использование построитель топологий Skype для бизнеса Server для обновления баз данных в пуле и обновление Skype для бизнеса Server In-Place на каждом сервере, связанном с пулом.</span><span class="sxs-lookup"><span data-stu-id="d67ec-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="d67ec-113">Чтобы завершить обновление, выполните восемь действий, которые необходимо выполнить в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d67ec-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="d67ec-114">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="d67ec-114">Before you begin</span></span>

- <span data-ttu-id="d67ec-115">Просмотрите [план обновления до Skype для бизнеса Server 2015.](../plan-your-deployment/upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="d67ec-116">Просмотрите [требования к серверу для Skype для бизнеса Server 2015.](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="d67ec-117">[Установка необходимых условий для Skype для бизнеса Server 2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="d67ec-118">[Установка Skype для бизнеса Server 2015.](install/install.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="d67ec-119">Шаг 1. Установка средств администратора и загрузка топологии</span><span class="sxs-lookup"><span data-stu-id="d67ec-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="d67ec-120">Подключите компьютер в топологии, на который не установлен Lync OCSCore или другие компоненты Lync.</span><span class="sxs-lookup"><span data-stu-id="d67ec-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="d67ec-121">На установок Skype для бизнеса Server 2015 запуститеSetup.exe **из** **OCS_Volume\Setup\AMD64.**</span><span class="sxs-lookup"><span data-stu-id="d67ec-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="d67ec-122">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="d67ec-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="d67ec-123">Принятие условий лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="d67ec-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="d67ec-124">В мастере развертывания щелкните **"Установить средства** администратора" и выполните действия по установке.</span><span class="sxs-lookup"><span data-stu-id="d67ec-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Снимок экрана: мастер развертывания со ссылкой на вызванную ссылку на средства установки администратора.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="d67ec-126">На стартовом экране Windows откройте построитель топологий Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d67ec-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="d67ec-127">Щелкните **"Загрузить топологию" из существующего развертывания** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="d67ec-128">Введите имя топологии и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="d67ec-129">Перейдите в расположение, в котором сохранена топология, и сделайте копию топологии.</span><span class="sxs-lookup"><span data-stu-id="d67ec-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="d67ec-130">Шаг 2. Обновление и публикация топологии с помощью построитель топологий</span><span class="sxs-lookup"><span data-stu-id="d67ec-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="d67ec-131">Перед началом процесса обновления все службы должны быть запущены для пулов, которые планируется обновить.</span><span class="sxs-lookup"><span data-stu-id="d67ec-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="d67ec-132">Это необходимо, чтобы изменения топологии реплицированы в локализованную базу данных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="d67ec-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="d67ec-133">Перед обновлением сохраните копию файла топологии.</span><span class="sxs-lookup"><span data-stu-id="d67ec-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="d67ec-134">После обновления вы не сможете понизить топологию.> Если службы находятся на тех же серверах, что и базы данных, например служба Persistent Chat находится на том же сервере, что и база данных Persistent Chat, пропустите этот шаг и перейдите к шагу 4.</span><span class="sxs-lookup"><span data-stu-id="d67ec-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="d67ec-135">После остановки служб запустите In-Place обновления на каждом сервере, чтобы обновить локальные базы данных.</span><span class="sxs-lookup"><span data-stu-id="d67ec-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d67ec-136">Если в топологии имеется зеркальное отражение базы данных, то при публикации топологии с помощью построитель топологий будут отражаться как основная, так и зеркальная базы данных. </span><span class="sxs-lookup"><span data-stu-id="d67ec-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="d67ec-137">Убедитесь, что все базы данных запущены на основном и при публикации топологии выбирается только основной, а не зеркальный. В противном случае после публикации топологии вы увидите предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d67ec-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="d67ec-138">Выберите один из вариантов обновления и публикации новой топологии с помощью построщика топологий Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d67ec-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="d67ec-139">После выполнения действий и публикации обновленной топологии переходить к шагу 3 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d67ec-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="d67ec-140">Вариант 1. Обновление изолированного пула переднего класса и связанных хранилищ архива и мониторинга</span><span class="sxs-lookup"><span data-stu-id="d67ec-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="d67ec-141">Если обновляемый пул имеет зависимость от архивации и хранения данных мониторинга, при использовании следующих действий также будет обновлено хранилище архивации и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d67ec-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="d67ec-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span><span class="sxs-lookup"><span data-stu-id="d67ec-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана: меню правой кнопкой мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="d67ec-144">В построитель топологий **щелкните "Опубликовать**  >  **топологию действий"** или **"Опубликовать**  >  **топологию**  >  **действий".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Снимок экрана меню действий с параметром "Опубликовать топологию" в построителье топологий.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="d67ec-146">Во время публикации выберите установку базы данных в хранилище архива и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d67ec-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="d67ec-147">Вариант 2. Обновление пула переднего уровня без обновления хранилищ архива и мониторинга</span><span class="sxs-lookup"><span data-stu-id="d67ec-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="d67ec-148">При использовании следующих действий архив и мониторинг для выбранного пула отключаются.</span><span class="sxs-lookup"><span data-stu-id="d67ec-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="d67ec-149">После обновления в пуле не будет хранилищ архива и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d67ec-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="d67ec-150">В построитель топологий выберите пул Lync Server 2013, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="d67ec-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="d67ec-151">Удалите зависимость от хранилищ архивации и мониторинга Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d67ec-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="d67ec-152">Перейдите **к свойству**  >  **"Изменение действий".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="d67ec-153">**Сойти с этого окне.**</span><span class="sxs-lookup"><span data-stu-id="d67ec-153">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана: "Архивировать" в диалоговом окне "Изменение свойств".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="d67ec-155">Счистим **этот контрольный** окне.</span><span class="sxs-lookup"><span data-stu-id="d67ec-155">Clear the **Monitoring** check box.</span></span>
    
     ![Снимок экрана диалоговое окно "Изменение свойств", в нем показан контрольный ящик мониторинга.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="d67ec-157">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите "Обновление до Skype для бизнеса **Server 2015"** и выполните действия.</span><span class="sxs-lookup"><span data-stu-id="d67ec-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана: меню правой кнопкой мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="d67ec-159">В построитель топологий **щелкните "Опубликовать**  >  **топологию действий"** или **"Опубликовать**  >  **топологию**  >  **действий".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="d67ec-160">Вариант 3. Обновление пула переднего сервера и связывание его с новыми хранилищами архива и мониторинга Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="d67ec-161">При использовании следующих действий архивная архива и мониторинга остановится в предыдущем хранилище и запустится в новом хранилище, созданном вами.</span><span class="sxs-lookup"><span data-stu-id="d67ec-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="d67ec-162">В построитель топологий выберите пул Lync Server 2013, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="d67ec-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="d67ec-163">Удалите зависимость от хранилищ архивации и мониторинга Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d67ec-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="d67ec-164">Перейдите **к свойству**  >  **"Изменение действий".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="d67ec-165">**Сойти с этого окне.**</span><span class="sxs-lookup"><span data-stu-id="d67ec-165">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана: "Архивировать" в диалоговом окне "Изменение свойств".](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="d67ec-167">Счистим **этот контрольный** окне.</span><span class="sxs-lookup"><span data-stu-id="d67ec-167">Clear the **Monitoring** check box.</span></span>
    
     ![Снимок экрана диалоговое окно "Изменение свойств", в нем показан контрольный ящик мониторинга.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="d67ec-169">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите "Обновление до Skype для бизнеса **Server 2015"** и выполните действия.</span><span class="sxs-lookup"><span data-stu-id="d67ec-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана: меню правой кнопкой мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="d67ec-171">Создайте новое хранилище SQL архива.</span><span class="sxs-lookup"><span data-stu-id="d67ec-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="d67ec-172">Выберите свойства пула **и**  >  **изменения действий.**</span><span class="sxs-lookup"><span data-stu-id="d67ec-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="d67ec-173">Select the **Archiving** check box.</span><span class="sxs-lookup"><span data-stu-id="d67ec-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="d67ec-174">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d67ec-174">Click **New**.</span></span>
    
     ![Снимок экрана диалоговое окно "Изменение свойств" с кнопкой "Новая" в разделе "Архив".](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="d67ec-176">Создайте новое хранилище SQL мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d67ec-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="d67ec-177">Выберите свойства пула **и**  >  **изменения действий.**</span><span class="sxs-lookup"><span data-stu-id="d67ec-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="d67ec-178">Select the **Monitoring** check box.</span><span class="sxs-lookup"><span data-stu-id="d67ec-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="d67ec-179">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d67ec-179">Click **New**.</span></span>
    
     ![Снимок экрана диалоговое окно "Изменение свойств" с кнопкой "Новая" в разделе "Мониторинг".](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="d67ec-181">В построитель топологий **щелкните "Опубликовать**  >  **топологию действий"** или **"Опубликовать**  >  **топологию**  >  **действий".**</span><span class="sxs-lookup"><span data-stu-id="d67ec-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="d67ec-182">Во время публикации выберите установку базы данных в новом хранилище архивов и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d67ec-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="d67ec-183">Шаг 3. Дождись репликации</span><span class="sxs-lookup"><span data-stu-id="d67ec-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="d67ec-184">Дайте репликации некоторое время для публикации обновленной топологии на всех серверах в среде.</span><span class="sxs-lookup"><span data-stu-id="d67ec-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="d67ec-185">Шаг 4. Остановка обновления всех служб в пуле</span><span class="sxs-lookup"><span data-stu-id="d67ec-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="d67ec-186">На каждом сервере, обслуживаемом обновляемом пулом, в PowerShell запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d67ec-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="d67ec-187">Рекомендуется использовать Disable-CsComputer, так как может потребоваться перезагрузка сервера во время In-Place обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="d67ec-188">Если вы используете Stop-CsWindowsService, некоторые службы могут автоматически перезапуститься после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="d67ec-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="d67ec-189">Это может привести к In-Place обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="d67ec-190">Шаг 5. Обновление пулов переднего и других серверов пулов</span><span class="sxs-lookup"><span data-stu-id="d67ec-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="d67ec-191">Перед обновлением установите все необходимые условия для Skype для бизнеса Server 2015, в том числе: > не менее 32 ГБ свободного места перед попыткой обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="d67ec-192">Кроме того, убедитесь, что диск является фиксированным локальным диском, не подключен usb или Firewire, форматирован с помощью файловой системы NTFS, не сжимается и не содержит файла страницы.> PowerShell версии 6.2. 9200.0 или более поздней версии.> Установлено последнее накопительное обновление Lync Server 2013.> SQL Server 2012 с накопительным обновлением 1 (SP1 >). Update):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="d67ec-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="d67ec-193">Используйте In-Place обновления на каждом сервере для обновления пула переднего сервера, пула, сервера-посредника и пула сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="d67ec-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="d67ec-194">На каждом сервере запустите **Setup.exe** из **OCS_Volume\Setup\amd64** на установок skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d67ec-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="d67ec-195">Примите лицензионный договор и следуйте In-Place обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="d67ec-196">Повторите эти действия для каждого сервера в пуле переднего сервера и на каждом сервере пула вне переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="d67ec-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d67ec-197">Может возникнуть запрос на перезагрузку сервера во время In-Place обновления.</span><span class="sxs-lookup"><span data-stu-id="d67ec-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="d67ec-198">Порядок.</span><span class="sxs-lookup"><span data-stu-id="d67ec-198">That's ok.</span></span> <span data-ttu-id="d67ec-199">После перезагрузки обновление In-Place продолжится с того места, где оно было отключено.</span><span class="sxs-lookup"><span data-stu-id="d67ec-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="d67ec-200">После успешного In-Place обновления вы увидите следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="d67ec-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Снимок экрана, на который показано успешное обновление на месте.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="d67ec-202">Шаг 6. Перезапуск служб на всех обновленных серверах</span><span class="sxs-lookup"><span data-stu-id="d67ec-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="d67ec-203">Перед перезапуском служб убедитесь, что %ProgramData%\WindowsFabric не существует на всех серверах переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="d67ec-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="d67ec-204">Если он существует, удалите его перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="d67ec-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="d67ec-205">После обновления всех серверов в пуле переднего сервера перезапустите службы с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d67ec-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="d67ec-206">Если перед запуском In-Place обновления уже требуется отложенная перезагрузка системы, In-Place обновление не попросит вас перезагружаться в конце установки.</span><span class="sxs-lookup"><span data-stu-id="d67ec-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="d67ec-207">Это приведет к тому, что при попытке запустить службы с помощью Start-CSPool на первом сервере переднего Start-CSPool будут выброшены некоторые исключения сборки.</span><span class="sxs-lookup"><span data-stu-id="d67ec-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="d67ec-208">Чтобы устранить эти ошибки, перезагружаем все серверы в пуле и снова запустите его.</span><span class="sxs-lookup"><span data-stu-id="d67ec-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="d67ec-209">Перезапустите службы на серверах, не влияли на серверы пула переднего сервера, выдав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d67ec-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="d67ec-210">После нажатия **кнопки "ОК"** на странице In-Place обновления вы увидите следующее напоминание для завершения этого шага.</span><span class="sxs-lookup"><span data-stu-id="d67ec-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Снимок экрана, на который показаны дальнейшие действия после успешного завершения обновления на месте.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="d67ec-212">Шаг 7. Проверка работы функций Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d67ec-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="d67ec-213">Чтобы убедиться в успешном обновлении пула, протестировать Skype для бизнеса, чтобы убедиться, что функциональность работает ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="d67ec-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="d67ec-214">Шаг 8. Обновление дополнительных пулов</span><span class="sxs-lookup"><span data-stu-id="d67ec-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="d67ec-215">Повторите действия, которые необходимо предпринять в этом разделе, чтобы обновить все дополнительные пулы, которые имеются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d67ec-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="d67ec-216">Устранение неполадок с обновлением In-Place обновления</span><span class="sxs-lookup"><span data-stu-id="d67ec-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="d67ec-217">В случае In-Place обновления может отобраться сообщение, аналогичное следующему.</span><span class="sxs-lookup"><span data-stu-id="d67ec-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Снимок экрана с ошибкой обновления на месте из-за того, что не установлено обязательное накопительное обновление.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="d67ec-219">Просмотрите полное сообщение в нижней части страницы, чтобы устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="d67ec-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="d67ec-220">Щелкните **"Просмотреть журналы",** чтобы получить дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="d67ec-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="d67ec-221">Если обновление In-Place не удается  проверить готовность к обновлению или установить отсутствующие необходимые точки, убедитесь, что на сервере установлены все последние обновления Windows Server, Lync Server и SQL Server, а также установлено все необходимое программное обеспечение и роли.</span><span class="sxs-lookup"><span data-stu-id="d67ec-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="d67ec-222">Список необходимых требований см. в требованиях к серверу для Skype для бизнеса [Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) и установке необходимых условий для Skype для бизнеса [Server 2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="d67ec-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d67ec-223">См. также</span><span class="sxs-lookup"><span data-stu-id="d67ec-223">See also</span></span>

[<span data-ttu-id="d67ec-224">Планирование обновления до Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="d67ec-225">Требования к серверу для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="d67ec-226">Установка необходимых условий для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="d67ec-227">Установка Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d67ec-227">Install Skype for Business Server 2015</span></span>](install/install.md)
