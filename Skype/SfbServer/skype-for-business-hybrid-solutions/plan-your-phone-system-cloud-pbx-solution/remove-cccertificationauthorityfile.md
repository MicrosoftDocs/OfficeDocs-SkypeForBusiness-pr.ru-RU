---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Этот Remove-CcCertificationAuthorityFile удаляет файл резервной копии службы центра сертификации в папке ЦС в каталоге share сайта Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824295"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="d7a34-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="d7a34-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="d7a34-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d7a34-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="d7a34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7a34-105">Parameters</span></span>

<span data-ttu-id="d7a34-106">Нет</span><span class="sxs-lookup"><span data-stu-id="d7a34-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d7a34-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="d7a34-107">Examples</span></span>
<span data-ttu-id="d7a34-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d7a34-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d7a34-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d7a34-109">Example 1</span></span>

<span data-ttu-id="d7a34-110">В следующем примере удаляется файл резервной копии службы центра сертификации &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" в папке ЦС в каталоге для совместной работы сайта:</span><span class="sxs-lookup"><span data-stu-id="d7a34-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="d7a34-111">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d7a34-111">Input Types</span></span>
<span data-ttu-id="d7a34-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d7a34-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d7a34-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="d7a34-113">None.</span></span> <span data-ttu-id="d7a34-114">Этот Remove-CcCertificationAuthorityFile не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="d7a34-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d7a34-115">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d7a34-115">Return Types</span></span>
<span data-ttu-id="d7a34-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d7a34-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d7a34-117">Нет</span><span class="sxs-lookup"><span data-stu-id="d7a34-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7a34-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a34-118">See also</span></span>
<span data-ttu-id="d7a34-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d7a34-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d7a34-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="d7a34-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

