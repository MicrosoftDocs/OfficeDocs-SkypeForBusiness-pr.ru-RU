---
title: Call Park Create New or Edit Existing
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
description: Диапазоны номеров парка вызовов определяют временные номера, на которых проводятся припаркованные вызовы до тех пор, пока кто-то не выищет их или не отыщет время.
ms.openlocfilehash: 1a85bacf1ebb13afd7302f8e1cf50c112c3139e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095683"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="c1583-103">Парковка вызовов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="c1583-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="c1583-104">Диапазоны номеров парка вызовов определяют временные номера, на которых проводятся припаркованные вызовы до тех пор, пока кто-то не выищет их или не отыщет время.</span><span class="sxs-lookup"><span data-stu-id="c1583-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c1583-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="c1583-105">UI Reference</span></span>

<span data-ttu-id="c1583-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="c1583-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c1583-107">**Имя** Введите описательное имя, которое определяет диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="c1583-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="c1583-108">После сохранения диапазона номеров это имя не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="c1583-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="c1583-109">**Диапазон номеров** В первом поле введите начало номера диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="c1583-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="c1583-110">Во втором поле введите конечное число диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="c1583-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="c1583-111">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="c1583-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c1583-112">Значение начального номера диапазона должно иметь такую же длину, что и конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="c1583-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="c1583-p103">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="c1583-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="c1583-115">Если диапазон номеров начинается с символа или #, диапазон должен быть больше \* 100.</span><span class="sxs-lookup"><span data-stu-id="c1583-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="c1583-116">Допустимые значения: должны соответствовать регулярной строке выражения ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="c1583-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="c1583-117">Это означает, что значение должно быть строкой, начинаемой с символа или #, или числом от 1 до 9 (первый символ не \* может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="c1583-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="c1583-118">Если первый символ или #, следующий символ должен быть \* номером от 1 до 9 (он не может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="c1583-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="c1583-119">Последующими символами могут быть любые числа от 0 до 9 до семи дополнительных символов (например, "#6000", \* "92000", \* "95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="c1583-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="c1583-120">Если первый символ не является или #, первый символ должен быть номером от 1 до 9 (он не может быть нулем), а затем до восьми символов, каждый из которых имеет значение от 0 до \* 9 (например: 915551212;41212;300).</span><span class="sxs-lookup"><span data-stu-id="c1583-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="c1583-p105">Не следует использовать более 50 000 номеров на пул. Каждый диапазон номеров обычно включает в себя 100 или менее номеров, но может иметь и гораздо больший размер, хотя вмещает менее 10 000 номеров. Например, вместо указания начального номера "7000000" и конечного номера "8000000" рекомендуется указать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="c1583-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="c1583-124">**FQDN сервера назначения** Выберите полное доменное имя (FQDN) или iD службы службы приложений, в котором размещено приложение Call Park.</span><span class="sxs-lookup"><span data-stu-id="c1583-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="c1583-125">Все вызовы, припаркованные для номеров в диапазоне, указанном стартовим номером и конечным номером в диапазоне номеров, будут перенаселяться на этот сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="c1583-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="c1583-126">Подробные сведения о возможностях и возможностях Call Park см. в материале [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="c1583-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="c1583-127">Сведения о работе с диапазонами номеров Call Park см. в материале [Configure Phone Number Extensions for Parking Calls.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="c1583-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>