---
title: Тестирование аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Выполните восстановление системы для сервера пула Skype для бизнеса Server, чтобы протестировать документированный процесс аварийного восстановления
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832819"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="6d641-103">Тестирование аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6d641-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="6d641-104">Выполните восстановление системы для сервера пула Skype для бизнеса Server, чтобы протестировать документированный процесс аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="6d641-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="6d641-105">Этот тест имитирует полный сбой оборудования для одного сервера и гарантирует, что ресурсы, планы и данные будут доступны для восстановления.</span><span class="sxs-lookup"><span data-stu-id="6d641-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="6d641-106">Попробуйте поворачивать фокус теста каждый месяц, чтобы организация каждый раз проверяла сбой другого сервера или другого оборудования.</span><span class="sxs-lookup"><span data-stu-id="6d641-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="6d641-107">Обратите внимание, что расписание, в котором организации выполняют тестирование аварийного восстановления, зависит от расписания.</span><span class="sxs-lookup"><span data-stu-id="6d641-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="6d641-108">Очень важно, чтобы тестирование аварийного восстановления не игнорируется или не игнорируется.</span><span class="sxs-lookup"><span data-stu-id="6d641-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="6d641-109">Экспорт топологии, политик и параметров конфигурации Skype для бизнеса Server в файл.</span><span class="sxs-lookup"><span data-stu-id="6d641-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="6d641-110">Помимо прочего, этот файл можно использовать для восстановления этих сведений в центральном хранилище управления после обновления, сбоя оборудования или другой проблемы, которая приводит к потере данных.</span><span class="sxs-lookup"><span data-stu-id="6d641-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="6d641-111">Импорт топологии, политик и параметров конфигурации Skype для бизнеса Server в центральное хранилище управления или на локальный компьютер, как показано в следующих командах:</span><span class="sxs-lookup"><span data-stu-id="6d641-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="6d641-112">Для этого спроизводить производственные данные:</span><span class="sxs-lookup"><span data-stu-id="6d641-112">To back up production data:</span></span>

- <span data-ttu-id="6d641-113">Резервное копирование баз данных RTC и LCSLog с помощью стандартного процесса резервного копирования SQL Server для дампа базы данных в файл или устройство дампа ленты.</span><span class="sxs-lookup"><span data-stu-id="6d641-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="6d641-114">Используйте стороне приложение резервного копирования для резервного копирования данных на файл или ленту.</span><span class="sxs-lookup"><span data-stu-id="6d641-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="6d641-115">Используйте Export-CsUserData для создания экспорта XML всей базы данных RTC.</span><span class="sxs-lookup"><span data-stu-id="6d641-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="6d641-116">Резервное копирование файловой системы или стороннего резервного копирования для резервного копирования содержимого собраний и журналов соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6d641-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="6d641-117">Используйте средство Export-CsConfiguration командной строки для создания back up Skype for Business Server settings.</span><span class="sxs-lookup"><span data-stu-id="6d641-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="6d641-118">Первый этап процедуры отключки включает принудительное перемещение пользователей из производственного пула в пул аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="6d641-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="6d641-119">Это будет принудительное перемещение, так как производственный пул будет не доступен для перемещения пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d641-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="6d641-120">Процесс перемещения пользователя Skype для бизнеса Server фактически является изменением атрибута в объекте учетной записи пользователя в дополнение к обновлению записей в базе данных RTC SQL.</span><span class="sxs-lookup"><span data-stu-id="6d641-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="6d641-121">Эти данные можно восстановить с исходного устройства дампа резервных копий из производственной SQL Server с помощью стандартного SQL Server восстановления или с помощью стороннего с помощью резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="6d641-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="6d641-122">После восстановления этих данных пользователи могут эффективно подключаться к пулу аварийного восстановления и работать в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="6d641-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="6d641-123">Чтобы пользователи могли подключаться к пулу аварийного восстановления, потребуется изменить запись DNS.</span><span class="sxs-lookup"><span data-stu-id="6d641-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="6d641-124">На производственный пул Skype для бизнеса будут ссылаться клиенты, использующие автоматическую настройку и записи DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="6d641-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="6d641-125">SRV: _sip._tls.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="6d641-126">/CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="6d641-127">CNAME: SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="6d641-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="6d641-129">Чтобы упростить отбой, необходимо обновить эту запись CNAME, чтобы она ссылалась на FQDN DROCSPool:</span><span class="sxs-lookup"><span data-stu-id="6d641-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="6d641-130">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="6d641-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="6d641-132">Sip.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-132">Sip.\<domain></span></span>
- <span data-ttu-id="6d641-133">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-133">AV.\<domain></span></span>
- <span data-ttu-id="6d641-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="6d641-134">webconf.\<domain></span></span>
