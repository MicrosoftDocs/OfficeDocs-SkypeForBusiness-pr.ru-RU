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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803809"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="29dc5-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="29dc5-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="29dc5-104">Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="29dc5-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="29dc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29dc5-105">Parameters</span></span>

<span data-ttu-id="29dc5-106">Нет</span><span class="sxs-lookup"><span data-stu-id="29dc5-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="29dc5-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="29dc5-107">Examples</span></span>
<span data-ttu-id="29dc5-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="29dc5-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="29dc5-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="29dc5-109">Example 1</span></span>

<span data-ttu-id="29dc5-110">В следующем примере выполняется резервное копирование службы центра сертификации в файл и сохранение папки CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="29dc5-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="29dc5-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="29dc5-111">Detailed Description</span></span>
<span data-ttu-id="29dc5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="29dc5-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="29dc5-113">Резервное копирование центра сертификации может быть полезно, если вы планируете повторное развертывание устройства облачного соединителя с помощью того же сертификата в случае аварии или вы хотите переместить устройство на новое оборудование.</span><span class="sxs-lookup"><span data-stu-id="29dc5-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="29dc5-114">С помощью этой команды можно сохранить копию службы центра сертификации облачного соединителя с AD на сервере "\<СИТЕРУТДИРЕКТОРИ\>\ка\сфб кце root. p12".</span><span class="sxs-lookup"><span data-stu-id="29dc5-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="29dc5-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="29dc5-115">Input Types</span></span>
<span data-ttu-id="29dc5-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="29dc5-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="29dc5-p102">Нет. Командлет Backup-CcCertificationAuthority не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="29dc5-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="29dc5-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="29dc5-119">Return Types</span></span>
<span data-ttu-id="29dc5-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="29dc5-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="29dc5-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="29dc5-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29dc5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="29dc5-122">See also</span></span>
<span data-ttu-id="29dc5-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="29dc5-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="29dc5-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="29dc5-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

