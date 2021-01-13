---
title: Создание или изменение существующей парковки вызовов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Диапазоны номеров парковки вызовов определяют временные номера, на которых удерживаются припаркованные вызовы до тех пор, пока кто-то не извлекает их или не будет по извлечения.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819389"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="846c6-103">Парковка вызовов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="846c6-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="846c6-104">Диапазоны номеров парковки вызовов определяют временные номера, на которых удерживаются припаркованные вызовы до тех пор, пока кто-то не извлекает их или не по истощеет время их действия.</span><span class="sxs-lookup"><span data-stu-id="846c6-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="846c6-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="846c6-105">UI Reference</span></span>

<span data-ttu-id="846c6-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="846c6-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="846c6-107">**Имя** Введите описательное имя, идентифицирующие диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="846c6-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="846c6-108">После сохранения диапазона номеров это имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="846c6-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="846c6-109">**Диапазон номеров** В первом поле введите первый номер диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="846c6-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="846c6-110">Во втором поле введите конец диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="846c6-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="846c6-111">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="846c6-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="846c6-112">Значение начального номера диапазона должно иметь такую же длину, что и конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="846c6-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="846c6-p103">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="846c6-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="846c6-115">Если диапазон номеров начинается с символа #, диапазон должен быть больше \* 100.</span><span class="sxs-lookup"><span data-stu-id="846c6-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="846c6-116">Допустимые значения: должны соответствовать строке регулярного выражения ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1–9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="846c6-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="846c6-117">Это означает, что значение должно быть строкой, начинаемой с символа или #, или числом от 1 до 9 (первый символ не может \* быть нулем).</span><span class="sxs-lookup"><span data-stu-id="846c6-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="846c6-118">Если первый символ является или #, следующий символ должен быть \* числом от 1 до 9 (не может быть нулем).</span><span class="sxs-lookup"><span data-stu-id="846c6-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="846c6-119">Последующие символы могут быть любым числом от 0 до 9 до семи дополнительных символов (например, "#6000", \* "92000", \* "95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="846c6-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="846c6-120">Если первый символ не является или #, первым должен быть номер от 1 до 9 (он не может быть нулем), за которым следует до восьми символов, каждый из которых имеет значение от 0 до \* 9 (например: 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="846c6-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="846c6-p105">Не следует использовать более 50 000 номеров на пул. Каждый диапазон номеров обычно включает в себя 100 или менее номеров, но может иметь и гораздо больший размер, хотя вмещает менее 10 000 номеров. Например, вместо указания начального номера "7000000" и конечного номера "8000000" рекомендуется указать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="846c6-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="846c6-124">**FQDN конечного сервера** Выберите полное доменное имя (FQDN) или ИД службы приложений, в котором размещено приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="846c6-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="846c6-125">Все вызовы, припаркованные на номера в диапазоне, указанном в начале и конце диапазона номеров, будут перенаться на этот сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="846c6-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="846c6-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="846c6-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="846c6-127">Подробные сведения о работе с диапазонами номеров парковки вызовов см. в подстроке "Настройка расширений телефонных [номеров для парковки вызовов".](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)</span><span class="sxs-lookup"><span data-stu-id="846c6-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


