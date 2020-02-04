---
title: 'Lync Server 2013: задачи, необходимые для выполнения задач'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="d26a4-102">Задачи, необходимые для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d26a4-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d26a4-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="d26a4-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="d26a4-104">При необходимости выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d26a4-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="d26a4-105">Они часто покрываются в стандартных процедурах:</span><span class="sxs-lookup"><span data-stu-id="d26a4-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="d26a4-106">**Аудит полного доступа   ** Вы можете регулярно выполнять этот аудит в ответ на обновление или Перепроектирование системы обмена сообщениями, а также в ответ на попытку (или успешно) нарушение безопасности.</span><span class="sxs-lookup"><span data-stu-id="d26a4-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="d26a4-107">Процедура может включать сканирование порта на серверах и брандмауэрах, аудит исправлений системы безопасности и тестов проникновения сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="d26a4-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="d26a4-108">**Замена сертификатов срок действия истекает**   проверка сертификатов сервера Lync — это один из регулярных еженедельных задач, а в рамках процедуры, которая должна быть зарегистрирована в качестве даты окончания срока действия всех сертификатов, администратором.</span><span class="sxs-lookup"><span data-stu-id="d26a4-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="d26a4-109">Эта запись позволяет администратору создать уведомление о том, что срок действия определенного сертификата уже истек и заменяется нужным образом.</span><span class="sxs-lookup"><span data-stu-id="d26a4-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="d26a4-110">**При обновлении базовых показателей производительности**   обновляются базовые показатели производительности после обновления или изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d26a4-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="d26a4-111">Ваша организация может использовать базовые показатели для измерения изменений производительности и для выявления проблем, влияющих на производительность системы.</span><span class="sxs-lookup"><span data-stu-id="d26a4-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="d26a4-112">**Управление**   первоначальной конфигурацией корпоративных пулов, серверов стандартных выпусков и других серверов в среде организации выполнялось при развертывании отдельных серверов.</span><span class="sxs-lookup"><span data-stu-id="d26a4-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="d26a4-113">Ниже перечислены задачи, которые следует выполнять после развертывания серверов и пулов для серверов стандартных выпусков и пулов предприятий.</span><span class="sxs-lookup"><span data-stu-id="d26a4-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="d26a4-114">Управление серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="d26a4-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="d26a4-115">Управление веб-конференциями</span><span class="sxs-lookup"><span data-stu-id="d26a4-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="d26a4-116">Управление конференциями</span><span class="sxs-lookup"><span data-stu-id="d26a4-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="d26a4-117">Изменение учетных данных учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="d26a4-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="d26a4-118">Управление базами данных</span><span class="sxs-lookup"><span data-stu-id="d26a4-118">Managing Databases</span></span>
    
      - <span data-ttu-id="d26a4-119">Запуск и остановка служб и отключение ролей сервера</span><span class="sxs-lookup"><span data-stu-id="d26a4-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="d26a4-120">Удаление серверов и ролей сервера, удаление пулов и списание серверов и пулов</span><span class="sxs-lookup"><span data-stu-id="d26a4-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="d26a4-121">**Управление использованием**   . Вы можете настроить Lync Server 2013 для предоставления функциональных возможностей и функций, наиболее подходящих для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d26a4-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="d26a4-122">Доступны следующие политики:</span><span class="sxs-lookup"><span data-stu-id="d26a4-122">This includes the following:</span></span>
    
      - <span data-ttu-id="d26a4-123">Управление поддержкой локальных собраний веб-конференций</span><span class="sxs-lookup"><span data-stu-id="d26a4-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="d26a4-124">Управление использованием групп рассылки для отправки мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="d26a4-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="d26a4-125">Управление контактами, присутствием и запросами</span><span class="sxs-lookup"><span data-stu-id="d26a4-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="d26a4-126">Настройка фильтрации клиентских версий</span><span class="sxs-lookup"><span data-stu-id="d26a4-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="d26a4-127">Настройка фильтрации интеллектуального обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="d26a4-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="d26a4-128">Настройка архивации, записи звонков и соответствия собранию</span><span class="sxs-lookup"><span data-stu-id="d26a4-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="d26a4-129">**Управление подключением**   пограничного сервера. Управление серверами и параметрами, необходимыми для обеспечения внешней связи, включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="d26a4-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="d26a4-130">Управление подключением между внутренними серверами и пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="d26a4-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="d26a4-131">Настройка внутренних и внешних интерфейсов и сертификатов для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="d26a4-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="d26a4-132">Управление доступом к федеративного партнера</span><span class="sxs-lookup"><span data-stu-id="d26a4-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="d26a4-133">**Администрирование адресной**   книги серверов с адресными книгами включает в себя следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="d26a4-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="d26a4-134">Настройка нормализации телефонной книги сервера в адресной книге</span><span class="sxs-lookup"><span data-stu-id="d26a4-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="d26a4-135">Управление сервером адресной книги из командной строки</span><span class="sxs-lookup"><span data-stu-id="d26a4-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="d26a4-136">**Управление учетными записями**   пользователей включает в себя указанные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="d26a4-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="d26a4-137">Включение учетных записей пользователей для Lync Server</span><span class="sxs-lookup"><span data-stu-id="d26a4-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="d26a4-138">Настройка пользователей Lync Server с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="d26a4-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="d26a4-139">Настройка отдельных свойств учетной записи пользователя в Lync Server</span><span class="sxs-lookup"><span data-stu-id="d26a4-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="d26a4-140">Поиск пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="d26a4-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="d26a4-141">Перемещение пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="d26a4-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="d26a4-142">Удаление пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="d26a4-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="d26a4-143">**Анализ файлов**   журнала Lync Server 2013 один очень полезный инструмент, который обычно используется для устранения неполадок, — это средство ведения журнала Lync Server 2013, подробно описанное в разделе [Работа с программой ведения журнала Lync Server 2013](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="d26a4-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="d26a4-144">Поскольку средство ведения журнала создает файлы журнала (отдельно для каждого сервера), эти файлы журнала можно просмотреть и проанализировать с помощью средства Снупер, если на компьютере установлены средства Microsoft Office Server 12 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="d26a4-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="d26a4-145">В противном случае журналы также можно проанализировать с помощью текстового редактора, который значительно менее прозрачен и сложнее, чем использование служебной программы Снупер.</span><span class="sxs-lookup"><span data-stu-id="d26a4-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="d26a4-146">Просмотр и анализ сообщений протокола</span><span class="sxs-lookup"><span data-stu-id="d26a4-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="d26a4-147">В средстве ведения журнала после завершения сеанса отладки выберите пункт анализ файлов журнала для просмотра файлов журнала с помощью средства Снупер.</span><span class="sxs-lookup"><span data-stu-id="d26a4-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="d26a4-148">Журналы протоколов можно анализировать для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="d26a4-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="d26a4-149">Lync Server Сипстакк (SIP)</span><span class="sxs-lookup"><span data-stu-id="d26a4-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="d26a4-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="d26a4-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="d26a4-151">Трафик сигналов для конференц-связи Lync Server (C3P), включая MCU бесC3P и Focus C3P</span><span class="sxs-lookup"><span data-stu-id="d26a4-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="d26a4-152">Трафик веб-конференций Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="d26a4-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="d26a4-153">Клиент клиентской платформы единой системы обмена сообщениями Lync Server (УККП)</span><span class="sxs-lookup"><span data-stu-id="d26a4-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="d26a4-154">Отчеты об ошибках из базы данных архивации</span><span class="sxs-lookup"><span data-stu-id="d26a4-154">Error reports from the archiving database</span></span>

<span data-ttu-id="d26a4-155">Чтобы помочь организовать задачи по мере необходимости, просмотрите Контрольный список операций, необходимых для выполнения задач.</span><span class="sxs-lookup"><span data-stu-id="d26a4-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d26a4-156">Подробное описание процедур администрирования и управления можно найти в руководстве по администрированию Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26a4-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="d26a4-157">Резервное копирование (и восстановление) политик или параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="d26a4-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="d26a4-158">Lync Server 2013 обеспечивает резервное копирование и восстановление всей системы.</span><span class="sxs-lookup"><span data-stu-id="d26a4-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="d26a4-159">IIf, для которого нужно создать резервную копию (и, возможно, удастся восстановить) единственной политики или единственной коллекцией параметров конфигурации, получить соответствующую политику, а затем передать этот объект в командлет Export-Кликсмл, который сохранит сведения о политике в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="d26a4-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="d26a4-160">Теперь вы можете поэкспериментировать с Редмондклиентполици и изменить множество параметров.</span><span class="sxs-lookup"><span data-stu-id="d26a4-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="d26a4-161">Если вы решите восстановить старую политику, введите:</span><span class="sxs-lookup"><span data-stu-id="d26a4-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="d26a4-162">Обратите внимание, что этот подход работает для большинства политик и параметров, но он не будет работать с некоторыми более сложными элементами — элементами, которые содержат несколько подобъектов (например, параметры конфигурации маршрутизации, которые содержат множество отдельных голосовых маршрутов).</span><span class="sxs-lookup"><span data-stu-id="d26a4-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

