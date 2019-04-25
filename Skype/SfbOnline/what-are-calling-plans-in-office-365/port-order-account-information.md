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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.PortOrderAccountInfo
ms.custom:
- Calling Plans
description: 'Узнайте, какие сведения учетной записи, вам потребуются при работе с помощью мастера новый локальный заказ номер порта. '
ms.openlocfilehash: 404bef2ad18728de90ac0a296c213e841719984b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229850"
---
# <a name="port-order-account-information"></a><span data-ttu-id="d24dd-103">Сведения об учетной записи в заказе на перенос номера</span><span class="sxs-lookup"><span data-stu-id="d24dd-103">Port order account information</span></span>

<span data-ttu-id="d24dd-104">При использовании страницы **сведений об учетной записи** в мастере **Новый локальный заказ номер порта** для отправки заказа на порт, необходимо будет почти все те же данные, который будет предоставлять ЗАГРУ, в том числе:</span><span class="sxs-lookup"><span data-stu-id="d24dd-104">When you are using the **Account information** page in the **New Local Number Port Order** wizard to submit a port order, you will need almost all of the same information that you would provide in the LOA, including:</span></span>
  
- <span data-ttu-id="d24dd-105">Номер учетной записи для поставщика услуг или поставщика</span><span class="sxs-lookup"><span data-stu-id="d24dd-105">Account number for the service provider or carrier</span></span>
    
- <span data-ttu-id="d24dd-106">Телефонный номер, на который выставляется счет (BTN)</span><span class="sxs-lookup"><span data-stu-id="d24dd-106">Billing Telephone Number (BTN)</span></span>
    
- <span data-ttu-id="d24dd-107">ПИН-код — Если необходимая для текущего поставщика услуг или поставщика</span><span class="sxs-lookup"><span data-stu-id="d24dd-107">PIN - if needed by your current service provider or carrier</span></span>
    
- <span data-ttu-id="d24dd-108">Название компании</span><span class="sxs-lookup"><span data-stu-id="d24dd-108">Company name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d24dd-109">Это принимает только 25 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="d24dd-109">This will only accept 25 characters, including spaces.</span></span> <span data-ttu-id="d24dd-110">Если название компании превышает 25 символов, в целях дальнейшей обработки заказа на перенос будут сохранены первые 25 символов.</span><span class="sxs-lookup"><span data-stu-id="d24dd-110">If the company's name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="d24dd-111">Имя уполномоченного представителя (доверителя)</span><span class="sxs-lookup"><span data-stu-id="d24dd-111">Authorized user's name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d24dd-112">Это принимает только 15 символов, включая пробелы.</span><span class="sxs-lookup"><span data-stu-id="d24dd-112">This will only accept 15 characters, including spaces.</span></span> <span data-ttu-id="d24dd-113">Если имя доверителя превышает 15 символов, в целях дальнейшей обработки заказа на перенос будут сохранены первые 15 символов.</span><span class="sxs-lookup"><span data-stu-id="d24dd-113">If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="d24dd-114">Адрес для получения корреспонденции</span><span class="sxs-lookup"><span data-stu-id="d24dd-114">Service address</span></span>
    
- <span data-ttu-id="d24dd-115">Город, состояние и почтовый индекс адреса для выставления счетов</span><span class="sxs-lookup"><span data-stu-id="d24dd-115">City, State, and Zip code of the billing address</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d24dd-116">Подпись авторизацию пользователя не нужно.</span><span class="sxs-lookup"><span data-stu-id="d24dd-116">You won't need the authorizing person's signature.</span></span> 
  
<span data-ttu-id="d24dd-117">Чтобы сделать Отправка простой номеру порта и избежать ошибок, убедитесь, что вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d24dd-117">To make submitting the port order easy and avoid errors, make sure you do the following:</span></span>
  
- <span data-ttu-id="d24dd-118">Удалите все компоненты (например, сервисные группы), связанные с номерам.</span><span class="sxs-lookup"><span data-stu-id="d24dd-118">Remove any features (such as Hunt Groups) associated with your numbers.</span></span> <span data-ttu-id="d24dd-119">Убедитесь, что нет компонентов управления расширенных вызовов, например вызова сервисной или особый сигнал, включены на эти номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="d24dd-119">Make sure there are no advanced call control features, such as Call Hunt or Distinctive Ring, enabled on these telephone numbers.</span></span>
    
- <span data-ttu-id="d24dd-120">Убедитесь, что не были помещены все новые заказы службы или отключает текущего поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="d24dd-120">Ensure that you haven't placed any new service orders or disconnects with your current service provider.</span></span>
    
- <span data-ttu-id="d24dd-121">Убедитесь в том, что все номера из того же поставщика и ту же учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d24dd-121">Make sure all numbers are from the same carrier and the same account.</span></span>
    
- <span data-ttu-id="d24dd-122">Убедитесь в том, что учетные данные, которые вам нужно предоставить соответствует только что своего телефона оператора влияет на запись.</span><span class="sxs-lookup"><span data-stu-id="d24dd-122">Make sure the account information you give matches exactly what your phone carrier has on record.</span></span> <span data-ttu-id="d24dd-123">Несоответствие информация является наиболее распространенные стать причиной ошибок и отложить заказа порт.</span><span class="sxs-lookup"><span data-stu-id="d24dd-123">Mismatched information is the most common cause of errors and can delay your port order.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="d24dd-124">**Не отключайте услуги, предоставляемые поставщиком услуг или оператором связи.**> **Для переноса номеров в Skype для бизнеса Online услуги предыдущего поставщика должны оставаться активными.**> **Не блокируйте свой счет у поставщика услуг или оператора связи. Поменять оператора связи заблокированного счета не представляется возможным. Для отмены блокировки счета уполномоченный представитель отправляет поставщику услуг соответствующую заявку. В зависимости от оператора связи, этот процесс может занять от 1 до 3 дней.**></span><span class="sxs-lookup"><span data-stu-id="d24dd-124">**Don't disconnect your services with your service provider or carrier.**> **You must keep your previous service active in order to port your phone numbers to Skype for Business Online.**> **Don't freeze your account with your service provider or carrier. Freezing the account prevents the change of carriers on the account. The authorized user will need to submit an order to the current carrier to remove the freeze. This process can take 1-3 weeks, depending on the carrier.**></span></span> 
  
 <span data-ttu-id="d24dd-125">**Подробные пошаговые инструкции в разделе [Передача телефонных номеров в Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="d24dd-125">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

 > [!NOTE]
> <span data-ttu-id="d24dd-126">Если вам нужно больше номеров, [обратитесь в службу поддержки администраторов Skype для бизнеса](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="d24dd-126">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d24dd-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d24dd-127">Related topics</span></span>
[<span data-ttu-id="d24dd-128">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="d24dd-128">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="d24dd-129">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="d24dd-129">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="d24dd-130">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="d24dd-130">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d24dd-131">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="d24dd-131">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="d24dd-132">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d24dd-132">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 