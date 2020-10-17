---
title: 'Lync Server 2013: Управление конфигурацией'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507836"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="9e870-102">Управление конфигурацией в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e870-102">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e870-103">_**Последнее изменение темы:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="9e870-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="9e870-104">Управление конфигурацией — это процесс записи и отслеживания аппаратных и программных ресурсов и сведений о конфигурации системы.</span><span class="sxs-lookup"><span data-stu-id="9e870-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="9e870-105">Он обычно используется для отслеживания лицензий на программное обеспечение, поддержки стандартного аппаратного и программного обеспечения для клиентских компьютеров и серверов, а также определения стандартов именования для новых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="9e870-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="9e870-106">Управление конфигурацией обычно включает в себя следующие категории:</span><span class="sxs-lookup"><span data-stu-id="9e870-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="9e870-107">**Аппаратное обеспечение**     В этой категории отслеживаются компоненты оборудования, которыми владеет ИТ-организация, где находится оборудование и кто использует оборудование.</span><span class="sxs-lookup"><span data-stu-id="9e870-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="9e870-108">Эта информация позволяет Организации планировать и планировать обновления, поддерживать стандартные аппаратные сборки, сообщать о стоимости ИТ – ресурсов для целей учета и предотвращать хищение.</span><span class="sxs-lookup"><span data-stu-id="9e870-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="9e870-109">**Программное обеспечение**     Эта категория отслеживает программное обеспечение, установленное на каждом компьютере, Номера версий и место проведения лицензий.</span><span class="sxs-lookup"><span data-stu-id="9e870-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="9e870-110">Эта информация поможет спланировать обновления, чтобы убедиться, что программное обеспечение лицензировано, и определить наличие нелицензионного (и нелицензированного) программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9e870-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="9e870-111">**Стандартные сборки**     Эта категория отслеживает текущее стандартное построение для клиентских компьютеров и серверов, а также от того, соответствует ли клиентские компьютеры и серверы этому стандарту.</span><span class="sxs-lookup"><span data-stu-id="9e870-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="9e870-112">Определение и применение стандартных сборок способствует поддержке персонала, так как персонал обязан поддерживать только ограниченное число версий каждой части программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9e870-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="9e870-113">**Накопительные пакеты обновления и исправления**     Эта категория отслеживает, какие пакеты обновления проверены и утверждены для использования и какие компьютеры обновлены.</span><span class="sxs-lookup"><span data-stu-id="9e870-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="9e870-114">Эта информация важна для снижения риска компрометации компьютеров и обнаружения пользователей с установленными неодобренными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="9e870-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="9e870-115">**Сведения о**     конфигурации системы В этой категории отслеживается функция системы, взаимодействие между элементами системы и процессы, зависящие от системы, работающей в нормальном режиме.</span><span class="sxs-lookup"><span data-stu-id="9e870-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="9e870-116">Например, прокси-сервер стороннего производителя можно настроить на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="9e870-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="9e870-117">В случае сбоя в случае сбоя может потребоваться использовать для этого сервера зависимость прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9e870-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="9e870-118">Если прокси-сервер может быть настроен для связи с другим сервером переднего плана, зависимости и планы на непредвиденные случаи, скорее всего, будут изменены.</span><span class="sxs-lookup"><span data-stu-id="9e870-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="9e870-119">Реализация управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="9e870-119">Implementing configuration management</span></span>

<span data-ttu-id="9e870-120">Определив, какие элементы нуждаются в управлении, реализуйте управление конфигурацией, собирая данные и отчеты.</span><span class="sxs-lookup"><span data-stu-id="9e870-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="9e870-121">Самым простым подходом для малых организаций является сбор данных вручную (число и модель клиентских компьютеров, операционная система, установленное программное обеспечение) и сохранение их в документе Office Word или Office Excel.</span><span class="sxs-lookup"><span data-stu-id="9e870-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="9e870-122">Для больших, более сложных и постоянно меняющихся систем обнаружение активов и сбор подробных данных должно быть автоматизировано.</span><span class="sxs-lookup"><span data-stu-id="9e870-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="9e870-123">Определите, какая информация важна для Организации, и запишите ее в базу данных.</span><span class="sxs-lookup"><span data-stu-id="9e870-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="9e870-124">База данных управления конфигурацией — это удобное средство для поддержки персонала и управления в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="9e870-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="9e870-125">**Аудиты безопасности**     С помощью базы данных можно определять серверы, на которых работают системы Lync Server и клиентские компьютеры, на которых должны быть применены исправления, или у которых пропущена Установка пакета обновления или последних обновлений антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="9e870-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="9e870-126">Установка программного **обеспечения**     Определение версий клиентского программного обеспечения и их отслеживание поможет администраторам в планировании обновлений версий и новых установках, а также при помощи документации и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9e870-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="9e870-127">**Сведения о конфигурации**     Если вы сохраняете актуальный список всех параметров, которые были изменены по умолчанию, вы сможете быстро и эффективно устранять неполадки.</span><span class="sxs-lookup"><span data-stu-id="9e870-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="9e870-128">**Планирование обновлений**     Если Обзор емкости показывает, что на серверах баз данных Lync требуется дополнительное пространство для хранения, важно знать, имеет ли каждый сервер внутренний RAID-контроллер.</span><span class="sxs-lookup"><span data-stu-id="9e870-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="9e870-129">Если это так, то они будут одной и той же моделью.</span><span class="sxs-lookup"><span data-stu-id="9e870-129">If they do, then are they the same model?</span></span> <span data-ttu-id="9e870-130">У них одинаковое число установленных дисков?</span><span class="sxs-lookup"><span data-stu-id="9e870-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="9e870-131">В базе данных управления конфигурациями указывается тип диска, который можно установить, число и путь обновления в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="9e870-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="9e870-132">Средства, используемые для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="9e870-132">Tools used for configuration management</span></span>

<span data-ttu-id="9e870-133">Существует множество средств для обнаружения, аудита и создания отчетов об активах.</span><span class="sxs-lookup"><span data-stu-id="9e870-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="9e870-134">В этом разделе обсуждаются некоторые из этих средств.</span><span class="sxs-lookup"><span data-stu-id="9e870-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="9e870-135">**Автоматизированные сценарии**     Вы можете создавать простые сценарии для создания отчетов об элементах, таких как операционная система, уровень пакета обновления, а также наличие программного обеспечения на определенном наборе компьютеров.</span><span class="sxs-lookup"><span data-stu-id="9e870-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="9e870-136">Эти сценарии можно писать в соответствии с требованиями Организации.</span><span class="sxs-lookup"><span data-stu-id="9e870-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="9e870-137">Однако необходимое количество сценариев и их сложность могут усложнить создание и обслуживание сценариев.</span><span class="sxs-lookup"><span data-stu-id="9e870-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="9e870-138">**Автоматизированные средства**     В зависимости от размера организации и потребностей Организации можно использовать автоматизированные средства.</span><span class="sxs-lookup"><span data-stu-id="9e870-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="9e870-139">Такие инструменты, как Microsoft Endpoint Configuration Manager, включают стандартные шаблоны отчетов (такие как уровень пакета обновления), а также позволяют создавать настраиваемые отчеты, например, для настраиваемого приложения.</span><span class="sxs-lookup"><span data-stu-id="9e870-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="9e870-140">Диспетчер конфигурации конечных точек Майкрософт также можно использовать для создания отчетов о конфигурациях оборудования и программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9e870-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="9e870-141">Связь с управлением изменениями</span><span class="sxs-lookup"><span data-stu-id="9e870-141">Relationship with change management</span></span>

<span data-ttu-id="9e870-142">Управление конфигурацией тесно связано с управлением изменениями.</span><span class="sxs-lookup"><span data-stu-id="9e870-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="9e870-143">Управление конфигурацией определяет необходимость изменения и идентификации, а также записи, которые были внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="9e870-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="9e870-144">Например, базу данных управления конфигурацией можно использовать для идентификации серверов, которым требуется исправление.</span><span class="sxs-lookup"><span data-stu-id="9e870-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="9e870-145">После этого Управление изменениями определяет процесс применения исправления.</span><span class="sxs-lookup"><span data-stu-id="9e870-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="9e870-146">И наоборот, если выполняется развертывание нового накопительного пакета обновления, процесс управления изменениями должен предоставлять эту информацию в систему управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="9e870-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="9e870-147">Средства управления конфигурацией, скорее всего, должны быть настроены для определения нового программного обеспечения, чтобы они могли обнаруживать и отслеживать место и время развертывания программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="9e870-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

