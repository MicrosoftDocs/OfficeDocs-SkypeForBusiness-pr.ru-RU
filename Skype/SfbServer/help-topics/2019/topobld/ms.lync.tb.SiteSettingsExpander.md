---
title: Расширитель параметров среды Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить свойства существующего сайта, выполните указанные ниже действия.
ms.openlocfilehash: 20c74cd3842137df5dce35647bdb5ad28b89b4e0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687972"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="8c56b-103">Расширитель параметров среды Lync Server</span><span class="sxs-lookup"><span data-stu-id="8c56b-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="8c56b-104">Чтобы изменить свойства существующего сайта, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8c56b-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="8c56b-105">Свойства сайта</span><span class="sxs-lookup"><span data-stu-id="8c56b-105">Site properties</span></span>

<span data-ttu-id="8c56b-106">В свойствах сайта вы можете изменить или изменить название сайта (обязательно), описание (необязательно), город (необязательно), область или район (необязательно), а также код страны или региона (необязательно).</span><span class="sxs-lookup"><span data-stu-id="8c56b-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="8c56b-107">Дополнительные сведения о свойствах сайта [можно найти в разделе Добавление сайтов филиалов в топологию](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c56b-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="8c56b-108">Свойства маршрута Федерации</span><span class="sxs-lookup"><span data-stu-id="8c56b-108">Federation Route properties</span></span>

<span data-ttu-id="8c56b-109">Для задания назначения маршрута Федерации сайта необходимо сначала включить федерацию на пограничном сервере или в пуле пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8c56b-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="8c56b-110">Если на пограничном сервере или в пуле не включена Федерация, параметры назначения маршрутов Федерации для сайта не будут доступны для изменения.</span><span class="sxs-lookup"><span data-stu-id="8c56b-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="8c56b-111">Если параметр Федерации на пограничном сервере или в пуле настроен, выберите **включить** на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="8c56b-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="8c56b-112">Затем выберите в раскрывающемся списке ребро или режиссера, которое будет указано как маршрут Федерации.</span><span class="sxs-lookup"><span data-stu-id="8c56b-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="8c56b-113">Этот параметр будет применяться ко всем сайтам.</span><span class="sxs-lookup"><span data-stu-id="8c56b-113">This setting will affect all sites.</span></span> <span data-ttu-id="8c56b-114">Убедитесь, что параметр, который вы настраиваете на этом сайте, подходит для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="8c56b-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c56b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8c56b-115">See also</span></span>

<span data-ttu-id="8c56b-116">Дополнительные сведения можно найти в разделе [топологии для доступа внешних пользователей](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c56b-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


