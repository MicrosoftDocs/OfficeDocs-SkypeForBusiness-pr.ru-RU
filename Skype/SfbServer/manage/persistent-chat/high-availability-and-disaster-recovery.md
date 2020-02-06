---
title: Управление высокой доступностью и аварийным восстановлением для сервера сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Сводка: сведения о том, как управлять сохраняемым сервером в режиме высокой доступности и аварийным восстановлением в Skype для бизнеса Server 2015.'
ms.openlocfilehash: ea81f72dfa65fd350b7c8b8c3aaf61bee6999b34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817230"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5dd67-103">Управление высокой доступностью и аварийным восстановлением для сервера сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5dd67-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5dd67-104">**Сводка:** Сведения о том, как управлять сохраняемым сервером в режиме высокой доступности и аварийным восстановлением в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5dd67-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5dd67-105">В этой статье описано, как переключиться на сохраняемый сервер чата и вернуть этот отказ.</span><span class="sxs-lookup"><span data-stu-id="5dd67-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="5dd67-106">Перед тем как читать этот раздел, не забудьте прочитать [план для обеспечения высокой доступности и аварийного восстановления для постоянного сервера чата в Skype для бизнеса server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) и [Настройте режим высокой доступности и аварийного восстановления для постоянного сервера чата в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="5dd67-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5dd67-107">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5dd67-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5dd67-108">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="5dd67-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="5dd67-109">Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="5dd67-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="5dd67-110">Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5dd67-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="5dd67-111">Переключение на сохраняемый сервер чата</span><span class="sxs-lookup"><span data-stu-id="5dd67-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="5dd67-112">Отработка отказа для сервера сохраняемого чата разработана в основном как процесс вручную.</span><span class="sxs-lookup"><span data-stu-id="5dd67-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="5dd67-113">Процедура отработки отказа основывается на предположении, что дополнительный центр обработки данных работает, но службы сервера сохраняемого чата, в которых находится первичная база данных чата, полностью недоступны, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="5dd67-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="5dd67-114">База данных основного сервера и зеркальный сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="5dd67-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="5dd67-115">Сервер клиентского доступа к Skype для бизнеса Server не работает.</span><span class="sxs-lookup"><span data-stu-id="5dd67-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="5dd67-116">Вся процедура состоит из двух основных этапов:</span><span class="sxs-lookup"><span data-stu-id="5dd67-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="5dd67-117">Восстановите первичную базу данных сохраняемого чата (MGC).</span><span class="sxs-lookup"><span data-stu-id="5dd67-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="5dd67-118">Реализация зеркального отображения для новой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="5dd67-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="5dd67-119">Не отменяется переключение на базу данных соответствия требованиям в отношении сохраняемого чата (мгккомп).</span><span class="sxs-lookup"><span data-stu-id="5dd67-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="5dd67-120">Содержимое этой базы данных является временным и очищается по мере обработки данных адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="5dd67-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="5dd67-121">Это ваша ответственность в том, чтобы правильно управлять выводом адаптера, чтобы избежать потери данных.</span><span class="sxs-lookup"><span data-stu-id="5dd67-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="5dd67-122">Порядок отработки отказа сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="5dd67-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="5dd67-123">Удалите доставку журналов из базы данных для резервного копирования журналов на сервере.</span><span class="sxs-lookup"><span data-stu-id="5dd67-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="5dd67-124">С помощью SQL Server Management Studio подключитесь к экземпляру базы данных, в котором находится база данных MGC сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="5dd67-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="5dd67-125">Откройте окно отправки запроса в базу данных master.</span><span class="sxs-lookup"><span data-stu-id="5dd67-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="5dd67-126">Используйте следующую команду для сброса доставки журналов:</span><span class="sxs-lookup"><span data-stu-id="5dd67-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="5dd67-127">Скопируйте все нескопированные файлы резервных копий из общей папки резервных копий в конечную папку копирования на резервном сервере.</span><span class="sxs-lookup"><span data-stu-id="5dd67-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="5dd67-128">По порядку примените все непримененные резервные копии журналов транзакций к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="5dd67-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="5dd67-129">Подробности можно найти [в статье инструкции по применению резервной копии журнала транзакций (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="5dd67-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="5dd67-p105">Подключите резервную базу данных mgc к сети. В окне запроса, которое было открыто в действии 1b, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5dd67-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="5dd67-132">Завершите все подключения к базе данных mgc при их наличии:</span><span class="sxs-lookup"><span data-stu-id="5dd67-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="5dd67-133">Выполните команду **exec sp_who2**, чтобы определить подключения к базе данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="5dd67-134">\*\* \<прервать\> SPID\*\* , чтобы завершить эти подключения.</span><span class="sxs-lookup"><span data-stu-id="5dd67-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="5dd67-135">Подключите базу данных к сети:</span><span class="sxs-lookup"><span data-stu-id="5dd67-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="5dd67-136">**restore database mgc with recovery**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="5dd67-137">В командной консоли управления Skype для бизнеса Server используйте команду **Set-ксперсистентчатстате-Identity "Service: ATL-CS-001.litwareinc.com"-Пулстате фаиледовер** , чтобы переходить на базу данных MGC Backup.</span><span class="sxs-lookup"><span data-stu-id="5dd67-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="5dd67-138">Обязательно замените полное доменное имя в пуле Persistent Chat для узла atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5dd67-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="5dd67-139">Резервная база данных mgc теперь выступает в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="5dd67-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="5dd67-140">В командной консоли управления Skype для бизнеса Server используйте командлет **Install-ксмиррордатабасе** , чтобы установить зеркало высокой доступности для резервной базы данных, которая теперь используется в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="5dd67-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="5dd67-141">Используйте экземпляр резервной базы данных в качестве базы данных-источника и экземпляр резервной зеркальной базы данных в качестве экземпляра зеркала.</span><span class="sxs-lookup"><span data-stu-id="5dd67-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="5dd67-142">Это не то же самое зеркало, которое изначально было настроено для базы данных-источника в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="5dd67-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="5dd67-143">Установите для сервера сохраняемые активные серверы чата.</span><span class="sxs-lookup"><span data-stu-id="5dd67-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="5dd67-144">С помощью командлета **Set-ксперсистентчатактивесервер** можно настроить список активных серверов в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5dd67-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5dd67-145">Все активные серверы должны быть расположены в том же центре обработки данных, что и новая база данных-источник, или подключенном к ней через соединение с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="5dd67-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="5dd67-146">На этом этапе резервная копия базы данных сервера сохраняемого чата будет успешно выполнена для базы данных архивации сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="5dd67-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="5dd67-147">Не удается вернуть сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="5dd67-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="5dd67-148">В этой процедуре описаны действия, которые необходимо выполнить для восстановления после отказа сервера с постоянным чат, и для повторного выполнения операций из основного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5dd67-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="5dd67-149">В случае отказа сервера сохраняемого чата в основном центре обработки данных снижается полный сбой, и основная и зеркальная базы данных становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="5dd67-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="5dd67-150">Основной центр обработки данных переключается на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="5dd67-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="5dd67-151">Ниже описывается процедура возобновления нормальной работы после восстановления базы данных-источника и подключения серверов.</span><span class="sxs-lookup"><span data-stu-id="5dd67-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="5dd67-152">В этой процедуре предполагается, что основной центр обработки данных восстановлен из общего отключения и что база данных MGC и база данных мгккомп были перестроены и переустановлены с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="5dd67-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="5dd67-153">Также предполагается, что в процессе отработки отказа не были развернуты новые зеркальные и резервные серверы и что единственный сервер, который был развернут, — это резервный и соответствующий зеркальный серверы, определенные в разделе "Отработка отказа сервером сохраняемого чата".</span><span class="sxs-lookup"><span data-stu-id="5dd67-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="5dd67-154">Данные инструкции служат для восстановления исходной конфигурации, которая существовала до сбоя, приведшего к переключению с основного на резервный сервер.</span><span class="sxs-lookup"><span data-stu-id="5dd67-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="5dd67-155">С помощью командлета **Set-ксперсистентчатактивесервер** в командной консоли управления Skype для бизнеса Server удалите все серверы из списка "активный сервер чата".</span><span class="sxs-lookup"><span data-stu-id="5dd67-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5dd67-156">Это прекратит выполнение всех постоянных серверов чата при подключении к базе данных MGC и базе данных мгккомп во время восстановления после сбоя.</span><span class="sxs-lookup"><span data-stu-id="5dd67-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5dd67-157">Агент SQL Server на дополнительном сервере сервера сохраняемого обратного чата должен выполняться под привилегированной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="5dd67-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="5dd67-158">В частности, эта учетная запись должна иметь следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="5dd67-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="5dd67-159">доступ на чтение к сетевой папке, в которую помещаются резервные копии;</span><span class="sxs-lookup"><span data-stu-id="5dd67-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="5dd67-160">доступ на запись к локальному каталогу, в который они копируются.</span><span class="sxs-lookup"><span data-stu-id="5dd67-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="5dd67-161">Отключите зеркальное отображение для резервной базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="5dd67-162">С помощью SQL Server Management Studio подключитесь к экземпляру резервной копии mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="5dd67-163">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="5dd67-164">Щелкните **Удалить зеркальное отображение**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="5dd67-165">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="5dd67-166">Выполните те же действия для базы данных mgccomp.</span><span class="sxs-lookup"><span data-stu-id="5dd67-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="5dd67-167">Создайте резервную копию базы данных mgc, чтобы ее можно было восстановить в новой основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5dd67-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="5dd67-168">С помощью SQL Server Management Studio подключитесь к экземпляру резервной копии mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="5dd67-p113">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи** и выберите пункт **Создать резервную копию**. Появится диалоговое окно **Резервное копирование базы данных**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="5dd67-171">В списке **Тип резервной копии** выберите пункт **Полная**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="5dd67-172">В списке **Компонент резервного копирования** выберите пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="5dd67-173">В поле **Имя** оставьте имя резервного набора данных по умолчанию или введите другое имя.</span><span class="sxs-lookup"><span data-stu-id="5dd67-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="5dd67-174">\* \<Необязательный\> \*  В поле **Описание**введите описание набора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="5dd67-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="5dd67-175">Удалите расположение резервной копии по умолчанию из списка назначений.</span><span class="sxs-lookup"><span data-stu-id="5dd67-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="5dd67-p114">Добавьте в список файл, указав путь к общей папке, которую вы выбрали для доставки журналов. Этот путь доступен как для основной, так и для резервной баз данных.</span><span class="sxs-lookup"><span data-stu-id="5dd67-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="5dd67-178">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно и начать процесс резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="5dd67-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="5dd67-179">Восстановите основную базу данных с помощью резервной копии, созданной в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="5dd67-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="5dd67-180">С помощью SQL Server Management Studio подключитесь к экземпляру основного mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="5dd67-p115">Щелкните правой кнопкой мыши базу данных mgc, наведите указатель на пункт **Задачи**, выберите пункт **Восстановить**, а затем **База данных**. Появится диалоговое окно **Восстановление базы данных**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="5dd67-183">Выберите пункт **С устройства**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="5dd67-p116">Нажмите кнопку "Обзор". Откроется диалоговое окно **Указание резервной копии**. В списке **Резервные носители** выберите пункт **Файл**. Нажмите кнопку **Добавить**, выберите файл резервной копии, созданный в шаге 3, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="5dd67-187">В таблице **Выберите резервные наборы данных для восстановления** выберите резервную копию.</span><span class="sxs-lookup"><span data-stu-id="5dd67-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="5dd67-188">В области **Выбор страницы** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="5dd67-189">В разделе **Параметры восстановления** выберите пункт **Перезаписать существующую базу данных**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="5dd67-190">На панели **Состояние восстановления** выберите пункт **Оставить базу данных готовой к использованию**.</span><span class="sxs-lookup"><span data-stu-id="5dd67-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="5dd67-191">Нажмите кнопку **ОК**, чтобы начать процесс восстановления.</span><span class="sxs-lookup"><span data-stu-id="5dd67-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="5dd67-192">Настройте доставку журналов SQL Server для базы данных PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="5dd67-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="5dd67-193">Выполните действия, описанные в разделе [Настройка обеспечения высокой доступности и аварийного восстановления для постоянного сервера чата в Skype для бизнеса server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) , чтобы установить доставку журналов для первичной базы данных mgc.</span><span class="sxs-lookup"><span data-stu-id="5dd67-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="5dd67-194">Установите для сервера сохраняемые активные серверы чата.</span><span class="sxs-lookup"><span data-stu-id="5dd67-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="5dd67-195">С помощью командлета **Set-ксперсистентчатактивесервер** можно настроить список активных серверов в командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5dd67-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5dd67-196">Все активные серверы должны быть расположены в том же центре обработки данных, что и новая база данных-источник, или подключенном к ней через соединение с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="5dd67-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="5dd67-197">Чтобы восстановить обычное состояние пула, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5dd67-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="5dd67-198">Дополнительные сведения см. в разделе справки с описанием командлета [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5dd67-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

