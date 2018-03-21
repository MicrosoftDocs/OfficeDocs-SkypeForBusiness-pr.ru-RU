---
title: "Задать ПИН-код для передачи номера для нового поставщика услуг"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f1defa5b-e49c-4d8c-a5f8-3f736201af5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Чтобы переключить или портов в работе телефонных номеров из Скайп для бизнеса в Интернет на другой поставщик услуг телефонной или поставщика, необходимо вручную задать ПИН-код. После установки ПИН-кода, необходимо включить его в случае запроса пользователя на порт номер телефона в работе."
ms.openlocfilehash: 5800ca846e4f71490be24ae02d031fa0579e2ce5
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="set-your-pin-for-transferring-numbers-to-a-new-service-provider"></a><span data-ttu-id="b2b11-104">Задать ПИН-код для передачи номера для нового поставщика услуг</span><span class="sxs-lookup"><span data-stu-id="b2b11-104">Set your PIN for transferring numbers to a new service provider</span></span>

<span data-ttu-id="b2b11-105">Для перемещения или *порта* номера телефонов из Скайп для бизнеса в Интернет на другой поставщик услуг телефонной или поставщика, необходимо вручную задать ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b2b11-105">To transfer or  *port out*  phone numbers from Skype for Business Online to another telephone service provider or carrier, you will need to manually set a PIN.</span></span> <span data-ttu-id="b2b11-106">После установки ПИН-кода, необходимо включить его в случае запроса пользователя на порт номер телефона в работе.</span><span class="sxs-lookup"><span data-stu-id="b2b11-106">After you set the PIN, you need to include it when you request to port a phone number out.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b2b11-107">Порт out ПИН-кода используется только для организаций, в США.</span><span class="sxs-lookup"><span data-stu-id="b2b11-107">A port out PIN is only used for organizations in the United States.</span></span> 
  
<span data-ttu-id="b2b11-108">[Перенос номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md) более подробные сведения о передаче и перенос ожидания телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="b2b11-108">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) for more information about transferring and porting in/out phone numbers.</span></span>
  
<span data-ttu-id="b2b11-109">Вот некоторые конкретные сведения о этот ПИН-код должен знать:</span><span class="sxs-lookup"><span data-stu-id="b2b11-109">Here is some specific information about this PIN you should know:</span></span>
  
- <span data-ttu-id="b2b11-110">Если не установить ПИН-код, нельзя будет для передачи или порта телефонных номеров из Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="b2b11-110">If a PIN isn't set, you won't be able to transfer or port out phone numbers from Skype for Business Online.</span></span>
    
- <span data-ttu-id="b2b11-111">Он может содержать 6 – 10 цифр (номера).</span><span class="sxs-lookup"><span data-stu-id="b2b11-111">It can contain 6-10 digits (numbers).</span></span>
    
- <span data-ttu-id="b2b11-112">Он не может содержать только буквы и специальные символы.</span><span class="sxs-lookup"><span data-stu-id="b2b11-112">It can't contain letters or special characters.</span></span>
    
- <span data-ttu-id="b2b11-113">ПИН-кода по умолчанию не задан, но если поместить в нельзя удалить или задайте значение пустым.</span><span class="sxs-lookup"><span data-stu-id="b2b11-113">The default PIN is blank, but if you put one in, you can't remove or set it back to blank.</span></span>
    
- <span data-ttu-id="b2b11-114">Можно обновить или изменить ПИН-код после внесения один.</span><span class="sxs-lookup"><span data-stu-id="b2b11-114">You can update or change the PIN after you put one in.</span></span>
    
## <a name="set-up-your-pin"></a><span data-ttu-id="b2b11-115">Настройка ПИН-код</span><span class="sxs-lookup"><span data-stu-id="b2b11-115">Set up your PIN</span></span>

1. <span data-ttu-id="b2b11-116">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="b2b11-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b2b11-117">Перейдите в **Центр администрирования Office 365** > **центры администрирования** > **Скайп для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b2b11-117">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b2b11-118">В левой панели навигации выберите **Voice** > **заказов на порт**.</span><span class="sxs-lookup"><span data-stu-id="b2b11-118">In the left navigation, choose **Voice** > **Port orders**.</span></span>
    
4. <span data-ttu-id="b2b11-119">Нажмите кнопку **задать вверх и управления ПИН-код** , используемый для передачи или перенос номеров для другого поставщика службы.</span><span class="sxs-lookup"><span data-stu-id="b2b11-119">Click **Set up and manage the PIN** that is used for transferring or porting numbers to another service carrier.</span></span>
    
5. <span data-ttu-id="b2b11-120">В **установить или изменить порт out ПИН-код** панели, введите ПИН-код и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b2b11-120">In the **Set or change your port out PIN** panel, enter your PIN and click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b2b11-121">Если вам нужно больше номеров, [обратитесь в службу поддержки администраторов Skype для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="b2b11-121">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b2b11-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2b11-122">Related topics</span></span>
[<span data-ttu-id="b2b11-123">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="b2b11-123">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="b2b11-124">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="b2b11-124">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b2b11-125">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="b2b11-125">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="b2b11-126">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="b2b11-126">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="b2b11-127">Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы</span><span class="sxs-lookup"><span data-stu-id="b2b11-127">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a><span data-ttu-id="b2b11-128">Отзыв?</span><span class="sxs-lookup"><span data-stu-id="b2b11-128">Feedback?</span></span>
<span data-ttu-id="b2b11-129">Для предоставления продукта свои отзывы и предложения или сообщите нам знать, как в нашем [Скайп для бизнеса свои отзывы и предложения](https://www.skypefeedback.com)см.</span><span class="sxs-lookup"><span data-stu-id="b2b11-129">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
  

