---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Этот Reset-CcCACertificate переустановит сервер AD Службы сертификации для создания нового корневого сертификата ЦС.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824255"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="b9c8c-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="b9c8c-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="b9c8c-104">Этот Reset-CcCACertificate переустановит сервер AD Службы сертификации для создания нового корневого сертификата ЦС.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="b9c8c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9c8c-105">Parameters</span></span>

<span data-ttu-id="b9c8c-106">Нет</span><span class="sxs-lookup"><span data-stu-id="b9c8c-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b9c8c-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="b9c8c-107">Examples</span></span>
<span data-ttu-id="b9c8c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c8c-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b9c8c-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="b9c8c-109">Example 1</span></span>

<span data-ttu-id="b9c8c-110">В следующем примере переустановка сервера AD Server службы сертификации для создания нового сертификата корневого ЦС:</span><span class="sxs-lookup"><span data-stu-id="b9c8c-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="b9c8c-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b9c8c-111">Detailed Description</span></span>
<span data-ttu-id="b9c8c-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c8c-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b9c8c-113">Если сертификат корневого ЦС скомпрометирован или больше не защищен, необходимо обновить сертификат корневого ЦС и все сертификаты, выданные корневым ЦС.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="b9c8c-114">Этот Reset-CcCACertificate отзывает все сертификаты, отменяет и переустанавлетирует ЦС сертификации, а затем очищает все сертификаты, связанные со старой службой центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="b9c8c-115">Дополнительные сведения см. в подключении "Срок действия сертификатов из ЦС, сервера-посредника и сервера-посредника истекает или они скомпрометированы" в устранении неполадок развертывания Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b9c8c-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="b9c8c-116">Input Types</span></span>
<span data-ttu-id="b9c8c-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c8c-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b9c8c-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-118">None.</span></span> <span data-ttu-id="b9c8c-119">Этот Reset-CcCACertificate не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b9c8c-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b9c8c-120">Return Types</span></span>
<span data-ttu-id="b9c8c-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c8c-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b9c8c-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="b9c8c-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9c8c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b9c8c-123">See also</span></span>
<span data-ttu-id="b9c8c-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c8c-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b9c8c-125">[Renew-CcCACertificate](renew-cccacertificate.md) Только версия 1.4.2</span><span class="sxs-lookup"><span data-stu-id="b9c8c-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="b9c8c-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Только версия 1.4.2</span><span class="sxs-lookup"><span data-stu-id="b9c8c-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="b9c8c-127">[Update-CcCACertificate](update-cccacertificate.md) Версия 2.0 и более поздние</span><span class="sxs-lookup"><span data-stu-id="b9c8c-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="b9c8c-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Версия 2.0 и более поздние</span><span class="sxs-lookup"><span data-stu-id="b9c8c-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="b9c8c-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="b9c8c-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

