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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.
ms.openlocfilehash: 6e8b055889175a46c7b3846fd45a60819b963a9f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587385"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Добавление внутреннего IP-адреса пограничного сервера 2010

Используйте эту страницу для определения внутреннего IP-адреса и внутреннего полного доменного имени пограничного сервера.

- Во **внутреннем ip-адресе IPv4** введите IP-адрес edge Server, который необходимо добавить в пул.

- Во **внутреннем FQDN** введите полное доменное имя (FQDN) edge Server, который необходимо добавить в пул.

Указанное полное доменное имя должно быть идентичным имени компьютера, настроенном для этого сервера. По умолчанию имя компьютера, не присоединенного к домену, является кратким именем, а не полным доменным именем. Построитель топологии использует полные доменные имена, а не короткие имена. Поэтому необходимо настроить DNS_суффикс для имени компьютера, который следует использовать в качестве пограничного сервера, не присоединенного к домену. Дополнительные сведения о добавлении DNS-суффикса к имени компьютера см. в разделе [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)