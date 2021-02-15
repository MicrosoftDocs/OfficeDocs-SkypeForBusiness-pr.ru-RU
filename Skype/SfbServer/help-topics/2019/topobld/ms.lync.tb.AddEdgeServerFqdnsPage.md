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
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="64941-104">Добавление полного доменного имени пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="64941-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="64941-105">Необходимо указать полное доменное имя службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="64941-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="64941-106">Если на странице "Выбор компонентов" не выбран параметр  "Использовать один **&amp; ip-адрес FQDN",** необходимо также указать FQDN для службы веб-конференций и для службы A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="64941-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="64941-107">Кроме того, если выбран параметр "Использовать один **ip-адрес FQDN", &amp;** необходимо указать разные номера портов для каждой из этих служб (рекомендуемые параметры портов: 444 для службы доступа, 8057 для службы веб-службы и 443 для службы A/V Edge).</span><span class="sxs-lookup"><span data-stu-id="64941-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="64941-108">Если этот параметр не выбран, можно использовать один номер порта (например, 443) для всех трех служб.</span><span class="sxs-lookup"><span data-stu-id="64941-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

