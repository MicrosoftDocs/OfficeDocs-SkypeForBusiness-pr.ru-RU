---
title: Аварийное восстановление, тестирование в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Выполните восстановление системы для Скайп для пула сервера Business Server для тестирования процесса документированным аварийного восстановления
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884966"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="1321f-103">Аварийное восстановление, тестирование в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="1321f-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="1321f-104">Выполните восстановление системы для Скайп для пула сервера Business Server для тестирования процесса документированным аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1321f-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="1321f-105">Этот тест будет моделировать сбой завершения аппаратного на одном сервере и поможет гарантировать, что ресурсы, планы и данные доступны для восстановления.</span><span class="sxs-lookup"><span data-stu-id="1321f-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="1321f-106">Попробуйте менять ориентир теста каждый месяц, чтобы в организации каждый раз проверялись сбои в работе разных серверов или других компонентов оборудования.</span><span class="sxs-lookup"><span data-stu-id="1321f-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="1321f-p102">Обратите внимание, что расписание выполнения организациями проверки аварийного восстановления будет отличаться. Очень важно, чтобы проверка аварийного восстановления выполнялась.</span><span class="sxs-lookup"><span data-stu-id="1321f-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="1321f-109">Экспорт в файл вашего Скайп для топологии, политик и параметров конфигурации Business Server.</span><span class="sxs-lookup"><span data-stu-id="1321f-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="1321f-110">Помимо прочего, данный файл может быть использован для восстановления данной информации в центральном хранилище управления после обновления, сбоя в работе оборудования или некоторых других неполадок, в результате которых произошла потеря данных.</span><span class="sxs-lookup"><span data-stu-id="1321f-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="1321f-111">Импортируйте вашей Скайп для топологии Business Server, политик и параметров конфигурации для хранилища централизованного управления или на локальном компьютере, как показано в следующей команды:</span><span class="sxs-lookup"><span data-stu-id="1321f-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="1321f-112">Резервное копирование рабочих данных:</span><span class="sxs-lookup"><span data-stu-id="1321f-112">To back up production data:</span></span>

- <span data-ttu-id="1321f-113">Резервное копирование баз данных RTC и LCSLog с помощью стандартных SQL Server резервного копирования для вывода базы данных на устройство дампа файла или ленты.</span><span class="sxs-lookup"><span data-stu-id="1321f-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="1321f-114">Используйте стороннее приложение резервного копирования для создания резервной копии данных в файле или на ленте.</span><span class="sxs-lookup"><span data-stu-id="1321f-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="1321f-115">Используйте командлет Export-CsUserData для создания экспорта XML всей базы данных RTC полностью.</span><span class="sxs-lookup"><span data-stu-id="1321f-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="1321f-116">Использование резервной копии сторонних производителей или резервное копирование файловой системы для резервного копирования содержимого и соответствия журналы на собрания.</span><span class="sxs-lookup"><span data-stu-id="1321f-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="1321f-117">Используйте средство командной строки Export-CsConfiguration для резервного копирования Скайп для параметров Business Server.</span><span class="sxs-lookup"><span data-stu-id="1321f-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="1321f-118">Первый этап процедуры обхода неисправностей содержит принудительное перемещение пользователей из производственного пула в пул аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="1321f-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="1321f-119">Данное перемещение будет принудительным, потому что производственный пул не будет доступен для принятия перемещения пользователей.</span><span class="sxs-lookup"><span data-stu-id="1321f-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="1321f-120">Скайп для пользователя процесс перемещения Business Server является внесение изменений в атрибут на объект учетной записи пользователя, в дополнение к обновление записи в базе данных RTC SQL.</span><span class="sxs-lookup"><span data-stu-id="1321f-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="1321f-121">Эти данные можно восстановить из исходного устройства резервного копирования дамп с рабочей SQL Server с помощью стандартный процесс восстановления SQL Server или с помощью стороннего резервного копирования и восстановления служебной программы.</span><span class="sxs-lookup"><span data-stu-id="1321f-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="1321f-122">После восстановления данных пользователей можно эффективно подключаться к пулу аварийного восстановления и работать как обычно.</span><span class="sxs-lookup"><span data-stu-id="1321f-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="1321f-123">Чтобы пользователи могли подключиться к пулу аварийного восстановления, потребуется изменение записей DNS.</span><span class="sxs-lookup"><span data-stu-id="1321f-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="1321f-124">Рабочая Скайп для бизнеса пула будет создана ссылка клиентами с помощью автоматической настройки и записей DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="1321f-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="1321f-125">Запись SRV: _sip._tls. \<domain> /CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="1321f-126">CNAME: SIP. \<domain> /cvc-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="1321f-127">Для облегчения процедуры отработки отказа данная запись CNAME должна быть обновлена с помощью ссылки на DROCSPool FQDN:</span><span class="sxs-lookup"><span data-stu-id="1321f-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="1321f-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="1321f-129">/ DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="1321f-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-130">Sip.\<domain></span></span>
- <span data-ttu-id="1321f-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-131">AV.\<domain></span></span>
- <span data-ttu-id="1321f-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="1321f-132">webconf.\<domain></span></span>
