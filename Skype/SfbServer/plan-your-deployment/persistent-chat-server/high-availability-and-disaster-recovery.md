---
title: Планирование высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: Сводка. В этом разделе вы узнаете, как планировать высокую доступность и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832359"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="2473e-103">Планирование высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2473e-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2473e-104">**Сводка:** В этом разделе вы узнаете, как спланировать высокую доступность и аварийное восстановление для сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2473e-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2473e-105">Для высокой доступности и аварийного восстановления для сервера сохраняемой беседы требуются дополнительные ресурсы, превысив обычно необходимые для полной работы.</span><span class="sxs-lookup"><span data-stu-id="2473e-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2473e-106">Использование SQL групп доступности AlwaysOn не поддерживается базами данных сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="2473e-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="2473e-107">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2473e-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2473e-108">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="2473e-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="2473e-109">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2473e-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2473e-110">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2473e-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="2473e-111">Требуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="2473e-111">Resource requirements</span></span>

<span data-ttu-id="2473e-112">Перед настройкой сервера сохраняемой беседы для обеспечения высокой доступности и аварийного восстановления убедитесь, что у вас есть следующие дополнительные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2473e-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="2473e-113">Один выделенный экземпляр базы данных, расположенный в том же физическом центре обработки данных, в котором расположена домашняя часть службы сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2473e-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="2473e-114">Эта база данных будет служить зеркальным SQL Server для основной базы данных сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="2473e-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="2473e-115">При желании назначь дополнительный SQL Server, который будет выступать в качестве свидетеля зеркального зеркального зеркала, если вы хотите автоматизировать отбой в зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="2473e-116">Один выделенный экземпляр базы данных, расположенный в другом физическом центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="2473e-117">Эта база данных будет служить SQL Server базы данных доставки журналов для базы данных в основном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="2473e-118">Один выделенный экземпляр базы данных, который будет служить SQL Server зеркальным отражением для базы данных-дополнительного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2473e-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="2473e-119">При желании назначь дополнительный сервер SQL Server в качестве свидетеля зеркального зеркального отражания.</span><span class="sxs-lookup"><span data-stu-id="2473e-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="2473e-120">Обе базы данных должны быть расположены в одном физическом центре обработки данных в качестве базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="2473e-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="2473e-121">Если включено соответствие сервера сохраняемой беседы, требуются дополнительные три выделенных экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="2473e-122">Их распределение такое же, как и для базы данных сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="2473e-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="2473e-123">Хотя база данных соответствия может совместно использовать тот же экземпляр SQL Server, что и база данных сохраняемой беседы, рекомендуется использовать автономные экземпляры для обеспечения высокой доступности и аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="2473e-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="2473e-124">Для журналов транзакций доставки журналов необходимо создать и назначить SQL Server файловой папки.</span><span class="sxs-lookup"><span data-stu-id="2473e-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="2473e-125">Все SQL-серверы в обоих центрах обработки данных, где работают базы данных сохраняемого чата, должны иметь доступ на чтение и записи к этой файловой папке.</span><span class="sxs-lookup"><span data-stu-id="2473e-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="2473e-126">Этот файловый ресурс не задается как часть роли хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="2473e-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="2473e-127">Файловая папка на дополнительном сервере баз данных, которая служит в качестве папки назначения для SQL Server транзакций, скопированные из основного файлового сервера.</span><span class="sxs-lookup"><span data-stu-id="2473e-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="2473e-128">Решения для аварийного восстановления и обеспечения высокой доступности</span><span class="sxs-lookup"><span data-stu-id="2473e-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="2473e-129">Skype для бизнеса Server поддерживает несколько режимов высокой доступности для серверов, в том числе зеркальное отражение базы данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="2473e-130">Дополнительные сведения см. в плане высокой доступности и аварийного восстановления [в Skype для бизнеса Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2473e-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="2473e-131">Решение аварийного восстановления для сервера сохраняемой беседы, описанное в этом разделе, построено на растянутом пуле серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="2473e-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="2473e-132">Для растянутой виртуальной локальной сети (VLAN) не существует требований.</span><span class="sxs-lookup"><span data-stu-id="2473e-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="2473e-133">Растягивая пул серверов сохраняемого чата, можно логически настроить один пул в топологии, но физически разместить серверы в пуле в двух разных центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="2473e-134">Зеркальное SQL Server базы данных настраивается аналогичным образом, а база данных и зеркальное отражение развертываются в одном центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2473e-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="2473e-135">Необходимо настроить резервную базу данных в дополнительном центре обработки данных (с необязательным зеркалом для обеспечения высокой доступности во время аварийного восстановления).</span><span class="sxs-lookup"><span data-stu-id="2473e-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="2473e-136">Это резервная база данных, используемая для от сбойов во время аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="2473e-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="2473e-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="2473e-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="2473e-138">На следующих рисунках покажите, как можно настроить пул серверов сохраняемого чата в двух разных растянутых конфигурациях пула:</span><span class="sxs-lookup"><span data-stu-id="2473e-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="2473e-139">Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой</span><span class="sxs-lookup"><span data-stu-id="2473e-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="2473e-140">Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой</span><span class="sxs-lookup"><span data-stu-id="2473e-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="2473e-141">На рисунке 1 показана растянутая топология пула серверов сохраняемого чата, в которой центры обработки данных расположены в географическом расположении с высокой пропускной способностью и низкой задержкой.</span><span class="sxs-lookup"><span data-stu-id="2473e-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="2473e-142">Предположим, что для логических и физических тоологий необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="2473e-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="2473e-143">Логическая топология состоит из следующих следующую:</span><span class="sxs-lookup"><span data-stu-id="2473e-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="2473e-144">Пул сохраняемой беседы на сайтах 1 и 2, содержащий серверы 1-8.</span><span class="sxs-lookup"><span data-stu-id="2473e-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="2473e-145">Пул серверов переднего сервера, база данных сохраняемой беседы, зеркальная база данных и, при желании, база данных-свидетель (не показанная на схеме) физически на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="2473e-146">Второй пул серверов переднего сервера и резервная база данных физически на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="2473e-147">Физическая топология состоит из сайтов 1 и 2 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2473e-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="2473e-148">Пул сохраняемой беседы, содержащий серверы от 1 до 4, два активных, два бездействия на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="2473e-149">Пул сохраняемой беседы, содержащий серверы от 5 до 8, два активных, два бездействия на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="2473e-150">Пул серверов переднего сервера, база данных сохраняемой беседы, зеркальная база данных и, при желании, база данных-свидетель (не показана на схеме) на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="2473e-151">Пул серверов переднего сервера и резервная база данных, SQL доставки журналов, на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="2473e-152">**Растянутый пул серверов сохраняемого чата, когда центры обработки данных расположены в географическом расположении с высокой пропускной способностью и низкой задержкой**</span><span class="sxs-lookup"><span data-stu-id="2473e-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![Растянутый пул сохраняемой беседы с высокой пропускной способностью и низкой задержкой](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="2473e-154">На рисунке 2 показана растянутая топология пула серверов сохраняемого чата, в которой центры обработки данных расположены в географическом расположении с низкой пропускной способностью и высокой задержкой.</span><span class="sxs-lookup"><span data-stu-id="2473e-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="2473e-155">Логическая топология состоит из следующих следующую:</span><span class="sxs-lookup"><span data-stu-id="2473e-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="2473e-156">Пул сохраняемой беседы на сайтах 1 и 2, содержащий серверы 1-8.</span><span class="sxs-lookup"><span data-stu-id="2473e-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="2473e-157">Пул серверов переднего сервера, база данных сохраняемой беседы, зеркальная база данных и, при желании, база данных-свидетель (не показанная на схеме) физически на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="2473e-158">Второй пул серверов переднего сервера и резервная база данных физически на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="2473e-159">Физическая топология состоит из сайтов 1 и 2 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2473e-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="2473e-160">Пул сохраняемой беседы, содержащий серверы от 1 до 4, все активные, на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="2473e-161">Пул сохраняемой беседы, содержащий серверы с 5 по 8 ( все бездействуют) на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="2473e-162">Пул серверов переднего сервера, база данных сохраняемой беседы, зеркальная база данных и, при желании, база данных-свидетель (не показана на схеме) на сайте 1.</span><span class="sxs-lookup"><span data-stu-id="2473e-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="2473e-163">Пул серверов переднего сервера и резервная база данных, SQL доставки журналов, на сайте 2.</span><span class="sxs-lookup"><span data-stu-id="2473e-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="2473e-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span><span class="sxs-lookup"><span data-stu-id="2473e-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![Растянутый пул сохраняемой беседы с низкой пропускной способностью и большой задержкой](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

