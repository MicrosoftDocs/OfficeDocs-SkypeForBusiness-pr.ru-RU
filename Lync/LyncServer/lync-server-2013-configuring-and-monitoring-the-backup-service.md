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

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Настройка и мониторинг службы резервного копирования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Для настройки и мониторинга службы архивации можно использовать следующие команды командной консоли Lync Server.

<div>


> [!NOTE]  
> Группа Рткуниверсалсерверадминс — единственная группа, у которой есть разрешения на запуск <STRONG>Get-ксбаккупсервицестатус</STRONG> по умолчанию. Чтобы использовать этот командлет, войдите в систему как участник этой группы. Вы также можете предоставить доступ к этой команде другим группам (например, Ксадминистратор) с помощью командлета <STRONG>Set-ксбаккупсервицеконфигуратион</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Просмотр конфигурации службы резервного копирования

Выполнить следующий командлет:

    Get-CsBackupServiceConfiguration

По умолчанию для СинЦинтервал используется два минуты.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Настройка интервала синхронизации службы резервного копирования

Выполнить следующий командлет:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Например, в приведенном ниже списке для интервала задается значение, равное трем минутам.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Несмотря на то, что вы можете использовать этот командлет для изменения интервала синхронизации по умолчанию для службы резервного копирования, это не следует делать, если только это не является обязательным, так как интервал синхронизации сильно влияет на производительность службы резервного копирования и цель точки восстановления (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Получение состояния службы резервного копирования для определенного пула

Выполнить следующий командлет:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Состояние синхронизации службы резервного копирования определяется односторонним из пула (P1) в резервный пул (P2). Состояние синхронизации от P1 до P2 может отличаться от P2 до P1. В случае P1 — P2 служба резервного копирования находится в состоянии «стабильно», если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации. Она находится в состоянии "завершено", если больше нет изменений для синхронизации из P1 в P2. Оба состояния указывают на то, что служба резервного копирования на момент выполнения командлета. Это не означает, что возвращенное состояние останется таким же, как и впоследствии. В частности, состояние "Final" продолжает храниться только в том случае, если P1 не создает никаких изменений после выполнения командлета. Это справедливо в случае сбоя P1 в P2 после того, как он будет помещен в режим "только для чтения" в рамках логики выполнения <STRONG>Invoke-кспулфаиловер</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Получение сведений об отношении резервного копирования для определенного пула

Выполнить следующий командлет:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Чтобы принудительно выполнить синхронизацию службы резервного копирования

Выполнить следующий командлет:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

