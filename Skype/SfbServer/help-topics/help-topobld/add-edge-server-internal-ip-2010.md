---
title: Добавление внутреннего IP-адреса пограничного сервера 2010
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: c8e6c7fb4722d7d6e8b9b01057dc38d64cfe557e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103345"
---
# <a name="add-edge-server-internal-ip-2010"></a>Добавление внутреннего IP-адреса пограничного сервера 2010

Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.

Этот FQDN, который вы указываете, должен быть идентичен имени компьютера, настроенного на сервере. По умолчанию имя компьютера, который не присоединен к домену, является коротким, а не полным доменным именем. Построитель топологии использует полные доменные имена, а не короткие имена. Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену. Дополнительные сведения о добавлении суффикса DNS в имя компьютера см. в [материале Configure DNS for Edge Support.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)