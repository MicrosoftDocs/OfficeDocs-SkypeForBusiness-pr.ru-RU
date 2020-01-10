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
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003029"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="932e7-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="932e7-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="932e7-104">Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="932e7-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="932e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="932e7-105">Parameters</span></span>

<span data-ttu-id="932e7-106">Нет</span><span class="sxs-lookup"><span data-stu-id="932e7-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="932e7-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="932e7-107">Examples</span></span>
<span data-ttu-id="932e7-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="932e7-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="932e7-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="932e7-109">Example 1</span></span>

<span data-ttu-id="932e7-110">В следующем примере выполняется резервное копирование службы центра сертификации в файл и сохранение папки CA в общем каталоге сайта.</span><span class="sxs-lookup"><span data-stu-id="932e7-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="932e7-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="932e7-111">Detailed Description</span></span>
<span data-ttu-id="932e7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="932e7-112"></span></span>

<span data-ttu-id="932e7-113">Резервное копирование центра сертификации может быть полезно, если вы планируете повторное развертывание устройства облачного соединителя с помощью того же сертификата в случае аварии или вы хотите переместить устройство на новое оборудование.</span><span class="sxs-lookup"><span data-stu-id="932e7-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="932e7-114">С помощью этой команды можно сохранить копию службы центра сертификации облачного соединителя с AD на сервере "\<СИТЕРУТДИРЕКТОРИ\>\ка\сфб кце root. p12".</span><span class="sxs-lookup"><span data-stu-id="932e7-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="932e7-115">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="932e7-115">Input Types</span></span>
<span data-ttu-id="932e7-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="932e7-116"></span></span>

<span data-ttu-id="932e7-p102">Нет. Командлет Backup-CcCertificationAuthority не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="932e7-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="932e7-119">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="932e7-119">Return Types</span></span>
<span data-ttu-id="932e7-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="932e7-120"></span></span>

<span data-ttu-id="932e7-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="932e7-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="932e7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="932e7-122">See also</span></span>
<span data-ttu-id="932e7-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="932e7-123"></span></span>

[<span data-ttu-id="932e7-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="932e7-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

