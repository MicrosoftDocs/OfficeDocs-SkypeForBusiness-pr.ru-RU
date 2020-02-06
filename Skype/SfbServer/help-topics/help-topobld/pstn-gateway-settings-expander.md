---
title: Расширитель настроек шлюза ТСОП
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.
ms.openlocfilehash: 1fa72dfc91f75994be4afadfea1d6f526af5607f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819421"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="d0b54-103">Расширитель настроек шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="d0b54-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="d0b54-104">Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.</span><span class="sxs-lookup"><span data-stu-id="d0b54-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="d0b54-105">Полное доменное имя или IP-адрес шлюза является обязательным параметром, определяющим **полное доменное имя** шлюза ТСОП в соответствии с записью узла (A) в службе доменных имен, статическую запись файла HOSTS или IP-адрес шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d0b54-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="d0b54-p101">Транспортный протокол SIP может являться TCP или TLS. По умолчанию он является TLS. Сведения о протоколах, поддерживаемых шлюзом, см. в документации производителя шлюза. По умолчанию используется защищенный протокол TLS, который рекомендуется использовать для обеспечения безопасности соединений, если шлюз также поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="d0b54-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="d0b54-110">Выберите, следует ли включить IPv4 и IPv6 для шлюза.</span><span class="sxs-lookup"><span data-stu-id="d0b54-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="d0b54-111">**Альтернативный IP-адрес мультимедиа** является определением сервера-посредника, для которого развернутый шлюз PSTN имеет другой IP-адрес для трафика мультимедиа по сравнению с IP-адресом по умолчанию, который обычно выделяется для трафика SIP.</span><span class="sxs-lookup"><span data-stu-id="d0b54-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="d0b54-112">Если задан этот параметр, шлюз ТСОП поддерживает другой сетевой интерфейс или путь для передачи мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="d0b54-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="d0b54-113">Если поле этого адреса не заполнено, шлюз ТСОП не поддерживает альтернативного пути для передачи мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="d0b54-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

