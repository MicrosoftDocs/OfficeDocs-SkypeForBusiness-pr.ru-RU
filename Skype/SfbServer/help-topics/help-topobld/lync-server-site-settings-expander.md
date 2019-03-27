---
title: Расширитель параметров среды Lync Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: Чтобы изменить свойства существующего сайта, выполните следующие действия.
ms.openlocfilehash: 0c6caf08060a94836d0c14169e550634c26e7dc9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883470"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="77ac5-103">Расширитель параметров среды Lync Server</span><span class="sxs-lookup"><span data-stu-id="77ac5-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="77ac5-104">Чтобы изменить свойства существующего сайта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="77ac5-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="77ac5-105">Свойства сайта</span><span class="sxs-lookup"><span data-stu-id="77ac5-105">Site properties</span></span>

<span data-ttu-id="77ac5-106">В свойствах сайта можно изменить или изменение сайта Name (обязательный), описание (необязательно), Город (необязательный параметр), край, Округ (необязательно) и код страны или региона (необязательно).</span><span class="sxs-lookup"><span data-stu-id="77ac5-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="77ac5-107">Для получения дополнительных сведений о свойствах сайта видеть [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="77ac5-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="77ac5-108">Свойства маршрута федерации</span><span class="sxs-lookup"><span data-stu-id="77ac5-108">Federation Route properties</span></span>

<span data-ttu-id="77ac5-109">Чтобы задать назначение федеративного маршрута сайта, сначала необходимо включена функция на пограничный сервер или пул пограничного сервера федерации.</span><span class="sxs-lookup"><span data-stu-id="77ac5-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="77ac5-110">Если федерация не включен на пограничный сервер или пул, параметры назначение маршрута федерации для сайта не будет доступен для изменения.</span><span class="sxs-lookup"><span data-stu-id="77ac5-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="77ac5-111">Если параметр федерации на пограничном сервере или пуле был настроен, установите флажок **Включить** на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="77ac5-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="77ac5-112">Выберите пункт пограничных серверов или Директор из раскрывающегося списка, чтобы установить в качестве маршрута федерации.</span><span class="sxs-lookup"><span data-stu-id="77ac5-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="77ac5-113">Этот параметр повлияет на всех сайтах.</span><span class="sxs-lookup"><span data-stu-id="77ac5-113">This setting will affect all sites.</span></span> <span data-ttu-id="77ac5-114">Убедитесь, что параметр, который настраивается на этом сайте подходит для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="77ac5-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="77ac5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="77ac5-115">See also</span></span>

<span data-ttu-id="77ac5-116">Дополнительные сведения см [топологии для доступа внешних пользователей](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="77ac5-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


