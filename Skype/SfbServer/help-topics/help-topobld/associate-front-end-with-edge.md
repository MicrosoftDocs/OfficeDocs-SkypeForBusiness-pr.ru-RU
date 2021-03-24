---
title: Связывание сервера переднего плана с пограничным
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: Каждый пул переднего конца может иметь только один пул Edge Server или Edge, связанный с ним. При впуске внешнего доступа к пользователю для сайта можно обеспечить поддержку удаленных пользователей. Вы также можете включить поддержку федеранных пользователей, которая может включать поддержку пользователей определенных поставщиков подключений для обмена мгновенными сообщениями (например, Windows Live) и поддержку анонимных пользователей.
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103225"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="f2595-105">Связывание сервера переднего плана с пограничным сервером</span><span class="sxs-lookup"><span data-stu-id="f2595-105">Associate Front End With Edge</span></span>

<span data-ttu-id="f2595-106">Каждый пул переднего конца может иметь только один пул Edge Server или Edge, связанный с ним.</span><span class="sxs-lookup"><span data-stu-id="f2595-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="f2595-107">При впуске внешнего доступа к пользователю для сайта можно обеспечить поддержку удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2595-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="f2595-108">Вы также можете включить поддержку федеранных пользователей, которая может включать поддержку пользователей определенных поставщиков подключений для обмена мгновенными сообщениями (например, Windows Live) и поддержку анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2595-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="f2595-109">Все пулы на сайте, а также пулы нескольких центральных сайтов, могут использовать один и тот же пограничный сервер, если мощность пограничного сервера позволяет это сделать.</span><span class="sxs-lookup"><span data-stu-id="f2595-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="f2595-110">Дополнительные сведения о мониторинге, включая масштабирование, см. в разделе [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f2595-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="f2595-111">Сведения о разработке топологии для поддержки доступа внешних пользователей см. в разделе [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f2595-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>