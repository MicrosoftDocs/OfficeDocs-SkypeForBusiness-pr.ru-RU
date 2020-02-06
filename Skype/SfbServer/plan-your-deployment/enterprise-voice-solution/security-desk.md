---
title: Включите службу безопасности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Планирование включения службы безопасности Организации в E9-1-1 развертывание в корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 19fc8a01fcb51be3ce36435a5a657c3253716b2c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802459"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="02b02-103">Включите службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="02b02-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="02b02-104">Планирование включения службы безопасности Организации в E9-1-1 развертывание в корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="02b02-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="02b02-p101">Вашей компании может потребоваться, чтобы в обработке экстренного вызова принимала участие служба безопасности. Чтобы помочь принять решения о способе интеграции службы безопасности с развертыванием E9-1-1, следует ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="02b02-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="02b02-107">**Требуется ли оповещать службу безопасности об экстренном вызове?**</span><span class="sxs-lookup"><span data-stu-id="02b02-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="02b02-108">Вы можете настроить политику расположения таким образом, чтобы в Skype для бизнеса Server отправлялись оповещения о мгновенных сообщениях в адреса SIP для Skype для бизнеса в одном или нескольких сотрудниках безопасности.</span><span class="sxs-lookup"><span data-stu-id="02b02-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="02b02-109">Эти предупреждения содержат имя, номер и место нахождения сотрудника, выполняющего экстренный вызов, и упрощают своевременное реагирование службы безопасности на экстренную ситуацию.</span><span class="sxs-lookup"><span data-stu-id="02b02-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="02b02-110">**Требуется ли подключать службу безопасности к каждому экстренному вызову в режиме конференц-связи?**</span><span class="sxs-lookup"><span data-stu-id="02b02-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="02b02-p103">Если это поддерживается поставщиком услуг экстренных служб, вы можете настроить политику расположения, чтобы включить в каждый экстренный вызов номер обратного вызова. Этот номер используется поставщиком, чтобы подключить службу безопасности вашей организации к экстренному вызову в режиме конференции. В политике расположения эту конференцию можно настроить как одностороннюю (только прослушивание) или двухстороннюю (двунаправленная связь).</span><span class="sxs-lookup"><span data-stu-id="02b02-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="02b02-p104">При необходимости вы можете настроить для каждой политики расположения различных сотрудников экстренной службы. Это позволяет настроить ответный сигнал для разных областей компании или создать отличную процедуру обработки экстренных вызовов, поступающих не извне, а изнутри сети. Можно использовать группы распределения для указания сотрудников, которых следует уведомлять о таких случаях.</span><span class="sxs-lookup"><span data-stu-id="02b02-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

