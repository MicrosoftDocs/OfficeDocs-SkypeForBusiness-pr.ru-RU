---
title: Тестирование аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Выполнение восстановления системы для сервера пула серверов Skype для бизнеса Server для проверки документированного процесса аварийного восстановления
ms.openlocfilehash: f3eba25d59c56f085b9bd6d347fcde910f11a00d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817305"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="b2a96-103">Тестирование аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b2a96-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="b2a96-104">Выполните восстановление системы для сервера пула серверов Skype для бизнеса Server, чтобы протестировать задокументированный процесс аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="b2a96-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="b2a96-105">Этот тест моделирует полную аппаратную сбои для одного сервера и поможет вам гарантировать доступность ресурсов, планов и данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="b2a96-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="b2a96-106">Попробуйте менять ориентир теста каждый месяц, чтобы в организации каждый раз проверялись сбои в работе разных серверов или других компонентов оборудования.</span><span class="sxs-lookup"><span data-stu-id="b2a96-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="b2a96-p102">Обратите внимание, что расписание выполнения организациями проверки аварийного восстановления будет отличаться. Очень важно, чтобы проверка аварийного восстановления выполнялась.</span><span class="sxs-lookup"><span data-stu-id="b2a96-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="b2a96-109">Экспортируйте топологию сервера Skype для бизнеса, политики и параметры конфигурации в файл.</span><span class="sxs-lookup"><span data-stu-id="b2a96-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="b2a96-110">Помимо прочего, данный файл может быть использован для восстановления данной информации в центральном хранилище управления после обновления, сбоя в работе оборудования или некоторых других неполадок, в результате которых произошла потеря данных.</span><span class="sxs-lookup"><span data-stu-id="b2a96-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="b2a96-111">Импортируйте топологию сервера Skype для бизнеса, политики и параметры конфигурации в хранилище Центрального управления или на локальный компьютер, как показано в следующих командах:</span><span class="sxs-lookup"><span data-stu-id="b2a96-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="b2a96-112">Чтобы создать резервные копии производственных данных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b2a96-112">To back up production data:</span></span>

- <span data-ttu-id="b2a96-113">Создавайте резервные копии баз данных RTC и Лкслог, используя стандартный процесс резервного копирования SQL Server, чтобы выгрузить ее из файла или накопительного дампа.</span><span class="sxs-lookup"><span data-stu-id="b2a96-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="b2a96-114">Используйте стороннее приложение резервного копирования для создания резервной копии данных в файле или на ленте.</span><span class="sxs-lookup"><span data-stu-id="b2a96-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="b2a96-115">Используйте командлет Export-CsUserData для создания экспорта XML всей базы данных RTC полностью.</span><span class="sxs-lookup"><span data-stu-id="b2a96-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="b2a96-116">Создайте резервные копии содержимого и журналов соответствия для собраний с помощью резервной копии файловой системы или стороннего средства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b2a96-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="b2a96-117">С помощью средства командной строки Export-Ксконфигуратион можно создавать резервные копии параметров Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b2a96-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="b2a96-118">Первый этап процедуры обхода неисправностей содержит принудительное перемещение пользователей из производственного пула в пул аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="b2a96-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="b2a96-119">Данное перемещение будет принудительным, потому что производственный пул не будет доступен для принятия перемещения пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2a96-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="b2a96-120">Пользовательский процесс перемещения в Skype для бизнеса Server — это изменение атрибута в объекте учетной записи пользователя в дополнение к обновлению записи в базе данных сервера реального времени.</span><span class="sxs-lookup"><span data-stu-id="b2a96-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="b2a96-121">Эти данные можно восстановить из исходного устройства резервного копирования на рабочем сервере SQL Server с помощью стандартного процесса восстановления SQL Server или с помощью сторонней программы резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="b2a96-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="b2a96-122">После восстановления эти данные пользователи могут подключаться к пулу аварийного восстановления и работать в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="b2a96-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="b2a96-123">Чтобы разрешить пользователям подключаться к пулу аварийного восстановления, потребуется изменение DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="b2a96-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="b2a96-124">На пул производственных данных в Skype для бизнеса будут ссылаться клиенты, использующие записи автоматической настройки и DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="b2a96-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="b2a96-125">SRV: _sip. _tls. \<Domain>/КНАМЕ: SIP. \<> домена</span><span class="sxs-lookup"><span data-stu-id="b2a96-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="b2a96-126">CNAME: SIP. \<> домена/CVC-Pool-1. \<> домена</span><span class="sxs-lookup"><span data-stu-id="b2a96-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="b2a96-127">Для облегчения процедуры отработки отказа данная запись CNAME должна быть обновлена с помощью ссылки на DROCSPool FQDN:</span><span class="sxs-lookup"><span data-stu-id="b2a96-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="b2a96-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="b2a96-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="b2a96-129">/дрокспул. \<> домена</span><span class="sxs-lookup"><span data-stu-id="b2a96-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="b2a96-130">Установка. \<> домена</span><span class="sxs-lookup"><span data-stu-id="b2a96-130">Sip.\<domain></span></span>
- <span data-ttu-id="b2a96-131">> AV\<. domain</span><span class="sxs-lookup"><span data-stu-id="b2a96-131">AV.\<domain></span></span>
- <span data-ttu-id="b2a96-132">"". \<> домена</span><span class="sxs-lookup"><span data-stu-id="b2a96-132">webconf.\<domain></span></span>
