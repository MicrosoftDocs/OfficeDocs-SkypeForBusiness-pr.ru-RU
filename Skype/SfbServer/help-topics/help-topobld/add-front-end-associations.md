---
title: Добавление связей переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:'
ms.openlocfilehash: 13d796bd5c33b0f56ebc43ba11f82a188cce0c76
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218390"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="a5312-105">Добавление связей переднего плана</span><span class="sxs-lookup"><span data-stu-id="a5312-105">Add Front End Associations</span></span>

<span data-ttu-id="a5312-p102">Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="a5312-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="a5312-109">Пограничный сервер аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="a5312-109">A/V Edge Server.</span></span> <span data-ttu-id="a5312-110">Дополнительные сведения о внедрении пограничного сервера аудио- и видеоданных см. в разделе [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a5312-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5312-111">Если вы сейчас включите поддержку для любой из этих возможностей, публикуемая структура топологии будет содержать серверные компоненты, требуемые для внедрения каждой из выбранных возможностей.</span><span class="sxs-lookup"><span data-stu-id="a5312-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="a5312-112">Для успешной публикации топологии следует присоединить физические компьютеры к домену.</span><span class="sxs-lookup"><span data-stu-id="a5312-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="a5312-113">Например, если включить поддержку архивации сейчас, необходимо развернуть сервер архивации и настроить соответствующие параметры архивации перед началом архивации данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="a5312-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


