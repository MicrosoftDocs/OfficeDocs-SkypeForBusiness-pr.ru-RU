---
title: Запрос сертификата (основные сведения)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: Страница Настройка имени и безопасности предоставляет текстовое поле для определения понятное имя раскрывающегося списка для длины бита для пары ключей и закрытого и флажок, который позволяет пометить закрытый ключ сертификата как экспортируемый.
ms.openlocfilehash: 474111f6f732353c80ceea88da3e9cebda1caae3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996468"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="ff44b-103">Запрос сертификата (основные сведения)</span><span class="sxs-lookup"><span data-stu-id="ff44b-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="ff44b-104">Страница **Настройка имени и безопасности** текстовое поле для определения **Понятное имя**, раскрывающемся списке **Bit length** пары ключей и закрытого и флажок, который позволяет вам **Марка сертификат закрытый ключ как экспортируемый**.</span><span class="sxs-lookup"><span data-stu-id="ff44b-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="ff44b-105">Понятное, или простое, имя в сертификате используется для того, чтобы тому, кто просматривает сертификат, было проще его опознать.</span><span class="sxs-lookup"><span data-stu-id="ff44b-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="ff44b-106">В качестве длины бита для пары открытого и закрытого ключей можно выбрать значение 1024, 2048 или 4096.</span><span class="sxs-lookup"><span data-stu-id="ff44b-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="ff44b-107">Если установлен флажок для **Пометить закрытый ключ сертификата как экспортируемый** позволяет сертификат и закрытый ключ, чтобы экспортировать и перемещены на другой компьютер или сервер.</span><span class="sxs-lookup"><span data-stu-id="ff44b-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="ff44b-108">Это требуется только в одном случае: при создании пула пограничных серверов для службы проверки подлинности при ретрансляции мультимедиа (MRAS).</span><span class="sxs-lookup"><span data-stu-id="ff44b-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ff44b-109">В интересах безопасности сертификата и пары ключей, следует выбрать пометить закрытый ключ сертификата как экспортируемый вариант только в том случае, если это действительно необходимо.</span><span class="sxs-lookup"><span data-stu-id="ff44b-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

