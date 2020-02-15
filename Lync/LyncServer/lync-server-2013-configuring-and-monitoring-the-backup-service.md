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
ms.openlocfilehash: 5f0fc9d65f1879c453c01813e09ad2ca0e8a99c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Настройка и мониторинг службы резервного копирования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Для настройки и мониторинга службы резервного копирования можно использовать следующие команды командной консоли Lync Server.

<div>


> [!NOTE]  
> Группа RTCUniversalServerAdmins является единственной группой, у которой есть разрешения на запуск <STRONG>Get-CsBackupServiceStatus</STRONG> по умолчанию. Для использования этого командлета выполните вход в качестве члена этой группы. Либо можно предоставить доступ к этой команде другим группам (например, CSAdministrator) с помощью командлета <STRONG>Set-CsBackupServiceConfiguration</STRONG>.



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Просмотр конфигурации службы резервного копирования

Выполните следующий командлет:

    Get-CsBackupServiceConfiguration

Значение SyncInterval по умолчанию равно двум минутам.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Установка интервала синхронизации для службы резервного копирования

Выполните следующий командлет:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Например, следующая команда задает интервал в три минуты.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Несмотря на то, что с помощью этого командлета можно изменить интервал синхронизации по умолчанию для службы резервного копирования, это следует делать только в случае крайней необходимости, поскольку интервал синхронизации оказывает огромное влияние на производительность работы службы резервного копирования и целевую точку восстановления (RPO).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Получение состояния службы резервного копирования для конкретного пула

Выполните следующий командлет:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Состояние синхронизации службы резервного копирования определяется в одном направлении — от пула P1 до его резервного пула P2. Состояние синхронизации от P1 до P2 может отличаться от состояния синхронизации от P2 до P1. Для направления от P1 до P2 служба резервного копирования находится в "готовом" состоянии, если все изменения, внесенные в P1, полностью реплицируются на P2 в течение интервала синхронизации. Она находится в "завершенном" состоянии, если изменений для синхронизации от P1 до P2 больше нет. Оба состояния указывают на мгновенный снимок службы резервного копирования в момент выполнения командлета. Возвращенное состояние не будет оставаться таким же и после. Например, "завершенное" состояние сохранится только до тех пор, пока на P1 не возникнет каких-либо изменений после выполнения командлета. Это же верно в случае аварийного переключения с P1 на P2 после перевода P1 режим только для чтения в рамках логики выполнения <STRONG>Invoke-CsPoolfailover</STRONG>.



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Получение сведений о резерве для конкретного пула

Выполните следующий командлет:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Принудительная синхронизация службы резервного копирования

Выполните следующий командлет:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

