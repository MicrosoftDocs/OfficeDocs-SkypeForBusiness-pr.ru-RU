---
title: Добавление внутреннего IP-адреса пограничного компьютера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: f14762642eb828e5fccd1fb436352e41263a6ed2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608416"
---
# <a name="add-edge-machine-internal-ip"></a>Добавление внутреннего IP-адреса пограничного компьютера

Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.

Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера. По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем. Построитель топологии использует полные доменные имена, а не короткие имена. Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену. Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)