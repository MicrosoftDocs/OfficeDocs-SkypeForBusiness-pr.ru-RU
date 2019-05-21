---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Командлет Renew-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. Эта команда была изменена на Update-Кккацертификате в облачном соединителе 2,0 и более поздних версиях.
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287106"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="6113b-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6113b-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="6113b-105">Командлет Renew-CcCACertificate продлевает сертификат корневого центра сертификации Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек.</span><span class="sxs-lookup"><span data-stu-id="6113b-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="6113b-106">Эта команда была изменена на Update-Кккацертификате в облачном соединителе 2,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="6113b-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="6113b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6113b-107">Parameters</span></span>

<span data-ttu-id="6113b-108">Нет</span><span class="sxs-lookup"><span data-stu-id="6113b-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6113b-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="6113b-109">Examples</span></span>
<span data-ttu-id="6113b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="6113b-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="6113b-111">Example 1</span></span>

<span data-ttu-id="6113b-112">В следующем примере продлевается сертификат корневого центра сертификации. </span><span class="sxs-lookup"><span data-stu-id="6113b-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="6113b-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="6113b-113">Detailed Description</span></span>
<span data-ttu-id="6113b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-114"></span></span>

<span data-ttu-id="6113b-115">Сертификат корневого центра сертификации Cloud Connector действует в течение пяти лет с момента установки службы центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="6113b-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="6113b-p103">Если срок действия корневого сертификата истекает или уже истек, выполните командлет Renew-CcCACertificate для его продления. После продления корневого сертификата серверу Active Directory, серверу центрального хранилища управления (CMS) и пограничному серверу автоматически будут выданы новые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="6113b-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="6113b-118">Если на одном сайте ТСОП используется несколько устройств, выполните командлет Renew-CcCACertificate на всех устройствах этого сайта ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6113b-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="6113b-119">Наконец, выполните командлет Export-CcRootCertificate, чтобы экспортировать корневой сертификат в локальный файл на первом устройстве, а затем скопируйте и установите экспортированный сертификат на шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="6113b-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6113b-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="6113b-120">Input Types</span></span>
<span data-ttu-id="6113b-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-121"></span></span>

<span data-ttu-id="6113b-p104">Нет. Командлет Renew-CcCACertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6113b-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6113b-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="6113b-124">Return Types</span></span>
<span data-ttu-id="6113b-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-125"></span></span>

<span data-ttu-id="6113b-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="6113b-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6113b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6113b-127">See also</span></span>
<span data-ttu-id="6113b-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6113b-128"></span></span>

[<span data-ttu-id="6113b-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6113b-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="6113b-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6113b-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="6113b-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="6113b-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

