---
title: Настройка и мониторинг службы резервного копирования
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Для настройки и отслеживания службы резервного копирования можно использовать команды командной оболочки Skype для бизнеса Server.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817199"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="01a59-103">Настройка и мониторинг службы резервного копирования в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="01a59-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="01a59-104">Для настройки и отслеживания службы резервного копирования можно использовать следующие команды командной оболочки Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="01a59-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="01a59-105">Сведения о восстановлении сведений о конференциях, [](#restore-conference-contents-using-the-backup-service)хранимые в хранилище файлов пула переднего уровня, см. ниже.</span><span class="sxs-lookup"><span data-stu-id="01a59-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="01a59-106">Группа RTCUniversalServerAdmins является единственной группой, у которой есть разрешения на запуск **Get-CsBackupServiceStatus** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="01a59-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="01a59-107">Для использования этого командлета выполните вход в качестве члена этой группы.</span><span class="sxs-lookup"><span data-stu-id="01a59-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="01a59-108">Либо можно предоставить доступ к этой команде другим группам (например, CSAdministrator) с помощью командлета **Set-CsBackupServiceConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="01a59-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="01a59-109">Просмотр конфигурации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="01a59-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="01a59-110">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="01a59-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="01a59-111">Значение SyncInterval по умолчанию равно двум минутам.</span><span class="sxs-lookup"><span data-stu-id="01a59-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="01a59-112">Установка интервала синхронизации для службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="01a59-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="01a59-113">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="01a59-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="01a59-114">Например, следующая команда задает интервал в три минуты.</span><span class="sxs-lookup"><span data-stu-id="01a59-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="01a59-115">Несмотря на то, что с помощью этого командлета можно изменить интервал синхронизации по умолчанию для службы резервного копирования, это следует делать только в случае крайней необходимости, поскольку интервал синхронизации оказывает огромное влияние на производительность работы службы резервного копирования и целевую точку восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="01a59-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="01a59-116">Получение состояния службы резервного копирования для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="01a59-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="01a59-117">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="01a59-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="01a59-118">Состояние синхронизации службы резервного копирования определяется в одном направлении — от пула P1 до его резервного пула P2.</span><span class="sxs-lookup"><span data-stu-id="01a59-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="01a59-119">Состояние синхронизации от P1 до P2 может отличаться от состояния синхронизации от P2 до P1.</span><span class="sxs-lookup"><span data-stu-id="01a59-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="01a59-120">Для направления от P1 до P2 служба резервного копирования находится в "готовом" состоянии, если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="01a59-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="01a59-121">Она находится в "завершенном" состоянии, если изменений для синхронизации от P1 до P2 больше нет.</span><span class="sxs-lookup"><span data-stu-id="01a59-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="01a59-122">Оба состояния указывают на мгновенный снимок службы резервного копирования в момент выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="01a59-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="01a59-123">Возвращенное состояние не будет оставаться таким же и после.</span><span class="sxs-lookup"><span data-stu-id="01a59-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="01a59-124">Например, "завершенное" состояние сохранится только до тех пор, пока на P1 не возникнет каких-либо изменений после выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="01a59-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="01a59-125">Это же верно в случае аварийного переключения с P1 на P2 после перевода P1 режим только для чтения в рамках логики выполнения **Invoke-CsPoolfailover**.</span><span class="sxs-lookup"><span data-stu-id="01a59-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="01a59-126">Получение сведений о резерве для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="01a59-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="01a59-127">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="01a59-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="01a59-128">Принудительная синхронизация службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="01a59-128">To force a Backup Service sync</span></span>

<span data-ttu-id="01a59-129">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="01a59-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="01a59-130">Восстановление содержимого конференции с помощью службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="01a59-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="01a59-131">Если сведения о конференции, хранимые в хранилище файлов пула переднего доступа, становятся недоступными, необходимо восстановить эти сведения, чтобы пользователи, которые были в пуле, сохраняли свои данные конференций.</span><span class="sxs-lookup"><span data-stu-id="01a59-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="01a59-132">Если пул переднего планирования, потеряв данные конференции, сопряжен с другим пулом переднего плану, для восстановления данных можно использовать службу резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="01a59-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="01a59-p105">Необходимо также выполнить эту задачу, если вследствие сбоя не работает весь пул и необходимо перенести его пользователей в резервный пул. При восстановлении пользователей в исходном пуле необходимо использовать эту процедуру для копирования контента конференций обратно в исходный пул.</span><span class="sxs-lookup"><span data-stu-id="01a59-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="01a59-135">Предположим, что пул1 объединен с пулом2, а данные конференций в пуле1 утрачены.</span><span class="sxs-lookup"><span data-stu-id="01a59-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="01a59-136">Для вызова службы резервного копирования для восстановления содержимого можно использовать следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="01a59-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="01a59-p107">Восстановление содержимого конференций может занять некоторое время в зависимости от размера. Можно использовать приведенный ниже командлет для проверки состояния процесса:</span><span class="sxs-lookup"><span data-stu-id="01a59-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="01a59-139">Процесс завершается, когда этот командлет возвращает значение Steady State для данных в модуле конференций.</span><span class="sxs-lookup"><span data-stu-id="01a59-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
