---
title: 'Lync Server 2013: необходимые задачи'
description: 'Lync Server 2013: необходимые задачи.'
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
ms.openlocfilehash: 91fe249d9615bb619426c58b22606c3ef182f9a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560005"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="e4424-103">Задачи, необходимые для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4424-103">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4424-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="e4424-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="e4424-105">При необходимости выполните следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="e4424-105">Perform the following tasks as necessary.</span></span> <span data-ttu-id="e4424-106">Кроме того, для них часто используются стандартные процедуры:</span><span class="sxs-lookup"><span data-stu-id="e4424-106">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="e4424-107">**Аудит полного уровня безопасности   ** Этот аудит можно выполнять регулярно, в ответ на обновление или изменение системы обмена сообщениями или в ответ на попытку (или успешное) нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="e4424-107">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="e4424-108">Эта процедура может включать сканирование портов на серверах и брандмауэрах, аудит исправлений системы безопасности и тесты возможности проникновения в систему сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="e4424-108">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="e4424-109">**Замена сертификатов сроком действия**     Проверка сертификатов Lync Server является одной из регулярных еженедельных задач, и в процессе выполнения процедуры администратор должен иметь запись об истечении срока действия всех сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e4424-109">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="e4424-110">Эта запись позволяет администратору создавать уведомление, когда срок действия определенного сертификата скоро истечет и он будет заменен при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e4424-110">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="e4424-111">**Обновление базовых показателей производительности**     Обновление базовых показателей производительности после обновления или изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4424-111">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="e4424-112">В Организации можно использовать базовые уровни для измерения изменений производительности и обнаружения проблем, влияющих на производительность системы.</span><span class="sxs-lookup"><span data-stu-id="e4424-112">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="e4424-113">**Управление корпоративным пулом**     Начальная настройка пулов предприятия, серверов Standard Edition и других серверов в среде организации выполнялась во время развертывания отдельных серверов.</span><span class="sxs-lookup"><span data-stu-id="e4424-113">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="e4424-114">Ниже перечислены задачи, выполняемые после развертывания серверов и пулов для серверов Standard Edition и пулов предприятия.</span><span class="sxs-lookup"><span data-stu-id="e4424-114">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="e4424-115">Управление серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="e4424-115">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="e4424-116">Управление веб-конференциями</span><span class="sxs-lookup"><span data-stu-id="e4424-116">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="e4424-117">Управление конференц-связью</span><span class="sxs-lookup"><span data-stu-id="e4424-117">Managing Conferencing</span></span>
    
      - <span data-ttu-id="e4424-118">Изменение учетных данных учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="e4424-118">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="e4424-119">Управление базами данных</span><span class="sxs-lookup"><span data-stu-id="e4424-119">Managing Databases</span></span>
    
      - <span data-ttu-id="e4424-120">Запуск и остановка служб и отключение ролей сервера</span><span class="sxs-lookup"><span data-stu-id="e4424-120">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="e4424-121">Удаление серверов и ролей серверов, удаление пулов и списание серверов и пулов</span><span class="sxs-lookup"><span data-stu-id="e4424-121">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="e4424-122">**Управление использованием**     Вы можете настроить Lync Server 2013, чтобы предоставить функции и функции, наиболее подходящие для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e4424-122">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="e4424-123">Эта кнопка предоставляет доступ ко следующим командам:</span><span class="sxs-lookup"><span data-stu-id="e4424-123">This includes the following:</span></span>
    
      - <span data-ttu-id="e4424-124">Управление поддержкой локальных собраний веб-конференций</span><span class="sxs-lookup"><span data-stu-id="e4424-124">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="e4424-125">Управление использованием групп рассылки для отправки мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="e4424-125">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="e4424-126">Управление контактами, присутствием и запросами</span><span class="sxs-lookup"><span data-stu-id="e4424-126">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="e4424-127">Настройка фильтрации версий клиентов</span><span class="sxs-lookup"><span data-stu-id="e4424-127">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="e4424-128">Настройка интеллектуальной фильтрации мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="e4424-128">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="e4424-129">Настройка архивации, регистрации вызовов и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="e4424-129">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="e4424-130">**Управление подключением**     пограничного сервера Непрерывное управление серверами и параметрами, необходимыми для обеспечения внешнего подключения, включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="e4424-130">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="e4424-131">Управление подключением между внутренними и пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="e4424-131">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="e4424-132">Настройка внутренних и внешних интерфейсов и сертификатов для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="e4424-132">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="e4424-133">Управление доступом к федеративным партнерам</span><span class="sxs-lookup"><span data-stu-id="e4424-133">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="e4424-134">**Администрирование адресной книги**     Администрирование серверов адресных книг состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e4424-134">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="e4424-135">Настройка нормализации телефонной книги сервера</span><span class="sxs-lookup"><span data-stu-id="e4424-135">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="e4424-136">Управление сервером адресной книги с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="e4424-136">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="e4424-137">**Управление учетными записями пользователей**     Управление учетными записями пользователей включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="e4424-137">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="e4424-138">Включение учетных записей пользователей для Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4424-138">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="e4424-139">Настройка пользователей Lync Server с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="e4424-139">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="e4424-140">Настройка отдельных свойств учетной записи пользователя Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4424-140">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="e4424-141">Поиск пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4424-141">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="e4424-142">Перемещение пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4424-142">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="e4424-143">Удаление пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="e4424-143">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="e4424-144">**Анализ файлов**     журнала Lync Server 2013 Одним из наиболее полезных средств, обычно используемых для устранения неполадок, является средство ведения журнала Lync Server 2013, подробно описанное в статье [Использование средства ведения журнала Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4424-144">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="e4424-145">Так как средство ведения журнала создает файлы журналов (отдельно для каждого сервера), эти файлы журналов можно просматривать и анализировать с помощью средства snooper, если на компьютере установлены средства набора ресурсов Microsoft Office Server 12.</span><span class="sxs-lookup"><span data-stu-id="e4424-145">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="e4424-146">В противном случае журналы также можно проанализировать с помощью текстового редактора, который является гораздо менее прозрачным и более сложным, чем использование служебной программы Snooper.</span><span class="sxs-lookup"><span data-stu-id="e4424-146">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="e4424-147">Просмотр и анализ сообщений протокола</span><span class="sxs-lookup"><span data-stu-id="e4424-147">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="e4424-148">В средстве ведения журнала после завершения сеанса отладки щелкните Анализ файлов журнала для просмотра файлов журнала с помощью средства snooper.</span><span class="sxs-lookup"><span data-stu-id="e4424-148">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="e4424-149">Журналы протокола можно анализировать для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e4424-149">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="e4424-150">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="e4424-150">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="e4424-151">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="e4424-151">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="e4424-152">Трафик сигналов конференц-связи Lync Server (C3P), в том числе MCU, C3P и Focus C3P</span><span class="sxs-lookup"><span data-stu-id="e4424-152">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="e4424-153">Трафик веб-конференций Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="e4424-153">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="e4424-154">Клиент клиентской платформы Объединенных коммуникаций Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="e4424-154">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="e4424-155">Отчеты об ошибках из базы данных архивации</span><span class="sxs-lookup"><span data-stu-id="e4424-155">Error reports from the archiving database</span></span>

<span data-ttu-id="e4424-156">Чтобы помочь организовать задачи, выполняемые при необходимости, ознакомьтесь со статьей As-Needed контрольный список операций.</span><span class="sxs-lookup"><span data-stu-id="e4424-156">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4424-157">Подробные процедуры администрирования и управления представлены в руководстве по администрированию Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4424-157">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="e4424-158">Резервное копирование (и восстановление) политик или параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="e4424-158">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="e4424-159">Lync Server 2013 позволяет выполнять резервное копирование и восстановление всей системы.</span><span class="sxs-lookup"><span data-stu-id="e4424-159">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="e4424-160">IIf, для которого необходимо выполнить резервное копирование (а затем, возможно, однажды), одной политики или одной коллекции параметров конфигурации, извлечения соответствующей политики, а затем передать этот объект в командлет Export-Clixml, сохраняющий сведения о политике в виде XML-файла:</span><span class="sxs-lookup"><span data-stu-id="e4424-160">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="e4424-161">Теперь вы можете поэкспериментировать с Редмондклиентполици и изменить множество параметров.</span><span class="sxs-lookup"><span data-stu-id="e4424-161">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="e4424-162">Если вы решили восстановить старую политику, введите:</span><span class="sxs-lookup"><span data-stu-id="e4424-162">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="e4424-163">Обратите внимание, что этот подход будет работать для большинства политик и параметров, но не будет работать с некоторыми более сложными элементами — элементами, содержащими несколько вложенных объектов (таких как параметры конфигурации маршрутизации, которые содержат множество отдельных маршрутов голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="e4424-163">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

