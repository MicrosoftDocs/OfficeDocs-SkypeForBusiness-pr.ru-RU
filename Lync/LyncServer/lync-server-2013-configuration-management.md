---
title: 'Lync Server 2013: Управление конфигурацией'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="8cf3d-102">Управление конфигурацией в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cf3d-102">Configuration management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf3d-103">_**Тема последнего изменения:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="8cf3d-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="8cf3d-104">Управление конфигурацией — это процесс записи и отслеживания аппаратных и программных ресурсов и сведений о конфигурации системы.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="8cf3d-105">Она обычно используется для отслеживания лицензий на программное обеспечение, обслуживания стандартных аппаратных и программных сборок для клиентских компьютеров и серверов и определения стандартов именования для новых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="8cf3d-106">В управлении конфигурацией обычно рассматриваются следующие категории:</span><span class="sxs-lookup"><span data-stu-id="8cf3d-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="8cf3d-107">**Оборудование**   . в этой категории отслеживается оборудование, которому принадлежит ИТ – организация, где находится оборудование и кто пользуется оборудованием.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="8cf3d-108">Эта информация позволяет организациям планировать и возобновлять обновления, поддерживать стандартные сборки оборудования, сообщать о стоимости информационных ресурсов в целях учета и помогать в предотвращении хищения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="8cf3d-109">**Программное обеспечение**   . Эта категория отслеживает программное обеспечение, которое установлено на каждом компьютере, Номера версий и места проведения лицензий.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="8cf3d-110">Эти сведения помогают планировать обновления, обеспечивать лицензирование программного обеспечения и определять наличие неавторизованного (и нелицензированного) программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="8cf3d-111">**Стандартные сборки**   . Эта категория отслеживает текущую стандартную сборку для клиентских компьютеров и серверов, а также от того, соответствуют ли клиентские компьютеры и серверы этим стандарту.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="8cf3d-112">Определение и принудительное использование стандартных сборок помогает специалистам службы поддержки, так как персонал обязан поддерживать только ограниченное количество версий каждой части программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="8cf3d-113">**Накопительные обновления и исправления**   . Эта категория отслеживает, какие пакеты обновления проверены и утверждены для использования и для каких компьютеров установлены обновления.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="8cf3d-114">Эта информация важна для снижения риска нарушения безопасности компьютеров и обнаружения пользователей с установленными неодобренными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="8cf3d-115">**Сведения о**   конфигурации системы в этой категории отслеживается функция системы, взаимодействие между системными элементами и процессы, зависящие от системы, в которой выполняется плавный запуск.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="8cf3d-116">Например, прокси-сервер стороннего поставщика можно настроить на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="8cf3d-117">При возникновении сбоя может потребоваться, чтобы прокси-сервер был заблокирован на этом сервере и планы на непредвиденные случаи.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="8cf3d-118">Если прокси-сервер можно настроить так, чтобы он также мог взаимодействовать с другим сервером переднего плана, зависимости и планы на непредвиденные случаи, скорее всего, изменятся.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="8cf3d-119">Реализация управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="8cf3d-119">Implementing configuration management</span></span>

<span data-ttu-id="8cf3d-120">Определив элементы, необходимые для управления, реализуйте управление конфигурацией, собирая данные и отчеты.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="8cf3d-121">Самый простой подход для малых организаций — собирать данные вручную (номер и модель клиентских компьютеров, операционную систему, установленное программное обеспечение) и сохранять их в документе Office Word или Office Excel.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="8cf3d-122">Для более крупных, более сложных и постоянно меняющихся систем обнаружение ресурсов и сбор подробных данных должно выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="8cf3d-123">Определите, какая информация важна для вашей организации, и записывайте ее в базу данных.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="8cf3d-124">База данных управления конфигурацией — это полезный инструмент для поддержки персонала и управления в указанных ниже областях.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="8cf3d-125">**Аудит безопасности база**   данных позволяет идентифицировать серверы, на которых работают системы Lync Server и клиентские компьютеры, на которых должны быть установлены исправления или пропущены Установка пакета обновления или последних обновлений антивирусной программы.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="8cf3d-126">**Установка программного**   обеспечения определение версий клиентского программного обеспечения и их отслеживание помогает администраторам планировать обновления версий и новые установки, а также помогать в документации и соответствии требованиям.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="8cf3d-127">**Сведения о**   конфигурации если вы сохраняете актуальный список всех параметров, которые были изменены по умолчанию, вы сможете быстро и эффективно устранять проблемы.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="8cf3d-128">**Планирование обновлений**   если в ходе проверки производительности выясняется, что на серверах баз данных Lync требуется дополнительное дисковое пространство, важно знать, имеет ли каждый сервер внутренний RAID-контроллер.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="8cf3d-129">Если это так, то они являются одной и той же моделью.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-129">If they do, then are they the same model?</span></span> <span data-ttu-id="8cf3d-130">Установлено ли на них одинаковое число дисков?</span><span class="sxs-lookup"><span data-stu-id="8cf3d-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="8cf3d-131">База данных управления конфигурацией будет указывать тип диска, который можно установить, номер и путь обновления в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="8cf3d-132">Инструменты, используемые для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="8cf3d-132">Tools used for configuration management</span></span>

<span data-ttu-id="8cf3d-133">Существует множество инструментов для работы с ресурсами, аудита и создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="8cf3d-134">Некоторые из этих средств обсуждаются в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="8cf3d-135">**Автоматические сценарии**   . Вы можете создавать простые сценарии для создания отчетов о таких элементах, как операционная система, уровень пакета обновления, а также сведения о том, существует ли программное обеспечение на определенном наборе компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="8cf3d-136">Эти сценарии можно писать на конкретные требования Организации.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="8cf3d-137">Тем не менее, требуемое количество сценариев и их сложность может усложнить создание и обслуживание сценариев.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="8cf3d-138">**Автоматические инструменты**   , зависящие от размера вашего бизнеса и потребностей Организации, вы можете использовать автоматизированные средства.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="8cf3d-139">Такие инструменты, как Microsoft Endpoint Configuration Manager, включают стандартные шаблоны отчетов (например, уровень пакета обновления), а также позволяют создавать пользовательские отчеты, например, для пользовательского приложения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="8cf3d-140">Диспетчер конфигурации конечных точек Майкрософт также можно использовать для создания отчетов о конфигурациях оборудования и программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="8cf3d-141">Связь с управлением изменениями</span><span class="sxs-lookup"><span data-stu-id="8cf3d-141">Relationship with change management</span></span>

<span data-ttu-id="8cf3d-142">Управление конфигурацией тесно связано с управлением изменениями.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="8cf3d-143">Управление конфигурацией определяет необходимость изменения и идентификации и записи, внесенные в ходе изменения.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="8cf3d-144">Например, можно использовать базу данных управления конфигурацией для идентификации серверов, которым требуется исправление.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="8cf3d-145">Управление изменениями затем определяет процесс применения исправления.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="8cf3d-146">И наоборот, если вы выйдете новое накопительное обновление, процесс управления изменениями должен предоставить эту информацию системе управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="8cf3d-147">Средства управления конфигурацией, скорее всего, должны быть настроены для идентификации нового программного обеспечения, чтобы они могли находить и отслеживать, где и когда развертывается программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="8cf3d-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

