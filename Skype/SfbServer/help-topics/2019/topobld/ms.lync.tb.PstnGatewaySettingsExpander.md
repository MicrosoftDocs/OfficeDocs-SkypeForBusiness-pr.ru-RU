---
title: Расширитель настроек шлюза ТСОП
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.
ms.openlocfilehash: c54acc930400f66bb04009a6c40dbcf0a1233100
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822309"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="8cbaa-103">Расширитель параметров шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="8cbaa-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="8cbaa-104">Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="8cbaa-105">Полное доменное имя или IP-адрес шлюза являются необходимым значением, которое определяет **Полное доменное имя** шлюза ТСОП, как оно определено в записи узла (A) на DNS-сервере, в статической записи файла HOSTS, или является IP-адресом шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="8cbaa-p101">Транспортный протокол SIP может являться TCP или TLS. По умолчанию он является TLS. Сведения о протоколах, поддерживаемых шлюзом, см. в документации производителя шлюза. По умолчанию используется защищенный протокол TLS, который рекомендуется использовать для обеспечения безопасности соединений, если шлюз также поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="8cbaa-110">Выберите, следует ли включить IPv4 и IPv6 для шлюза.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="8cbaa-p102">**Другой IP-адрес для мультимедиа** является определением для сервера-посредника, если шлюз ТСОП использует при работе с этим сервером другой IP-адрес для передачи трафика мультимедиа, отличный от стандартного IP-адреса, который, как правило, используется для передачи SIP-трафика. Если определить этот параметр, значит шлюз ТСОП поддерживает другой сетевой интерфейс или путь для передачи мультимедиа. Если этот адрес оставлен пустым, шлюз ТСОП не поддерживает альтернативный путь для мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-p102">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic. If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media. If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

