---
title: 'Lync Server 2013: параметры групповой политики для Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="53275-102">Параметры групповой политики для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53275-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53275-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="53275-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="53275-104">В предыдущих версиях Lync и Office Communicator вы можете настроить параметры групповой политики клиента с помощью отдельного административного шаблона Communicator. adm.</span><span class="sxs-lookup"><span data-stu-id="53275-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="53275-105">Для Lync 2013 новые файлы административных шаблонов (ADMX и ADML) включаются вместе с административным шаблоном групповой политики Office.</span><span class="sxs-lookup"><span data-stu-id="53275-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="53275-106">Доступность файлов Lync 2013. ADMX и. ADML позволяет загружать шаблоны и централизованно управлять параметрами групповой политики для всех программ Office и языковых пакетов.</span><span class="sxs-lookup"><span data-stu-id="53275-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="53275-107">Подробные сведения можно найти в разделе "файлы административных шаблонов Office 2013 (ADMX, ADML)" в документации Office 2013 <http://go.microsoft.com/fwlink/p/?linkid=267516>по адресу.</span><span class="sxs-lookup"><span data-stu-id="53275-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="53275-108">Политики начальной загрузки клиента</span><span class="sxs-lookup"><span data-stu-id="53275-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="53275-109">Существует несколько политик начальной настройки клиентов, которые необходимо настроить, прежде чем пользователи будут впервые входить на сервер.</span><span class="sxs-lookup"><span data-stu-id="53275-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="53275-110">Поскольку эти политики вступают в силу перед входом клиента и начинают получать параметры подготовки по каналу с сервера, вы можете настроить их с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="53275-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="53275-111">Дополнительные сведения можно найти в разделе [Настройка политик начальной настройки клиента в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="53275-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

