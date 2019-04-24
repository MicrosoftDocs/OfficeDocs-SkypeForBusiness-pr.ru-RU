---
title: Restore-CcCredentials
ms.reviewer: ''
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
ms.openlocfilehash: 0b790b9f2edab9fade2738c3c95348be864f9017
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250865"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="b4fcf-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="b4fcf-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="b4fcf-104">Командлет учетные данные копия на восстановление восстанавливает все учетные данные текущего Скайп для развертывания соединителя Cloud Business Edition.</span><span class="sxs-lookup"><span data-stu-id="b4fcf-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="b4fcf-105">Этот командлет применяется к Скайп для соединителя выпуск Business Cloud 2.1.</span><span class="sxs-lookup"><span data-stu-id="b4fcf-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="b4fcf-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b4fcf-106">Detailed Description</span></span>

<span data-ttu-id="b4fcf-107">Командлет Restore-CcCredentials очищает все учетные данные, необходимо повторно ввести все учетные данные, используемые для текущего Скайп для развертывания Cloud Business Connector.</span><span class="sxs-lookup"><span data-stu-id="b4fcf-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b4fcf-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4fcf-108">Parameters</span></span>

<span data-ttu-id="b4fcf-109">Нет</span><span class="sxs-lookup"><span data-stu-id="b4fcf-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b4fcf-110">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="b4fcf-110">Input Types</span></span>

<span data-ttu-id="b4fcf-111">Отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b4fcf-111">None.</span></span> <span data-ttu-id="b4fcf-112">Командлет Restore-CcCredentials не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="b4fcf-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b4fcf-113">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b4fcf-113">Return Types</span></span>

<span data-ttu-id="b4fcf-114">Нет. </span><span class="sxs-lookup"><span data-stu-id="b4fcf-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="b4fcf-115">Пример</span><span class="sxs-lookup"><span data-stu-id="b4fcf-115">Example</span></span>

<span data-ttu-id="b4fcf-116">В следующем примере восстанавливается все учетные данные текущего развертывания облака соединителя:</span><span class="sxs-lookup"><span data-stu-id="b4fcf-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="b4fcf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b4fcf-117">See also</span></span>

[<span data-ttu-id="b4fcf-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b4fcf-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="b4fcf-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="b4fcf-119">Set-CcCredential</span></span>](set-cccredential.md)
  

