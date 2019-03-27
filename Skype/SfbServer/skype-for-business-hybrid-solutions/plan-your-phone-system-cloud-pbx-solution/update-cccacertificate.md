---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'Командлет Update-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. '
ms.openlocfilehash: d123474240fb18ffcb6c1c037cc5407eb4c6c4e3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877935"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="a3603-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="a3603-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="a3603-104">Командлет Update-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. </span><span class="sxs-lookup"><span data-stu-id="a3603-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="a3603-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3603-105">Parameters</span></span>

<span data-ttu-id="a3603-106">Нет.</span><span class="sxs-lookup"><span data-stu-id="a3603-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="a3603-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="a3603-107">Examples</span></span>
<span data-ttu-id="a3603-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a3603-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="a3603-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a3603-109">Example 1</span></span>

<span data-ttu-id="a3603-110">В следующем примере продлевается сертификат корневого центра сертификации. </span><span class="sxs-lookup"><span data-stu-id="a3603-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="a3603-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a3603-111">Detailed Description</span></span>
<span data-ttu-id="a3603-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a3603-112"></span></span>

<span data-ttu-id="a3603-113">Сертификат корневого центра сертификации Cloud Connector действует в течение пяти лет с момента установки службы центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="a3603-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="a3603-p101">Если срок действия корневого сертификата истекает или уже истек, выполните командлет Update-CcCACertificate для его продления. После продления корневого сертификата серверу Active Directory, серверу центрального хранилища управления (CMS) и пограничному серверу автоматически будут выданы новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="a3603-p101">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="a3603-116">Если на одном сайте ТСОП используется несколько устройств, выполните командлет Update-CcCACertificate на всех устройствах этого сайта ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a3603-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="a3603-117">Наконец, выполните командлет Export-CcRootCertificate, чтобы экспортировать корневой сертификат в локальный файл на первом устройстве, а затем скопируйте и установите экспортированный сертификат на шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a3603-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="a3603-118">Эта команда заменяет командлет Renew-CcCACertificate в Cloud Connector 2.0 и более поздних выпусков.</span><span class="sxs-lookup"><span data-stu-id="a3603-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a3603-119">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a3603-119">Input Types</span></span>
<span data-ttu-id="a3603-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a3603-120"></span></span>

<span data-ttu-id="a3603-p102">Нет. Командлет Update-CcCACertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a3603-p102">None. The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a3603-123">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a3603-123">Return Types</span></span>
<span data-ttu-id="a3603-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a3603-124"></span></span>

<span data-ttu-id="a3603-125">Нет. </span><span class="sxs-lookup"><span data-stu-id="a3603-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a3603-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a3603-126">See also</span></span>
<span data-ttu-id="a3603-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a3603-127"></span></span>

[<span data-ttu-id="a3603-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="a3603-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="a3603-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="a3603-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="a3603-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="a3603-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

