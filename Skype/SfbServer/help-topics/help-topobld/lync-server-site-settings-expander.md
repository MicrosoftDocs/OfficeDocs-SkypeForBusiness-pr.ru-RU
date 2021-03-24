---
title: Расширитель параметров среды Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Чтобы изменить свойства существующего сайта, выполните следующие действия:'
ms.openlocfilehash: aedb248bf229af754d2ef8eb9c5e3837c69c808d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104455"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="bf1e8-103">Расширитель параметров среды Lync Server</span><span class="sxs-lookup"><span data-stu-id="bf1e8-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="bf1e8-104">Чтобы изменить свойства существующего сайта, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bf1e8-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="bf1e8-105">Свойства сайта</span><span class="sxs-lookup"><span data-stu-id="bf1e8-105">Site properties</span></span>

<span data-ttu-id="bf1e8-106">В свойствах сайта можно изменить имя (обязательный параметр), описание (необязательный параметр), город (необязательный параметр), область и регион (необязательный параметр), а также код страны или региона (необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="bf1e8-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="bf1e8-107">Дополнительные сведения о свойствах сайта см. в разделе [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span><span class="sxs-lookup"><span data-stu-id="bf1e8-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="bf1e8-108">Свойства маршрута федерации</span><span class="sxs-lookup"><span data-stu-id="bf1e8-108">Federation Route properties</span></span>

<span data-ttu-id="bf1e8-p101">Чтобы задать назначение маршрута федерации для сайта, сначала следует включить федерацию на пограничном сервере или в пуле пограничных серверов. Если федерация на пограничном сервере или в пуле не включена, параметры назначения маршрута федерации для сайта будут недоступны для изменения.</span><span class="sxs-lookup"><span data-stu-id="bf1e8-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="bf1e8-p102">Если на пограничном сервере или в пуле настроена федерация, выберите **Включить** на уровне сайтов. После этого выберите пограничный сервер или Директор в раскрывающемся списке, чтобы задать его в качестве маршрута федерации.</span><span class="sxs-lookup"><span data-stu-id="bf1e8-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="bf1e8-p103">Этот параметр охватывает все сайты. Убедитесь, что настройка данного сайта подходит для всех остальных сайтов.</span><span class="sxs-lookup"><span data-stu-id="bf1e8-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf1e8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bf1e8-115">See also</span></span>

<span data-ttu-id="bf1e8-116">Дополнительные сведения см. в разделе [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span><span class="sxs-lookup"><span data-stu-id="bf1e8-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>