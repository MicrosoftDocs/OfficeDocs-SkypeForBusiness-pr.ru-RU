---
title: Включить службу безопасности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Планирование того, как включить службу безопасности организации в развертывание E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813409"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="6f804-103">Включить службу безопасности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f804-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="6f804-104">Планирование того, как включить службу безопасности организации в развертывание E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="6f804-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6f804-p101">Вашей компании может потребоваться, чтобы в обработке экстренного звонка принимала участие служба безопасности. Чтобы облегчить принятие решения о способе интеграции службы безопасности с развертыванием E9-1-1, вам следует ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="6f804-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="6f804-107">**Вы хотите оповещать службу безопасности об экстренном звонке?**</span><span class="sxs-lookup"><span data-stu-id="6f804-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="6f804-108">Вы можете настроить политику расположения таким образом, чтобы Skype для бизнеса Server отправляет оповещения системы обмена мгновенными сообщениями SIP-адресам Skype для бизнеса одного или более сотрудников службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="6f804-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="6f804-109">Эти предупреждения содержат имя, номер и расположение сотрудника, выполняющего экстренный звонок, и упрощают своевременное реагирование службы безопасности на экстренную ситуацию.</span><span class="sxs-lookup"><span data-stu-id="6f804-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="6f804-110">**Вы хотите подключать службу безопасности в каждому экстренному звонку в режиме конференции?**</span><span class="sxs-lookup"><span data-stu-id="6f804-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="6f804-p103">Если это поддерживается поставщиком услуг экстренных служб, вы можете настроить политику определения местоположения, чтобы включить в каждый экстренный звонок номер обратного вызова. Этот номер используется поставщиком, чтобы подключить службу безопасности вашей организации к экстренному вызову в режиме конференции. В политике определения местоположения эту конференцию можно настроить как одностороннюю (только прослушивание) или двухстороннюю (двунаправленная связь).</span><span class="sxs-lookup"><span data-stu-id="6f804-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6f804-p104">При необходимости вы можете настроить различных сотрудников экстренной службы для каждой политики определения местоположения. Это позволяет настроить ответ для разных областей вашей компании или создать отличную процедуру обработки экстренных звонков, поступающих не извне, изнутри сети. Можно использовать группы распределения для указания сотрудников, которых следует уведомлять.</span><span class="sxs-lookup"><span data-stu-id="6f804-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

