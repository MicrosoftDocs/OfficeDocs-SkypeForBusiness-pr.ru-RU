---
title: Сведения об учетной записи в заказе на перенос номера
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: bf4ea2ea-4f7c-4f41-8e4c-d9ceb11626cc
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
f1keywords:
- ms.lync.lac.PortOrderAccountInfo
ms.custom:
- Calling Plans
description: 'Сведения об учетной записи, которые понадобятся при работе с новым местным мастером заказа на перенос номеров. '
ms.openlocfilehash: 4d1ac6831287281b5e9dfa691e09807d2887aaf4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280709"
---
# <a name="port-order-account-information"></a><span data-ttu-id="802d3-103">Сведения об учетной записи в заказе на перенос номера</span><span class="sxs-lookup"><span data-stu-id="802d3-103">Port order account information</span></span>

<span data-ttu-id="802d3-104">При использовании страницы " **сведения об учетной записи** " в мастере создания **заказов на переносные номера в новом локальном номере** для отправки заказа на перенос вам понадобятся практически все данные, которые вы бы хотели бы использовать в LOA, в том числе:</span><span class="sxs-lookup"><span data-stu-id="802d3-104">When you are using the **Account information** page in the **New Local Number Port Order** wizard to submit a port order, you will need almost all of the same information that you would provide in the LOA, including:</span></span>
  
- <span data-ttu-id="802d3-105">Номер счета для поставщика услуг или оператора</span><span class="sxs-lookup"><span data-stu-id="802d3-105">Account number for the service provider or carrier</span></span>
    
- <span data-ttu-id="802d3-106">Телефонный номер, на который выставляется счет (BTN)</span><span class="sxs-lookup"><span data-stu-id="802d3-106">Billing Telephone Number (BTN)</span></span>
    
- <span data-ttu-id="802d3-107">PIN-код — при необходимости у текущего поставщика услуг или оператора</span><span class="sxs-lookup"><span data-stu-id="802d3-107">PIN - if needed by your current service provider or carrier</span></span>
    
- <span data-ttu-id="802d3-108">Название компании</span><span class="sxs-lookup"><span data-stu-id="802d3-108">Company name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="802d3-109">Это позволит получать только 25 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="802d3-109">This will only accept 25 characters, including spaces.</span></span> <span data-ttu-id="802d3-110">Если название компании превышает 25 символов, в целях дальнейшей обработки заказа на перенос будут сохранены первые 25 символов.</span><span class="sxs-lookup"><span data-stu-id="802d3-110">If the company's name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="802d3-111">Имя уполномоченного представителя (доверителя)</span><span class="sxs-lookup"><span data-stu-id="802d3-111">Authorized user's name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="802d3-112">Это может быть только 15 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="802d3-112">This will only accept 15 characters, including spaces.</span></span> <span data-ttu-id="802d3-113">Если имя доверителя превышает 15 символов, в целях дальнейшей обработки заказа на перенос будут сохранены первые 15 символов.</span><span class="sxs-lookup"><span data-stu-id="802d3-113">If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="802d3-114">Адрес для получения корреспонденции</span><span class="sxs-lookup"><span data-stu-id="802d3-114">Service address</span></span>
    
- <span data-ttu-id="802d3-115">Город, штат и почтовый индекс для адреса выставления счета</span><span class="sxs-lookup"><span data-stu-id="802d3-115">City, State, and Zip code of the billing address</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="802d3-116">Вы не хотите, чтобы подпись пользователя для авторизации была авторизована.</span><span class="sxs-lookup"><span data-stu-id="802d3-116">You won't need the authorizing person's signature.</span></span> 
  
<span data-ttu-id="802d3-117">Чтобы отправить заказ на перенос по номеру порта и устранить ошибки, убедитесь, что вы сделали следующее:</span><span class="sxs-lookup"><span data-stu-id="802d3-117">To make submitting the port order easy and avoid errors, make sure you do the following:</span></span>
  
- <span data-ttu-id="802d3-118">Удалите все компоненты (например, группы слежения), связанные с Вашими числами.</span><span class="sxs-lookup"><span data-stu-id="802d3-118">Remove any features (such as Hunt Groups) associated with your numbers.</span></span> <span data-ttu-id="802d3-119">Убедитесь, что у вас есть дополнительные возможности управления звонками, такие как слежение за звонками и Различение звонков, которые включены на этих телефонных номерах.</span><span class="sxs-lookup"><span data-stu-id="802d3-119">Make sure there are no advanced call control features, such as Call Hunt or Distinctive Ring, enabled on these telephone numbers.</span></span>
    
- <span data-ttu-id="802d3-120">Убедитесь в том, что вы не поместили новые заказы на обслуживание или отключаются от текущего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="802d3-120">Ensure that you haven't placed any new service orders or disconnects with your current service provider.</span></span>
    
- <span data-ttu-id="802d3-121">Убедитесь, что все номера указаны в одной и той же несущей и одной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="802d3-121">Make sure all numbers are from the same carrier and the same account.</span></span>
    
- <span data-ttu-id="802d3-122">Убедитесь в том, что предоставленные сведения учетной записи точно соответствуют вашей записи телефонной несущей.</span><span class="sxs-lookup"><span data-stu-id="802d3-122">Make sure the account information you give matches exactly what your phone carrier has on record.</span></span> <span data-ttu-id="802d3-123">Несовпадающая информация является наиболее распространенной причиной ошибок и может задержать ваш заказ на перенос.</span><span class="sxs-lookup"><span data-stu-id="802d3-123">Mismatched information is the most common cause of errors and can delay your port order.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="802d3-124">**Не отключайте услуги, предоставляемые поставщиком услуг или оператором связи.**> **Для переноса номеров в Skype для бизнеса Online услуги предыдущего поставщика должны оставаться активными.**> **Не блокируйте свой счет у поставщика услуг или оператора связи. Поменять оператора связи заблокированного счета не представляется возможным. Для отмены блокировки счета уполномоченный представитель отправляет поставщику услуг соответствующую заявку. В зависимости от оператора связи, этот процесс может занять от 1 до 3 дней.**></span><span class="sxs-lookup"><span data-stu-id="802d3-124">**Don't disconnect your services with your service provider or carrier.**> **You must keep your previous service active in order to port your phone numbers to Skype for Business Online.**> **Don't freeze your account with your service provider or carrier. Freezing the account prevents the change of carriers on the account. The authorized user will need to submit an order to the current carrier to remove the freeze. This process can take 1-3 weeks, depending on the carrier.**></span></span> 
  
 <span data-ttu-id="802d3-125">**Полные пошаговые инструкции можно найти [в статье перенос номеров телефонов в Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="802d3-125">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

 > [!NOTE]
> <span data-ttu-id="802d3-126">Если вам нужно больше номеров, [обратитесь в службу поддержки администраторов Skype для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="802d3-126">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="802d3-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="802d3-127">Related topics</span></span>
[<span data-ttu-id="802d3-128">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="802d3-128">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="802d3-129">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="802d3-129">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="802d3-130">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="802d3-130">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="802d3-131">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="802d3-131">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="802d3-132">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="802d3-132">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 