---
title: Добавление внутреннего IP-адреса пограничного компьютера
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: ec5d4b603fe32aa209aeb31c196382c8747caa3f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841701"
---
# <a name="add-edge-machine-internal-ip"></a>Добавление внутреннего IP-адреса пограничного компьютера

Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.

Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера. По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем. Построитель топологии использует полные доменные имена, а не короткие имена. Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену. Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)