---
title: Включение службы безопасности в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Планирование способов включить службу безопасности вашей организации в развертывании E9-1-1, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: adaa1096651c5e3f86d15af1b2409a8de03e6c9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a><span data-ttu-id="b983b-103">Включение службы безопасности в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b983b-103">Include the security desk in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b983b-104">Планирование способов включить службу безопасности вашей организации в развертывании E9-1-1, в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b983b-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b983b-p101">Вашей компании может потребоваться, чтобы в обработке экстренного вызова принимала участие служба безопасности. Чтобы помочь принять решения о способе интеграции службы безопасности с развертыванием E9-1-1, следует ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="b983b-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="b983b-107">**Требуется ли оповещать службу безопасности об экстренном вызове?**</span><span class="sxs-lookup"><span data-stu-id="b983b-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="b983b-108">Можно настроить политику расположения, чтобы Скайп для Business Server отправляет мгновенного обмена сообщениями (IM) оповещения Скайп для бизнеса SIP-адреса из одного или нескольких сотрудников службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b983b-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="b983b-109">Эти предупреждения содержат имя, номер и место нахождения сотрудника, выполняющего экстренный вызов, и упрощают своевременное реагирование службы безопасности на экстренную ситуацию.</span><span class="sxs-lookup"><span data-stu-id="b983b-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="b983b-110">**Требуется ли подключать службу безопасности к каждому экстренному вызову в режиме конференц-связи?**</span><span class="sxs-lookup"><span data-stu-id="b983b-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="b983b-p103">Если это поддерживается поставщиком услуг экстренных служб, вы можете настроить политику расположения, чтобы включить в каждый экстренный вызов номер обратного вызова. Этот номер используется поставщиком, чтобы подключить службу безопасности вашей организации к экстренному вызову в режиме конференции. В политике расположения эту конференцию можно настроить как одностороннюю (только прослушивание) или двухстороннюю (двунаправленная связь).</span><span class="sxs-lookup"><span data-stu-id="b983b-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b983b-p104">При необходимости вы можете настроить для каждой политики расположения различных сотрудников экстренной службы. Это позволяет настроить ответный сигнал для разных областей компании или создать отличную процедуру обработки экстренных вызовов, поступающих не извне, а изнутри сети. Можно использовать группы распределения для указания сотрудников, которых следует уведомлять о таких случаях.</span><span class="sxs-lookup"><span data-stu-id="b983b-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

