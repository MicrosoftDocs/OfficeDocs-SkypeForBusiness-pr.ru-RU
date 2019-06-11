---
title: 'Lync Server 2013: аудио-и видеограничные серверы (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="e05b6-102">Пограничные серверы для аудио-и видеоустройств (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e05b6-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e05b6-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e05b6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e05b6-104">Служба "A/V Edge" обеспечивает способ предоставления внутренних пользователей (пользователей, вошедших в вашу организационную сеть) для совместного использования звуковых и видеофайлов с внешними пользователями (пользователям, которые не вошли в свою организационную сеть).</span><span class="sxs-lookup"><span data-stu-id="e05b6-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="e05b6-105">Помимо звуковых и видеофайлов, служба Edge/V также обеспечивает поддержку общего и обмена данными с рабочим столом.</span><span class="sxs-lookup"><span data-stu-id="e05b6-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="e05b6-106">Служба EDGE (A/V) главным образом управляется с помощью конфигурации Edge/V. Эти параметры позволяют управлять максимальной пропускной способностью, выделенной для каждого порта и пользователем, а также время, в течение которого маркер проверки подлинности может быть использован до того, как он должен быть обновлен.</span><span class="sxs-lookup"><span data-stu-id="e05b6-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="e05b6-107">Параметры конфигурации EDGE можно применять к сайтам и отдельным пограничным серверам (/V).</span><span class="sxs-lookup"><span data-stu-id="e05b6-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="e05b6-108">Когда вы определяете, какой набор параметров имеет приоритет, используйте следующее руководство:</span><span class="sxs-lookup"><span data-stu-id="e05b6-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="e05b6-109">Параметры, настроенные для области службы (то есть на отдельном сервере), имеют приоритет над всеми.</span><span class="sxs-lookup"><span data-stu-id="e05b6-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="e05b6-110">Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="e05b6-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="e05b6-111">Однако параметры области служб также будут заменять параметры области сайта.</span><span class="sxs-lookup"><span data-stu-id="e05b6-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="e05b6-112">Параметры в глобальной области будут использоваться только в том случае, если на отдельном сервере не настроены параметры службы и для сайта, на котором находится этот сервер, отсутствуют параметры сайта.</span><span class="sxs-lookup"><span data-stu-id="e05b6-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="e05b6-113">Служба EDGE (A/V) может управляться только с помощью Lync Server PowerShell и командлетов Ксаведжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="e05b6-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e05b6-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="e05b6-114">In This Section</span></span>

  - [<span data-ttu-id="e05b6-115">Возврат сведений о конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e05b6-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="e05b6-116">Создание и изменение коллекции параметров конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e05b6-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="e05b6-117">Удаление существующей коллекции параметров конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e05b6-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

