---
title: Добавление связей переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:'
ms.openlocfilehash: f269b51477dce0d502c1ca00956f4a25bfc124f2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689338"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="21688-105">Добавление связей переднего плана</span><span class="sxs-lookup"><span data-stu-id="21688-105">Add Front End Associations</span></span>

<span data-ttu-id="21688-p102">Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="21688-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="21688-p103">Пограничный сервер аудио- и видеоданных. Дополнительные сведения о реализации пограничного сервера аудио- и видеоданных см. в разделе [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="21688-p103">A/V Edge Server. For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21688-p104">Если на этом этапе включить поддержку каких-либо из этих функциональных возможностей, публикуемая топологическая схема будет содержать серверные компоненты, необходимые для реализации каждой из выбранных возможностей. Для успешной публикации топологии физические компьютеры должны быть присоединены к домену. Например, если на этом этапе включить поддержку архивации, обмен данными для архивации в данной организации будет возможен только после развертывания сервера архивации и надлежащей настройки параметров архивации.</span><span class="sxs-lookup"><span data-stu-id="21688-p104">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature. For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain. For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


