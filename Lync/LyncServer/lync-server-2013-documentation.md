---
title: 'Lync Server 2013: Документация'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2785391f93f2844809aaad06e4efff9c2e86505d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501176"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="c1107-102">Документация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1107-102">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1107-103">_**Последнее изменение темы:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c1107-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="c1107-104">Модель MOF состоит из многих функций управления службами.</span><span class="sxs-lookup"><span data-stu-id="c1107-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="c1107-105">Документация о том, как и когда выполняются задачи, могут быть предоставлены участникам одной и той же команды или с другими командами.</span><span class="sxs-lookup"><span data-stu-id="c1107-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="c1107-106">Способ хранения и совместного использования документации может различаться в зависимости от типа функции.</span><span class="sxs-lookup"><span data-stu-id="c1107-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="c1107-107">Например, процедуры для администрирования системы могут храниться в виде документов Word, так как они, скорее всего, будут напечатаны и часто ссылаются.</span><span class="sxs-lookup"><span data-stu-id="c1107-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="c1107-108">Сведения об управлении конфигурацией могут автоматически создаваться и храниться в базе данных для упрощения поиска и индексирования.</span><span class="sxs-lookup"><span data-stu-id="c1107-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="c1107-109">Некоторые документы могут быть конфиденциальными и должны быть ограничены.</span><span class="sxs-lookup"><span data-stu-id="c1107-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="c1107-110">Системы управления документами</span><span class="sxs-lookup"><span data-stu-id="c1107-110">Document management systems</span></span>

<span data-ttu-id="c1107-111">Система управления документацией выступает в качестве центрального репозитория для документов и гарантирует, что доступна только последняя версия документа.</span><span class="sxs-lookup"><span data-stu-id="c1107-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="c1107-112">Вы также можете использовать архивацию предыдущей версии документа для справки.</span><span class="sxs-lookup"><span data-stu-id="c1107-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="c1107-113">Lync Server предоставляет функциональные возможности, которые подходят для этой задачи.</span><span class="sxs-lookup"><span data-stu-id="c1107-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="c1107-114">Databases</span><span class="sxs-lookup"><span data-stu-id="c1107-114">Databases</span></span>

<span data-ttu-id="c1107-115">Обсуждалось несколько средств и функций управления, которые подходят для использования баз данных.</span><span class="sxs-lookup"><span data-stu-id="c1107-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="c1107-116">Процесс управления конфигурацией, скорее всего, использует автоматические процессы для хранения больших объемов данных, требующих индексирования и поиска.</span><span class="sxs-lookup"><span data-stu-id="c1107-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="c1107-117">Сотрудники службы поддержки могут выполнять поиск в базе данных с прошлыми проблемами и решениями при устранении новых проблем.</span><span class="sxs-lookup"><span data-stu-id="c1107-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="c1107-118">Скорее всего, для разных целей будут использоваться разные базы данных.</span><span class="sxs-lookup"><span data-stu-id="c1107-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="c1107-119">Определите, должны ли эти базы данных быть связаны или объединены.</span><span class="sxs-lookup"><span data-stu-id="c1107-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="c1107-120">Например, если служба поддержки определяет несколько проблем с общей темой (например, при возникновении проблемы с определенным сетевым адаптером), сотрудники службы поддержки могут запрашивать базу данных конфигурации, чтобы предсказать количество компьютеров, на которые может повлиять.</span><span class="sxs-lookup"><span data-stu-id="c1107-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

