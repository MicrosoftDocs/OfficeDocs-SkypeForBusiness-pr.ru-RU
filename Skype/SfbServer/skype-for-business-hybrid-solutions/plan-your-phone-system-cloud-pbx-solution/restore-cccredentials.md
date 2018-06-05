---
title: Восстановление CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Командлет учетные данные копия на восстановление восстанавливает все учетные данные текущего Скайп для развертывания соединителя Cloud Business Edition.
ms.openlocfilehash: bb74444c5f63b792abf6c12c317c1a824298426c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569735"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="c125e-103">Восстановление CcCredentials</span><span class="sxs-lookup"><span data-stu-id="c125e-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="c125e-104">Командлет учетные данные копия на восстановление восстанавливает все учетные данные текущего Скайп для развертывания соединителя Cloud Business Edition.</span><span class="sxs-lookup"><span data-stu-id="c125e-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="c125e-105">Этот командлет применяется к Скайп для соединителя выпуск Business Cloud 2.1.</span><span class="sxs-lookup"><span data-stu-id="c125e-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="c125e-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c125e-106">Detailed Description</span></span>

<span data-ttu-id="c125e-107">Командлет Restore-CcCredentials очищает все учетные данные, необходимо повторно ввести все учетные данные, используемые для текущего Скайп для развертывания Cloud Business Connector.</span><span class="sxs-lookup"><span data-stu-id="c125e-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c125e-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c125e-108">Parameters</span></span>

<span data-ttu-id="c125e-109">Нет</span><span class="sxs-lookup"><span data-stu-id="c125e-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c125e-110">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c125e-110">Input Types</span></span>

<span data-ttu-id="c125e-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="c125e-111">None.</span></span> <span data-ttu-id="c125e-112">Командлет Restore-CcCredentials не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="c125e-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c125e-113">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c125e-113">Return Types</span></span>

<span data-ttu-id="c125e-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="c125e-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="c125e-115">Пример</span><span class="sxs-lookup"><span data-stu-id="c125e-115">Example</span></span>

<span data-ttu-id="c125e-116">В следующем примере восстанавливается все учетные данные текущего развертывания облака соединителя:</span><span class="sxs-lookup"><span data-stu-id="c125e-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="c125e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c125e-117">See also</span></span>

[<span data-ttu-id="c125e-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="c125e-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="c125e-119">SET-CcCredential</span><span class="sxs-lookup"><span data-stu-id="c125e-119">Set-CcCredential</span></span>](set-cccredential.md)
  

