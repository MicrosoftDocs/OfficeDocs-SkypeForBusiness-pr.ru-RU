---
title: Обновление до Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Сводка: Узнайте, как обновление с Lync Server 2013 Скайп для Business Server 2015. Загрузить бесплатную пробную версию программы Скайп для 2015 Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 0c869527fe9e07187149b63ed3c360b0290c8a87
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="feaa9-104">Обновление до Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="feaa9-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="feaa9-105">**Сводка:** Узнайте, как обновление с Lync Server 2013 Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="feaa9-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="feaa9-106">Загрузите бесплатную пробную версию программы Скайп для Business Server 2015 [Центр оценки Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="feaa9-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="feaa9-107">Используйте процедуры, описанные в этом документе обновления Lync Server 2013 до Скайп для Business Server 2015 с помощью Скайп for Business Server Topology Builder и новая функция обновление на месте.</span><span class="sxs-lookup"><span data-stu-id="feaa9-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="feaa9-108">Если требуется обновление с Lync Server 2010 или Office Communications Server 2007 R2, ознакомьтесь со [Планирование обновления до Скайп для Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="feaa9-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="feaa9-109">Обновление с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feaa9-109">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="feaa9-110">Обновление Lync Server 2013 до Скайп для Business Server 2015 включает в себя Установка необходимого программного обеспечения, с помощью Скайп для Business Server Topology Builder для обновления баз данных в пуле и использование Скайп для обновления на месте Business Server на каждом серверы, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="feaa9-110">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="feaa9-111">В этом разделе приведена процедура обновления, состоящая из восьми шагов.</span><span class="sxs-lookup"><span data-stu-id="feaa9-111">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="feaa9-112">До начала работы</span><span class="sxs-lookup"><span data-stu-id="feaa9-112">Before you begin</span></span>

- <span data-ttu-id="feaa9-113">Просмотрите [Планирование обновления до Скайп для Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="feaa9-113">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="feaa9-114">Обзор [требований для сервера для Скайп для Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feaa9-114">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="feaa9-115">[Установка необходимых компонентов для Скайп для Business Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="feaa9-115">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="feaa9-116">[Установка Скайп для Business Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="feaa9-116">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="feaa9-117">Шаг 1. Установка средств администрирования и загрузка топологии</span><span class="sxs-lookup"><span data-stu-id="feaa9-117">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="feaa9-118">Подключитесь к компьютеру в топологии, для которого не Lync OCSCore или другие компоненты Lync, установленные.</span><span class="sxs-lookup"><span data-stu-id="feaa9-118">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="feaa9-119">Запустите **Setup.exe** из **OCS_Volume\Setup\AMD64**Скайп для Business Server 2015 установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="feaa9-119">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="feaa9-120">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-120">Click **Install**.</span></span> 
    
4. <span data-ttu-id="feaa9-121">Примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="feaa9-121">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="feaa9-122">В мастере развертывания нажмите **Установить средства администрирования** и выполните процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="feaa9-122">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Снимок экрана мастера развертывания со ссылкой на вызываемую функцию "Установить средства администрирования".](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="feaa9-124">На экране запуска Windows откройте Скайп для Business Server Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="feaa9-124">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="feaa9-125">Выберите **Загрузить топологию из существующего развертывания** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-125">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="feaa9-126">Введите имя топологии и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-126">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="feaa9-127">Перейдите в папку, где сохранена топология, и создайте ее копию.</span><span class="sxs-lookup"><span data-stu-id="feaa9-127">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="feaa9-128">Шаг 2. Обновление и публикация топологии с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="feaa9-128">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="feaa9-129">Перед началом процесса обновления необходимо запустить все службы для пулов, которые планируется обновить.</span><span class="sxs-lookup"><span data-stu-id="feaa9-129">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="feaa9-130">Это обеспечит репликацию изменений топологии в локальную базу данных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="feaa9-130">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="feaa9-131">Перед обновлением сохраните копию топологии.</span><span class="sxs-lookup"><span data-stu-id="feaa9-131">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="feaa9-132">После обновления, вы не сможете для возврата к предыдущей версии топология. > Если вашей службы на тех же серверах как баз данных, как служба — на том же сервере базы данных сохраняемого чата Persistent Chat пропустить этот этап и перейдите к шагу 4.</span><span class="sxs-lookup"><span data-stu-id="feaa9-132">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="feaa9-133">После остановки служб запустите на каждом сервере настройку обновления на месте для обновления локальных баз данных.</span><span class="sxs-lookup"><span data-stu-id="feaa9-133">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="feaa9-p107">Если топология имеет внутреннюю зеркальную базу данных, тогда **при публикации топологии** с помощью построителя топологий отобразятся и основная и зеркальная базы данных. Убедитесь, что все базы данных запущены на основном сервере, а при публикации топологии выберите только основную, а не зеркальную базу данных. В противном случае после публикации топологии отобразится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="feaa9-p107">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="feaa9-136">Выберите один из параметров ниже, чтобы обновить и публикации новой топологии с помощью Скайп for Business Server 2015 Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="feaa9-136">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="feaa9-137">После выполнения указанных шагов и публикации обновленной топологии перейдите к шагу 3 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="feaa9-137">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="feaa9-138">Вариант 1. Обновление изолированного интерфейсного пула и связанных с ним хранилищ архивных данных и данных наблюдения</span><span class="sxs-lookup"><span data-stu-id="feaa9-138">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="feaa9-139">Если для обновляемого пула задана зависимость от хранилищ архивных данных и данных наблюдения, при выполнении следующих шагов эти хранилища также обновляются.</span><span class="sxs-lookup"><span data-stu-id="feaa9-139">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="feaa9-140">В построителе топологий щелкните правой кнопкой мыши пул Lync Server 2013, установите **обновление Скайп для Business Server 2015**и выполните действия, описанные.</span><span class="sxs-lookup"><span data-stu-id="feaa9-140">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="feaa9-142">В построителе топологий выберите **Действие** > **опубликовать топологию** или **Действие** > **топологии** > **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-142">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Снимок экрана меню действий с параметром топологии публикации в построителе топологий.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="feaa9-144">В процессе публикации выберите установку базу данных в хранилищах архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="feaa9-144">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="feaa9-145">Вариант 2: Обновление интерфейсный пул без обновления архивирование и мониторинг хранилищ</span><span class="sxs-lookup"><span data-stu-id="feaa9-145">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="feaa9-p109">При выполнении указанных ниже шагов для выбранного пула отключаются архивация и наблюдение. После обновления с пулом не будут связаны хранилища архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="feaa9-p109">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="feaa9-148">В построителе топологий выберите пул Lync Server 2013, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="feaa9-148">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="feaa9-149">Удалите зависимость в Lync Server 2013 архивирование и мониторинг хранилища.</span><span class="sxs-lookup"><span data-stu-id="feaa9-149">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="feaa9-150">Последовательно выберите пункты **Действие** > **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-150">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="feaa9-151">Снимите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-151">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана флажка архивации в диалоговом окне изменения свойств.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="feaa9-153">Снимите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-153">Clear the **Monitoring** check box.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показан флажок наблюдения.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="feaa9-155">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите **обновление Скайп для Business Server 2015**и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="feaa9-155">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="feaa9-157">В построителе топологий выберите **Действие** > **опубликовать топологию** или **Действие** > **топологии** > **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-157">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="feaa9-158">Вариант 3: Обновления интерфейсного пула и связанные с новой Скайп для архивации 2015 Business Server и мониторинг хранилищ</span><span class="sxs-lookup"><span data-stu-id="feaa9-158">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="feaa9-159">При выполнении следующих шагов архивация и наблюдения останавливаются в прежних хранилищах и запускаются во вновь созданных хранилищах.</span><span class="sxs-lookup"><span data-stu-id="feaa9-159">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="feaa9-160">В построителе топологий выберите пул Lync Server 2013, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="feaa9-160">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="feaa9-161">Удалите зависимость в Lync Server 2013 архивирование и мониторинг хранилища.</span><span class="sxs-lookup"><span data-stu-id="feaa9-161">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="feaa9-162">Последовательно выберите пункты **Действие** > **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-162">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="feaa9-163">Снимите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-163">Clear the **Archiving** check box.</span></span>
    
     ![Снимок экрана флажка архивации в диалоговом окне изменения свойств.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="feaa9-165">Снимите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-165">Clear the **Monitoring** check box.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показан флажок наблюдения.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="feaa9-167">Щелкните правой кнопкой мыши пул Lync Server 2013, выберите **обновление Скайп для Business Server 2015**и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="feaa9-167">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Снимок экрана меню правой копки мыши с параметром обновления для Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="feaa9-169">Создайте новое хранилище SQL для архивации.</span><span class="sxs-lookup"><span data-stu-id="feaa9-169">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="feaa9-170">Выберите пул, а также **Действие** > **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-170">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="feaa9-171">Установите флажок **Архивация**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-171">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="feaa9-172">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-172">Click **New**.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показана кнопка "Создать" в разделе "Архивация".](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="feaa9-174">Создайте новое хранилище SQL для наблюдения.</span><span class="sxs-lookup"><span data-stu-id="feaa9-174">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="feaa9-175">Выберите пул, а также **Действие** > **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-175">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="feaa9-176">Установите флажок **Наблюдение**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-176">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="feaa9-177">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-177">Click **New**.</span></span>
    
     ![Значок для диалогового окна изменения свойств, на котором показана кнопка "Создать" в разделе наблюдения.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="feaa9-179">В построителе топологий выберите **Действие** > **опубликовать топологию** или **Действие** > **топологии** > **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-179">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="feaa9-180">В процессе публикации выберите установку базы данных в новое хранилище архивных данных и данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="feaa9-180">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="feaa9-181">Шаг 3. Ожидание репликации</span><span class="sxs-lookup"><span data-stu-id="feaa9-181">Step 3: Wait for replication</span></span>

<span data-ttu-id="feaa9-182">Дождитесь публикации обновленной топологии на всех серверах в данной среде путем репликации.</span><span class="sxs-lookup"><span data-stu-id="feaa9-182">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="feaa9-183">Шаг 4. Остановка всех служб в обновляемом пуле</span><span class="sxs-lookup"><span data-stu-id="feaa9-183">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="feaa9-184">На каждом сервере, который обслуживает пула, в котором нужно обновить, выполните следующий командлет в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="feaa9-184">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="feaa9-185">Рекомендуется использовать Disable-CsComputer, так как может потребоваться перезагрузка сервера во время процесса обновления на месте.</span><span class="sxs-lookup"><span data-stu-id="feaa9-185">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="feaa9-186">В случае применения команды Stop-CsWindowsService возможен автоматический запуск некоторых служб после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="feaa9-186">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="feaa9-187">Это может привести к сбою обновления на месте.</span><span class="sxs-lookup"><span data-stu-id="feaa9-187">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="feaa9-188">Шаг 5. Обновление интерфейсных пулов и серверов, не входящих в этот пул</span><span class="sxs-lookup"><span data-stu-id="feaa9-188">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="feaa9-189">До обновления установите все новые компоненты, необходимые для Скайп для Business Server 2015 которые включают: > по крайней мере 32 ГБ свободного места на диске перед обновлением.</span><span class="sxs-lookup"><span data-stu-id="feaa9-189">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="feaa9-190">Кроме того, убедитесь в том, что диск — это локальном жестком диске, не соединена с USB и Firewire, отформатированные с файловой системой NTFS, не сжимается и не содержит файла страницы. > PowerShell версии 6.2.9200.0 или более поздняя версия. > последние Lync Server 2013 Накопительное обновление. > SQL Server 2012 SP1. > следующие КБ установленные (установлены автоматически, если с помощью центра обновления Майкрософт): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="feaa9-190">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="feaa9-191">Обновление на месте на каждом сервере для обновления используйте пула переднего плана, пограничного пула, сервер-посредник и пула Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="feaa9-191">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="feaa9-192">На каждом сервере запустите **Setup.exe** из **OCS_Volume\Setup\amd64** на Скайп для Business Server 2015 установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="feaa9-192">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="feaa9-193">Примите условия лицензионного соглашения и следуйте инструкциям для обновления на месте.</span><span class="sxs-lookup"><span data-stu-id="feaa9-193">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="feaa9-194">Повторите эти шаги для каждого сервера в разделе пул переднего плана и на каждом сервере, не являющиеся переднего плана пула.</span><span class="sxs-lookup"><span data-stu-id="feaa9-194">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="feaa9-195">В процессе обновления на месте может появиться запрос на перезагрузку сервера.</span><span class="sxs-lookup"><span data-stu-id="feaa9-195">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="feaa9-196">Подтвердите перезагрузку.</span><span class="sxs-lookup"><span data-stu-id="feaa9-196">That's ok.</span></span> <span data-ttu-id="feaa9-197">После перезагрузки компьютера, от места, где будет обновление на месте.</span><span class="sxs-lookup"><span data-stu-id="feaa9-197">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="feaa9-198">При успешном завершении обновления на месте отображается следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="feaa9-198">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Снимок экрана, на котором показано успешное выполнение обновления на месте.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="feaa9-200">Шаг 6. Повторный запуск служб на всех обновленных серверах</span><span class="sxs-lookup"><span data-stu-id="feaa9-200">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="feaa9-201">Перед перезапуском службы, чтобы убедиться, что %ProgramData%\WindowsFabric не существует на всех серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="feaa9-201">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="feaa9-202">Если он существует, удалите его перед запуском служб.</span><span class="sxs-lookup"><span data-stu-id="feaa9-202">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="feaa9-203">После обновления всех серверов в пуле переднего плана, перезапустите службы с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="feaa9-203">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="feaa9-p114">Если к моменту запуска обновления на месте уже была потребность в обязательной перезагрузке системы, процесс обновления на месте не будет запрашивать выполнение перезагрузки в конце установки. Поэтому при попытке запустить службы с помощью командлета Start-CSPool первый сервер переднего плана получит ряд исключительных ситуаций. Для устранения этих ошибок перезагрузите все серверы в пуле и снова запустите командлет.</span><span class="sxs-lookup"><span data-stu-id="feaa9-p114">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="feaa9-207">Снова запустите службы на серверах, не входящих в интерфейсный пул, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="feaa9-207">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="feaa9-208">После нажатия кнопки **ОК** на странице обновления на месте отображается следующее напоминание о необходимости завершить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="feaa9-208">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Снимок экрана, на котором показаны действия после успешного выполнения обновления на месте.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="feaa9-210">Шаг 7: Проверка Скайп для бизнеса функциональные возможности works</span><span class="sxs-lookup"><span data-stu-id="feaa9-210">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="feaa9-211">Чтобы убедиться в том, что обновление прошло успешно, для пула, в котором было выполнено обновление, тестирования Скайп для бизнеса, чтобы убедиться, что функция работает как надо.</span><span class="sxs-lookup"><span data-stu-id="feaa9-211">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="feaa9-212">Шаг 8. Обновление дополнительных пулов</span><span class="sxs-lookup"><span data-stu-id="feaa9-212">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="feaa9-213">Повторите приведенные в этом разделе шаги для обновления всех дополнительных пулов в данной среде.</span><span class="sxs-lookup"><span data-stu-id="feaa9-213">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="feaa9-214">Устранение неполадок при обновлении на месте</span><span class="sxs-lookup"><span data-stu-id="feaa9-214">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="feaa9-215">В случае сбоя обновления на месте может отображаться сообщение, подобное показанному на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="feaa9-215">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Снимок экрана, на котором показан сбой обновления на месте из-за отсутствия установки требуемого накопительного пакета обновления.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="feaa9-p115">Просмотрите полное сообщение внизу страницы, содержащее указания по устранению неполадки. Для просмотра подробных сведений выберите **Просмотреть журналы**.</span><span class="sxs-lookup"><span data-stu-id="feaa9-p115">Review the full message at the bottom of the page to help you troubleshoot the issue. Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="feaa9-219">Если обновление на месте не удалось выполнить на **Готовность к обновлению проверка** или ** установка предварительные условия отсутствующий **, убедитесь, что на сервере есть последних Windows Server, Lync Server и установленными обновлениями SQL Server и все необходимое программное обеспечение и роли установить.</span><span class="sxs-lookup"><span data-stu-id="feaa9-219">If the In-Place Upgrade fails on **Verifying upgrade readiness** or ** Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="feaa9-220">Что необходимо список в разделе [требования к серверу для Скайп для Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) и [установить необходимые компоненты для Скайп для Business Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="feaa9-220">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="feaa9-221">См. также</span><span class="sxs-lookup"><span data-stu-id="feaa9-221">See also</span></span>

#### 

[<span data-ttu-id="feaa9-222">Планирование обновления до Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="feaa9-222">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="feaa9-223">Требования к серверу для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="feaa9-223">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="feaa9-224">Установка необходимых компонентов для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="feaa9-224">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="feaa9-225">Установка Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="feaa9-225">Install Skype for Business Server 2015</span></span>](install/install.md)

