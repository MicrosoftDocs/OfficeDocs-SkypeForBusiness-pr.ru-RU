---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287085"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="39e76-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="39e76-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="39e76-104">Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="39e76-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="39e76-105">Этот командлет применим к Skype для бизнеса Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="39e76-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="39e76-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="39e76-106">Detailed Description</span></span>

<span data-ttu-id="39e76-107">Командлет Restore-Кккредентиалс удаляет все учетные данные и предлагает вам повторно ввести все учетные данные, которые используются для текущего развертывания облачного соединителя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="39e76-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="39e76-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="39e76-108">Parameters</span></span>

<span data-ttu-id="39e76-109">Нет</span><span class="sxs-lookup"><span data-stu-id="39e76-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="39e76-110">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="39e76-110">Input Types</span></span>

<span data-ttu-id="39e76-111">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="39e76-111">None.</span></span> <span data-ttu-id="39e76-112">Командлет Restore-Кккредентиалс не поддерживает конвейерный вход.</span><span class="sxs-lookup"><span data-stu-id="39e76-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="39e76-113">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="39e76-113">Return Types</span></span>

<span data-ttu-id="39e76-114">Нет. </span><span class="sxs-lookup"><span data-stu-id="39e76-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="39e76-115">Пример</span><span class="sxs-lookup"><span data-stu-id="39e76-115">Example</span></span>

<span data-ttu-id="39e76-116">В следующем примере восстанавливаются все учетные данные для текущего развертывания облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="39e76-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="39e76-117">См. также</span><span class="sxs-lookup"><span data-stu-id="39e76-117">See also</span></span>

[<span data-ttu-id="39e76-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="39e76-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="39e76-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="39e76-119">Set-CcCredential</span></span>](set-cccredential.md)
  

