---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294420"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="db020-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="db020-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="db020-104">Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="db020-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="db020-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="db020-105">Parameters</span></span>

<span data-ttu-id="db020-106">Нет</span><span class="sxs-lookup"><span data-stu-id="db020-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="db020-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="db020-107">Examples</span></span>
<span data-ttu-id="db020-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="db020-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="db020-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="db020-109">Example 1</span></span>

<span data-ttu-id="db020-110">В следующем примере выполняется резервное копирование службы центра сертификации в файл и сохранение папки CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="db020-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="db020-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="db020-111">Detailed Description</span></span>
<span data-ttu-id="db020-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="db020-112"></span></span>

<span data-ttu-id="db020-113">Резервное копирование центра сертификации может быть полезно, если вы планируете повторное развертывание устройства облачного соединителя с помощью того же сертификата в случае аварии или вы хотите переместить устройство на новое оборудование.</span><span class="sxs-lookup"><span data-stu-id="db020-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="db020-114">С помощью этой команды можно сохранить копию службы центра сертификации облачного соединителя с AD на сервере "\<СИТЕРУТДИРЕКТОРИ\>\ка\сфб кце root. p12".</span><span class="sxs-lookup"><span data-stu-id="db020-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="db020-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="db020-115">Input Types</span></span>
<span data-ttu-id="db020-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db020-116"></span></span>

<span data-ttu-id="db020-p102">Нет. Командлет Backup-CcCertificationAuthority не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="db020-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="db020-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="db020-119">Return Types</span></span>
<span data-ttu-id="db020-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db020-120"></span></span>

<span data-ttu-id="db020-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="db020-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db020-122">См. также</span><span class="sxs-lookup"><span data-stu-id="db020-122">See also</span></span>
<span data-ttu-id="db020-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="db020-123"></span></span>

[<span data-ttu-id="db020-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="db020-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

