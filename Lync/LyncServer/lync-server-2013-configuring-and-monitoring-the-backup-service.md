---
title: 'Lync Server 2013: настройка и мониторинг службы резервного копирования'
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
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="bcbcf-102">Настройка и мониторинг службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcbcf-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcbcf-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bcbcf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bcbcf-104">Для настройки и мониторинга службы архивации можно использовать следующие команды командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bcbcf-105">Группа Рткуниверсалсерверадминс — единственная группа, у которой есть разрешения на запуск <STRONG>Get-ксбаккупсервицестатус</STRONG> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="bcbcf-106">Чтобы использовать этот командлет, войдите в систему как участник этой группы.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="bcbcf-107">Вы также можете предоставить доступ к этой команде другим группам (например, Ксадминистратор) с помощью командлета <STRONG>Set-ксбаккупсервицеконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="bcbcf-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="bcbcf-108">Просмотр конфигурации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="bcbcf-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="bcbcf-109">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bcbcf-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="bcbcf-110">По умолчанию для СинЦинтервал используется два минуты.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="bcbcf-111">Настройка интервала синхронизации службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="bcbcf-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="bcbcf-112">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bcbcf-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="bcbcf-113">Например, в приведенном ниже списке для интервала задается значение, равное трем минутам.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bcbcf-114">Несмотря на то, что вы можете использовать этот командлет для изменения интервала синхронизации по умолчанию для службы резервного копирования, это не следует делать, если только это не является обязательным, так как интервал синхронизации сильно влияет на производительность службы резервного копирования и цель точки восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="bcbcf-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="bcbcf-115">Получение состояния службы резервного копирования для определенного пула</span><span class="sxs-lookup"><span data-stu-id="bcbcf-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="bcbcf-116">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bcbcf-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="bcbcf-117">Состояние синхронизации службы резервного копирования определяется односторонним из пула (P1) в резервный пул (P2).</span><span class="sxs-lookup"><span data-stu-id="bcbcf-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="bcbcf-118">Состояние синхронизации от P1 до P2 может отличаться от P2 до P1.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="bcbcf-119">В случае P1 — P2 служба резервного копирования находится в состоянии «стабильно», если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="bcbcf-120">Она находится в состоянии "завершено", если больше нет изменений для синхронизации из P1 в P2.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="bcbcf-121">Оба состояния указывают на то, что служба резервного копирования на момент выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="bcbcf-122">Это не означает, что возвращенное состояние останется таким же, как и впоследствии.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="bcbcf-123">В частности, состояние "Final" продолжает храниться только в том случае, если P1 не создает никаких изменений после выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="bcbcf-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="bcbcf-124">Это справедливо в случае сбоя P1 в P2 после того, как он будет помещен в режим "только для чтения" в рамках логики выполнения <STRONG>Invoke-кспулфаиловер</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="bcbcf-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="bcbcf-125">Получение сведений об отношении резервного копирования для определенного пула</span><span class="sxs-lookup"><span data-stu-id="bcbcf-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="bcbcf-126">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bcbcf-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="bcbcf-127">Чтобы принудительно выполнить синхронизацию службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="bcbcf-127">To force a Backup Service sync</span></span>

<span data-ttu-id="bcbcf-128">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bcbcf-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

