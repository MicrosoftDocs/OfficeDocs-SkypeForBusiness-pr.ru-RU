---
title: Запрос сертификата (основные сведения)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: На странице "Имя и параметры безопасности" имеется текстовое поле для определения понятного имени, выпадаемый список длины бита пары закрытых и открытых ключей, а также поле, которое позволяет пометить закрытый ключ сертификата как экспортируемый.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830419"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="bac0a-103">Запрос сертификата (основные сведения)</span><span class="sxs-lookup"><span data-stu-id="bac0a-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="bac0a-104">На  странице "Имя и параметры безопасности" есть текстовое поле для  определения понятного **имени,** выпадаемый список для длины бита пары закрытых и открытых ключей, а также поле, которое позволяет пометить закрытый ключ сертификата как экспортируемый. </span><span class="sxs-lookup"><span data-stu-id="bac0a-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="bac0a-105">Понятное, или простое, имя в сертификате используется для того, чтобы тому, кто просматривает сертификат, было проще его опознать.</span><span class="sxs-lookup"><span data-stu-id="bac0a-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="bac0a-106">В качестве длины бита для пары открытого и закрытого ключей можно выбрать значение 1024, 2048 или 4096.</span><span class="sxs-lookup"><span data-stu-id="bac0a-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="bac0a-107">Если пометить  закрытый ключ сертификата как экспортируемый, сертификат и закрытый ключ будут экспортироваться и перемещены на другой компьютер или сервер.</span><span class="sxs-lookup"><span data-stu-id="bac0a-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="bac0a-108">Это требуется только при создании пула серверов для службы проверки подлинности при ретрансляции мультимедиа (MRAS).</span><span class="sxs-lookup"><span data-stu-id="bac0a-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bac0a-109">Чтобы обеспечить безопасность сертификата и пары ключей, следует отметить закрытый ключ сертификата как экспортируемый параметр, только если это абсолютно необходимо.</span><span class="sxs-lookup"><span data-stu-id="bac0a-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

