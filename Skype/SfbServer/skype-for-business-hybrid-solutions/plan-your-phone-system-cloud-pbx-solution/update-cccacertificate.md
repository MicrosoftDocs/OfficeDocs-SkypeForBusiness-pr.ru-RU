---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'Командлет Update-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. '
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824123"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="85db5-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="85db5-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="85db5-104">Командлет Update-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. </span><span class="sxs-lookup"><span data-stu-id="85db5-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="85db5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85db5-105">Parameters</span></span>

<span data-ttu-id="85db5-106">Нет.</span><span class="sxs-lookup"><span data-stu-id="85db5-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="85db5-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="85db5-107">Examples</span></span>
<span data-ttu-id="85db5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="85db5-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="85db5-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="85db5-109">Example 1</span></span>

<span data-ttu-id="85db5-110">В следующем примере продлевается сертификат корневого центра сертификации. </span><span class="sxs-lookup"><span data-stu-id="85db5-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="85db5-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="85db5-111">Detailed Description</span></span>
<span data-ttu-id="85db5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="85db5-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="85db5-113">Сертификат корневого центра сертификации Cloud Connector действует в течение пяти лет с момента установки службы центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="85db5-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="85db5-p101">Если срок действия корневого сертификата истекает или уже истек, выполните командлет Update-CcCACertificate для его продления. После продления корневого сертификата серверу Active Directory, серверу центрального хранилища управления (CMS) и пограничному серверу автоматически будут выданы новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="85db5-p101">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="85db5-116">Если на одном сайте ТСОП используется несколько устройств, выполните командлет Update-CcCACertificate на всех устройствах этого сайта ТСОП.</span><span class="sxs-lookup"><span data-stu-id="85db5-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="85db5-117">Наконец, выполните командлет Export-CcRootCertificate, чтобы экспортировать корневой сертификат в локальный файл на первом устройстве, а затем скопируйте и установите экспортированный сертификат на шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="85db5-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="85db5-118">Эта команда заменяет командлет Renew-CcCACertificate в Cloud Connector 2.0 и более поздних выпусков.</span><span class="sxs-lookup"><span data-stu-id="85db5-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="85db5-119">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="85db5-119">Input Types</span></span>
<span data-ttu-id="85db5-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85db5-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="85db5-p102">Нет. Командлет Update-CcCACertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="85db5-p102">None. The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="85db5-123">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="85db5-123">Return Types</span></span>
<span data-ttu-id="85db5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85db5-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="85db5-125">Нет. </span><span class="sxs-lookup"><span data-stu-id="85db5-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="85db5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="85db5-126">See also</span></span>
<span data-ttu-id="85db5-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="85db5-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="85db5-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="85db5-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="85db5-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="85db5-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="85db5-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="85db5-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

