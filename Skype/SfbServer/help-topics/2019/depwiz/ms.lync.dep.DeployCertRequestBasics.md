---
title: Запрос сертификата (основные сведения)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: На странице "имя и параметры безопасности" можно задать понятное имя, раскрывающийся список для длины битов закрытого и открытого ключа, а также флажок, который позволяет помечать закрытый ключ сертификата как экспортируемый.
ms.openlocfilehash: 26315f24dd14989bd2832d6f28e591a7ae38cc64
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796770"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="7c592-103">Запрос сертификата (основные сведения)</span><span class="sxs-lookup"><span data-stu-id="7c592-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="7c592-104">На странице " **имя и параметры безопасности** " можно задать **понятное имя**, раскрывающийся список для **длины битов** закрытого и открытого ключа, а также флажок, который позволяет **помечать закрытый ключ сертификата как экспортируемый**.</span><span class="sxs-lookup"><span data-stu-id="7c592-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="7c592-105">Понятное, или простое, имя в сертификате используется для того, чтобы тому, кто просматривает сертификат, было проще его опознать.</span><span class="sxs-lookup"><span data-stu-id="7c592-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="7c592-106">В качестве длины бита для пары открытого и закрытого ключей можно выбрать значение 1024, 2048 или 4096.</span><span class="sxs-lookup"><span data-stu-id="7c592-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="7c592-107">Установка флажка для **отметки закрытого ключа сертификата как экспортируемого** позволяет экспортировать и переносить сертификат и закрытый ключ на другой компьютер или сервер.</span><span class="sxs-lookup"><span data-stu-id="7c592-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="7c592-108">Это требуется только в одном случае: при создании пула пограничных серверов для службы проверки подлинности при ретрансляции мультимедиа (MRAS).</span><span class="sxs-lookup"><span data-stu-id="7c592-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7c592-109">Для обеспечения безопасности сертификата и пары ключей следует выбрать параметр пометка закрытого ключа сертификата как экспортируемого, только если это абсолютно необходимо.</span><span class="sxs-lookup"><span data-stu-id="7c592-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

