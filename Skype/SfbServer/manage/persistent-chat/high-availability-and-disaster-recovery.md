---
title: Управление высокой доступностью и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: Сводка. Узнайте, как управлять высокой доступностью и аварийной восстановлением сервера сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815049"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5a913-103">Управление высокой доступностью и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a913-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5a913-104">**Сводка:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a913-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5a913-105">В этом разделе описывается отбой и отбой сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="5a913-106">Прежде чем читать этот раздел, ознакомьтесь с разделом "Планирование высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса [Server 2015"](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) и "Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в [Skype для бизнеса Server 2015".](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="5a913-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a913-107">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5a913-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5a913-108">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="5a913-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="5a913-109">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a913-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="5a913-110">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a913-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="5a913-111">Отбой сервера сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="5a913-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="5a913-112">Отбой для сервера сохраняемого чата предназначен в основном для ручного процесса.</span><span class="sxs-lookup"><span data-stu-id="5a913-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="5a913-113">Процедура отключки основана на предположении, что дополнительный центр обработки данных запущен, но службы сервера сохраняемого чата, в котором расположена основная база данных сохраняемого чата, полностью недоступны, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="5a913-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="5a913-114">Базовая база данных сервера сохраняемой беседы и зеркальная база данных сервера сохраняемой беседы отсев.</span><span class="sxs-lookup"><span data-stu-id="5a913-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="5a913-115">Сервер переднего сервера Skype для бизнеса Server неабит.</span><span class="sxs-lookup"><span data-stu-id="5a913-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="5a913-116">Вся процедура состоит из двух основных этапов:</span><span class="sxs-lookup"><span data-stu-id="5a913-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="5a913-117">Восстановление основной базы данных сохраняемой беседы (mgc).</span><span class="sxs-lookup"><span data-stu-id="5a913-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="5a913-118">Реализация зеркального отображения для новой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="5a913-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="5a913-119">База данных соответствия сохраняемой беседы (mgccomp) не отлалачивается.</span><span class="sxs-lookup"><span data-stu-id="5a913-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="5a913-120">Содержимое этой базы данных является временным и очищается по мере обработки данных адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="5a913-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="5a913-121">Вы как администратор сохраняемой беседы несете ответственность за правильное управление выходными данными адаптеров во избежание потери данных.</span><span class="sxs-lookup"><span data-stu-id="5a913-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="5a913-122">Чтобы перенаправить сервер сохраняемой беседы, сохраняемая беседа:</span><span class="sxs-lookup"><span data-stu-id="5a913-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="5a913-123">Удалите доставку журналов из базы данных доставки журналов резервной копии сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="5a913-124">С SQL Server Management Studio подключите экземпляр базы данных, в котором расположена резервная база данных mgc сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="5a913-125">Откройте окно отправки запроса в базу данных master.</span><span class="sxs-lookup"><span data-stu-id="5a913-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="5a913-126">Используйте следующую команду для сброса доставки журналов:</span><span class="sxs-lookup"><span data-stu-id="5a913-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="5a913-127">Скопируйте все нескопированные файлы резервных копий из общей папки резервных копий в конечную папку копирования на резервном сервере.</span><span class="sxs-lookup"><span data-stu-id="5a913-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="5a913-128">По порядку примените все непримененные резервные копии журналов транзакций к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="5a913-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="5a913-129">Подробные сведения см. в сведениях о применении резервного копирования журнала [транзакций (Transact-SQL).](https://go.microsoft.com/fwlink/p/?linkid=247428)</span><span class="sxs-lookup"><span data-stu-id="5a913-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="5a913-p105">Подключите резервную базу данных mgc к сети. В окне запроса, которое было открыто в действии 1b, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5a913-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="5a913-132">Завершите все подключения к базе данных mgc при их наличии:</span><span class="sxs-lookup"><span data-stu-id="5a913-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="5a913-133">**exec sp_who2** для определения подключений к базе данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="5a913-134">**kill \<spid\>** для окончания этих подключений.</span><span class="sxs-lookup"><span data-stu-id="5a913-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="5a913-135">Подключите базу данных к сети.</span><span class="sxs-lookup"><span data-stu-id="5a913-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="5a913-136">**восстановление базы данных mgc с восстановлением.**</span><span class="sxs-lookup"><span data-stu-id="5a913-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="5a913-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span><span class="sxs-lookup"><span data-stu-id="5a913-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="5a913-138">Не забудьте заменить полное доменное имя пула сохраняемого чата для atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5a913-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="5a913-139">Резервная база данных mgc теперь выступает в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="5a913-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="5a913-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span><span class="sxs-lookup"><span data-stu-id="5a913-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="5a913-141">Используйте экземпляр резервной базы данных в качестве базы данных источника и экземпляр резервной зеркальной базы данных в качестве экземпляра зеркала.</span><span class="sxs-lookup"><span data-stu-id="5a913-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="5a913-142">Это не то же самое зеркало, которое изначально было настроено для базы данных-источника в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="5a913-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="5a913-143">Установите активные серверы сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="5a913-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span><span class="sxs-lookup"><span data-stu-id="5a913-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a913-145">Все активные серверы должны располагаться в одном центре обработки данных с новой базой данных-источником или в центре обработки данных, имеющем подключение к базе данных с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="5a913-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="5a913-146">На этом этапе успешно завершается отбой из основной базы данных сервера сохраняемой беседы в резервную базу данных сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="5a913-147">Отбой сервера сохраняемой беседы</span><span class="sxs-lookup"><span data-stu-id="5a913-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="5a913-148">В этой процедуре описаны действия, необходимые для восстановления после сбоя сервера сохраняемого чата и восстановления операций из основного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5a913-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="5a913-149">Во время сбоя сервера сохраняемого чата основной центр обработки данных полностью перебои в работе, а основная и зеркальная базы данных становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="5a913-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="5a913-150">Основной центр обработки данных переключается на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="5a913-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="5a913-151">Ниже описывается процедура возобновления нормальной работы после восстановления основной базы данных и подключения серверов.</span><span class="sxs-lookup"><span data-stu-id="5a913-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="5a913-152">В этой процедуре предполагается, что основной центр обработки данных был восстановлен после полного отключения и что база данных mgc и база данных mgccomp были перестроены и переустановлены с помощью построщика топологий.</span><span class="sxs-lookup"><span data-stu-id="5a913-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="5a913-153">В процедуре также предполагается, что в период от сбойа не были развернуты новые зеркальные серверы и резервные серверы, а единственным развернутым сервером является резервный сервер и его зеркальный сервер, как было определено ранее в fail over Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="5a913-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="5a913-154">Данные инструкции служат для восстановления исходной конфигурации, которая существовала до сбоя, приведшего к переключению с основного на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="5a913-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="5a913-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5a913-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5a913-156">Это останавливает подключение всех серверов сохраняемого чата к базе данных mgc и базе данных mgccomp во время отката.</span><span class="sxs-lookup"><span data-stu-id="5a913-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a913-157">Агент SQL Server на дополнительном тыловом сервере сохраняемого чата должен работать под привилегированной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="5a913-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="5a913-158">В частности, эта учетная запись должна иметь следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="5a913-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="5a913-159">доступ на чтение к сетевой папке, в которую помещаются резервные копии;</span><span class="sxs-lookup"><span data-stu-id="5a913-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="5a913-160">доступ на запись к локальному каталогу, в который они копируются.</span><span class="sxs-lookup"><span data-stu-id="5a913-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="5a913-161">Отключите зеркальное отображение для резервной базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="5a913-162">Подключите SQL Server Management Studio к резервному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="5a913-163">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="5a913-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="5a913-164">Щелкните **Удалить зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="5a913-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="5a913-165">При появлении запроса на подтверждение нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5a913-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="5a913-166">Выполните те же действия для базы данных mgccomp.</span><span class="sxs-lookup"><span data-stu-id="5a913-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="5a913-167">Создайте резервную копию базы данных mgc, чтобы ее можно было восстановить в новой основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5a913-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="5a913-168">Подключите SQL Server Management Studio к резервному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="5a913-p113">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Создать резервную копию**. Появится диалоговое окно **Резервное копирование базы данных**.</span><span class="sxs-lookup"><span data-stu-id="5a913-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="5a913-171">В списке **Тип резервной копии** выберите пункт **Полная**.</span><span class="sxs-lookup"><span data-stu-id="5a913-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="5a913-172">В списке **Компонент резервного копирования** выберите пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="5a913-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="5a913-173">В поле **Имя** оставьте имя резервного набора данных по умолчанию или введите другое имя.</span><span class="sxs-lookup"><span data-stu-id="5a913-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="5a913-174">*\<Optional\>*  В **описании** введите описание резервного набора.</span><span class="sxs-lookup"><span data-stu-id="5a913-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="5a913-175">Удалите расположение резервной копии по умолчанию из списка назначений.</span><span class="sxs-lookup"><span data-stu-id="5a913-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="5a913-p114">Добавьте в список файл, указав путь к общей папке, которую вы выбрали для доставки журналов. Этот путь доступен как для основной, так и для резервной баз данных.</span><span class="sxs-lookup"><span data-stu-id="5a913-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="5a913-178">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно и начать процесс резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="5a913-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="5a913-179">Восстановите основную базу данных с помощью резервной копии, созданной в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="5a913-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="5a913-180">Подключите SQL Server Management Studio к основному экземпляру mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="5a913-p115">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи**, выберите пункт **Восстановить**, а затем **База данных**. Появится диалоговое окно **Восстановление базы данных**.</span><span class="sxs-lookup"><span data-stu-id="5a913-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="5a913-183">Выберите пункт **С устройства**.</span><span class="sxs-lookup"><span data-stu-id="5a913-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="5a913-p116">Нажмите кнопку "Обзор". Откроется диалоговое окно **Указание резервной копии**. В списке **Резервные носители** выберите пункт **Файл**. Нажмите кнопку **Добавить**, выберите файл резервной копии, созданный в шаге 3, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5a913-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="5a913-187">В таблице **Выберите резервные наборы данных для восстановления** выберите резервную копию.</span><span class="sxs-lookup"><span data-stu-id="5a913-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="5a913-188">В области **Выбор страницы** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5a913-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="5a913-189">В разделе **Параметры восстановления** выберите пункт **Перезаписать существующую базу данных**.</span><span class="sxs-lookup"><span data-stu-id="5a913-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="5a913-190">На панели **Состояние восстановления** выберите пункт **Оставить базу данных готовой к использованию**.</span><span class="sxs-lookup"><span data-stu-id="5a913-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="5a913-191">Нажмите кнопку **ОК**, чтобы начать процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="5a913-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="5a913-192">Настройте SQL Server журналов для основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="5a913-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="5a913-193">Выполните процедуры в процедуре настройки высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса [Server 2015,](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) чтобы установить доставку журналов для основной базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5a913-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="5a913-194">Установите активные серверы сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="5a913-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="5a913-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span><span class="sxs-lookup"><span data-stu-id="5a913-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5a913-196">Все активные серверы должны располагаться в одном центре обработки данных с новой базой данных-источником или в центре обработки данных, имеющем подключение к базе данных с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="5a913-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="5a913-197">Чтобы восстановить нормальное состояние пула, запустите следующую Windows PowerShell команду:</span><span class="sxs-lookup"><span data-stu-id="5a913-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="5a913-198">Дополнительные сведения см. в разделе справки по [cmdlet Set-CsPersistentChatState.](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5a913-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

