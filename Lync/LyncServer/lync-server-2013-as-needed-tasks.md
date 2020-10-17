---
title: 'Lync Server 2013: необходимые задачи'
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
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529546"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="4ca4a-102">Задачи, необходимые для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ca4a-102">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ca4a-103">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="4ca4a-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="4ca4a-104">При необходимости выполните следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="4ca4a-105">Кроме того, для них часто используются стандартные процедуры:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="4ca4a-106">**Аудит полного уровня безопасности   ** Этот аудит можно выполнять регулярно, в ответ на обновление или изменение системы обмена сообщениями или в ответ на попытку (или успешное) нарушения безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="4ca4a-107">Эта процедура может включать сканирование портов на серверах и брандмауэрах, аудит исправлений системы безопасности и тесты возможности проникновения в систему сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="4ca4a-108">**Замена сертификатов сроком действия**     Проверка сертификатов Lync Server является одной из регулярных еженедельных задач, и в процессе выполнения процедуры администратор должен иметь запись об истечении срока действия всех сертификатов.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="4ca4a-109">Эта запись позволяет администратору создавать уведомление, когда срок действия определенного сертификата скоро истечет и он будет заменен при необходимости.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="4ca4a-110">**Обновление базовых показателей производительности**     Обновление базовых показателей производительности после обновления или изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="4ca4a-111">В Организации можно использовать базовые уровни для измерения изменений производительности и обнаружения проблем, влияющих на производительность системы.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="4ca4a-112">**Управление корпоративным пулом**     Начальная настройка пулов предприятия, серверов Standard Edition и других серверов в среде организации выполнялась во время развертывания отдельных серверов.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="4ca4a-113">Ниже перечислены задачи, выполняемые после развертывания серверов и пулов для серверов Standard Edition и пулов предприятия.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="4ca4a-114">Управление серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="4ca4a-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="4ca4a-115">Управление веб-конференциями</span><span class="sxs-lookup"><span data-stu-id="4ca4a-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="4ca4a-116">Управление конференц-связью</span><span class="sxs-lookup"><span data-stu-id="4ca4a-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="4ca4a-117">Изменение учетных данных учетной записи службы</span><span class="sxs-lookup"><span data-stu-id="4ca4a-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="4ca4a-118">Управление базами данных</span><span class="sxs-lookup"><span data-stu-id="4ca4a-118">Managing Databases</span></span>
    
      - <span data-ttu-id="4ca4a-119">Запуск и остановка служб и отключение ролей сервера</span><span class="sxs-lookup"><span data-stu-id="4ca4a-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="4ca4a-120">Удаление серверов и ролей серверов, удаление пулов и списание серверов и пулов</span><span class="sxs-lookup"><span data-stu-id="4ca4a-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="4ca4a-121">**Управление использованием**     Вы можете настроить Lync Server 2013, чтобы предоставить функции и функции, наиболее подходящие для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="4ca4a-122">Эта кнопка предоставляет доступ ко следующим командам:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-122">This includes the following:</span></span>
    
      - <span data-ttu-id="4ca4a-123">Управление поддержкой локальных собраний веб-конференций</span><span class="sxs-lookup"><span data-stu-id="4ca4a-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="4ca4a-124">Управление использованием групп рассылки для отправки мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="4ca4a-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="4ca4a-125">Управление контактами, присутствием и запросами</span><span class="sxs-lookup"><span data-stu-id="4ca4a-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="4ca4a-126">Настройка фильтрации версий клиентов</span><span class="sxs-lookup"><span data-stu-id="4ca4a-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="4ca4a-127">Настройка интеллектуальной фильтрации мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="4ca4a-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="4ca4a-128">Настройка архивации, регистрации вызовов и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4ca4a-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="4ca4a-129">**Управление подключением**     пограничного сервера Непрерывное управление серверами и параметрами, необходимыми для обеспечения внешнего подключения, включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="4ca4a-130">Управление подключением между внутренними и пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="4ca4a-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="4ca4a-131">Настройка внутренних и внешних интерфейсов и сертификатов для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="4ca4a-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="4ca4a-132">Управление доступом к федеративным партнерам</span><span class="sxs-lookup"><span data-stu-id="4ca4a-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="4ca4a-133">**Администрирование адресной книги**     Администрирование серверов адресных книг состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="4ca4a-134">Настройка нормализации телефонной книги сервера</span><span class="sxs-lookup"><span data-stu-id="4ca4a-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="4ca4a-135">Управление сервером адресной книги с помощью командной строки</span><span class="sxs-lookup"><span data-stu-id="4ca4a-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="4ca4a-136">**Управление учетными записями пользователей**     Управление учетными записями пользователей включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="4ca4a-137">Включение учетных записей пользователей для Lync Server</span><span class="sxs-lookup"><span data-stu-id="4ca4a-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="4ca4a-138">Настройка пользователей Lync Server с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="4ca4a-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="4ca4a-139">Настройка отдельных свойств учетной записи пользователя Lync Server</span><span class="sxs-lookup"><span data-stu-id="4ca4a-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="4ca4a-140">Поиск пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="4ca4a-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="4ca4a-141">Перемещение пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="4ca4a-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="4ca4a-142">Удаление пользователей Lync Server</span><span class="sxs-lookup"><span data-stu-id="4ca4a-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="4ca4a-143">**Анализ файлов**     журнала Lync Server 2013 Одним из наиболее полезных средств, обычно используемых для устранения неполадок, является средство ведения журнала Lync Server 2013, подробно описанное в статье [Использование средства ведения журнала Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).</span><span class="sxs-lookup"><span data-stu-id="4ca4a-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="4ca4a-144">Так как средство ведения журнала создает файлы журналов (отдельно для каждого сервера), эти файлы журналов можно просматривать и анализировать с помощью средства snooper, если на компьютере установлены средства набора ресурсов Microsoft Office Server 12.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="4ca4a-145">В противном случае журналы также можно проанализировать с помощью текстового редактора, который является гораздо менее прозрачным и более сложным, чем использование служебной программы Snooper.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="4ca4a-146">Просмотр и анализ сообщений протокола</span><span class="sxs-lookup"><span data-stu-id="4ca4a-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="4ca4a-147">В средстве ведения журнала после завершения сеанса отладки щелкните Анализ файлов журнала для просмотра файлов журнала с помощью средства snooper.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="4ca4a-148">Журналы протокола можно анализировать для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="4ca4a-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="4ca4a-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="4ca4a-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="4ca4a-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="4ca4a-151">Трафик сигналов конференц-связи Lync Server (C3P), в том числе MCU, C3P и Focus C3P</span><span class="sxs-lookup"><span data-stu-id="4ca4a-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="4ca4a-152">Трафик веб-конференций Lync Server (PSOM)</span><span class="sxs-lookup"><span data-stu-id="4ca4a-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="4ca4a-153">Клиент клиентской платформы Объединенных коммуникаций Lync Server (UCCP)</span><span class="sxs-lookup"><span data-stu-id="4ca4a-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="4ca4a-154">Отчеты об ошибках из базы данных архивации</span><span class="sxs-lookup"><span data-stu-id="4ca4a-154">Error reports from the archiving database</span></span>

<span data-ttu-id="4ca4a-155">Чтобы помочь организовать задачи, выполняемые при необходимости, ознакомьтесь со статьей As-Needed контрольный список операций.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ca4a-156">Подробные процедуры администрирования и управления представлены в руководстве по администрированию Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="4ca4a-157">Резервное копирование (и восстановление) политик или параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="4ca4a-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="4ca4a-158">Lync Server 2013 позволяет выполнять резервное копирование и восстановление всей системы.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="4ca4a-159">IIf, для которого необходимо выполнить резервное копирование (а затем, возможно, однажды), одной политики или одной коллекции параметров конфигурации, извлечения соответствующей политики, а затем передать этот объект в командлет Export-Clixml, сохраняющий сведения о политике в виде XML-файла:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="4ca4a-160">Теперь вы можете поэкспериментировать с Редмондклиентполици и изменить множество параметров.</span><span class="sxs-lookup"><span data-stu-id="4ca4a-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="4ca4a-161">Если вы решили восстановить старую политику, введите:</span><span class="sxs-lookup"><span data-stu-id="4ca4a-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="4ca4a-162">Обратите внимание, что этот подход будет работать для большинства политик и параметров, но не будет работать с некоторыми более сложными элементами — элементами, содержащими несколько вложенных объектов (таких как параметры конфигурации маршрутизации, которые содержат множество отдельных маршрутов голосовой связи).</span><span class="sxs-lookup"><span data-stu-id="4ca4a-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

