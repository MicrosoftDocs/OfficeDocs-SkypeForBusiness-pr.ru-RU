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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824245"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="887ae-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="887ae-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="887ae-104">Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="887ae-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="887ae-105">Этот командлет применим к Skype для бизнеса Cloud Connector Edition 2,1.</span><span class="sxs-lookup"><span data-stu-id="887ae-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="887ae-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="887ae-106">Detailed Description</span></span>

<span data-ttu-id="887ae-107">Командлет Restore-Кккредентиалс удаляет все учетные данные и предлагает вам повторно ввести все учетные данные, которые используются для текущего развертывания облачного соединителя Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="887ae-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="887ae-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="887ae-108">Parameters</span></span>

<span data-ttu-id="887ae-109">Нет</span><span class="sxs-lookup"><span data-stu-id="887ae-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="887ae-110">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="887ae-110">Input Types</span></span>

<span data-ttu-id="887ae-111">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="887ae-111">None.</span></span> <span data-ttu-id="887ae-112">Командлет Restore-Кккредентиалс не поддерживает конвейерный вход.</span><span class="sxs-lookup"><span data-stu-id="887ae-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="887ae-113">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="887ae-113">Return Types</span></span>

<span data-ttu-id="887ae-114">Нет. </span><span class="sxs-lookup"><span data-stu-id="887ae-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="887ae-115">Пример</span><span class="sxs-lookup"><span data-stu-id="887ae-115">Example</span></span>

<span data-ttu-id="887ae-116">В следующем примере восстанавливаются все учетные данные для текущего развертывания облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="887ae-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="887ae-117">См. также</span><span class="sxs-lookup"><span data-stu-id="887ae-117">See also</span></span>

[<span data-ttu-id="887ae-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="887ae-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="887ae-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="887ae-119">Set-CcCredential</span></span>](set-cccredential.md)
  

