---
title: Как правильно вводить телефонные номера?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Научитесь настраивать номера телефонов при переносе их в Skype для бизнеса. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280533"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="c8585-103">Как правильно вводить телефонные номера?</span><span class="sxs-lookup"><span data-stu-id="c8585-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="c8585-104">При переносе номеров телефонов необходимо ввести их в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="c8585-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c8585-105">Каждый номер телефона или диапазон номера должен быть введен отдельно в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="c8585-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="c8585-106">Когда вы вводите один номер телефона, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c8585-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="c8585-107">Все специальные символы будут игнорироваться (в том числе тире "-").</span><span class="sxs-lookup"><span data-stu-id="c8585-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="c8585-108">Например:</span><span class="sxs-lookup"><span data-stu-id="c8585-108">For example:</span></span>
    
  - <span data-ttu-id="c8585-109">Для 10-значных номеров: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* будет исправлено на **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="c8585-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="c8585-110">Для 11-значных номеров: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** будет исправлено на **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="c8585-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="c8585-111">При наличии 10 или 11 цифр все теги будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="c8585-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="c8585-112">Например, \*\* \<див_гт_ 4255551234\</див_гт_\*\* будет **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="c8585-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="c8585-113">"-", пробел и скобка будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="c8585-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="c8585-114">Например:</span><span class="sxs-lookup"><span data-stu-id="c8585-114">For example:</span></span>
    
  - <span data-ttu-id="c8585-115">Для 10-значных номеров: **(425) 555-6776** будет исправлено на **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="c8585-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="c8585-116">Для 11-значных номеров: **1 (425) 555-6776** будет исправлено на **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="c8585-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="c8585-117">Все буквы обрабатываются как специальные символы и пропускаются, если номер телефона состоит из 10 цифр или 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="c8585-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="c8585-118">Например:</span><span class="sxs-lookup"><span data-stu-id="c8585-118">For example:</span></span>
    
  - <span data-ttu-id="c8585-119">Для 10-значных номеров: **14jaosia2reoij05jof55506ajfoj49isdjf** будет исправлено на **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="c8585-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="c8585-120">Для 11-значных номеров: **1ade4jaoda2rfoij05ojof55506dsfoj49if** будет исправлено на **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="c8585-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="c8585-121">Будут исправлены все комбинации специальных знаков, даже на других языках.</span><span class="sxs-lookup"><span data-stu-id="c8585-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="c8585-122">Например:</span><span class="sxs-lookup"><span data-stu-id="c8585-122">For example:</span></span> 
    
  - <span data-ttu-id="c8585-123">Для 10-значных номеров:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** будет исправлено на **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="c8585-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="c8585-124">Для 11-значных номеров:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** будет исправлено на **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="c8585-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="c8585-125">Если числа содержат менее 10 цифр или более 11 цифр, они будут выделены, чтобы пользователь был сам правильно:</span><span class="sxs-lookup"><span data-stu-id="c8585-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="c8585-126">\*\*5551245\* \* будет выделена и должна быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="c8585-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="c8585-127">**1234567891011** будет выделена и должна быть исправлена.</span><span class="sxs-lookup"><span data-stu-id="c8585-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="c8585-128">Любые числа, сокоторые менее 10 цифр или более 11 цифр, будут выделены без автоматического исправления.</span><span class="sxs-lookup"><span data-stu-id="c8585-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="c8585-129">Для 7-значного числа без ввода специальных знаков: **123456abcdefg7** будет выделена, и его необходимо будет исправить, но буквы не будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="c8585-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="c8585-130">Для 7-значного числа со всеми введенными символами: **12345! @ # $% ^&amp;\*()--@ # $&amp;\*% ^ () 7** будет выделена для исправления.</span><span class="sxs-lookup"><span data-stu-id="c8585-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="c8585-131">Специальные символы не будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="c8585-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="c8585-132">Когда вы вводите диапазон телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="c8585-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="c8585-133">Разрешено использовать только два номера телефона.</span><span class="sxs-lookup"><span data-stu-id="c8585-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="c8585-134">Меньший номер должен быть первым числом в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="c8585-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="c8585-135">Все специальные символы (за исключением тире "-") обрабатываются одинаково одинарными числами.</span><span class="sxs-lookup"><span data-stu-id="c8585-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="c8585-136">Например, **(425) 555 0&amp;\*(123-(1425) 5557899nm** будет исправлено на **+ 14255550123-+ 13202040659**.</span><span class="sxs-lookup"><span data-stu-id="c8585-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="c8585-137">"-" Используется только для разделения двух чисел.</span><span class="sxs-lookup"><span data-stu-id="c8585-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="c8585-138">Она не поддерживается для включения нескольких "-" в диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="c8585-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="c8585-139">Например, **(425) 555-0649-(425) 555-1115** следует ввести как **(425) 5550649-(425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="c8585-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="c8585-140">**Полные пошаговые инструкции можно найти [в статье перенос номеров телефонов в Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="c8585-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8585-141">Если вам нужно больше номеров, [обратитесь в службу поддержки администраторов Skype для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c8585-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="c8585-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8585-142">Related topics</span></span>
[<span data-ttu-id="c8585-143">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="c8585-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="c8585-144">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="c8585-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="c8585-145">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="c8585-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c8585-146">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="c8585-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c8585-147">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c8585-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 