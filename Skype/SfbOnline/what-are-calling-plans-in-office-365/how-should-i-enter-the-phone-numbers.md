---
title: Как ввести номера телефонов?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Узнайте, как настраивать номера телефонов при переносе их Скайп для бизнеса. '
ms.openlocfilehash: 74914b98ccc60984f1d2be16f6a3351e7b26b2cf
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="454a8-103">Как ввести номера телефонов?</span><span class="sxs-lookup"><span data-stu-id="454a8-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="454a8-104">При переносе номера телефонов, им необходимо ввести в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="454a8-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="454a8-105">Каждый номер телефона или диапазон номер телефона должен указываться отдельно в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="454a8-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="454a8-106">При вводе одного номера телефонов:</span><span class="sxs-lookup"><span data-stu-id="454a8-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="454a8-107">Все специальные символы будет игнорироваться (включая тире «-»).</span><span class="sxs-lookup"><span data-stu-id="454a8-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="454a8-108">Например:</span><span class="sxs-lookup"><span data-stu-id="454a8-108">For example:</span></span>
    
  - <span data-ttu-id="454a8-109">Для 10-значное число: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* будет исправлена в **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="454a8-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="454a8-110">Для 11-значного числа: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** будет исправлена в **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="454a8-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="454a8-111">Все теги будут игнорироваться при наличии 10 или 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="454a8-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="454a8-112">Например ** \<div > 4255551234\</div >** будет **+14255551234**.</span><span class="sxs-lookup"><span data-stu-id="454a8-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="454a8-113">«-», будет игнорироваться пространство и скобки.</span><span class="sxs-lookup"><span data-stu-id="454a8-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="454a8-114">Например:</span><span class="sxs-lookup"><span data-stu-id="454a8-114">For example:</span></span>
    
  - <span data-ttu-id="454a8-115">Для 10-значное число: **(425) 555-6776** будет исправлена в **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="454a8-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="454a8-116">Для 11-значного числа: **1(425) 555-6776** будет исправлена в **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="454a8-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="454a8-117">Все буквы будет рассматриваться как специальные символы и игнорируется, если номер телефона цифра 10 или 11 разрядов.</span><span class="sxs-lookup"><span data-stu-id="454a8-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="454a8-118">Например:</span><span class="sxs-lookup"><span data-stu-id="454a8-118">For example:</span></span>
    
  - <span data-ttu-id="454a8-119">Для 10-значное число: **14jaosia2reoij05jof55506ajfoj49isdjf** будет исправлена в **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="454a8-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="454a8-120">Для 11-значного числа: **1ade4jaoda2rfoij05ojof55506dsfoj49if** будет исправлена в **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="454a8-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="454a8-121">Будет исправлена любое сочетание специальные знаки, даже на других языках.</span><span class="sxs-lookup"><span data-stu-id="454a8-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="454a8-122">Например:</span><span class="sxs-lookup"><span data-stu-id="454a8-122">For example:</span></span> 
    
  - <span data-ttu-id="454a8-123">Для 10-значное число:**中文4中文2ajj5\*() (\*(5()... 551345** будет исправлена в **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="454a8-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="454a8-124">Для 11-значного числа:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** будет исправлена в **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="454a8-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="454a8-125">Если все номера содержит не более 10 цифр или более 11 знаков, они будут выделены для пользователя для исправления:</span><span class="sxs-lookup"><span data-stu-id="454a8-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="454a8-126">\*\*5551245\* \* будут выделены и требуется исправить.</span><span class="sxs-lookup"><span data-stu-id="454a8-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="454a8-127">**1234567891011** будет выделена и требуется исправить.</span><span class="sxs-lookup"><span data-stu-id="454a8-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="454a8-128">Все номера, которые не более 10 цифр или более 11 цифр, и специальные знаки, будет выделена без автоматически исправленные.</span><span class="sxs-lookup"><span data-stu-id="454a8-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="454a8-129">Для 7-значного числа без специальных символов, введенных: **123456abcdefg7** будут выделены и требуется исправить, но буквы не будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="454a8-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="454a8-130">Для числа 7-значных с специальных символов, введенных: **12345!@#$%^&amp;\*(--) @# $% ^&amp;\*(7)** будет выделена исправить.</span><span class="sxs-lookup"><span data-stu-id="454a8-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="454a8-131">Специальные символы не будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="454a8-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="454a8-132">При вводе диапазон номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="454a8-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="454a8-133">Разрешены только два телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="454a8-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="454a8-134">Меньшее число должен быть первый номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="454a8-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="454a8-135">Все специальные символы (за исключением дефиса «-»), обрабатывается так же, как одного числа.</span><span class="sxs-lookup"><span data-stu-id="454a8-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="454a8-136">Например **(425) 555 0&amp;\*(123-(1425) 5557899nm** будет исправлена в **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="454a8-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="454a8-137">«-» Используется для только разделение двух чисел.</span><span class="sxs-lookup"><span data-stu-id="454a8-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="454a8-138">Он не поддерживается для включения нескольких «-» в диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="454a8-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="454a8-139">Например, следует вводить **(425) 555-0649-(425) 555-1115** в виде **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="454a8-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="454a8-140">**Подробные пошаговые инструкции в разделе [Передача телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="454a8-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="454a8-141">Если вам нужно больше номеров, [обратитесь в службу поддержки администраторов Skype для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="454a8-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="454a8-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="454a8-142">Related topics</span></span>
[<span data-ttu-id="454a8-143">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="454a8-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="454a8-144">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="454a8-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="454a8-145">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="454a8-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="454a8-146">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="454a8-146">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="454a8-147">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="454a8-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 