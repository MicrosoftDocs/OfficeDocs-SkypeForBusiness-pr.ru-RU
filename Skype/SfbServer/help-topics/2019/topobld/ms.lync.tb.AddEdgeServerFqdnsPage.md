---
title: Добавление полного доменного имени пограничного сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
ROBOTS: NOINDEX, NOFOLLOW
description: Необходимо указать полное доменное имя службы пограничного доступа. Если на странице "Выбор компонентов" не выбран параметр "Использовать один ip-адрес FQDN", необходимо также указать FQDN для службы веб-конференций и для службы &amp; A/V Edge.
ms.openlocfilehash: b54e496ca90372c815b850bf87800e73dd354a11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835929"
---
# <a name="add-edge-server-fqdn"></a>Добавление полного доменного имени пограничного сервера
 
Необходимо указать полное доменное имя службы пограничного доступа. Если на странице "Выбор компонентов" не выбран параметр  "Использовать один **&amp; ip-адрес FQDN",** необходимо также указать FQDN для службы веб-конференций и для службы A/V Edge.
  
Кроме того, если выбран параметр "Использовать один **ip-адрес FQDN", &amp;** необходимо указать разные номера портов для каждой из этих служб (рекомендуемые параметры портов: 444 для службы доступа, 8057 для службы веб-службы и 443 для службы A/V Edge). Если этот параметр не выбран, можно использовать один номер порта (например, 443) для всех трех служб.
  

