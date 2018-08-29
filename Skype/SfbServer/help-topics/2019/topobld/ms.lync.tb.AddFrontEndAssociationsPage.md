---
title: Добавление связей переднего плана
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:'
ms.openlocfilehash: 01acce8ab01d132a11a8e01ef09c9e26c9830a6a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23242192"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="2a373-105">Добавление связей переднего плана</span><span class="sxs-lookup"><span data-stu-id="2a373-105">Add Front End Associations</span></span>

<span data-ttu-id="2a373-p102">Вы можете включить поддержку для отдельных возможностей, требующих развертывания других серверов, сопоставив роли сервера с интерфейсным пулом как прямо сейчас, так и позднее. К ролям сервера, которые можно сопоставить с интерфейсным пулом, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="2a373-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="2a373-109">Пограничный сервер аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="2a373-109">A/V Edge Server.</span></span> <span data-ttu-id="2a373-110">Для получения дополнительных сведений о реализации A / V Edge Server см [конференц-связи](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="2a373-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a373-p104">Если на этом этапе включить поддержку каких-либо из этих функциональных возможностей, публикуемая топологическая схема будет содержать серверные компоненты, необходимые для реализации каждой из выбранных возможностей. Для успешной публикации топологии физические компьютеры должны быть присоединены к домену. Например, если на этом этапе включить поддержку архивации, обмен данными для архивации в данной организации будет возможен только после развертывания сервера архивации и надлежащей настройки параметров архивации.</span><span class="sxs-lookup"><span data-stu-id="2a373-p104">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature. For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain. For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


