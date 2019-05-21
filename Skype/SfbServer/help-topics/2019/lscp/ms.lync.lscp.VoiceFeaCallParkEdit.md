---
title: Допустить Звонок создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Диапазоны номеров приостановки вызовов определяют временные номера, в которых приостановленные звонки удерживаются, пока кто-то не получит их.
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290172"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="0c0fa-103">Парковка вызовов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="0c0fa-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="0c0fa-104">Диапазоны номеров приостановки вызовов определяют временные номера, в которых приостановленные звонки удерживаются, пока кто-то не получит их.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0c0fa-105">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="0c0fa-105">UI Reference</span></span>

<span data-ttu-id="0c0fa-106">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0c0fa-107">**Name (имя** ) Введите описательное имя, определяющее диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="0c0fa-108">Не удается изменить это имя после сохранения диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="0c0fa-109">**Диапазон номеров** В первом поле введите начальный номер диапазона чисел.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="0c0fa-110">Во втором поле Введите конечный номер диапазона чисел.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="0c0fa-111">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="0c0fa-112">Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="0c0fa-p103">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="0c0fa-115">Если диапазон номеров начинается с символа \* или #, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="0c0fa-116">Допустимые значения: должны соответствовать строке регулярного выражения (\\[\* | #] _км_ [1-9]{0,7}\d) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="0c0fa-117">Это означает, что значение должно быть строкой, начинающейся с \* символа или # или числа 1 – 9 (первый символ не может равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="0c0fa-118">Если первый символ имеет \* значение или #, следующий символ должен быть числом от 1 до 9 (оно не может равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="0c0fa-119">Последующие символы могут быть числами от 0 до 9 до семи дополнительных символов (например, "#6000", "\*92000", "\*95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="0c0fa-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="0c0fa-120">Если первый символ не \* или является числом #, первый символ должен быть цифрами от 1 до 9 (он не может быть равен нулю), после чего следует использовать до восьми символов, каждый из которых содержит число от 0 до 9 (например: 915551212; 41212; 300).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="0c0fa-p105">Не следует использовать более 50 000 номеров на пул. Каждый диапазон номеров обычно включает в себя 100 или менее номеров, но может иметь и гораздо больший размер, хотя вмещает менее 10 000 номеров. Например, вместо указания начального номера "7000000" и конечного номера "8000000" рекомендуется указать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="0c0fa-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="0c0fa-124">**Полное доменное имя конечного сервера** Выберите полное доменное имя (FQDN) или идентификатор службы приложения, на котором размещается приложение для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="0c0fa-125">Все звонки, приостановленные на номера в диапазоне, указанном начальным номером и конечным номером в диапазоне номеров, будут перенаправлены на этот сервер или в пул.</span><span class="sxs-lookup"><span data-stu-id="0c0fa-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="0c0fa-126">Дополнительные сведения о функциях и возможностях приостановки звонка можно найти [в разделе Планирование приостановки звонков в Skype для бизнеса](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="0c0fa-127">Подробнее о работе с диапазонами номеров для присоединения к абоненту можно узнать в разделе [Настройка расширений номеров телефонов для вызовов парковки](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="0c0fa-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


