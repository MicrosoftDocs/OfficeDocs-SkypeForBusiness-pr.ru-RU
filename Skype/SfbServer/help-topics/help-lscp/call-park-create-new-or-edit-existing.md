---
title: Создание новой или редактирование существующей парковки вызовов
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Диапазоны номеров для парковки вызовов определяют временные номера, где удерживаются запаркованные вызовы, пока кто-то восстановит их, или они времени ожидания.
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="4d8b8-103">Парковка вызовов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="4d8b8-103">Call Park: Create New or Edit Existing</span></span>
 
<span data-ttu-id="4d8b8-104">Диапазоны номеров для парковки вызовов определяют временные номера, где удерживаются запаркованные вызовы, пока кто-то восстановит их, или они времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="4d8b8-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="4d8b8-105">UI Reference</span></span>

<span data-ttu-id="4d8b8-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="4d8b8-107">**Имя** Введите описательное имя, которое определяет диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="4d8b8-108">После сохранения диапазон номеров, это имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-108">After you save the number range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="4d8b8-109">**Номер диапазона** В первом поле введите первый номер диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="4d8b8-110">Во втором поле введите последний номер диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-110">In the second field, type the ending number of the number range.</span></span>
    
  - <span data-ttu-id="4d8b8-111">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="4d8b8-112">Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
  - <span data-ttu-id="4d8b8-p103">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
  - <span data-ttu-id="4d8b8-115">Если диапазон номеров начинается с символа \* или #, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
  - <span data-ttu-id="4d8b8-116">Допустимые значения: должны совпадать со строкой регулярного выражения ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d {0,8}).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="4d8b8-117">Это означает, что значение должно быть строк, начиная с любого из символа \* или # или число от 1 до 9 (первого знака не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="4d8b8-118">Если первый символ \* или #, символ должно быть число от 1 до 9 (его не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="4d8b8-119">Последующие символы могут быть любое число от 0 до 9 до 7 дополнительных символов (например, «#6000», "\*92000" "\*95551212" и «915551212»).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="4d8b8-120">Если первый символ не \* или #, первым символом должно быть числом 1 до 9 (не может быть равно нулю), а затем до восьми знаков, каждый номер цифры от 0 до 9 (например: 915551212; 41212; 300).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>
    
  - <span data-ttu-id="4d8b8-p105">Не следует использовать более 50 000 номеров на пул. Каждый диапазон номеров обычно включает в себя 100 или менее номеров, но может иметь и гораздо больший размер, хотя вмещает менее 10 000 номеров. Например, вместо указания начального номера "7000000" и конечного номера "8000000" рекомендуется указать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="4d8b8-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
- <span data-ttu-id="4d8b8-124">**Полное доменное имя конечного сервера** Выберите полное доменное имя (FQDN) или идентификатор службы приложения, на котором размещается приложение парковки вызовов службы.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="4d8b8-125">Приостанавливать всех вызовов на номера в диапазон, указанный с начальное число и конечный номер диапазона номеров будут направляться на этот сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="4d8b8-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>
    
<span data-ttu-id="4d8b8-126">Для получения дополнительных сведений о парковки вызовов функций и возможностей видеть [Планирование парковки вызовов в Скайп для 2015 бизнеса](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="4d8b8-127">Для получения дополнительных сведений о работе с диапазоны номеров для парковки вызовов видеть [Настройки расширений номер телефона для парковки вызовов](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d8b8-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

