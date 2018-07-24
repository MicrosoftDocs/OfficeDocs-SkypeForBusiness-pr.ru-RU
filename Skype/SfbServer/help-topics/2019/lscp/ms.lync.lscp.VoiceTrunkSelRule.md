---
title: Выбор правил преобразования
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Корпоративной голосовой связи требуется, что все номера строк преобразовываться в формат E.164 для выполнения обратного номеров поиск. Ответная часть магистрали (то есть связанный шлюз, УАТС или магистраль SIP) может требовать того, чтобы номера были указаны в местном формате набора номеров. Чтобы преобразовать номера из формата E.164 в местный формат набора номеров, можно задать одно или несколько правил преобразования, которые будут изменять URI запроса перед отправкой его в ответную часть магистрали. Например, можно написать правило преобразования для удаления +44 из начала строки набора и замены этой последовательности номером 0144.
ms.openlocfilehash: c1a8b5e3506eea97e6f9bab7c455eb31d26f4455
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998990"
---
# <a name="select-translation-rules"></a><span data-ttu-id="72f18-106">Выбор правил преобразования</span><span class="sxs-lookup"><span data-stu-id="72f18-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="72f18-107">Корпоративной голосовой связи требуется, что все номера строк преобразовываться в формат E.164 для выполнения обратного номеров поиск.</span><span class="sxs-lookup"><span data-stu-id="72f18-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="72f18-108">Ответная часть магистрали (то есть связанный шлюз, УАТС или магистраль SIP) может требовать того, чтобы номера были указаны в местном формате набора номеров.</span><span class="sxs-lookup"><span data-stu-id="72f18-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="72f18-109">Чтобы преобразовать номера из формата E.164 в местный формат набора номеров, можно задать одно или несколько правил преобразования, которые будут изменять URI запроса перед отправкой его в ответную часть магистрали.</span><span class="sxs-lookup"><span data-stu-id="72f18-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="72f18-110">Например, можно написать правило преобразования для удаления +44 из начала строки набора и замены этой последовательности номером 0144.</span><span class="sxs-lookup"><span data-stu-id="72f18-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="72f18-111">Связывать один или несколько правил преобразования с конфигурацией магистрали корпоративной голосовой связи предназначен для использования в качестве альтернативного при настройке правил преобразования на узле магистрали.</span><span class="sxs-lookup"><span data-stu-id="72f18-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="72f18-112">Не связывайте правила трансляции с конфигурацией магистрали корпоративной голосовой связи, если вы настроили правила преобразования на узле магистрали два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="72f18-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="72f18-113">Чтобы использовать существующее правило преобразования, щелкните правило в списке, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72f18-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

