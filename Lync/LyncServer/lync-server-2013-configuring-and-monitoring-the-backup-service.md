---
title: 'Lync Server 2013: Настройка и мониторинг службы резервного копирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fbbf4db9e15eac2d29fcde6bd126355c794a95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="c8aa0-102">Настройка и мониторинг службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8aa0-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8aa0-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c8aa0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c8aa0-104">Для настройки и мониторинга службы резервного копирования можно использовать следующие команды командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8aa0-105">Группа RTCUniversalServerAdmins является единственной группой, у которой есть разрешения на запуск <STRONG>Get-CsBackupServiceStatus</STRONG> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="c8aa0-106">Для использования этого командлета выполните вход в качестве члена этой группы.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="c8aa0-107">Либо можно предоставить доступ к этой команде другим группам (например, CSAdministrator) с помощью командлета <STRONG>Set-CsBackupServiceConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="c8aa0-108">Просмотр конфигурации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="c8aa0-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="c8aa0-109">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c8aa0-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="c8aa0-110">Значение SyncInterval по умолчанию равно двум минутам.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="c8aa0-111">Установка интервала синхронизации для службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="c8aa0-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="c8aa0-112">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c8aa0-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="c8aa0-113">Например, следующая команда задает интервал в три минуты.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8aa0-114">Несмотря на то, что с помощью этого командлета можно изменить интервал синхронизации по умолчанию для службы резервного копирования, это следует делать только в случае крайней необходимости, поскольку интервал синхронизации оказывает огромное влияние на производительность работы службы резервного копирования и целевую точку восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="c8aa0-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="c8aa0-115">Получение состояния службы резервного копирования для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="c8aa0-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="c8aa0-116">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c8aa0-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="c8aa0-117">Состояние синхронизации службы резервного копирования определяется в одном направлении — от пула P1 до его резервного пула P2.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="c8aa0-118">Состояние синхронизации от P1 до P2 может отличаться от состояния синхронизации от P2 до P1.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="c8aa0-119">Для направления от P1 до P2 служба резервного копирования находится в "готовом" состоянии, если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="c8aa0-120">Она находится в "завершенном" состоянии, если изменений для синхронизации от P1 до P2 больше нет.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="c8aa0-121">Оба состояния указывают на мгновенный снимок службы резервного копирования в момент выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="c8aa0-122">Возвращенное состояние не будет оставаться таким же и после.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="c8aa0-123">Например, "завершенное" состояние сохранится только до тех пор, пока на P1 не возникнет каких-либо изменений после выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="c8aa0-124">Это же верно в случае аварийного переключения с P1 на P2 после перевода P1 режим только для чтения в рамках логики выполнения <STRONG>Invoke-CsPoolfailover</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c8aa0-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="c8aa0-125">Получение сведений о резерве для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="c8aa0-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="c8aa0-126">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c8aa0-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="c8aa0-127">Принудительная синхронизация службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="c8aa0-127">To force a Backup Service sync</span></span>

<span data-ttu-id="c8aa0-128">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c8aa0-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

