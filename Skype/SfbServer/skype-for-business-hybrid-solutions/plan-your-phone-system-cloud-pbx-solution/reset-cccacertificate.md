---
title: Сброс CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Командлет Reset-CcCACertificate переустанавливает сервера AD службы центра сертификации для создания нового сертификата корневого ЦС.
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="3c7e1-103">Сброс CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3c7e1-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="3c7e1-104">Командлет Reset-CcCACertificate переустанавливает сервера AD службы центра сертификации для создания нового сертификата корневого ЦС.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="3c7e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c7e1-105">Parameters</span></span>

<span data-ttu-id="3c7e1-106">Нет</span><span class="sxs-lookup"><span data-stu-id="3c7e1-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3c7e1-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c7e1-107">Examples</span></span>
<span data-ttu-id="3c7e1-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3c7e1-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="3c7e1-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="3c7e1-109">Example 1</span></span>

<span data-ttu-id="3c7e1-110">В следующем примере переустанавливается сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="3c7e1-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3c7e1-111">Detailed Description</span></span>
<span data-ttu-id="3c7e1-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3c7e1-112"></span></span>

<span data-ttu-id="3c7e1-113">Если сертификат корневого центра сертификации скомпрометирован или не обеспечивает нужный уровень безопасности, необходимо обновить его и все остальные сертификаты, выданные корневым центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="3c7e1-114">Командлет Reset-CcCACertificate отзывает все сертификаты, удаляет и переустанавливает центр сертификации, после чего очищает все сертификаты, связанные со старой службой центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="3c7e1-115">Для получения дополнительных сведений см раздел «Сертификат центра сертификации или внутренних сертификатам, выданным CMS, сервер-посредник и пограничного сервера, срок действия или скомпрометированы» Устранение неполадок развертывания облака соединителя.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3c7e1-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="3c7e1-116">Input Types</span></span>
<span data-ttu-id="3c7e1-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c7e1-117"></span></span>

<span data-ttu-id="3c7e1-p102">Нет. Командлет Reset-CcCACertificate не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3c7e1-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="3c7e1-120">Return Types</span></span>
<span data-ttu-id="3c7e1-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c7e1-121"></span></span>

<span data-ttu-id="3c7e1-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="3c7e1-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c7e1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3c7e1-123">See also</span></span>
<span data-ttu-id="3c7e1-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3c7e1-124"></span></span>

<span data-ttu-id="3c7e1-125">[Обновить CcCACertificate](renew-cccacertificate.md) Только версии 1.4.2</span><span class="sxs-lookup"><span data-stu-id="3c7e1-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="3c7e1-126">[Обновить CcServerCertificate](renew-ccservercertificate.md) Только версии 1.4.2</span><span class="sxs-lookup"><span data-stu-id="3c7e1-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="3c7e1-127">[Обновление CcCACertificate](update-cccacertificate.md) Версии 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3c7e1-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="3c7e1-128">[Обновить CcServerCertificate](renew-ccservercertificate.md) Версии 2.0 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="3c7e1-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="3c7e1-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3c7e1-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

