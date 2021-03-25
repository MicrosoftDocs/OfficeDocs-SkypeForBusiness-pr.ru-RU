---
title: Связывание сервера переднего плана с пограничным
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: Каждый пул переднего конца может иметь только один пул Edge Server или Edge, связанный с ним. При впуске внешнего доступа к пользователю для сайта можно обеспечить поддержку удаленных пользователей. Вы также можете включить поддержку федеранных пользователей, которая может включать поддержку пользователей определенных поставщиков подключений для обмена мгновенными сообщениями (например, Windows Live) и поддержку анонимных пользователей.
ms.openlocfilehash: a70949bc72684aa5896c09bab39bc77b405bd206
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122640"
---
# <a name="associate-front-end-with-edge"></a>Связывание сервера переднего плана с пограничным сервером

Каждый пул переднего конца может иметь только один пул Edge Server или Edge, связанный с ним. При впуске внешнего доступа к пользователю для сайта можно обеспечить поддержку удаленных пользователей. Вы также можете включить поддержку федеранных пользователей, которая может включать поддержку пользователей определенных поставщиков подключений для обмена мгновенными сообщениями (например, Windows Live) и поддержку анонимных пользователей.

Все пулы на сайте, а также пулы нескольких центральных сайтов, могут использовать один и тот же пограничный сервер, если мощность пограничного сервера позволяет это сделать. Дополнительные сведения о мониторинге, включая масштабирование, см. в разделе [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) руководства по развертыванию. Сведения о разработке топологии для поддержки доступа внешних пользователей см. в разделе [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) руководства по развертыванию.