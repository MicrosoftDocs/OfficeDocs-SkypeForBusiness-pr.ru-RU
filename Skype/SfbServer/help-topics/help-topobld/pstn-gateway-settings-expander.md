---
title: Расширитель настроек шлюза ТСОП
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.
ms.openlocfilehash: 9b00cdadab9f2a7967bab7601a0c691ca35819c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219235"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="032c5-103">Расширитель настроек шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="032c5-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="032c5-104">Чтобы изменить или отредактировать параметры телефонной сети общего пользования, измените значения следующих полей.</span><span class="sxs-lookup"><span data-stu-id="032c5-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="032c5-105">Полное доменное имя или IP-адрес шлюза является обязательным параметром, определяющим **полное доменное имя** шлюза ТСОП в соответствии с записью узла (A) в службе доменных имен, статическую запись файла HOSTS или IP-адрес шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="032c5-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="032c5-p101">Транспортный протокол SIP может являться TCP или TLS. По умолчанию он является TLS. Сведения о протоколах, поддерживаемых шлюзом, см. в документации производителя шлюза. По умолчанию используется защищенный протокол TLS, который рекомендуется использовать для обеспечения безопасности соединений, если шлюз также поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="032c5-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="032c5-110">Выберите, следует ли включить IPv4 и IPv6 для шлюза.</span><span class="sxs-lookup"><span data-stu-id="032c5-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="032c5-111">**IP-адрес альтернативного посредника** — определение для сервера-посредника, для которого развернутое шлюза ТСОП имеет другой IP-адрес для трафика мультимедиа, чем по умолчанию настроен IP-адрес, обычно предназначенный для трафика SIP.</span><span class="sxs-lookup"><span data-stu-id="032c5-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="032c5-112">Если задан этот параметр, шлюз ТСОП поддерживает другой сетевой интерфейс или путь для передачи мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="032c5-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="032c5-113">Если поле этого адреса не заполнено, шлюз ТСОП не поддерживает альтернативного пути для передачи мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="032c5-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

