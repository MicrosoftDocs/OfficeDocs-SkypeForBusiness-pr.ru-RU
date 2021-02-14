---
title: Тип правила трансляции регулярное выражение
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: В поле Соответствовать шаблону укажите шаблон, который будет использоваться для того, чтобы ему соответствовали номера, предназначенные для преобразования. В поле Правило преобразования укажите шаблон для формата преобразованных номеров. Например, если ввести ^ (\d \d+)$ в поле "Соответствие этому шаблону" и 011$1 в поле правила трансляции, правило переведет \+ {9} +441235551010 в 011441235551010.
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818859"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="37781-105">Правило преобразования: ввод регулярного выражения</span><span class="sxs-lookup"><span data-stu-id="37781-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="37781-106">В поле **Соответствовать шаблону** укажите шаблон, который будет использоваться для того, чтобы ему соответствовали номера, предназначенные для преобразования.</span><span class="sxs-lookup"><span data-stu-id="37781-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="37781-107">В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="37781-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="37781-108">Например, если ввести ^ (\d \d+)$ в поле "Соответствие этому шаблону" и 011$1 в поле правила трансляции, правило переведет \+ {9} +441235551010 в 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="37781-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="37781-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="37781-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

