---
title: Тип правила трансляции регулярное выражение
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: 'В поле Соответствовать шаблону укажите шаблон, который будет использоваться для того, чтобы ему соответствовали номера, предназначенные для преобразования. В поле Правило преобразования укажите шаблон для формата преобразованных номеров. '
ms.openlocfilehash: a1e04cc94c004b520c077816ae535ca4154047ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819989"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="a778d-104">Правило преобразования: ввод регулярного выражения</span><span class="sxs-lookup"><span data-stu-id="a778d-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="a778d-105">В поле **Соответствовать шаблону** укажите шаблон, который будет использоваться для того, чтобы ему соответствовали номера, предназначенные для преобразования.</span><span class="sxs-lookup"><span data-stu-id="a778d-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="a778d-106">В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="a778d-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="a778d-107">Например, если ввести ^ (\d \d+)$ в поле "Соответствие этому шаблону" и 011$1 в поле правила трансляции, правило переведет \+ {9} +441235551010 в 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="a778d-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

